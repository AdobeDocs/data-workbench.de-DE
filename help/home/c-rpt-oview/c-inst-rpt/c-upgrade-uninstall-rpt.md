---
description: Informationen zum Aktualisieren und Deinstallieren Ihrer Report Server-Software.
solution: Analytics
title: Aktualisieren und Deinstallieren von Report Server
topic: Data workbench
uuid: 42f0d190-1a88-424d-be4b-90338144d287
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Aktualisieren und Deinstallieren von Report Server{#upgrading-and-uninstalling-report-server}

Informationen zum Aktualisieren und Deinstallieren Ihrer Report Server-Software.

* [Bericht aktualisieren](../../../home/c-rpt-oview/c-inst-rpt/c-upgrade-uninstall-rpt.md#section-95fea4bddad74616a8aea450dcdb2282)
* [Bericht deinstallieren](../../../home/c-rpt-oview/c-inst-rpt/c-upgrade-uninstall-rpt.md#section-96eb3281c45a45c0a7065deaa6845c25)

## Aktualisieren des Berichtsservers {#section-95fea4bddad74616a8aea450dcdb2282}

Wenn Sie ein Upgrade auf [!DNL Report Server] 5.4 durchführen, können Sie die Anweisungen zur Aktualisierung Ihrer [!DNL Report Server] Software verwenden. Wenn Sie [!DNL Report Server] 3.6 oder früher verwenden, wenden Sie sich an Adobe, um Unterstützung bei Ihrem Upgrade zu erhalten.

Um [!DNL Report Server] 5.4 zu aktualisieren, verwenden Sie Data Workbench, um eine Aktualisierungsdatei auf den Data Workbench-Server zu kopieren, mit dem eine Verbindung hergestellt [!DNL Report Server] wird. Danach aktualisieren sich [!DNL Report] Serverinstanzen automatisch selbst, wenn sie eine Verbindung zu diesem Server herstellen und ein Profil laden.

>[!NOTE]
>
>Vergewissern Sie sich vor der Aktualisierung [!DNL Report Server], dass Sie die Data Workbench-Serversoftware sowie die Profile, die auf dem Data Workbench-Server ausgeführt werden, ordnungsgemäß aktualisiert haben. Weitere Informationen erhalten Sie bei Adobe Consulting Services.

Um das folgende Verfahren auszuführen, müssen Sie zunächst die Aktualisierungsdatei für [!DNL Report Server]abrufen.

**So aktualisieren Sie auf Version[!DNL Report Server]5.4 und höher**

1. Erstellen Sie eine Sicherungskopie aller Dateien unter [!DNL E:\Portal] und entfernen Sie alle Dateien und Ordner in diesem Ordner.
1. Copy the contents of the new build into [!DNL E:\Portal].
1. Ändern Sie [!DNL global.asa], [!DNL email.asp]und [!DNL TopNavigation.xml] entsprechend den Anweisungen im vorherigen Abschnitt.

1. Kopieren Sie die [!DNL users.mdb] Datei aus Ihrem Backup.

   >[!NOTE]
   >
   >Wenn Sie zuvor keine Berichte mit der PNG-Ausgabe erstellt haben, müssen Sie in die einzelnen Berichtsordner gehen und die Einstellung ändern, [!DNL reports.xml] um ein Berichtsformat einzuschließen. Andernfalls wird möglicherweise ein 500-Fehler ausgegeben. Ihr Original [!DNL reports.xml] würde etwa wie folgt aussehen:

   ```
      <?xml version="1.0" encoding="UTF-8" standalone="no" ?>
   <REPORTS>
    <REPORT format="xls">
     <NAME>Dashboard</NAME>
     <PATH>Dashboard.xls</PATH>
     <WEB_PATH>Dashboard.xls</WEB_PATH>
    </REPORT>
   </REPORTS>
   ```

   Er müsste wie folgt geändert werden:

   ```
   <?xml version="1.0" encoding="UTF-8" standalone="no" ?>
   <REPORTS>
    <REPORT format="xls">
     <NAME>Dashboard</NAME>
     <PATH>Dashboard.xls</PATH>
     <WEB_PATH>Dashboard.xls</WEB_PATH>
    </REPORT>
    <REPORT format="png">
    <NAME>Dashboard</NAME>
     <PATH>Dashboard.png</PATH>
     <WEB_PATH>Dashboard.png</WEB_PATH>
    </REPORT>
   </REPORTS>
   ```

1. Schließen Sie im [!DNL report.cfg]Dialogfeld das Ausgabeformat &quot;png&quot;und &quot;save&quot;ein. In Zukunft sollte es Berichte im PNG-Format generieren.

**So aktualisieren Sie auf[!DNL Report Server]4.0**

1. Kopieren Sie auf dem Data Workbench-Computer die Aktualisierungsdatei für den Report Server in den [!DNL Temp\Software] Ordner, in dem die Data Workbench installiert ist.
1. Starten Sie die Data Workbench und laden Sie das [!DNL Configuration] Profil.
1. Klicken Sie auf die **[!UICONTROL Configure Connection to Servers]** Miniaturansicht.
1. Klicken Sie im [!DNL Servers Manager]Kontextmenü mit der rechten Maustaste auf das Symbol Data Workbench-Server und klicken Sie auf **[!UICONTROL Server Files]**.

1. Öffnen Sie im Ordner Software den [!DNL Report Server] Ordner.
1. Klicken Sie mit der rechten Maustaste auf das **[!UICONTROL Temp]** Häkchen [!DNL ReportServer.exe] und wählen Sie **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

## Deinstallieren von Report Server {#section-96eb3281c45a45c0a7065deaa6845c25}

**So deinstallieren[!DNL Report Server]**

1. Heben Sie die Registrierung des [!DNL Report Windows] Dienstes auf.

   1. Öffnen Sie eine Eingabeaufforderung und navigieren Sie zum Unterordner &quot;bin&quot;in dem Ordner, in dem Sie den Data Workbench-Server installiert haben (InsightServer64.exe). Beispiel: [!DNL D:\Adobe\Report\bin]
   1. Führen Sie an der Eingabeaufforderung den folgenden Befehl aus, um ihn unter Microsoft Windows als Dienst zu beenden und die Registrierung aufzuheben: [!DNL visualreport /unregserver]

1. Löschen Sie den Installationsordner des Berichtsservers.

