---
description: Schritte zum Registrieren und Ausführen von Report Server.
title: Registrieren von Report Server als Windows-Service
uuid: 01fc0bbf-9f4a-487e-b1cb-16bf6974a541
exl-id: 46ea5dd4-7041-451e-91e5-f927873fc7d7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '398'
ht-degree: 3%

---

# Registrieren von Report Server als Windows-Service{#registering-report-server-as-a-windows-service}

{{eol}}

Schritte zum Registrieren und Ausführen von Report Server.

Bevor Sie dieses Verfahren durchführen, müssen Sie das Windows-Konto identifizieren, unter dem die [!DNL Report Server] wird ausgeführt. Vergewissern Sie sich, dass dieses Konto über die entsprechenden Berechtigungen verfügt, um auf den Speicherort zuzugreifen, an dem die generierten Berichte gespeichert sind (verwenden Sie also nicht das [!DNL Local System Account]).

Gehen Sie wie folgt vor, um zu beginnen [!DNL Report Server]. Wenn Sie beginnen [!DNL Report Server] Erstmalig registriert es sich automatisch als Windows-Dienst.

Wenn Sie beginnen [!DNL Report Server] Zum ersten Mal stellt es automatisch eine Verbindung zum Adobe License Server her, um Ihr digitales Zertifikat zu registrieren. Um den Registrierungsprozess erfolgreich abzuschließen, muss Ihr Computer mit dem Internet verbunden sein, wenn Sie die folgenden Schritte ausführen.

1. Navigieren Sie unter Windows zum Ordner, in dem Sie installiert haben. [!DNL Report Server].

   Beispiel: D:\Adobe\Report

1. Doppelklicken **[!UICONTROL ReportServer.exe]**.
1. So bestätigen Sie Folgendes: [!DNL Report Server] korrekt ausgeführt wird, klicken Sie auf **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Services]**. Diese Befehlssequenz kann je nach verwendeter Windows-Version variieren.
1. Suchen Sie in der Dienstliste den Eintrag für [!DNL Report Server] und bestätigen Sie, dass der Status Started und der Starttyp Automatisch lautet.
1. Führen Sie die folgenden Schritte aus, um das Benutzerkonto anzugeben, unter dem [!DNL Report Server] wird ausgeführt:

   1. Doppelklicken **[!UICONTROL Report Server]** , um [!DNL Properties] Fenster.

   1. Wählen Sie die **[!UICONTROL Log On]** Registerkarte.
   1. Wählen Sie die **[!UICONTROL This account]** Optionsfeld.
   1. Geben oder suchen Sie nach dem Kontonamen. Dieses Konto muss Zugriff auf den Speicherort haben, an dem die generierten Berichte gespeichert werden.

      >[!NOTE]
      >
      >Wenn [!DNL Report Server] verteilt Berichte als Microsoft Excel ( [!DNL .xls] oder [!DNL .xlsx]), stellen Sie sicher, dass das Konto auch berechtigt ist, Microsoft Excel auszuführen.

   1. Geben Sie das Kennwort für das Konto ein und bestätigen Sie es.
   1. Klicken Sie auf **[!UICONTROL OK]**.

1. Klicken Sie mit der rechten Maustaste auf die [!DNL Report Server] Dienst und wählen Sie **[!UICONTROL Restart]** , um den Dienst unter dem von Ihnen angegebenen Konto neu zu starten.
1. Überprüfen, ob [!DNL Report Server] während des Starts Fehler aufgetreten sind, klicken Sie auf **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**. Diese Befehlssequenz kann je nach verwendeter Windows-Version variieren.

   1. Im linken Bereich des [!DNL Event Viewer] Wählen Sie das Anwendungsprotokoll aus.
   1. Suchen Sie im rechten Bereich nach Ereignissen mit Adobe im [!DNL Source] Spalte.
   1. Wenn eine Fehlermeldung aus der Adobe auftritt, doppelklicken Sie auf die Fehlermeldung, um die [!DNL Event Properties] Fenster. In diesem Fenster erhalten Sie detaillierte Informationen zum Fehler.

      >[!NOTE]
      >
      >Nach dem [!DNL Report Server] Dienst startet, die Datei [!DNL ReportServer.log] wird im Report Server erstellt [!DNL Trace] Verzeichnis. Diese Datei ist auch zur Fehlerbehebung bei Problemen mit [!DNL Report Server].

Sie haben die Installation der [!DNL Report Server]. [!DNL Report Server] ist so ausgelegt, dass sie kontinuierlich läuft. Wenn Sie den Computer neu starten, [!DNL Report Server] wird automatisch neu gestartet. Wenn Sie beginnen und anhalten müssen [!DNL Report Server] manuell verwenden, können Sie dies mithilfe der [!DNL Services] Bedienfeld in Windows.
