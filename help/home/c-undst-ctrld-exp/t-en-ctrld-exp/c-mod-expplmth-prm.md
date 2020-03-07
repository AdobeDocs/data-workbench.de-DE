---
description: 'null'
solution: Insight,Analytics
title: Ändern des ExpPartialMatch-Parameters (Optional)
topic: Data workbench
uuid: 15ed33cc-5ec8-45b2-a4eb-d1941962ca9d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Ändern des ExpPartialMatch-Parameters (Optional){#modifying-the-exppartialmatch-parameter-optional}

Wenn Sie Ihre kontrollierten Experimente aktivieren möchten, um Ihre gesamte Website oder ein ganzes Unterverzeichnis Ihrer Website an einen anderen Speicherort zu verschieben, können Sie den Parameter ExpPartialMatch in der [!DNL txlogd.conf] Datei auf &quot;on&quot;setzen. Der Standardwert ist &quot;off&quot;.

Im Folgenden finden Sie ein Beispiel für den Parameter ExpPartialMatch:

[!DNL ExpPartialMatch off]

Seien Sie vorsichtig, wenn Sie diesen Parameter auf &quot;on&quot;setzen, da dies zu einer unbeabsichtigten Neuzuordnung Ihrer gesamten Website führen kann.
