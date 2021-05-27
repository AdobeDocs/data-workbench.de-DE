---
description: Schritte zum Registrieren und Ausführen von Report Server.
title: Registrieren von Report Server als Windows-Service
uuid: 01fc0bbf-9f4a-487e-b1cb-16bf6974a541
exl-id: 46ea5dd4-7041-451e-91e5-f927873fc7d7
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '398'
ht-degree: 3%

---

# Registrieren von Report Server als Windows-Service{#registering-report-server-as-a-windows-service}

Schritte zum Registrieren und Ausführen von Report Server.

Bevor Sie dieses Verfahren durchführen, müssen Sie das Windows-Konto identifizieren, unter dem der [!DNL Report Server]-Dienst ausgeführt wird. Stellen Sie sicher, dass dieses Konto über die entsprechenden Berechtigungen für den Zugriff auf den Speicherort der erstellten Berichte verfügt (verwenden Sie also nicht die [!DNL Local System Account]-Variable).

Gehen Sie wie folgt vor, um [!DNL Report Server] zu starten. Wenn Sie [!DNL Report Server] zum ersten Mal starten, wird es automatisch als Windows-Dienst registriert.

Wenn Sie [!DNL Report Server] zum ersten Mal starten, wird automatisch eine Verbindung zum Adobe License Server hergestellt, um Ihr digitales Zertifikat zu registrieren. Um den Registrierungsprozess erfolgreich abzuschließen, muss Ihr Computer mit dem Internet verbunden sein, wenn Sie die folgenden Schritte ausführen.

1. Navigieren Sie unter Windows zu dem Ordner, in dem Sie [!DNL Report Server] installiert haben.

   Beispiel: D:\Adobe\Report

1. Doppelklicken Sie auf **[!UICONTROL ReportServer.exe]**.
1. Um zu bestätigen, dass [!DNL Report Server] ordnungsgemäß ausgeführt wird, klicken Sie auf **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Services]**. Diese Befehlssequenz kann je nach verwendeter Windows-Version variieren.
1. Suchen Sie in der Dienstliste den Eintrag für [!DNL Report Server] und vergewissern Sie sich, dass sein Status &quot;Started&quot;und sein Starttyp &quot;Automatisch&quot;lautet.
1. Gehen Sie wie folgt vor, um das Benutzerkonto anzugeben, unter dem [!DNL Report Server] ausgeführt wird:

   1. Doppelklicken Sie auf **[!UICONTROL Report Server]** , um das Fenster [!DNL Properties] zu öffnen.

   1. Wählen Sie die Registerkarte **[!UICONTROL Log On]** aus.
   1. Wählen Sie das Optionsfeld **[!UICONTROL This account]** aus.
   1. Geben oder suchen Sie nach dem Kontonamen. Dieses Konto muss Zugriff auf den Speicherort haben, an dem die generierten Berichte gespeichert werden.

      >[!NOTE]
      >
      >Wenn [!DNL Report Server] Berichte als Microsoft Excel-Dateien ( [!DNL .xls] oder [!DNL .xlsx]) verteilt, stellen Sie sicher, dass das Konto auch über die Berechtigung zum Ausführen von Microsoft Excel verfügt.

   1. Geben Sie das Kennwort für das Konto ein und bestätigen Sie es.
   1. Klicken Sie auf **[!UICONTROL OK]**.

1. Klicken Sie mit der rechten Maustaste auf den Dienst [!DNL Report Server] und wählen Sie **[!UICONTROL Restart]** aus, um den Dienst unter dem von Ihnen angegebenen Konto neu zu starten.
1. Um zu überprüfen, ob [!DNL Report Server] beim Start Fehler aufgetreten sind, klicken Sie auf **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**. Diese Befehlssequenz kann je nach verwendeter Windows-Version variieren.

   1. Wählen Sie im linken Bereich des Fensters [!DNL Event Viewer] das Protokoll &quot;Applications&quot;aus.
   1. Suchen Sie im rechten Bereich nach Ereignissen mit Adobe in der Spalte [!DNL Source] .
   1. Doppelklicken Sie auf eine Fehlermeldung in der Adobe, um das Fenster [!DNL Event Properties] anzuzeigen. In diesem Fenster erhalten Sie detaillierte Informationen zum Fehler.

      >[!NOTE]
      >
      >Nachdem der Dienst [!DNL Report Server] gestartet wurde, wird die Datei [!DNL ReportServer.log] im Verzeichnis Report Server [!DNL Trace] erstellt. Diese Datei ist auch zur Fehlerbehebung bei Problemen mit [!DNL Report Server] nützlich.

Sie haben die Installation von [!DNL Report Server] abgeschlossen. [!DNL Report Server] ist so ausgelegt, dass sie kontinuierlich läuft. Wenn Sie den Computer neu starten, wird [!DNL Report Server] automatisch neu gestartet. Wenn Sie [!DNL Report Server] manuell starten und stoppen müssen, können Sie dies über das [!DNL Services]-Control Panel in Windows tun.
