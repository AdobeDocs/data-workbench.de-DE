---
description: Informationen zur Aktualisierung und Deinstallation Ihrer Report Server-Software.
title: Upgrade und Deinstallation von Report Server
uuid: 42f0d190-1a88-424d-be4b-90338144d287
exl-id: 86d0d848-4e2a-45cb-a1b3-b8a856332d33
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 2%

---

# Upgrade und Deinstallation von Report Server{#upgrading-and-uninstalling-report-server}

{{eol}}

Informationen zur Aktualisierung und Deinstallation Ihrer Report Server-Software.

* [Upgrade von Berichten](../../../home/c-rpt-oview/c-inst-rpt/c-upgrade-uninstall-rpt.md#section-95fea4bddad74616a8aea450dcdb2282)
* [Bericht deinstallieren](../../../home/c-rpt-oview/c-inst-rpt/c-upgrade-uninstall-rpt.md#section-96eb3281c45a45c0a7065deaa6845c25)

## Aktualisieren von Report Server {#section-95fea4bddad74616a8aea450dcdb2282}

Wenn Sie ein Upgrade auf [!DNL Report Server] 5.4 Sie können die Anweisungen zum Aktualisieren Ihrer [!DNL Report Server] Software. Wenn Sie [!DNL Report Server] 3.6 oder früher: Wenden Sie sich an die Adobe, um Unterstützung bei Ihrem Upgrade zu erhalten.

Aktualisierung [!DNL Report Server] 5.4 Verwenden Sie Data Workbench, um eine Aktualisierungsdatei auf den Data Workbench-Server zu kopieren, auf den [!DNL Report Server] stellt Verbindungen her. Anschließend [!DNL Report] Serverinstanzen aktualisieren sich automatisch selbst, wenn sie eine Verbindung zu diesem Server herstellen und ein Profil laden.

>[!NOTE]
>
>Vor der Aktualisierung [!DNL Report Server]müssen Sie sicherstellen, dass Sie Ihre Data Workbench-Server-Software sowie die Profile, die auf dem Data Workbench-Server ausgeführt werden, ordnungsgemäß aktualisiert haben. Weitere Informationen erhalten Sie von Adobe Consulting Services.

Um das folgende Verfahren durchzuführen, müssen Sie zunächst die Aktualisierungsdatei für [!DNL Report Server].

**Aktualisieren auf [!DNL Report Server] 5.4 und neuere Versionen**

1. Erstellen Sie eine Sicherungskopie aller Dateien unter [!DNL E:\Portal] und entfernen Sie alle Dateien und Ordner in diesem Verzeichnis.
1. Kopieren Sie den Inhalt des neuen Builds nach [!DNL E:\Portal].
1. Ändern [!DNL global.asa], [!DNL email.asp]und [!DNL TopNavigation.xml] gemäß den Anweisungen im vorherigen Abschnitt.

1. Kopieren Sie die [!DNL users.mdb] aus Ihrer Sicherung.

   >[!NOTE]
   >
   >Wenn Sie zuvor keine Berichte mit der Ausgabe .png erstellt haben, müssen Sie die einzelnen Berichtsordner aufrufen und die [!DNL reports.xml] , um ein Berichtsformat von png einzuschließen. Andernfalls wird möglicherweise ein 500-Fehler ausgegeben. Ihr Original [!DNL reports.xml] würde ungefähr wie folgt aussehen:

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

1. Im [!DNL report.cfg], fügen Sie ein Ausgabeformat von &quot;png&quot;und &quot;save&quot;hinzu. In Zukunft sollte es Berichte im PNG-Format generieren.

**Aktualisieren auf [!DNL Report Server] 4,0**

1. Kopieren Sie auf dem Data Workbench-Computer die Datei für das Report Server-Upgrade in die [!DNL Temp\Software] Ordner in dem Ordner, in dem Data Workbench installiert ist.
1. Starten Sie Data Workbench und laden Sie die [!DNL Configuration] Profil.
1. Klicken Sie auf **[!UICONTROL Configure Connection to Servers]** Miniaturansicht.
1. Im [!DNL Servers Manager]klicken Sie mit der rechten Maustaste auf das Data Workbench-Server-Symbol und klicken Sie auf **[!UICONTROL Server Files]**.

1. Öffnen Sie im Ordner Software den [!DNL Report Server] Ordner.
1. Klicken Sie mit der rechten Maustaste auf die **[!UICONTROL Temp]** Häkchen für [!DNL ReportServer.exe] und wählen Sie **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

## Deinstallieren von Report Server {#section-96eb3281c45a45c0a7065deaa6845c25}

**Deinstallation[!DNL Report Server]**

1. Rückgängigmachen der Registrierung [!DNL Report Windows] Dienst.

   1. Öffnen Sie eine Eingabeaufforderung und navigieren Sie zum Unterordner &quot;bin&quot;in dem Ordner, in dem Sie den Data Workbench-Server installiert haben (InsightServer64.exe). Beispiel: [!DNL D:\Adobe\Report\bin]
   1. Führen Sie an der Eingabeaufforderung den folgenden Befehl aus, um die Registrierung als Dienst unter Microsoft Windows zu beenden und aufzuheben: [!DNL visualreport /unregserver]

1. Löschen Sie den Installationsordner von Report Server.
