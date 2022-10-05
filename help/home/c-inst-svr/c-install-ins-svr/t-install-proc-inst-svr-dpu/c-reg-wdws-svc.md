---
description: Verfahren zum Starten von Insight Server und zur gleichzeitigen Registrierung als Microsoft Windows Service.
title: Registrieren von Insight Server als Windows-Service
uuid: 1b3d53ca-d50f-4520-abf5-6d5c40493b88
exl-id: ba74d4c0-5d99-47a4-8b92-c65d0ec514e2
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '581'
ht-degree: 3%

---

# Registrieren von Insight Server als Windows-Service{#registering-insight-server-as-a-windows-service}

{{eol}}

Verfahren zum Starten von Insight Server und zur gleichzeitigen Registrierung als Microsoft Windows Service.

>[!NOTE]
>
>Wenn Sie beginnen [!DNL Insight Server] Zum ersten Mal stellt es automatisch eine Verbindung zum Adobe License Server her, um Ihr digitales Zertifikat zu registrieren. Um den Registrierungsprozess erfolgreich abzuschließen, muss Ihr Computer mit dem Internet verbunden sein, wenn Sie die folgenden Schritte ausführen.

**Zu Beginn [!DNL Insight Server] und registrieren Sie es als Windows-Dienst**

1. Öffnen Sie eine Eingabeaufforderung und navigieren Sie zum Unterordner &quot;bin&quot;im Ordner, in dem Sie installiert haben [!DNL Insight Server].

   Beispiel: [!DNL C:\Adobe\Server\bin]

1. Führen Sie an der Eingabeaufforderung den folgenden Befehl aus, um zu starten [!DNL Insight Server] und registrieren Sie sie gleichzeitig für die Ausführung als Dienst unter Microsoft Windows:

   ```
   <filepath>
   InsightServer64.exe /regserver 
   </filepath>
   ```

1. So bestätigen Sie Folgendes: [!DNL Insight Server] korrekt ausgeführt wird, klicken Sie auf **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Services]**. Diese Befehlssequenz kann je nach verwendeter Windows-Version variieren.

   1. Suchen Sie in der Dienstliste den Eintrag für **[!DNL Adobe Insight Server]** und bestätigen Sie, dass der Status Started und der Starttyp Automatisch lautet.
   1. Schließen Sie die Systemsteuerung &quot;Dienste&quot;.

1. Überprüfen, ob [!DNL Insight Server] während des Starts Fehler aufgetreten sind, klicken Sie auf **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**. Diese Befehlssequenz kann je nach verwendeter Windows-Version variieren.

   1. Im linken Bereich des [!DNL Event Viewer] auswählen, wählen Sie die **[!UICONTROL Application]** log.
   1. Suchen Sie im rechten Bereich nach Ereignissen mit &quot;Adobe&quot;im [!DNL Source] Spalte.
   1. Wenn Sie einen Fehler aus &quot;Adobe&quot;finden, doppelklicken Sie auf den Fehler, um die [!DNL Event Properties] Fenster. In diesem Fenster erhalten Sie detaillierte Informationen zum Fehler.

1. Wenn Sie mit der Untersuchung des [!DNL Applications] Protokoll erstellen, schließen Sie die Ereignis-Anzeige.

Sie haben die Installation der [!DNL Insight Server]. [!DNL Insight Server] ist so ausgelegt, dass sie kontinuierlich läuft. Wenn Sie den Computer neu starten, [!DNL Insight Server] wird automatisch neu gestartet. Wenn Sie beginnen und anhalten müssen [!DNL Insight Server] manuell verwenden, können Sie dies über die Systemsteuerung &quot;Dienste&quot;in Windows tun. Wie im folgenden Abschnitt beschrieben, können Sie optional [!DNL Insight Server] -Dienst automatisch regelmäßig neu gestartet werden.

## Automatische Neustartkonfiguration des Dienstes {#section-f9bb91614513435f84ee55c0ec8edb13}

