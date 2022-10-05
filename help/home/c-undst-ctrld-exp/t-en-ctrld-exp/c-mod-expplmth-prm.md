---
description: Bearbeiten des ExpPartialMatch-Parameters (optional)
title: Bearbeiten des ExpPartialMatch-Parameters (optional)
uuid: 15ed33cc-5ec8-45b2-a4eb-d1941962ca9d
exl-id: 8ad45368-85a4-4865-b66b-52c29c28799c
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '82'
ht-degree: 18%

---

# Bearbeiten des ExpPartialMatch-Parameters (optional){#modifying-the-exppartialmatch-parameter-optional}

{{eol}}

Wenn Sie Ihre gesteuerten Experimente aktivieren möchten, um Ihre gesamte Website oder ein ganzes Unterverzeichnis Ihrer Website an einen anderen Speicherort zu verweisen, können Sie den Parameter ExpPartialMatch im [!DNL txlogd.conf] -Datei auf &quot;on&quot;gesetzt. Der Standardwert ist &quot;off&quot;.

Im Folgenden finden Sie ein Beispiel für den Parameter ExpPartialMatch :

[!DNL ExpPartialMatch off]

Seien Sie vorsichtig, wenn Sie diesen Parameter auf &quot;ein&quot;setzen, da dies zu einer unbeabsichtigten Neukodifizierung Ihrer gesamten Website führen kann.
