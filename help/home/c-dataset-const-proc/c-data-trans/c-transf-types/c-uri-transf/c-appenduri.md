---
description: Die AppendURI-Transformation bietet eine Möglichkeit, Informationen zum Standardwert hinzuzufügen, der aus den Protokolleinträgen stammt, die zum Erstellen des Datensatzes verwendet werden.
title: AppendURI
uuid: 8334d4f9-2bf6-4bd0-af65-8f2b0959652d
exl-id: 0d5901c0-bd13-4499-8e26-44839aeb7413
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '557'
ht-degree: 1%

---

# AppendURI{#appenduri}

{{eol}}

Die AppendURI-Transformation bietet eine Möglichkeit, Informationen zum Standardwert hinzuzufügen, der aus den Protokolleinträgen stammt, die zum Erstellen des Datensatzes verwendet werden.

Die Umwandlung platziert ein Name-Wert-Paar am Ende des internen Felds, das zum Erstellen der URI-Dimension verwendet wird. Das Name-Wert-Paar wird mithilfe des Abfragezeichenfolgen-Schlüsselparameters als Name und Wert des identifizierten Eingabeparameters als Wert des Paars erstellt. Die [!DNL AppendURI] -Befehl fügt geeignete hinzu? und &amp; -Symbole, die erforderlich sind, um die Name-Wert-Paare von der [!DNL URI] von [!DNL AppendURI] Vorgänge, die möglicherweise auf den URI angewendet wurden.

Die [!DNL AppendURI] Die Umwandlung funktioniert nur, wenn sie in [!DNL Transformation.cfg] oder [!DNL Transformation Dataset Include] -Datei.

| Parameter | Beschreibung | Standard |
|---|---|---|
| Name | Deskriptiver Name der Transformation. Hier können Sie einen beliebigen Namen eingeben. |  |
| Kommentare | Optional. Anmerkungen zur Transformation. |  |
| Bedingung | Die Bedingungen, unter denen diese Umwandlung angewendet wird. |  |
| Standard | Der Standardwert, der verwendet wird, wenn die Bedingung erfüllt ist und der Eingabewert nicht verfügbar ist. |  |
| Eingabe | Der Name des Felds, dessen Wert an den URI angehängt wird. |  |
| Abfragezeichenfolgenschlüssel | Der Name, der bei der Erstellung des angehängten Name-Wert-Paares verwendet wird. |  |

Nehmen wir eine Website, die mit einem herkömmlichen Modell-View-Controller-Ansatz erstellt wurde. In solchen Systemen ist es üblich, dass eine einzelne Webseite als Zugriffspunkt für das System dient. Für eine solche Site wären Visualisierungen von Traffic-Mustern im System sehr uninteressant und würden keine Einblicke in die Besuchernutzung und den Traffic-Fluss liefern. Betrachten Sie beispielsweise eine Website, die alle Webanfragen über einen URI des folgenden Formulars durchführt:

* [!DNL https://www.examplesite.com/modelview.asp?id=login&name=bob]

Die ASP-Seite für die Modellansicht empfängt den gesamten Traffic und bestimmt ihre Aktionen basierend auf dem Wert des ID-Felds in der Abfrage. Standardmäßig enthält die URI-Dimension einen einzelnen Eintrag:

* [!DNL modelview.asp]

Dies würde zu einer ziemlich uninteressanten Zuordnung des Traffics durch die Site führen, da der gesamte Traffic über einen einzelnen URI geleitet wird. Um dieses spezielle Szenario anzugehen und einen informativeren Überblick über die zugrunde liegende Architektur der Website zu erhalten, [!DNL AppendURI] kann verwendet werden, um einige der eindeutigen Name-Wert-Paare aus dem cs-uri-Abfragefeld in die URI-Dimension zu verschieben, die für Visualisierungen verwendet wird. Die folgende Umwandlung liefert die Details einer solchen Umwandlung:

![](assets/cfg_TransformationType_AppendURI.png)

In diesem Beispiel gibt es zwei Seiten, die vom System zur Verarbeitung aller Anforderungen verwendet werden: [!DNL modelview.asp] und [!DNL xmlmodelview.asp]. Eine Seite wird für den Browser-Traffic verwendet, die andere für die System-zu-System-XML-Kommunikation. Der Anwendungsserverprozess verwendet den ID-Namen der cs-uri-Abfrage, um zu bestimmen, welche Aktion ausgeführt werden soll. Daher können Sie den Wert aus dem Feld ID extrahieren und an den URI anhängen. Das Ergebnis ist eine Sammlung von URIs mit einer Reihe von Varianten, die den Besucher-Traffic auf der Website widerspiegeln. Hier ein [!DNL String Match] -Bedingung bestimmt die Protokolleinträge, auf die die Transformation angewendet wird, indem das Feld cs-uri-stamm nach den beiden interessanten Webseiten durchsucht und alle anderen ignoriert wird. Die Eingabe (der Wert unseres Name-Wert-Paares) ist das Ergebnis von cs-uri-query(id), das &quot;login&quot;ist. Wie durch den Abfragezeichenfolgen-Schlüsselparameter angegeben, lautet der angehängte Name &quot;id&quot;. Daher wird für den eingehenden cs-uri -Wert unseres Beispiels der resultierende URI verwendet, der von der [!DNL URI] Dimension ist [!DNL /modelview.asp&id=login].
