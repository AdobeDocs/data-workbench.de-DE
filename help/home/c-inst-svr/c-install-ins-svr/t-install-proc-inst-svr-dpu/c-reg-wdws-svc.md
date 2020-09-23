---
description: Verfahren zum Beginn Insight Server und zur gleichzeitigen Registrierung als Microsoft Windows Service.
solution: Analytics
title: Registrieren von Insight Server als Windows-Service
uuid: 1b3d53ca-d50f-4520-abf5-6d5c40493b88
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '582'
ht-degree: 3%

---


# Registrieren von Insight Server als Windows-Service{#registering-insight-server-as-a-windows-service}

Verfahren zum Beginn Insight Server und zur gleichzeitigen Registrierung als Microsoft Windows Service.

>[!NOTE]
>
>Wenn Sie [!DNL Insight Server] zum ersten Mal einen Beginn erstellen, wird automatisch eine Verbindung mit der Adobe License Server hergestellt, um das digitale Zertifikat zu registrieren. Um den Registrierungsprozess erfolgreich abzuschließen, muss Ihr Computer mit dem Internet verbunden sein, wenn Sie die folgenden Schritte ausführen.

**Beginn[!DNL Insight Server]und Registrierung als Windows-Dienst**

1. Öffnen Sie eine Eingabeaufforderung und navigieren Sie zum Unterverzeichnis &quot;bin&quot;in dem Ordner, in dem Sie installiert haben [!DNL Insight Server].

   Beispiel: [!DNL C:\Adobe\Server\bin]

1. Führen Sie an der Eingabeaufforderung den folgenden Befehl zum Beginn aus [!DNL Insight Server] und registrieren Sie ihn gleichzeitig für die Ausführung als Dienst unter Microsoft Windows:

   ```
   <filepath>
   InsightServer64.exe /regserver 
   </filepath>
   ```

1. Um zu bestätigen, dass [!DNL Insight Server] die Funktion korrekt ausgeführt wird, klicken Sie auf **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Services]**. Diese Befehlssequenz kann je nach verwendeter Windows-Version variieren.

   1. Suchen Sie in der Dienst-Liste den Eintrag für **[!DNL Adobe Insight Server]** und bestätigen Sie, dass dessen Status &quot;Started&quot;und der Starttyp &quot;Automatic&quot;lautet.
   1. Schließen Sie das Bedienfeld &quot;Dienste&quot;.

1. Um zu überprüfen, ob während des Beginns Fehler [!DNL Insight Server] aufgetreten sind, klicken Sie auf **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**. Diese Befehlssequenz kann je nach verwendeter Windows-Version variieren.

   1. Wählen Sie im linken Bereich des [!DNL Event Viewer] Fensters das **[!UICONTROL Application]** Protokoll aus.
   1. Suchen Sie im rechten Bereich nach Ereignissen mit &quot;Adobe&quot;in der [!DNL Source] Spalte.
   1. Wenn die Fehlermeldung &quot;Adobe&quot;angezeigt wird, klicken Sie bei gedrückter Dublette auf die Fehlermeldung, um das [!DNL Event Properties] Fenster anzuzeigen. Dieses Fenster enthält detaillierte Informationen zum Fehler.

1. Wenn Sie die Überprüfung des [!DNL Applications] Protokolls abgeschlossen haben, schließen Sie den Ereignis-Viewer.

Sie haben die Installation von abgeschlossen [!DNL Insight Server]. [!DNL Insight Server] ist so ausgelegt, dass sie kontinuierlich läuft. Wenn Sie den Computer neu starten, [!DNL Insight Server] wird er automatisch neu gestartet. Wenn Sie den Beginn [!DNL Insight Server] manuell beenden müssen, können Sie dies über das Bedienfeld &quot;Dienste&quot;in Windows tun. Wie im folgenden Abschnitt beschrieben, können Sie optional den [!DNL Insight Server] Dienst so konfigurieren, dass er regelmäßig automatisch neu gestartet wird.

## Konfigurieren des Dienstes zum automatischen Neustart {#section-f9bb91614513435f84ee55c0ec8edb13}

[!DNL Insight Server] ist so ausgelegt, dass sie ununterbrochen ausgeführt wird. Es wird normalerweise nur angehalten oder gestartet, wenn seltene Aufgaben wie Software-Upgrades oder Zertifikatänderungen oder im Ereignis bestimmter Systemfehler ausgeführt werden. Es ist nicht erforderlich, den [!DNL Insight Server] Dienst während des normalen Systembetriebs zu beenden oder neu zu starten. Sie können jedoch konfigurieren, dass der Dienst regelmäßig neu gestartet wird (täglich, wöchentlich oder monatlich), um beispielsweise die Ereignis-Meldungen zu löschen.

**So konfigurieren Sie den[!DNL Insight Server]Dienst für einen automatischen Neustart**

1. Navigieren Sie zu dem [!DNL Components] Ordner, in dem Sie installiert haben [!DNL Insight Server].

   Beispiel: [!DNL C:\Adobe\Server\Components]

1. Verwenden Sie einen Texteditor wie Notepad, um eine neue Datei namens [!DNL ScheduledRestart.cfg].
1. Geben Sie den folgenden Text in die [!DNL ScheduledRestart.cfg] Datei ein:

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
      <td colname="col1"> <i>Monat TT, JJJJ HH:MM:SS TZone</i> </td> 
      <td colname="col2"> <p>Der Zeitpunkt, zu dem <span class="keyword"> Insight Server zum ersten Mal neu gestartet </span> werden soll. </p> <p>Beispiel: 13. August 2013 22:30:00 EST </p> <p> <p>Hinweis:  Sie müssen eine Zeitzone angeben. Die Zeitzone wird nicht standardmäßig auf Systemzeit gesetzt, wenn sie nicht angegeben wird. Wenn Sie die Sommerzeit oder eine ähnliche Richtlinie zum Wechseln der Uhr implementieren möchten, müssen Sie die <span class="filepath"> .dst- </span> Datei mit den entsprechenden Regeln auf dem Base\Dataset\Timezone directory on the <span class="keyword"> Insight Server- </span> Computer speichern. Eine Liste der unterstützten Zeitzonenabkürzungen und Informationen zur Implementierung der Sommerzeit finden Sie unter <a href="../../../../home/c-inst-svr/c-time-zn-cds.md#concept-eed5ba32d5d347cf94b76db83b29f211"> Zeitzonencodes </a>. </p> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <i>frequency</i> </td> 
      <td colname="col2"> <p>Einer der folgenden Werte: 
       <ul id="ul_C29A40CD8FBB4333B5FA1D9E7DAD35EC"> 
       <li id="li_9FE07DD30C524CBB81C8F7968E7C733E">month </li> 
       <li id="li_E5E1B97ED8FB43C0BDA496C620D24A4C">Woche </li> 
       <li id="li_E6043B382FAE4B5D85CAADDFA60E4902">day </li> 
       </ul> </p> <p>Geben Sie an, wie oft <span class="keyword"> Insight Server nach der in Beginn Time festgelegten Anfangszeit neu gestartet </span> werden soll. </p> <p>Wenn Sie beispielsweise möchten, dass <span class="keyword"> Insight Server einmal pro Woche neu gestartet </span> wird, setzen Sie diesen Wert auf "Woche". </p> </td> 
      </tr> 
    </tbody> 
   </table>

1. Save the [!DNL ScheduledRestart.cfg] file.

   Vergewissern Sie sich, dass sich die [!DNL ScheduledRestart.cfg] Datei im [!DNL Components] Ordner befindet, in dem Sie installiert haben [!DNL Insight Server].
