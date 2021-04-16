---
description: Bearbeiten des ExpPartialMatch-Parameters (optional)
title: Bearbeiten des ExpPartialMatch-Parameters (optional)
uuid: 15ed33cc-5ec8-45b2-a4eb-d1941962ca9d
exl-id: 8ad45368-85a4-4865-b66b-52c29c28799c
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '82'
ht-degree: 18%

---

# Bearbeiten des ExpPartialMatch-Parameters (optional){#modifying-the-exppartialmatch-parameter-optional}

Wenn Sie Ihre kontrollierten Experimente aktivieren möchten, um Ihre gesamte Website oder ein ganzes Unterverzeichnis Ihrer Website an einen anderen Speicherort zu verschieben, können Sie den Parameter ExpPartialMatch in der Datei [!DNL txlogd.conf] auf &quot;on&quot;setzen. Der Standardwert ist &quot;off&quot;.

Im Folgenden finden Sie ein Beispiel für den Parameter ExpPartialMatch:

[!DNL ExpPartialMatch off]

Seien Sie vorsichtig, wenn Sie diesen Parameter auf &quot;on&quot;setzen, da dies zu einer unbeabsichtigten Neuzuordnung Ihrer gesamten Website führen kann.
