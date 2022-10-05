---
description: Das Attributionsprofil ist ein geerbtes, einsatzbereites Profil. In Kombination mit dem Adobe SC-Profil und dem Analytics (SC/Insight)-Daten-Feed kann das Profil bereitgestellt werden, um schnell neue Attributionsmodelle über digitale Kanäle hinweg verfügbar zu machen.
title: Implementieren des Attributionsprofils
uuid: acc4e92a-2af1-4993-bae7-015ece3da26c
exl-id: 287e1710-7e74-4904-b258-7b811ad484b7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '437'
ht-degree: 3%

---

# Implementieren des Attributionsprofils{#deploying-the-attribution-profile}

{{eol}}

Das Attributionsprofil ist ein geerbtes, einsatzbereites Profil. In Kombination mit dem Adobe SC-Profil und dem Analytics (SC/Insight)-Daten-Feed kann das Profil bereitgestellt werden, um schnell neue Attributionsmodelle über digitale Kanäle hinweg verfügbar zu machen.

Nach dem Speichern des Attributionsprofils auf dem primären Server sind zwei weitere Schritte erforderlich, um es in das aktuelle Profil im [!DNL Profile] directory: (1) Richten Sie die Datei Profil.cfg ein und (2) deklarieren Sie die erforderlichen Felder.

## Datei &quot;profile.cfg&quot;einrichten {#section-7531cb865d994207baba692a6fc842d7}

Wie alle Profile muss das Attributionsprofil dem [!DNL profile.cfg] -Datei. Da das Attributionsprofil vom Adobe SC-Profil abhängt, muss das Adobe SC-Profil zuerst in der Konfigurationsdatei vor dem Attributionsprofil aufgelistet werden.

>[!NOTE]
>
>Diese Schritte erfordern eine Neuumwandlung des Datensatzes.

1. Öffnen Sie die [!DNL profile.cfg] in Ihrem benutzerdefinierten Profilordner. (Öffnen in [!DNL server\Profiles\(custom profile name)\profile.cfg].

1. Wenn das Attributionsprofil nicht in der Konfigurationsdatei aufgeführt ist, fügen Sie es der Liste hinzu. ![](assets/new_profile_cfg.png)

1. Stellen Sie sicher, dass **[!UICONTROL Attribution]** -Zeichenfolge wird unter der **[!UICONTROL Adobe SC]** Profil-Zeichenfolge.

1. Speichern Sie die Aktualisierung [!DNL profile.cfg] und speichern Sie sie dann im Profil-Manager auf dem Server.

## Erforderliche Felder deklarieren {#section-23d4273af0c34b7a85ae3430e2c9350e}

Das Attributionsprofil verwendet vordefinierte Felder und zeigt diese Felder mit einer Reihe von Umwandlungen auf neue und nützliche Weise durch erweiterte Dimensionen an. Um den schnellsten Wert bereitzustellen, hängt das Attributionsprofil von den Feldern ab, die im Adobe SC-Profil verfügbar sind.

<table id="table_97751B73CCAA4B96BB162641A178A68A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Standardvariablen </th> 
   <th colname="col2" class="entry"> Feldname und Decoder-Position (Adobe SC) </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Kampagne </td> 
   <td colname="col2"> <p>x-campaign, #199 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Marketing-Kanäle </td> 
   <td colname="col2"> <p>x-va_closer_detail, #162 </p> <p>x-va_instance_event, #163 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Bestellereignis </td> 
   <td colname="col2"> <p>x-order, #206 </p> <p>x-purchaseid, #200 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Umsatz </td> 
   <td colname="col2"> x-revenue, #205 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Einheiten </td> 
   <td colname="col2"> <p>x-unit, #204 </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Stellen Sie sicher, dass diese Felder in der Decoder-Gruppe deklariert sind, die zum Definieren der Adobe Analytics-Datenquelle verwendet wird. Die standardmäßige Decoder-Gruppe wird unter [!DNL Dataset\Log Procesing\Decoding Instructions.cfg].
1. Stellen Sie sicher, dass diese Felder im **[!UICONTROL Fields]** Abschnitt [!DNL SC Fields.cfg] -Datei. Diese Datei befindet sich unter [!DNL Dataset\Log Processing\SC Fields.cfg].

## Attribution - Ergänzungen und Fehlerbehebung {#section-168133a8a1a54e1281e532033878d246}

Das Attributionsprofil hat eine Konfigurationsdatei hinzugefügt, [!DNL 0a_Marketing Channels.cfg], der den Wert der [!DNL x-va_closer_detail] in ein neues Feld namens [!DNL x-marketing-channel], wenn die [!DNL x-va_instance_event] -Feld entspricht &quot;1&quot;. Beide [!DNL x-va_closer_detail] und [!DNL x-va_instant_event] werden standardmäßig dekodiert und aus der Dekodierung in den installierten Packages übergeben, die beim Aktualisieren auf Version 6.2 verfügbar sind.

Die [!DNL x-marketing-channel] wird dann in der einfachen Dimension Marketing-Kanal verwendet.

>[!IMPORTANT]
>
>Wenn Sie Ihre Profile durch Entfernen zuvor nicht verwendeter Felder verändert haben, die jetzt verwendet werden, sollten Sie sicherstellen, dass die Variable [!DNL x-va_closer_detail] und [!DNL x-va_instance_event] -Felder werden dekodiert und zur Verwendung weitergegeben.

Wenn Felder fehlen, erhalten Sie eine Nachricht in Ihrem detaillierten Status:

```
<b>x-va_closer_detail</b> is not available
```

oder

```
<b>x-va_instance_event</b> is not available
```
