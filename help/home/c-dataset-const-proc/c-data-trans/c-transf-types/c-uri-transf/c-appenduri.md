---
description: Die AppendURI-Transformation bietet eine Möglichkeit, Informationen zum Standardwert hinzuzufügen, der aus den Protokolleinträgen stammt, die zum Erstellen des Datensatzes verwendet werden.
solution: Analytics
title: AppendURI
topic: Data workbench
uuid: 8334d4f9-2bf6-4bd0-af65-8f2b0959652d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# AppendURI{#appenduri}

Die AppendURI-Transformation bietet eine Möglichkeit, Informationen zum Standardwert hinzuzufügen, der aus den Protokolleinträgen stammt, die zum Erstellen des Datensatzes verwendet werden.

Die Transformation platziert ein Name-Wert-Paar am Ende des internen Felds, das zum Erstellen der URI-Dimension verwendet wird. Das Namens-Wert-Paar wird mithilfe des Abfragezeichenfolgen-Schlüsselparameters als Name und Wert des angegebenen Eingabeparameters als Wert des Paars erstellt. Der [!DNL AppendURI] Befehl fügt entsprechende hinzu? und &amp; Symbole, die erforderlich sind, um die Name-Wert-Paare vom [!DNL URI] Stamm und von allen vorherigen [!DNL AppendURI] Vorgängen zu trennen, die möglicherweise auf den URI angewendet wurden.

Die [!DNL AppendURI] Transformation funktioniert nur, wenn sie in der [!DNL Transformation.cfg] Datei oder in einer [!DNL Transformation Dataset Include] Datei definiert ist.

| Parameter | Beschreibung | Standardeinstellung |
|---|---|---|
| Name | Beschreibender Name der Transformation. Sie können hier einen beliebigen Namen eingeben. |  |
| Kommentare | Optional. Anmerkungen zur Transformation. |  |
| Bedingung | Die Bedingungen, unter denen diese Umwandlung angewendet wird. |  |
| Standardeinstellung | Der Standardwert, der verwendet wird, wenn die Bedingung erfüllt ist und der Eingabewert nicht verfügbar ist. |  |
| Eingabe | Der Name des Felds, dessen Wert an den URI angehängt wird. |  |
| Abfragezeichenfolgenschlüssel | Der Name, der bei der Erstellung des angehängten Name-Wert-Paars verwendet wird. |  |

Betrachten Sie eine Website, die mit einem traditionellen Modell-View-Controller-Ansatz erstellt wurde. In solchen Systemen ist es üblich, dass eine einzelne Webseite der Zugang zum System ist. Für eine solche Site wären Visualisierungen von Traffic-Mustern im System sehr uninteressant und würden keine Einblicke in die Besuchernutzung und den Traffic-Fluss bieten. Betrachten Sie zum Beispiel eine Website, auf der alle Webanforderungen über einen URI des folgenden Formulars gesendet werden:

* [!DNL http://www.examplesite.com/modelview.asp?id=login&name=bob]

Die ASP-Seite der Modellansicht empfängt den gesamten Traffic und bestimmt ihre Aktionen auf Grundlage des Werts des Felds &quot;id&quot;in der Abfrage. Standardmäßig enthält die URI-Dimension einen einzelnen Eintrag:

* [!DNL modelview.asp]

Dies würde zu einer ziemlich uninteressanten Zuordnung des Traffics durch die Site führen, da der gesamte Traffic über einen einzelnen URI geleitet wird. Um dieses spezielle Szenario zu lösen und einen informativeren Einblick in die zugrunde liegende Architektur der Website zu erhalten, können Sie einige der eindeutigen Name-Wert-Paare aus dem cs-uri-Abfragefeld in die URI-Dimension verschieben, die für Visualisierungen verwendet wird. [!DNL AppendURI] Die folgende Transformation enthält die Details einer solchen Transformation:

![](assets/cfg_TransformationType_AppendURI.png)

In diesem Beispiel gibt es zwei Seiten, die vom System zur Verarbeitung aller Anforderungen verwendet werden: [!DNL modelview.asp] und [!DNL xmlmodelview.asp]. Eine Seite wird für den Browser-Traffic verwendet, die andere für die System-zu-System-XML-Kommunikation. Der Anwendungsserverprozess verwendet den ID-Namen der cs-uri-Abfrage, um zu bestimmen, welche Aktion ausgeführt werden soll. Daher können Sie den Wert aus dem Feld &quot;id&quot;extrahieren und ihn an den URI anhängen. Das Ergebnis ist eine Sammlung von URIs mit verschiedenen Varianten, die den Besucher-Traffic durch die Website widerspiegeln. Hier bestimmt eine [!DNL String Match] Bedingung die Protokolleinträge, auf die die Transformation angewendet wird, indem sie das cs-uri-Stammfeld nach den beiden Webseiten durchsucht und alle anderen ignoriert. Die Eingabe (der Wert unseres Namens-Wert-Paars) ist das Ergebnis von cs-uri-query(id), was &quot;login&quot; ist. Wie vom Abfragezeichenfolgen-Schlüsselparameter angegeben, lautet der angehängte Name &quot;id&quot;. Daher wird für den eingehenden cs-uri-Wert unseres Beispiels der resultierende URI, der von der [!DNL URI] Dimension verwendet wird, [!DNL /modelview.asp&id=login]verwendet.
