---
description: Führen Sie die folgenden Schritte aus, um von Ihrer Data Workbench v6.0x-Installation auf Data Workbench v6.1 zu aktualisieren.
solution: Analytics
title: Aktualisierung von Data Workbench 6.0 auf 6.1
topic: Data workbench
uuid: 4671c2bf-06ab-49c4-8dd1-24115facd83b
translation-type: tm+mt
source-git-commit: cb3ca4b3b993f5f04f6b6cee25850600ff3d8986

---


# Aktualisierung von Data Workbench 6.0 auf 6.1{#data-workbench-to-upgrade}

Führen Sie die folgenden Schritte aus, um von Ihrer Data Workbench v6.0x-Installation auf Data Workbench v6.1 zu aktualisieren.

**Schritt 1**: [Serveraktualisierung](../../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-6-0-to-6-1-upgrade.md#section-7845393f76214aa7ad53ac4b2cca9e5b)

**Schritt 2**: Aktualisierung [des Berichtsservers](../../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-6-0-to-6-1-upgrade.md#section-afd9560a446242e9b06490e5f98aaaec)

**Schritt 3**: [Client-Aktualisierung](../../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-6-0-to-6-1-upgrade.md#section-c896e57ecd2847afb18f4d8ef7cc0e06)

>[!IMPORTANT]
>
>Server-, Berichtsserver- und Client-Komponenten werden aktualisiert, um auf 64-Bit-Windows-Betriebssystemen ausgeführt zu werden.

## Serveraktualisierung {#section-7845393f76214aa7ad53ac4b2cca9e5b}

Führen Sie die folgenden Schritte aus, um die **[!UICONTROL Server v6.1]** Komponenten zu aktualisieren:

1. Öffnen Sie mithilfe des **[!UICONTROL Software and Docs]** Profils den **[!UICONTROL Start Here]** Arbeitsbereich und laden Sie alle erforderlichen Serverpakete in einen lokalen Ordner herunter.

   * Laden Sie **[!UICONTROL Server Packages]** \ **[!UICONTROL v6.1]** ZIP-Ordner herunter und extrahieren Sie alle Dateien.

      Das Serverpaket enthält Ordner **[!UICONTROL Lookup]** und **[!UICONTROL Profile]** Ordner mit **[!UICONTROL Base]** und **[!UICONTROL Transform]** Profilen, um den Server zu aktualisieren.

      * Laden Sie die **[!UICONTROL Profiles]** Ordner herunter.
      * Laden Sie die **[!UICONTROL Lookup]** Ordner herunter.
      * Laden Sie das **[!UICONTROL Report Server]** \ **[!UICONTROL v6.1]** Paket herunter.
      * Laden Sie nach Bedarf weitere **[!UICONTROL Sensor]**-, **[!UICONTROL Documentation]**- und **[!UICONTROL Dashboard]** -Dateien für Ihr System herunter.

1. Beenden Sie den **[!UICONTROL Adobe Insight Server]** Dienst.

   ![](assets/install_server_download1.png)

1. Aus dem heruntergeladenen **[!UICONTROL Server]** Paket:

   1. Ersetzen Sie den [!DNL Server\Bin] Ordner, um die [!DNL InsightServer64.exe] unterstützenden Dateien zu aktualisieren.

   1. Ersetzen Sie den [!DNL Server\Profiles] Ordner. Sie können alle Dateien überschreiben.
   1. Aktualisieren Sie den [!DNL Server\Lookups] Ordner. Sie möchten die neu heruntergeladenen Dateien den benutzerdefinierten Dateien hinzufügen, die sich bereits im Ordner befinden.
   1. Ersetzen Sie den zu aktualisierenden [!DNL Server\Software] Ordner [!DNL Insight.exe] und [!DNL ReportServer.exe]
   1. Aktualisieren Sie den zu aktualisierenden [!DNL Server\Scripts] Ordner [!DNL TnTSend.exe].

1. Wenn Sie **[!UICONTROL DeviceAtlas]** das Bundle [im](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/trans-config-file/c-deviceatlas-update.html) Ordner [!DNL Server\Lookups] aktualisieren, müssen Sie es aktualisieren.

1. Konfigurieren Sie die [!DNL Profile.cfg] Datei, um sicherzustellen, dass der Vektor aktualisiert wird, um die Anzahl der Elemente für jedes Profil widerzuspiegeln.

   Um beispielsweise das **[!UICONTROL Predictive Analytics]** Profil zu aktivieren, müssen Sie diese Einstellung aktualisieren.

   ```
   Directories = vector: 5 items 
       0 = string: Base\\ 
       1 = string: Geography\\ 
       2 = string: Predictive Analytics\\ 
       3 = string: Adobe SC\\ 
       4 = string: Profile Name\\
   ```

1. Konfigurieren und speichern Sie die Datei PAServer.cfg für die Funktion Predictive Analytics.

   Wenn Sie Predictive Analytics-Aufträge an die Server senden möchten, müssen Sie die [!DNL Server > Predictive Analytics > Dataset > PAServer.cfg] Datei für die Verwaltung serverseitiger Cluster-Übermittlungen konfigurieren.

   Das benutzerdefinierte Profil sollte die Einstellungen aus dem Predictive Analytics-Konfigurationsprofil übernehmen, sodass Sie die [!DNL PAServer.cfg] Datei basierend auf der Implementierung Ihrer Site konfigurieren und speichern können.

1. Define the **[!UICONTROL Log Source ID]**.

   Die **[!UICONTROL Recording of Rows per Log Source]** Datei wurde in der **[!UICONTROL v6.04]** Datei des benutzerdefinierten Profils hinzugefügt [!DNL Log Processing.cfg] und durch Hinzufügen eines eindeutigen Namens definiert **[!UICONTROL Log Source ID]**.

   ```
   Log Processing.cfg
   Log Source ID = string: <Name your ID Here>
   ```

   Wenn Sie die Protokollquellen-ID nicht definiert haben, erhalten Sie die folgende Fehlermeldung:

   ```
   Missing Log Source ID in log processing.cfg.  
   Log Source ID must be defined for all log sources.
   ```

1. Da das [!DNL EventMessages.dll] Update aktualisiert wurde, müssen Sie die Registrierung aufheben und dann die Registrierung im **[!UICONTROL Adobe Insight Server]** gesamten Cluster durchführen.

   * [!DNL InsightServer64.exe /unregserver]
   * [!DNL InsightServer64.exe /regserver]

1. Starten Sie den **[!UICONTROL Adobe Insight Server]** Dienst im Cluster.

Die Serverinstallation ist jetzt abgeschlossen.

## Aktualisierung des Berichtsservers {#section-afd9560a446242e9b06490e5f98aaaec}

>[!IMPORTANT]
>
>Vor der Aktualisierung auf müssen **[!UICONTROL Report Server v6.1]** Sie zunächst auf **[!UICONTROL Server v6.1]**.

1. Laden Sie das **[!UICONTROL Software and Docs]** Profil **[!UICONTROL v6.1]** aus dem **[!UICONTROL Report Server]** Paket in einen lokalen Ordner herunter.

1. Kopieren Sie **[!UICONTROL Report Server 6.1]** aus dem heruntergeladenen Paket und ersetzen Sie die Profilpakete.

   >[!NOTE]
   >
   >Die [!DNL Insight.zbin] Datei im [!DNL install] Ordner ist eine Sicherungsdatei, die für die Lokalisierung verwendet wird und im [!DNL install] Ordner vorhanden sein muss. Diese oder andere [!DNL .zbin] Dateien werden je nach den beim Starten übergebenen Befehlszeileneinstellungen verwendet.

1. (Optional) Data Workbench unterstützt derzeit Englisch (-en-us) und Chinesisch (-zh-cn). Sie müssen eine Schriftart zur Unterstützung von Einzel- und Doppelbyte-Zeichen festlegen:

   ```
   Report Server.cfg - Add Fonts 
      Fonts = vector: 2 items  
      0 = string: SimSun  
      1 = string: Arial 
   ```

   Das Windows-Betriebssystem muss auch die aufgelisteten Schriftarten installiert haben.

1. Konfigurieren [!DNL Report Server v6.1] für die Lokalisierung.

   1. Beenden Sie den **[!UICONTROL Adobe Insight Report Server]** Dienst.
   1. Starten Sie eine Eingabeaufforderung als &quot;Administrator&quot;.
   1. Navigieren Sie zum [!DNL install] Ordner &quot;Report Server&quot;.
   1. Löschen Sie den Report Server-Dienst mit dem folgenden Befehl:

      ```
      ReportServer.exe /unregserver
      ```

   1. Starten Sie den Dienst auf Grundlage der Spracheinstellungen:

      ```
      ReportServer.exe -RegServer -Locale -en-us (English)  
      ReportServer.exe -RegServer -Locale -zh-cn (Simplified Chinese)
      ```

1. Um sicherzustellen, dass Report Server mit den richtigen Einstellungen ausgeführt wird, öffnen Sie den Bericht **[!UICONTROL Windows Service Manager]** und klicken Sie mit der rechten Maustaste **[!UICONTROL Adobe Insight Report Server - Properties]**. Der Pfad zur ausführbaren Datei zeigt die aktualisierten Befehlszeileneinstellungen an.

Die Installation des Berichtsservers ist jetzt abgeschlossen.

## Client-Aktualisierung {#section-c896e57ecd2847afb18f4d8ef7cc0e06}

>[!IMPORTANT]
>
>Vor der Aktualisierung auf **[!UICONTROL Client v6.1]** muss der Administrator zuerst auf **[!UICONTROL Insight Server v6.1.]**

1. Starten Sie, [!DNL Insight.exe] aber stellen Sie keine Verbindung zu Profilen her.
1. Bearbeiten Sie die [!DNL Insight.cfg] Datei.

   ```
   Update Software = bool: true
   ```

1. Stellen Sie eine Verbindung zu Ihrem Profil her.

   Erlauben Sie dem Client die Synchronisierung mit dem Server, und Ihr Client wird mit den neuesten v6.1-Clientprofilen, ausführbaren Dateien und Konfigurationsdateien aktualisiert.

   >[!NOTE]
   >
   >Die [!DNL Insight.zbin] Datei im [!DNL install] Ordner ist eine Sicherungsdatei, die für die Lokalisierung verwendet wird und vorhanden sein muss. Diese oder andere [!DNL .zbin] Dateien werden je nach den beim Starten übergebenen Befehlszeileneinstellungen verwendet.

   Siehe [Einrichten lokalisierter Sprachen](../../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-localized-ime.md#concept-86d7602cd6ec416b8d4a518f325e001e) , um eine für lokalisierte Einstellungen erforderliche [!DNL insight.zbin] Datei hinzuzufügen.

**Zusätzliche Client-Einstellungen**

Bevor Sie Dateien konfigurieren [!DNL Insight.exe] und unterstützen, müssen Sie die Clientanwendung beenden.

So installieren Sie vereinfachtes Chinesisch:

1. Erstellen Sie eine Verknüpfung, die die Befehlszeileneinstellung an die [!DNL Insight.exe] Datei übergibt.

   ```
   Insight.exe -zh-cn
   ```

1. Konfigurieren Sie [!DNL Insight.cfg] die Unterstützung von Einzel- und Doppelbyte-Schriftzeichen.

   Data Workbench unterstützt derzeit sowohl Englisch als auch vereinfachtes Chinesisch. Sie können Schriftarten auswählen, um beide Sprachen zu unterstützen:

   ```
   Fonts = vector: 2 items 
   0 = string: SimSun 
   1 = string: Arial 
   ```

   Das Windows-Betriebssystem muss auch die angeforderten Schriftarten installiert haben.

1. Starten Sie den von Ihnen erstellten Tastaturbefehl zum Synchronisieren von Profilen und der aktualisierten . [!DNL zbin] Datei.

Zum Verwenden des Eingabemethoden-Editors (IME).

Mit IME können Sie internationale Zeichen eingeben.

1. Aktualisieren Sie die [!DNL Insight.cfg] Datei mit den folgenden Einstellungen:

   ```
   Localized IME = bool: true
   ```

1. Starten Sie den von Ihnen erstellten Tastaturbefehl zum Synchronisieren von Profilen und der aktualisierten [!DNL .zbin] Datei.

Die Clientinstallation ist jetzt abgeschlossen.
