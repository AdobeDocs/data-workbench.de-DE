---
description: Schritte zum Registrieren und Ausführen von Report Server.
solution: Analytics
title: Registrieren des Berichtsservers als Windows-Dienst
topic: Data workbench
uuid: 01fc0bbf-9f4a-487e-b1cb-16bf6974a541
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Registrieren des Berichtsservers als Windows-Dienst{#registering-report-server-as-a-windows-service}

Schritte zum Registrieren und Ausführen von Report Server.

Bevor Sie dieses Verfahren durchführen, müssen Sie das Windows-Konto angeben, unter dem der [!DNL Report Server] Dienst ausgeführt werden soll. Vergewissern Sie sich, dass dieses Konto über die erforderlichen Berechtigungen verfügt, um auf den Speicherort zuzugreifen, an dem die generierten Berichte gespeichert werden (verwenden Sie also nicht die [!DNL Local System Account]).

Gehen Sie wie folgt vor, um zu beginnen [!DNL Report Server]. Wenn Sie [!DNL Report Server] zum ersten Mal starten, registriert es sich automatisch als Windows-Dienst.

Wenn Sie [!DNL Report Server] zum ersten Mal starten, wird automatisch eine Verbindung zum Adobe License Server hergestellt, um Ihr digitales Zertifikat zu registrieren. Um den Registrierungsprozess erfolgreich abzuschließen, muss Ihr Computer mit dem Internet verbunden sein, wenn Sie die folgenden Schritte ausführen.

1. Navigieren Sie unter Windows zu dem Ordner, in dem Sie installiert haben [!DNL Report Server].

   Beispiel: D:\Adobe\Report

1. Double-click **[!UICONTROL ReportServer.exe]**.
1. Um zu bestätigen, dass [!DNL Report Server] die Funktion korrekt ausgeführt wird, klicken Sie auf **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Services]**. Diese Befehlssequenz kann je nach verwendeter Windows-Version variieren.
1. Suchen Sie in der Liste &quot;Dienst&quot;den Eintrag für [!DNL Report Server] und bestätigen Sie, dass der Status &quot;Started&quot;und der Starttyp &quot;Automatisch&quot;lautet.
1. Führen Sie die folgenden Schritte aus, um das Benutzerkonto anzugeben, unter dem ausgeführt [!DNL Report Server] wird:

   1. Doppelklicken Sie auf **[!UICONTROL Report Server]** , um das [!DNL Properties] Fenster zu öffnen.

   1. Wählen Sie die **[!UICONTROL Log On]** Registerkarte.
   1. Wählen Sie das **[!UICONTROL This account]** Optionsfeld aus.
   1. Geben Sie den Kontonamen ein oder suchen Sie ihn. Dieses Konto muss über die Berechtigung zum Zugriff auf den Speicherort der generierten Berichte verfügen.

      >[!NOTE]
      >
      >Wenn Berichte als Microsoft Excel-Dateien ( [!DNL Report Server] oder [!DNL .xls] [!DNL .xlsx]) verteilt werden, vergewissern Sie sich, dass das Konto auch berechtigt ist, Microsoft Excel auszuführen.

   1. Geben Sie das Kennwort für das Konto ein und bestätigen Sie es.
   1. Klicken Sie auf **[!UICONTROL OK]**.

1. Klicken Sie mit der rechten Maustaste auf den [!DNL Report Server] Dienst und wählen Sie **[!UICONTROL Restart]** den Dienst unter dem angegebenen Konto neu starten.
1. Um zu überprüfen, ob beim Start Fehler [!DNL Report Server] aufgetreten sind, klicken Sie auf **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**. Diese Befehlssequenz kann je nach verwendeter Windows-Version variieren.

   1. Wählen Sie im linken Bereich des [!DNL Event Viewer] Fensters das Anwendungsprotokoll aus.
   1. Suchen Sie im rechten Bereich nach Ereignissen mit Adobe in der [!DNL Source] Spalte.
   1. Wenn Sie einen Fehler von Adobe erhalten, doppelklicken Sie auf den Fehler, um das [!DNL Event Properties] Fenster anzuzeigen. Dieses Fenster enthält detaillierte Informationen zum Fehler.

      >[!NOTE]
      >
      >Nach dem Start des [!DNL Report Server] Dienstes [!DNL ReportServer.log] wird die Datei im [!DNL Trace] Ordner &quot;Report Server&quot;erstellt. Diese Datei ist auch zur Fehlerbehebung bei Problemen mit [!DNL Report Server]DPS nützlich.

Sie haben die Installation von abgeschlossen [!DNL Report Server]. [!DNL Report Server] ist so ausgelegt, dass sie kontinuierlich läuft. Wenn Sie den Computer neu starten, [!DNL Report Server] wird er automatisch neu gestartet. Wenn Sie [!DNL Report Server] manuell starten und anhalten müssen, können Sie dies über das [!DNL Services] Bedienfeld in Windows tun.
