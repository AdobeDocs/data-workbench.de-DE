---
description: Verfahren zum Starten von Insight Server und zur gleichzeitigen Registrierung als Microsoft Windows Service.
title: Registrieren von Insight Server als Windows-Service
uuid: 1b3d53ca-d50f-4520-abf5-6d5c40493b88
exl-id: ba74d4c0-5d99-47a4-8b92-c65d0ec514e2
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '582'
ht-degree: 3%

---

# Registrieren von Insight Server als Windows-Service{#registering-insight-server-as-a-windows-service}

Verfahren zum Starten von Insight Server und zur gleichzeitigen Registrierung als Microsoft Windows Service.

>[!NOTE]
>
>Wenn Sie [!DNL Insight Server] zum ersten Mal starten, wird automatisch eine Verbindung zum Adobe License Server hergestellt, um Ihr digitales Zertifikat zu registrieren. Um den Registrierungsprozess erfolgreich abzuschließen, muss Ihr Computer mit dem Internet verbunden sein, wenn Sie die folgenden Schritte ausführen.

**So starten  [!DNL Insight Server] und registrieren Sie es als Windows-Dienst**

1. Öffnen Sie eine Eingabeaufforderung und navigieren Sie zum Unterverzeichnis &quot;bin&quot;im Ordner, in dem Sie [!DNL Insight Server] installiert haben.

   Beispiel: [!DNL C:\Adobe\Server\bin]

1. Führen Sie an der Eingabeaufforderung den folgenden Befehl aus, um [!DNL Insight Server] zu starten, und registrieren Sie ihn gleichzeitig für die Ausführung als Dienst unter Microsoft Windows:

   ```
   <filepath>
   InsightServer64.exe /regserver 
   </filepath>
   ```

1. Um zu bestätigen, dass [!DNL Insight Server] ordnungsgemäß ausgeführt wird, klicken Sie auf **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Services]**. Diese Befehlssequenz kann je nach verwendeter Windows-Version variieren.

   1. Suchen Sie in der Dienstliste den Eintrag für **[!DNL Adobe Insight Server]** und vergewissern Sie sich, dass sein Status &quot;Started&quot;und sein Starttyp &quot;Automatisch&quot;lautet.
   1. Schließen Sie die Systemsteuerung &quot;Dienste&quot;.

1. Um zu überprüfen, ob [!DNL Insight Server] beim Start Fehler aufgetreten sind, klicken Sie auf **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**. Diese Befehlssequenz kann je nach verwendeter Windows-Version variieren.

   1. Wählen Sie im linken Bereich des Fensters [!DNL Event Viewer] das Protokoll **[!UICONTROL Application]** aus.
   1. Suchen Sie im rechten Bereich nach Ereignissen mit &quot;Adobe&quot;in der Spalte [!DNL Source] .
   1. Wenn Sie einen Fehler aus &quot;Adobe&quot;finden, doppelklicken Sie auf den Fehler, um das Fenster [!DNL Event Properties] anzuzeigen. In diesem Fenster erhalten Sie detaillierte Informationen zum Fehler.

1. Wenn Sie die Untersuchung des [!DNL Applications]-Protokolls abgeschlossen haben, schließen Sie die Ereignisanzeige.

Sie haben die Installation von [!DNL Insight Server] abgeschlossen. [!DNL Insight Server] ist so ausgelegt, dass sie kontinuierlich läuft. Wenn Sie den Computer neu starten, wird [!DNL Insight Server] automatisch neu gestartet. Wenn Sie [!DNL Insight Server] manuell starten und stoppen müssen, können Sie dies über das Bedienfeld Dienste in Windows tun. Wie im folgenden Abschnitt beschrieben, können Sie optional den Dienst [!DNL Insight Server] so konfigurieren, dass er regelmäßig automatisch neu gestartet wird.

## Konfigurieren des Dienstes zum automatischen Neustart von {#section-f9bb91614513435f84ee55c0ec8edb13}

[!DNL Insight Server] ist so konzipiert, dass es weiterhin unterbrechungsfrei läuft. Sie wird normalerweise nur bei seltenen Aufgaben wie Software-Upgrades oder Zertifikatänderungen oder bei bestimmten Systemfehlern angehalten oder gestartet. Es ist nicht erforderlich, den Dienst [!DNL Insight Server] während des normalen Systembetriebs zu beenden oder neu zu starten. Sie können den Dienst jedoch so konfigurieren, dass er regelmäßig neu gestartet wird (täglich, wöchentlich oder monatlich), um beispielsweise die Ereignismeldungen zu löschen.

**So konfigurieren Sie den  [!DNL Insight Server] Dienst so, dass er automatisch neu gestartet wird**

1. Navigieren Sie zum Ordner [!DNL Components] im Ordner, in dem Sie [!DNL Insight Server] installiert haben.

   Beispiel: [!DNL C:\Adobe\Server\Components]

1. Verwenden Sie einen Texteditor wie Notepad, um eine neue Datei mit dem Namen [!DNL ScheduledRestart.cfg] zu erstellen.
1. Geben Sie den folgenden Text in die Datei [!DNL ScheduledRestart.cfg] ein:

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
      <td colname="col2"> <p>Der Zeitpunkt, zu dem <span class="keyword"> Insight Server </span> zum ersten Mal neu gestartet werden soll. </p> <p>Beispiel: 13. August 2013 22:30:00 EST </p> <p> <p>Hinweis:  Sie müssen eine Zeitzone angeben. Wenn nicht angegeben, wird in der Zeitzone nicht standardmäßig Systemzeit verwendet. Wenn Sie die Sommerzeit oder eine ähnliche Richtlinie zum Wechsel der Uhr implementieren möchten, müssen Sie die Datei <span class="filepath"> .dst </span> mit den entsprechenden Regeln auf dem Computer Base\Dataset\Timezone directory on the <span class="keyword"> Insight Server </span> speichern. Eine Liste der unterstützten Zeitzonenabkürzungen und Informationen zur Implementierung der Sommerzeit finden Sie unter <a href="../../../../home/c-inst-svr/c-time-zn-cds.md#concept-eed5ba32d5d347cf94b76db83b29f211"> Zeitzonencodes </a>. </p> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <i>Häufigkeit</i> </td> 
      <td colname="col2"> <p>Einer der folgenden Werte: 
       <ul id="ul_C29A40CD8FBB4333B5FA1D9E7DAD35EC"> 
       <li id="li_9FE07DD30C524CBB81C8F7968E7C733E">month </li> 
       <li id="li_E5E1B97ED8FB43C0BDA496C620D24A4C">Woche </li> 
       <li id="li_E6043B382FAE4B5D85CAADDFA60E4902">day </li> 
       </ul> </p> <p>Um anzugeben, wie oft <span class="keyword"> Insight Server </span> nach der in der Startzeit angegebenen anfänglichen Zeit neu gestartet werden soll. </p> <p>Wenn Sie beispielsweise möchten, dass <span class="keyword"> Insight Server </span> einmal wöchentlich neu gestartet wird, setzen Sie diesen Wert auf "week". </p> </td> 
      </tr> 
    </tbody> 
   </table>

1. Speichern Sie die Datei [!DNL ScheduledRestart.cfg].

   Stellen Sie sicher, dass sich die Datei [!DNL ScheduledRestart.cfg] im Ordner [!DNL Components] des Ordners befindet, in dem Sie [!DNL Insight Server] installiert haben.