[!DNL Insight Server] ist so konzipiert, dass es weiterhin unterbrechungsfrei läuft. Sie wird normalerweise nur bei seltenen Aufgaben wie Software-Upgrades oder Zertifikatänderungen oder bei bestimmten Systemfehlern angehalten oder gestartet. Es ist nicht erforderlich, die [!DNL Insight Server] Betrieb während des normalen Systembetriebs; Sie können den Dienst jedoch so konfigurieren, dass er regelmäßig neu gestartet wird (täglich, wöchentlich oder monatlich), um beispielsweise die Ereignismeldungen zu löschen.

**So konfigurieren Sie die [!DNL Insight Server] Dienst zum automatischen Neustart**

1. Navigieren Sie zum [!DNL Components] Ordner im Verzeichnis, in dem Sie installiert haben [!DNL Insight Server].

   Beispiel: [!DNL C:\Adobe\Server\Components]

1. Verwenden Sie einen Texteditor wie Notepad, um eine neue Datei mit dem Namen [!DNL ScheduledRestart.cfg].
1. Geben Sie den folgenden Text in die [!DNL ScheduledRestart.cfg] Datei:

   ```
   component = ScheduledRestart:  
     Start Time = string: Month DD, YYYY HH:MM:SS TZone 
     Restart Every = string: frequency
   ```

   <table id="table_AC05861E141E4928BE844C8611DEC43D"> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> Für diesen Wert... </th> 
      <th colname="col2" class="entry"> Legen Sie  </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <i>Monat DD, JJJJ HH:MM:SS TZone</i> </td> 
      <td colname="col2"> <p>Der Zeitpunkt, zu dem Sie möchten <span class="keyword"> Insight Server </span> zum ersten Mal neu gestartet werden. </p> <p>Beispiel: 13. August 2013 22:30:00 EST </p> <p> <p>Hinweis: Sie müssen eine Zeitzone angeben. Wenn nicht angegeben, wird in der Zeitzone nicht standardmäßig Systemzeit verwendet. Wenn Sie die Sommerzeit oder eine ähnliche Uhrzeitverschiebungspolitik implementieren möchten, müssen Sie die <span class="filepath"> .dst </span> -Datei mit den entsprechenden Regeln im Ordner "Base\Dataset\Timezone"auf der <span class="keyword"> Insight Server </span> Maschine. Eine Liste der unterstützten Zeitzonen-Abkürzungen und Informationen zur Implementierung der Sommerzeit finden Sie unter <a href="../../../../home/c-inst-svr/c-time-zn-cds.md#concept-eed5ba32d5d347cf94b76db83b29f211"> Zeitzonencodes </a>. </p> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <i>Häufigkeit</i> </td> 
      <td colname="col2"> <p>Einer der folgenden Werte: 
       <ul id="ul_C29A40CD8FBB4333B5FA1D9E7DAD35EC"> 
       <li id="li_9FE07DD30C524CBB81C8F7968E7C733E">month </li> 
       <li id="li_E5E1B97ED8FB43C0BDA496C620D24A4C">Woche </li> 
       <li id="li_E6043B382FAE4B5D85CAADDFA60E4902">day </li> 
       </ul> </p> <p>So geben Sie die Häufigkeit an, mit der Sie <span class="keyword"> Insight Server </span> nach der in Startzeit angegebenen Anfangszeit neu gestartet werden. </p> <p>Wenn Sie beispielsweise <span class="keyword"> Insight Server </span> um einen Neustart einmal pro Woche durchzuführen, würden Sie diesen Wert auf "Woche"setzen. </p> </td> 
      </tr> 
    </tbody> 
   </table>

1. Speichern Sie die [!DNL ScheduledRestart.cfg] -Datei.

   Stellen Sie sicher, dass [!DNL ScheduledRestart.cfg] -Datei im [!DNL Components] Ordner im Verzeichnis, in dem Sie installiert haben [!DNL Insight Server].
