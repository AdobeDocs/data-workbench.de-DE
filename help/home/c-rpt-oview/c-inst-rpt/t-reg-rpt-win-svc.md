---
description: Schritte zum Registrieren und Ausführen von Report Server.
title: Registrieren von Report Server als Windows-Service
uuid: 01fc0bbf-9f4a-487e-b1cb-16bf6974a541
exl-id: 46ea5dd4-7041-451e-91e5-f927873fc7d7
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '398'
ht-degree: 3%

---

# Registrieren von Report Server als Windows-Service{#registering-report-server-as-a-windows-service}

Schritte zum Registrieren und Ausführen von Report Server.

Bevor Sie dieses Verfahren durchführen, müssen Sie das Windows-Konto identifizieren, unter dem der [!DNL Report Server]-Dienst ausgeführt wird. Vergewissern Sie sich, dass dieses Konto über die erforderlichen Berechtigungen verfügt, um auf den Speicherort zuzugreifen, an dem die generierten Berichte gespeichert sind (verwenden Sie nicht das [!DNL Local System Account]).

Gehen Sie wie folgt vor, um Beginn [!DNL Report Server] zu erstellen. Wenn Sie zum ersten Mal [!DNL Report Server] Beginn ausführen, wird es automatisch als Windows-Dienst registriert.

Wenn Sie zum ersten Mal [!DNL Report Server] Beginn, wird automatisch eine Verbindung mit der Adobe License Server hergestellt, um Ihr digitales Zertifikat zu registrieren. Um den Registrierungsprozess erfolgreich abzuschließen, muss Ihr Computer mit dem Internet verbunden sein, wenn Sie die folgenden Schritte ausführen.

1. Navigieren Sie unter Windows zu dem Ordner, in dem Sie [!DNL Report Server] installiert haben.

   Beispiel: D:\Adobe\Report

1. Klicken Sie mit der Dublette auf **[!UICONTROL ReportServer.exe]**.
1. Um zu bestätigen, dass [!DNL Report Server] korrekt ausgeführt wird, klicken Sie auf **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Services]**. Diese Befehlssequenz kann je nach verwendeter Windows-Version variieren.
1. Suchen Sie in der Dienst-Liste den Eintrag für [!DNL Report Server] und bestätigen Sie, dass dessen Status &quot;Started&quot;und der Starttyp &quot;Automatic&quot;lautet.
1. Führen Sie die folgenden Schritte aus, um das Benutzerkonto anzugeben, unter dem [!DNL Report Server] ausgeführt wird:

   1. Klicken Sie mit der Dublette auf **[!UICONTROL Report Server]**, um das Fenster [!DNL Properties] zu öffnen.

   1. Wählen Sie die Registerkarte **[!UICONTROL Log On]**.
   1. Wählen Sie das Optionsfeld **[!UICONTROL This account]** aus.
   1. Geben Sie den Kontonamen ein oder suchen Sie ihn. Dieses Konto muss über die Berechtigung zum Zugriff auf den Speicherort der generierten Berichte verfügen.

      >[!NOTE]
      >
      >Verteilt [!DNL Report Server] Berichte als Microsoft Excel-Dateien ( [!DNL .xls] oder [!DNL .xlsx]), vergewissern Sie sich, dass das Konto auch berechtigt ist, Microsoft Excel auszuführen.

   1. Geben Sie das Kennwort für das Konto ein und bestätigen Sie es.
   1. Klicken Sie auf **[!UICONTROL OK]**.

1. Klicken Sie mit der rechten Maustaste auf den Dienst [!DNL Report Server] und wählen Sie **[!UICONTROL Restart]**, um den Dienst unter dem angegebenen Konto neu zu starten.
1. Um zu überprüfen, ob [!DNL Report Server] während des Beginns Fehler auftrat, klicken Sie auf **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**. Diese Befehlssequenz kann je nach verwendeter Windows-Version variieren.

   1. Wählen Sie im linken Bereich des Fensters [!DNL Event Viewer] das Anwendungsprotokoll aus.
   1. Suchen Sie im rechten Bereich in der Spalte [!DNL Source] nach Ereignissen mit Adobe.
   1. Wenn Sie einen Fehler aus der Adobe finden, klicken Sie bei gedrückter Dublette auf den Fehler, um das Fenster [!DNL Event Properties] anzuzeigen. Dieses Fenster enthält detaillierte Informationen zum Fehler.

      >[!NOTE]
      >
      >Nach den Beginn des Diensts [!DNL Report Server] wird die Datei [!DNL ReportServer.log] im Berichtsserver [!DNL Trace] erstellt. Diese Datei ist auch hilfreich, um Probleme mit [!DNL Report Server] zu beheben.

Sie haben die Installation von [!DNL Report Server] abgeschlossen. [!DNL Report Server] ist so ausgelegt, dass sie kontinuierlich läuft. Wenn Sie den Computer neu starten, wird [!DNL Report Server] automatisch neu gestartet. Wenn [!DNL Report Server] manuell Beginn und beendet werden muss, können Sie dies über das [!DNL Services]-Bedienfeld in Windows tun.
