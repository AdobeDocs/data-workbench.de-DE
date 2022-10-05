---
description: Führen Sie diese Schritte aus, um von Ihrer Data Workbench v6.0x-Installation auf Data Workbench v6.1 zu aktualisieren.
title: 'Data Workbench-Upgrade: 6.0 auf 6.1'
uuid: 4671c2bf-06ab-49c4-8dd1-24115facd83b
exl-id: 559e1942-561c-4270-9670-550177730cdb,2a337d2e-c70e-4f35-a6c2-c3a7f50a0800
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '743'
ht-degree: 1%

---

# Data Workbench-Upgrade: 6.0 auf 6.1{#data-workbench-to-upgrade}

{{eol}}

Führen Sie diese Schritte aus, um von Ihrer Data Workbench v6.0x-Installation auf Data Workbench v6.1 zu aktualisieren.

**Schritt 1**: [Serveraktualisierung](../../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-6-0-to-6-1-upgrade.md#section-7845393f76214aa7ad53ac4b2cca9e5b)

**Schritt 2**: [Report Server-Aktualisierung](../../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-6-0-to-6-1-upgrade.md#section-afd9560a446242e9b06490e5f98aaaec)

**Schritt 3**: [Client-Upgrade](../../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-6-0-to-6-1-upgrade.md#section-c896e57ecd2847afb18f4d8ef7cc0e06)

>[!IMPORTANT]
>
>Die Server-, Report Server- und Client-Komponenten werden aktualisiert, um unter 64-Bit-Windows-Betriebssystemen ausgeführt zu werden.

## Serveraktualisierung {#section-7845393f76214aa7ad53ac4b2cca9e5b}

Führen Sie die folgenden Schritte aus, um die **[!UICONTROL Server v6.1]** Komponenten:

1. Verwenden der **[!UICONTROL Software and Docs]** Profil, öffnen Sie die **[!UICONTROL Start Here]** Arbeitsbereich und laden Sie alle erforderlichen Serverpakete in einen lokalen Ordner herunter.

   * Download **[!UICONTROL Server Packages]** \ **[!UICONTROL v6.1]** Ordner komprimieren und alle Dateien extrahieren.

      Das Serverpaket umfasst **[!UICONTROL Lookup]** und **[!UICONTROL Profile]** Ordner mit **[!UICONTROL Base]** und **[!UICONTROL Transform]** Profile, um den Server zu aktualisieren.

      * Laden Sie die **[!UICONTROL Profiles]** Ordner.
      * Laden Sie die **[!UICONTROL Lookup]** Ordner.
      * Laden Sie die **[!UICONTROL Report Server]** \ **[!UICONTROL v6.1]** Paket.
      * Herunterladen zusätzlicher **[!UICONTROL Sensor]**, **[!UICONTROL Documentation]** und **[!UICONTROL Dashboard]** Dateien nach Bedarf für Ihr System.

1. Stoppen Sie die **[!UICONTROL Adobe Insight Server]** Dienst.

   ![](assets/install_server_download1.png)

1. Aus dem heruntergeladenen **[!UICONTROL Server]** package:

   1. Ersetzen Sie die [!DNL Server\Bin] Ordner zum Aktualisieren [!DNL InsightServer64.exe] und unterstützenden Dateien.

   1. Ersetzen Sie die [!DNL Server\Profiles] Ordner. Sie können alle Dateien überschreiben.
   1. Aktualisieren Sie die [!DNL Server\Lookups] Ordner. Sie möchten die neu heruntergeladenen Dateien zu den benutzerdefinierten Dateien hinzufügen, die sich bereits im Ordner befinden.
   1. Ersetzen Sie die [!DNL Server\Software] Ordner, der aktualisiert werden soll [!DNL Insight.exe] und [!DNL ReportServer.exe]
   1. Aktualisieren Sie die [!DNL Server\Scripts] Ordner, der aktualisiert werden soll [!DNL TnTSend.exe].

1. Wenn Sie **[!UICONTROL DeviceAtlas]**, müssen Sie [Bundle aktualisieren](/help/home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-deviceatlas-update.md) im [!DNL Server\Lookups] Ordner.

1. Konfigurieren Sie die [!DNL Profile.cfg] -Datei, um sicherzustellen, dass der Vektor aktualisiert wird, um die Anzahl der Elemente für jedes Profil widerzuspiegeln.

   Um beispielsweise die **[!UICONTROL Predictive Analytics]** Profil verwenden, müssen Sie diese Einstellung aktualisieren.

   ```
   Directories = vector: 5 items
       0 = string: Base\\
       1 = string: Geography\\
       2 = string: Predictive Analytics\\
       3 = string: Adobe SC\\
       4 = string: Profile Name\\
   ```

1. Konfigurieren und speichern Sie die Datei PAServer.cfg für die Funktion Predictive Analytics .

   Wenn Sie Predictive Analytics-Aufträge an die Server senden möchten, müssen Sie die [!DNL Server > Predictive Analytics > Dataset > PAServer.cfg] -Datei zum Verwalten von serverseitigen Clustering-Übermittlungen.

   Das benutzerdefinierte Profil sollte die Einstellungen aus dem Predictive Analytics-Konfigurationsprofil übernehmen, damit Sie die [!DNL PAServer.cfg] -Datei basierend auf der Implementierung Ihrer Site.

1. Definieren Sie die **[!UICONTROL Log Source ID]**.

   Die **[!UICONTROL Recording of Rows per Log Source]** wurde hinzugefügt in **[!UICONTROL v6.04]** und definiert im benutzerdefinierten Profil [!DNL Log Processing.cfg] Datei durch Hinzufügen eines eindeutigen Namens **[!UICONTROL Log Source ID]**.

   ```
   Log Processing.cfg
   Log Source ID = string: <Name your ID Here>
   ```

   Wenn Sie die Protokollquellen-ID nicht definiert haben, erhalten Sie den folgenden Fehler:

   ```
   Missing Log Source ID in log processing.cfg.
   Log Source ID must be defined for all log sources.
   ```

1. Da die [!DNL EventMessages.dll] aktualisiert wurde, müssen Sie die Registrierung aufheben und dann die **[!UICONTROL Adobe Insight Server]** im Cluster.

   * [!DNL InsightServer64.exe /unregserver]
   * [!DNL InsightServer64.exe /regserver]

1. Starten Sie die **[!UICONTROL Adobe Insight Server]** -Dienst im gesamten Cluster.

Die Serverinstallation ist jetzt abgeschlossen.

## Aktualisierung des Report Servers {#section-afd9560a446242e9b06490e5f98aaaec}

>[!IMPORTANT]
>
>Vor der Aktualisierung auf **[!UICONTROL Report Server v6.1]**, müssen Sie zunächst auf **[!UICONTROL Server v6.1]**.

1. Verwenden der **[!UICONTROL Software and Docs]** Profil, herunterladen **[!UICONTROL v6.1]** von **[!UICONTROL Report Server]** in einen lokalen Ordner speichern.

1. Kopieren **[!UICONTROL Report Server 6.1]** aus dem heruntergeladenen Paket und ersetzen Sie die Profilpakete.

   >[!NOTE]
   >
   >Die [!DNL Insight.zbin] in der Datei [!DNL install] -Ordner ist eine Sicherungsdatei, die für die Lokalisierung verwendet wird und im [!DNL install] Verzeichnis. Diese Datei oder andere [!DNL .zbin] -Dateien werden abhängig von den beim Starten übergebenen Befehlszeileneinstellungen verwendet.

1. (Optional) Data Workbench unterstützt derzeit Englisch (-en-us) und Chinesisch (-zh-cn). Sie müssen eine Schriftart festlegen, um Einzel- und Doppelbyte-Zeichen zu unterstützen:

   ```
   Report Server.cfg - Add Fonts
      Fonts = vector: 2 items
      0 = string: SimSun
      1 = string: Arial
   ```

   Außerdem müssen die aufgelisteten Schriftarten auf dem Windows-Betriebssystem installiert sein.

1. Konfigurieren [!DNL Report Server v6.1] für die Lokalisierung.

   1. Stoppen Sie die **[!UICONTROL Adobe Insight Report Server]** Dienst.
   1. Starten Sie eine Eingabeaufforderung als &quot;Administrator&quot;.
   1. Navigieren zum Report Server [!DNL install] Ordner.
   1. Löschen Sie den Report Server-Dienst mit dem folgenden Befehl:

      ```
      ReportServer.exe /unregserver
      ```

   1. Starten Sie den Dienst basierend auf den Spracheinstellungen:

      ```
      ReportServer.exe -RegServer -Locale -en-us (English)
      ReportServer.exe -RegServer -Locale -zh-cn (Simplified Chinese)
      ```

1. Um sicherzustellen, dass Report Server mit den richtigen Einstellungen ausgeführt wird, öffnen Sie **[!UICONTROL Windows Service Manager]** und Rechtsklick **[!UICONTROL Adobe Insight Report Server - Properties]**. Der Pfad zur ausführbaren Datei zeigt die aktualisierten Befehlszeileneinstellungen an.

Die Installation des Berichtsservers ist jetzt abgeschlossen.

## Client Upgrade {#section-c896e57ecd2847afb18f4d8ef7cc0e06}

>[!IMPORTANT]
>
>Vor der Aktualisierung auf **[!UICONTROL Client v6.1]** muss der Administrator zunächst auf **[!UICONTROL Insight Server v6.1.]**

1. Launch [!DNL Insight.exe] jedoch keine Verbindung zu Profilen herstellen.
1. Bearbeiten Sie die [!DNL Insight.cfg] -Datei.

   ```
   Update Software = bool: true
   ```

1. Stellen Sie eine Verbindung zu Ihrem Profil her.

   Lassen Sie zu, dass der Client mit dem Server synchronisiert wird, und Ihr Client wird mit den neuesten v6.1-Clientprofilen, ausführbaren Dateien und Konfigurationsdateien aktualisiert.

   >[!NOTE]
   >
   >Die [!DNL Insight.zbin] in der Datei [!DNL install] -Ordner ist eine Sicherungsdatei, die für die Lokalisierung verwendet wird und vorhanden sein muss. Diese Datei oder andere [!DNL .zbin] -Dateien werden abhängig von den beim Starten übergebenen Befehlszeileneinstellungen verwendet.

   Siehe [Einrichten lokalisierter Sprachen](../../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-localized-ime.md#concept-86d7602cd6ec416b8d4a518f325e001e) , um [!DNL insight.zbin] -Datei, die für lokalisierte Einstellungen erforderlich ist.

**Zusätzliche Client-Einstellungen**

Vor der Konfiguration [!DNL Insight.exe] und unterstützenden Dateien, müssen Sie die Clientanwendung beenden.

So installieren Sie Vereinfachtes Chinesisch:

1. Erstellen Sie einen Tastaturbefehl, der die Befehlszeileneinstellung an die [!DNL Insight.exe] -Datei.

   ```
   Insight.exe -zh-cn
   ```

1. Konfigurieren [!DNL Insight.cfg] um Einzel- und Doppelbyte-Schriftzeichen zu unterstützen.

   Data Workbench unterstützt derzeit sowohl Englisch als auch Vereinfachtes Chinesisch. Sie können Schriftarten auswählen, um beide Sprachen zu unterstützen:

   ```
   Fonts = vector: 2 items
   0 = string: SimSun
   1 = string: Arial
   ```

   Außerdem müssen die angeforderten Schriftarten auf dem Windows-Betriebssystem installiert sein.

1. Starten Sie den von Ihnen erstellten Tastaturbefehl zum Synchronisieren von Profilen und die aktualisierte . [!DNL zbin] -Datei.

Verwenden des Eingabemethoden-Editors (IME).

Mit IME können Sie internationale Zeichen eingeben.

1. Aktualisieren Sie die [!DNL Insight.cfg] Datei mit den folgenden Einstellungen:

   ```
   Localized IME = bool: true
   ```

1. Starten Sie den von Ihnen erstellten Tastaturbefehl zum Synchronisieren von Profilen und die aktualisierte [!DNL .zbin] -Datei.

Die Client-Installation ist jetzt abgeschlossen.
