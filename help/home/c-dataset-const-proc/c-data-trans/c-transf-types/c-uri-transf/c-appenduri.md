---
description: Die AppendURI-Transformation bietet eine Möglichkeit, Informationen zum Standardwert hinzuzufügen, der aus den Protokolleinträgen stammt, die zum Erstellen des Datensatzes verwendet werden.
title: AppendURI
uuid: 8334d4f9-2bf6-4bd0-af65-8f2b0959652d
exl-id: 0d5901c0-bd13-4499-8e26-44839aeb7413
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '557'
ht-degree: 1%

---

# AppendURI{#appenduri}

Die AppendURI-Transformation bietet eine Möglichkeit, Informationen zum Standardwert hinzuzufügen, der aus den Protokolleinträgen stammt, die zum Erstellen des Datensatzes verwendet werden.

Die Transformation platziert ein Name-Wert-Paar am Ende des internen Felds, das zum Erstellen der URI-Dimension verwendet wird. Das Namens-Wert-Paar wird mithilfe des Parameters Abfrage String Key als Name und Wert des angegebenen Eingabeparameters als Wert des Paars erstellt. Der Befehl [!DNL AppendURI] fügt geeignete hinzu? und &amp; Symbole, die erforderlich sind, um die Name-Wert-Paare vom [!DNL URI]-Stamm und von allen vorherigen [!DNL AppendURI]-Vorgängen zu trennen, die möglicherweise auf den URI angewendet wurden.

Die Transformation von [!DNL AppendURI] funktioniert nur, wenn sie in der Datei [!DNL Transformation.cfg] oder in einer Datei [!DNL Transformation Dataset Include] definiert ist.

| Parameter | Beschreibung | Standard |
|---|---|---|
| Name | Beschreibender Name der Transformation. Sie können hier einen beliebigen Namen eingeben. |  |
| Kommentare | Optional. Anmerkungen zur Transformation. |  |
| Bedingung | Die Bedingungen, unter denen diese Umwandlung angewendet wird. |  |
| Standard | Der Standardwert, der verwendet wird, wenn die Bedingung erfüllt ist und der Eingabewert nicht verfügbar ist. |  |
| Eingabe | Der Name des Felds, dessen Wert an den URI angehängt wird. |  |
| Abfrage-Zeichenfolgenschlüssel | Der Name, der bei der Erstellung des angehängten Name-Wert-Paars verwendet wird. |  |

Betrachten Sie eine Website, die mit einem herkömmlichen Modell-Ansicht-Controller-Ansatz erstellt wurde. In solchen Systemen ist es üblich, dass eine einzelne Webseite der Zugang zum System ist. Für eine solche Site wären Visualisierungen von Traffic-Mustern im System sehr uninteressant und würden keine Einblicke in die Nutzung der Besucher und den Traffic-Fluss bieten. Betrachten Sie zum Beispiel eine Website, auf der alle Webanforderungen über einen URI des folgenden Formulars gesendet werden:

* [!DNL http://www.examplesite.com/modelview.asp?id=login&name=bob]

Die ASP-Seite der Modellansicht empfängt den gesamten Traffic und bestimmt ihre Aktionen auf der Grundlage des Werts des ID-Felds in der Abfrage. Standardmäßig enthält die URI-Dimension einen einzelnen Eintrag:

* [!DNL modelview.asp]

Dies würde zu einer ziemlich uninteressanten Zuordnung des Traffics durch die Site führen, da der gesamte Traffic über einen einzelnen URI geleitet wird. Um dieses spezielle Szenario zu lösen und eine informativere Ansicht in die zugrunde liegende Architektur der Website bereitzustellen, können [!DNL AppendURI] verwendet werden, um einige der eindeutigen Name/Wert-Paare aus dem Feld cs-uri-Abfrage in die URI-Dimension zu verschieben, die für Visualisierungen verwendet wird. Die folgende Transformation enthält die Details einer solchen Transformation:

![](assets/cfg_TransformationType_AppendURI.png)

In diesem Beispiel gibt es zwei Seiten, die vom System zur Verarbeitung aller Anforderungen verwendet werden: [!DNL modelview.asp] und [!DNL xmlmodelview.asp]. Eine Seite wird für den Browser-Traffic verwendet, die andere für die System-zu-System-XML-Kommunikation. Der Anwendungsserverprozess verwendet den ID-Namen der cs-uri-Abfrage, um zu bestimmen, welche Aktion ausgeführt werden soll. Daher können Sie den Wert aus dem Feld &quot;id&quot;extrahieren und ihn an den URI anhängen. Das Ergebnis ist eine Sammlung von URIs mit einer Variationsbreite, die den Besucher-Traffic durch die Website widerspiegelt. Hier bestimmt eine [!DNL String Match]-Bedingung die Protokolleinträge, auf die die Transformation angewendet wird, indem das cs-uri-Stammfeld nach den beiden Webseiten durchsucht und alle anderen ignoriert wird. Die Eingabe (der Wert unseres Namens-Wert-Paars) ist das Ergebnis von cs-uri-Abfrage(id), die &quot;login&quot; heißt. Wie vom Parameter &quot;Abfrage-String-Schlüssel&quot;angegeben, lautet der angehängte Name &quot;id&quot;. Für den eingehenden cs-uri-Wert unseres Beispiels ist der resultierende URI, der von der Dimension [!DNL URI] verwendet wird, [!DNL /modelview.asp&id=login].
