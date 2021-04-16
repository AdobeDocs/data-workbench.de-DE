---
description: Verfahren zum Beginn Insight Server und zur gleichzeitigen Registrierung als Microsoft Windows Service.
title: Registrieren von Insight Server als Windows-Service
uuid: 1b3d53ca-d50f-4520-abf5-6d5c40493b88
exl-id: ba74d4c0-5d99-47a4-8b92-c65d0ec514e2
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '582'
ht-degree: 3%

---

# Registrieren von Insight Server als Windows-Service{#registering-insight-server-as-a-windows-service}

Verfahren zum Beginn Insight Server und zur gleichzeitigen Registrierung als Microsoft Windows Service.

>[!NOTE]
>
>Wenn Sie zum ersten Mal [!DNL Insight Server] Beginn, wird automatisch eine Verbindung mit der Adobe License Server hergestellt, um Ihr digitales Zertifikat zu registrieren. Um den Registrierungsprozess erfolgreich abzuschließen, muss Ihr Computer mit dem Internet verbunden sein, wenn Sie die folgenden Schritte ausführen.

**Beginn  [!DNL Insight Server] und Registrierung als Windows-Dienst**

1. Öffnen Sie eine Eingabeaufforderung und navigieren Sie zum Unterverzeichnis &quot;bin&quot;in dem Ordner, in dem Sie [!DNL Insight Server] installiert haben.

   Beispiel: [!DNL C:\Adobe\Server\bin]

1. Führen Sie an der Eingabeaufforderung den folgenden Befehl aus, um Beginn [!DNL Insight Server] zu starten, und registrieren Sie ihn gleichzeitig für die Ausführung als Dienst unter Microsoft Windows:

   ```
   <filepath>
   InsightServer64.exe /regserver 
   </filepath>
   ```

1. Um zu bestätigen, dass [!DNL Insight Server] korrekt ausgeführt wird, klicken Sie auf **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Services]**. Diese Befehlssequenz kann je nach verwendeter Windows-Version variieren.

   1. Suchen Sie in der Dienst-Liste den Eintrag für **[!DNL Adobe Insight Server]** und bestätigen Sie, dass dessen Status &quot;Started&quot;und der Starttyp &quot;Automatic&quot;lautet.
   1. Schließen Sie das Bedienfeld &quot;Dienste&quot;.

1. Um zu überprüfen, ob [!DNL Insight Server] während des Beginns Fehler auftrat, klicken Sie auf **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**. Diese Befehlssequenz kann je nach verwendeter Windows-Version variieren.

   1. Wählen Sie im linken Bereich des Fensters [!DNL Event Viewer] das Protokoll **[!UICONTROL Application]** aus.
   1. Suchen Sie im rechten Bereich nach Ereignissen mit &quot;Adobe&quot;in der Spalte [!DNL Source].
   1. Wenn Sie eine Fehlermeldung aus &quot;Adobe&quot;erhalten, klicken Sie bei gedrückter Dublette auf den Fehler, um das Fenster [!DNL Event Properties] anzuzeigen. Dieses Fenster enthält detaillierte Informationen zum Fehler.

1. Wenn Sie das [!DNL Applications]-Protokoll überprüft haben, schließen Sie den Ereignis-Viewer.

Sie haben die Installation von [!DNL Insight Server] abgeschlossen. [!DNL Insight Server] ist so ausgelegt, dass sie kontinuierlich läuft. Wenn Sie den Computer neu starten, wird [!DNL Insight Server] automatisch neu gestartet. Wenn [!DNL Insight Server] manuell Beginn und beendet werden muss, können Sie dies über das Bedienfeld &quot;Dienste&quot;in Windows tun. Wie im folgenden Abschnitt beschrieben, können Sie optional den Dienst [!DNL Insight Server] so konfigurieren, dass er regelmäßig automatisch neu gestartet wird.

## Konfigurieren des Dienstes zum automatischen Neustart von {#section-f9bb91614513435f84ee55c0ec8edb13}

[!DNL Insight Server] ist so ausgelegt, dass sie ununterbrochen ausgeführt wird. Es wird normalerweise nur angehalten oder gestartet, wenn seltene Aufgaben wie Software-Upgrades oder Zertifikatänderungen oder im Ereignis bestimmter Systemfehler ausgeführt werden. Es ist nicht erforderlich, den [!DNL Insight Server]-Dienst während des normalen Systembetriebs zu beenden oder neu zu starten. Sie können jedoch konfigurieren, dass der Dienst regelmäßig neu gestartet wird (täglich, wöchentlich oder monatlich), um beispielsweise die Ereignis-Meldungen zu löschen.

**So konfigurieren Sie den  [!DNL Insight Server] Dienst für einen automatischen Neustart**

1. Navigieren Sie zum Ordner [!DNL Components] in dem Ordner, in dem Sie [!DNL Insight Server] installiert haben.

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
      <td colname="col1"> <i>Monat TT, JJJJ HH:MM:SS TZone</i> </td> 
      <td colname="col2"> <p>Der Zeitpunkt, zu dem <span class="keyword"> Insight Server </span> zum ersten Mal neu gestartet werden soll. </p> <p>Beispiel: 13. August 2013 22:30:00 EST </p> <p> <p>Hinweis:  Sie müssen eine Zeitzone angeben. Die Zeitzone wird nicht standardmäßig auf Systemzeit gesetzt, wenn sie nicht angegeben wird. Wenn Sie die Sommerzeit oder eine ähnliche Richtlinie zum Wechseln der Uhr implementieren möchten, müssen Sie die Datei <span class="filepath"> .dst </span> mit den entsprechenden Regeln auf dem Computer Base\Dataset\Timezone directory on the <span class="keyword"> Insight Server </span> speichern. Eine Liste der unterstützten Zeitzonenabkürzungen und Informationen zur Implementierung der Sommerzeit finden Sie unter <a href="../../../../home/c-inst-svr/c-time-zn-cds.md#concept-eed5ba32d5d347cf94b76db83b29f211"> Zeitzonencodes </a>. </p> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <i>frequency</i> </td> 
      <td colname="col2"> <p>Einer der folgenden Werte: 
       <ul id="ul_C29A40CD8FBB4333B5FA1D9E7DAD35EC"> 
       <li id="li_9FE07DD30C524CBB81C8F7968E7C733E">month </li> 
       <li id="li_E5E1B97ED8FB43C0BDA496C620D24A4C">Woche </li> 
       <li id="li_E6043B382FAE4B5D85CAADDFA60E4902">day </li> 
       </ul> </p> <p>Mit dieser Option geben Sie an, wie oft <span class="keyword"> Insight Server </span> nach der in Beginn Time angegebenen Anfangszeit neu gestartet werden soll. </p> <p>Wenn Sie beispielsweise möchten, dass <span class="keyword"> Insight Server </span> einmal wöchentlich neu gestartet wird, setzen Sie diesen Wert auf "week". </p> </td> 
      </tr> 
    </tbody> 
   </table>

1. Speichern Sie die Datei [!DNL ScheduledRestart.cfg].

   Vergewissern Sie sich, dass sich die Datei [!DNL ScheduledRestart.cfg] im Ordner [!DNL Components] des Ordners befindet, in dem Sie [!DNL Insight Server] installiert haben.
