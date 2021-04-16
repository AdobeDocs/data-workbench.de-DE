---
description: Führen Sie die folgenden Schritte aus, um von Ihrer Data Workbench v6.0x-Installation auf Data Workbench v6.1 zu aktualisieren.
title: 'Data Workbench-Upgrade: 6.0 auf 6.1'
uuid: 4671c2bf-06ab-49c4-8dd1-24115facd83b
exl-id: 559e1942-561c-4270-9670-550177730cdb,2a337d2e-c70e-4f35-a6c2-c3a7f50a0800
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '753'
ht-degree: 1%

---

# Data Workbench-Upgrade: 6.0 auf 6.1{#data-workbench-to-upgrade}

Führen Sie die folgenden Schritte aus, um von Ihrer Data Workbench v6.0x-Installation auf Data Workbench v6.1 zu aktualisieren.

**Schritt 1**:  [Serveraktualisierung](../../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-6-0-to-6-1-upgrade.md#section-7845393f76214aa7ad53ac4b2cca9e5b)

**Schritt 2**:  [Aktualisierung des Berichtsservers](../../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-6-0-to-6-1-upgrade.md#section-afd9560a446242e9b06490e5f98aaaec)

**Schritt 3**:  [Client-Aktualisierung](../../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-6-0-to-6-1-upgrade.md#section-c896e57ecd2847afb18f4d8ef7cc0e06)

>[!IMPORTANT]
>
>Server-, Berichtsserver- und Client-Komponenten werden aktualisiert, um auf 64-Bit-Windows-Betriebssystemen ausgeführt zu werden.

## Serveraktualisierung {#section-7845393f76214aa7ad53ac4b2cca9e5b}

Führen Sie die folgenden Schritte aus, um die Komponenten **[!UICONTROL Server v6.1]** zu aktualisieren:

1. Öffnen Sie mit dem Profil **[!UICONTROL Software and Docs]** den Arbeitsbereich **[!UICONTROL Start Here]** und laden Sie alle erforderlichen Serverpakete in einen lokalen Ordner herunter.

   * Laden Sie die ZIP-Ordner **[!UICONTROL Server Packages]** \ **[!UICONTROL v6.1]** herunter und extrahieren Sie alle Dateien.

      Das Serverpaket enthält die Ordner **[!UICONTROL Lookup]** und **[!UICONTROL Profile]** mit den Profilen **[!UICONTROL Base]** und **[!UICONTROL Transform]**, um den Server zu aktualisieren.

      * Laden Sie die Ordner **[!UICONTROL Profiles]** herunter.
      * Laden Sie die Ordner **[!UICONTROL Lookup]** herunter.
      * Laden Sie das **[!UICONTROL Report Server]** \ **[!UICONTROL v6.1]**-Paket herunter.
      * Laden Sie nach Bedarf weitere **[!UICONTROL Sensor]**-, **[!UICONTROL Documentation]**- und **[!UICONTROL Dashboard]**-Dateien für Ihr System herunter.

1. Beenden Sie den Dienst **[!UICONTROL Adobe Insight Server]**.

   ![](assets/install_server_download1.png)

1. Aus dem heruntergeladenen **[!UICONTROL Server]**-Paket:

   1. Ersetzen Sie den Ordner [!DNL Server\Bin], um die [!DNL InsightServer64.exe]- und die zugehörigen Dateien zu aktualisieren.

   1. Ersetzen Sie den Ordner [!DNL Server\Profiles]. Sie können alle Dateien überschreiben.
   1. Aktualisieren Sie den Ordner [!DNL Server\Lookups]. Sie möchten die neu heruntergeladenen Dateien den benutzerdefinierten Dateien hinzufügen, die sich bereits im Ordner befinden.
   1. Ersetzen Sie den Ordner [!DNL Server\Software], um [!DNL Insight.exe] und [!DNL ReportServer.exe] zu aktualisieren.
   1. Aktualisieren Sie den Ordner [!DNL Server\Scripts], um [!DNL TnTSend.exe] zu aktualisieren.

1. Wenn Sie **[!UICONTROL DeviceAtlas]** verwenden, müssen Sie [das Bundle](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/trans-config-file/c-deviceatlas-update.html) im Ordner [!DNL Server\Lookups] aktualisieren.

1. Konfigurieren Sie die [!DNL Profile.cfg]-Datei, um sicherzustellen, dass der Vektor aktualisiert wird, um die Anzahl der Elemente für jedes Profil widerzuspiegeln.

   Um beispielsweise das Profil **[!UICONTROL Predictive Analytics]** zu aktivieren, müssen Sie diese Einstellung aktualisieren.

   ```
   Directories = vector: 5 items 
       0 = string: Base\\ 
       1 = string: Geography\\ 
       2 = string: Predictive Analytics\\ 
       3 = string: Adobe SC\\ 
       4 = string: Profile Name\\
   ```

1. Konfigurieren und speichern Sie die Datei PAServer.cfg für die Funktion Predictive Analytics.

   Wenn Sie Predictive Analytics-Aufträge an die Server senden möchten, müssen Sie die [!DNL Server > Predictive Analytics > Dataset > PAServer.cfg]-Datei konfigurieren, um serverseitige Clustering-Übermittlungen zu verwalten.

   Das benutzerdefinierte Profil sollte die Einstellungen aus dem Predictive Analytics-Konfigurationsprogramm übernehmen, sodass Sie die [!DNL PAServer.cfg]-Datei entsprechend der Implementierung Ihrer Site konfigurieren und speichern können.

1. Definieren Sie **[!UICONTROL Log Source ID]**.

   Das **[!UICONTROL Recording of Rows per Log Source]** wurde in **[!UICONTROL v6.04]** hinzugefügt und in der [!DNL Log Processing.cfg]-Datei des benutzerspezifischen Profils definiert, indem ein eindeutiger Name **[!UICONTROL Log Source ID]** hinzugefügt wurde.

   ```
   Log Processing.cfg
   Log Source ID = string: <Name your ID Here>
   ```

   Wenn Sie die Protokollquellen-ID nicht definiert haben, erhalten Sie die folgende Fehlermeldung:

   ```
   Missing Log Source ID in log processing.cfg.  
   Log Source ID must be defined for all log sources.
   ```

1. Da das [!DNL EventMessages.dll] aktualisiert wurde, müssen Sie die Registrierung aufheben und dann das **[!UICONTROL Adobe Insight Server]** im Cluster registrieren.

   * [!DNL InsightServer64.exe /unregserver]
   * [!DNL InsightServer64.exe /regserver]

1. Beginn Sie den **[!UICONTROL Adobe Insight Server]**-Dienst im Cluster.

Die Serverinstallation ist jetzt abgeschlossen.

## Report Server-Aktualisierung {#section-afd9560a446242e9b06490e5f98aaaec}

>[!IMPORTANT]
>
>Vor der Aktualisierung auf **[!UICONTROL Report Server v6.1]** müssen Sie zunächst auf **[!UICONTROL Server v6.1]** aktualisieren.

1. Laden Sie das **[!UICONTROL Software and Docs]**-Profil **[!UICONTROL v6.1]** aus dem **[!UICONTROL Report Server]**-Paket in einen lokalen Ordner herunter.

1. Kopieren Sie **[!UICONTROL Report Server 6.1]** aus dem heruntergeladenen Paket und ersetzen Sie die Profil-Pakete.

   >[!NOTE]
   >
   >Die [!DNL Insight.zbin]-Datei im Ordner [!DNL install] ist eine Sicherungsdatei, die für die lokale Anpassung verwendet wird und im Ordner [!DNL install] vorhanden sein muss. Diese oder andere [!DNL .zbin]-Dateien werden je nach den beim Starten übergebenen Befehlszeileneinstellungen verwendet.

1. (Optional) Data Workbench unterstützt derzeit Englisch (-en-us) und Chinesisch (-zh-cn). Sie müssen eine Schriftart zur Unterstützung von Einzel- und Dubletten-Byte-Zeichen festlegen:

   ```
   Report Server.cfg - Add Fonts 
      Fonts = vector: 2 items  
      0 = string: SimSun  
      1 = string: Arial 
   ```

   Das Windows-Betriebssystem muss auch die aufgelisteten Schriftarten installiert haben.

1. [!DNL Report Server v6.1] für die lokale Anpassung konfigurieren.

   1. Beenden Sie den Dienst **[!UICONTROL Adobe Insight Report Server]**.
   1. Starten Sie eine Eingabeaufforderung als &quot;Administrator&quot;.
   1. Navigieren Sie zum Ordner Report Server [!DNL install].
   1. Löschen Sie den Report Server-Dienst mit dem folgenden Befehl:

      ```
      ReportServer.exe /unregserver
      ```

   1. Beginn des Dienstes auf Grundlage der Spracheinstellungen:

      ```
      ReportServer.exe -RegServer -Locale -en-us (English)  
      ReportServer.exe -RegServer -Locale -zh-cn (Simplified Chinese)
      ```

1. Um sicherzustellen, dass Report Server mit den richtigen Einstellungen ausgeführt wird, öffnen Sie **[!UICONTROL Windows Service Manager]** und klicken Sie mit der rechten Maustaste auf **[!UICONTROL Adobe Insight Report Server - Properties]**. Der Pfad zur ausführbaren Datei zeigt die aktualisierten Befehlszeileneinstellungen an.

Die Installation des Berichtsservers ist jetzt abgeschlossen.

## Client-Aktualisierung {#section-c896e57ecd2847afb18f4d8ef7cc0e06}

>[!IMPORTANT]
>
>Vor der Aktualisierung auf **[!UICONTROL Client v6.1]** muss der Administrator zuerst auf **[!UICONTROL Insight Server v6.1.]** aktualisieren

1. Starten Sie [!DNL Insight.exe], aber stellen Sie keine Verbindung zu Profilen her.
1. Bearbeiten Sie die Datei [!DNL Insight.cfg].

   ```
   Update Software = bool: true
   ```

1. Stellen Sie eine Verbindung zu Ihrem Profil her.

   Erlauben Sie dem Client die Synchronisierung mit dem Server, und Ihr Client wird mit den neuesten Profilen, ausführbaren Dateien und Konfigurationsdateien der Version 6.1 aktualisiert.

   >[!NOTE]
   >
   >Die [!DNL Insight.zbin]-Datei im Ordner [!DNL install] ist eine Sicherungsdatei, die für die lokale Anpassung verwendet wird und vorhanden sein muss. Diese oder andere [!DNL .zbin]-Dateien werden je nach den beim Starten übergebenen Befehlszeileneinstellungen verwendet.

   Siehe [Lokalisierte Sprachen einrichten](../../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-localized-ime.md#concept-86d7602cd6ec416b8d4a518f325e001e), um eine [!DNL insight.zbin]-Datei hinzuzufügen, die für lokalisierte Einstellungen erforderlich ist.

**Zusätzliche Client-Einstellungen**

Bevor Sie [!DNL Insight.exe] und unterstützende Dateien konfigurieren, müssen Sie die Clientanwendung beenden.

So installieren Sie vereinfachtes Chinesisch:

1. Erstellen Sie eine Verknüpfung, die die Befehlszeileneinstellung an die Datei [!DNL Insight.exe] übergibt.

   ```
   Insight.exe -zh-cn
   ```

1. Konfigurieren Sie [!DNL Insight.cfg], um Einzel- und Dublette-Byte-Schriftzeichen zu unterstützen.

   Data Workbench unterstützt derzeit sowohl Englisch als auch vereinfachtes Chinesisch. Sie können Schriftarten auswählen, um beide Sprachen zu unterstützen:

   ```
   Fonts = vector: 2 items 
   0 = string: SimSun 
   1 = string: Arial 
   ```

   Das Windows-Betriebssystem muss auch die angeforderten Schriftarten installiert haben.

1. Starten Sie den von Ihnen erstellten Tastaturbefehl zum Synchronisieren von Profilen und den aktualisierten . [!DNL zbin] Datei.

Zum Verwenden des Eingabemethoden-Editors (IME).

Mit IME können Sie internationale Zeichen eingeben.

1. Aktualisieren Sie die Datei [!DNL Insight.cfg] mit den folgenden Einstellungen:

   ```
   Localized IME = bool: true
   ```

1. Starten Sie den Tastaturbefehl, den Sie zum Synchronisieren von Profilen erstellt haben, und die aktualisierte [!DNL .zbin]-Datei.

Die Clientinstallation ist jetzt abgeschlossen.
