---
description: Das Zuordnungsprofil ist ein geerbtes, sofort einsetzbares Profil. In Kombination mit dem Adobe SC-Profil- und Analytics (SC/Insight)-Datenfeed kann das Profil bereitgestellt werden, um neue Zuordnungsmodelle schnell über digitale Kanäle verfügbar zu machen.
title: Bereitstellen des Zuordnungsprofils
uuid: acc4e92a-2af1-4993-bae7-015ece3da26c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Bereitstellen des Zuordnungsprofils{#deploying-the-attribution-profile}

Das Zuordnungsprofil ist ein geerbtes, sofort einsetzbares Profil. In Kombination mit dem Adobe SC-Profil- und Analytics (SC/Insight)-Datenfeed kann das Profil bereitgestellt werden, um neue Zuordnungsmodelle schnell über digitale Kanäle verfügbar zu machen.

Nach dem Speichern des Zuordnungsprofils auf dem primären Server sind zwei weitere Schritte erforderlich, um es in das aktuelle Profil im [!DNL Profile] Ordner zu integrieren: (1) Richten Sie die Datei &quot;profile.cfg&quot;ein und (2) Deklarieren Sie die erforderlichen Felder.

## Profil.cfg-Datei einrichten {#section-7531cb865d994207baba692a6fc842d7}

Wie alle Profile muss auch das Namenszuordnungsprofil der [!DNL profile.cfg] Datei hinzugefügt werden. Da das Zuordnungsprofil vom Adobe SC-Profil abhängt, muss das Adobe SC-Profil zuerst in der Konfigurationsdatei vor dem Zuordnungsprofil aufgeführt werden.

>[!NOTE]
>
>Diese Schritte erfordern eine Umgestaltung des Datensatzes.

1. Öffnen Sie die [!DNL profile.cfg] Datei im benutzerdefinierten Profilordner. (Öffnen in [!DNL server\Profiles\(custom profile name)\profile.cfg].

1. Wenn das Zuordnungsprofil nicht in der Konfigurationsdatei aufgeführt ist, fügen Sie es der Liste hinzu. ![](assets/new_profile_cfg.png)

1. Vergewissern Sie sich, dass die **[!UICONTROL Attribution]** Zeichenfolge unter der **[!UICONTROL Adobe SC]** Profilzeichenfolge aufgeführt ist.

1. Speichern Sie die aktualisierte [!DNL profile.cfg] Datei und speichern Sie sie dann im Profil-Manager auf dem Server.

## Erforderliche Felder deklarieren {#section-23d4273af0c34b7a85ae3430e2c9350e}

Das Zuordnungsprofil nimmt vordefinierte Felder und mit einer Reihe von Transformationen macht diese Felder auf neue und nützliche Weise durch erweiterte Dimensionen verfügbar. Um den schnellsten Wert bereitzustellen, hängt das Zuordnungsprofil von den Feldern ab, die im Adobe SC-Profil verfügbar sind.

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
   <td colname="col2"> x-Umsatz, #205 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Einheiten </td> 
   <td colname="col2"> <p>x-unit, #204 </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Vergewissern Sie sich, dass diese Felder in der Decoder-Gruppe deklariert sind, die zum Definieren der Adobe Analytics-Datenquelle verwendet wird. Die standardmäßige Decoder-Gruppe wird unter [!DNL Dataset\Log Procesing\Decoding Instructions.cfg].
1. Vergewissern Sie sich, dass diese Felder im **[!UICONTROL Fields]** Abschnitt der [!DNL SC Fields.cfg] Datei deklariert sind. Diese Datei befindet sich unter [!DNL Dataset\Log Processing\SC Fields.cfg].

## Zuordnungen und Fehlerbehebung {#section-168133a8a1a54e1281e532033878d246}

Das Zuordnungsprofil hat eine Konfigurationsdatei hinzugefügt, [!DNL 0a_Marketing Channels.cfg]die den Wert des Feldes in ein neues Feld namens [!DNL x-va_closer_detail] kopiert, wenn das [!DNL x-marketing-channel][!DNL x-va_instance_event] Feld mit &quot;1&quot;übereinstimmt. Sowohl [!DNL x-va_closer_detail] als auch [!DNL x-va_instant_event] werden standardmäßig dekodiert und aus der Dekodierung in den installierten Paketen übergeben, die beim Aktualisieren auf Version 6.2 verfügbar sind.

Das [!DNL x-marketing-channel] Feld wird dann in der einfachen Dimension &quot;Marketingkanal&quot;verwendet.

>[!IMPORTANT]
>
>Wenn Sie Ihre Profile geändert haben, indem Sie zuvor nicht verwendete Felder, die jetzt verwendet werden, entfernen, möchten Sie überprüfen, ob die Felder [!DNL x-va_closer_detail] und [!DNL x-va_instance_event] Felder dekodiert und zur Verwendung weitergeleitet werden.

Wenn Felder fehlen, erhalten Sie eine Meldung in Ihrem detaillierten Status:

```
<b>x-va_closer_detail</b> is not available
```

oder

```
<b>x-va_instance_event</b> is not available
```

