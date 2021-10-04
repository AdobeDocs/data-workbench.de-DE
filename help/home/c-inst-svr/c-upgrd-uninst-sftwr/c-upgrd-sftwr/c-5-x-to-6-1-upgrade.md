---
description: Führen Sie diese Schritte aus, um von Ihrer Insight v5.5x-Installation auf Data Workbench v6.1 zu aktualisieren.
title: 'Data Workbench-Upgrade: 5.5 auf 6.1'
uuid: 14e3612e-11a2-402a-9478-904ec55df23c
exl-id: c730f6d5-2171-4d97-a967-509dc2517c86,3f25917b-b929-4e3b-84f0-1a81b30ba641
source-git-commit: b21da6d12175fa8570b1b366049baa9c8e8ea862
workflow-type: tm+mt
source-wordcount: '757'
ht-degree: 1%

---

# Data Workbench-Upgrade: 5.5 auf 6.1{#data-workbench-to-upgrade}

Führen Sie diese Schritte aus, um von Ihrer Insight v5.5x-Installation auf Data Workbench v6.1 zu aktualisieren.

**Schritt 1**:  [Serveraktualisierung](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-5-x-to-6-1-upgrade.md#section-08bd6fe3da8740fcb19688e8cac6f223)

**Schritt 2**:  [Aktualisierung des Report Servers](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-5-x-to-6-1-upgrade.md#section-afd9560a446242e9b06490e5f98aaaec)

**Schritt 3**:  [Client Upgrade](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-5-x-to-6-1-upgrade.md#section-c896e57ecd2847afb18f4d8ef7cc0e06)

>[!IMPORTANT]
>
>Die Server-, Report Server- und Client-Komponenten werden aktualisiert, um unter 64-Bit-Windows-Betriebssystemen ausgeführt zu werden.

## Serveraktualisierung {#section-08bd6fe3da8740fcb19688e8cac6f223}

Führen Sie die folgenden Schritte aus, um die **[!UICONTROL Server v6.1]**-Komponenten zu aktualisieren:

1. Öffnen Sie mithilfe des Profils **[!UICONTROL Software and Docs]** den Arbeitsbereich **[!UICONTROL Start Here]** und laden Sie alle erforderlichen Serverpakete in einen lokalen Ordner herunter.

   * Laden Sie **[!UICONTROL Server Packages]** \ **[!UICONTROL v6.1]** ZIP-Ordner herunter und extrahieren Sie alle Dateien.

      Das Paket **[!UICONTROL Server]** enthält die Ordner **[!UICONTROL Lookup]** und **[!UICONTROL Profile]** mit den Lookup-Dateien **[!UICONTROL Base]** und **[!UICONTROL Transform]**, die hinzugefügt und ersetzt werden sollen, um den Server zu aktualisieren.

   * Laden Sie die neuen Ordner **[!UICONTROL Profiles]** herunter.
   * Laden Sie aktualisierte **[!UICONTROL Lookup]** Ordner herunter.
   * Laden Sie das Paket **[!UICONTROL Report Server]** \ **[!UICONTROL v6.1]** herunter.
   * Laden Sie nach Bedarf weitere **[!UICONTROL Sensor]**-, **[!UICONTROL Documentation]**- und **[!UICONTROL Dashboard]**-Dateien für Ihr System herunter.

1. Beenden Sie den Dienst **[!UICONTROL Adobe Insight Server]**.

   ![](assets/install_server_download1.png)

1. Aus dem heruntergeladenen Paket **[!UICONTROL Server]** :

   1. Ersetzen Sie den Ordner [!DNL Server\Bin] , um die [!DNL InsightServer64.exe] und die unterstützenden Dateien zu aktualisieren.

   1. Ersetzen Sie den Ordner [!DNL Server\Profiles] . Sie können alle Dateien überschreiben.
   1. Aktualisieren Sie den Ordner [!DNL Server\Lookups] . Sie möchten die neu heruntergeladenen Dateien zu den benutzerdefinierten Dateien hinzufügen, die sich bereits im Ordner befinden.
   1. Ersetzen Sie den Ordner [!DNL Server\Software] , um [!DNL Insight.exe] und [!DNL ReportServer.exe] zu aktualisieren.

   1. Aktualisieren Sie den Ordner [!DNL Server\Scripts], um [!DNL TnTSend.exe] zu aktualisieren.

1. Wenn Sie **[!UICONTROL DeviceAtlas]** verwenden, müssen Sie [das Bundle](/help/home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-deviceatlas-update.md) im Ordner [!DNL Server\Lookups] aktualisieren.
1. Legen Sie [!DNL Directories] in der Datei [!DNL Profile.cfg] fest, um sicherzustellen, dass der Vektor aktualisiert wird, um die Anzahl der Elemente für jedes Profil widerzuspiegeln.

   Um beispielsweise das Profil **[!UICONTROL Predictive Analytics]** zu aktivieren, müssen Sie diese Einstellung aktualisieren.

   ```
   Directories = vector: 5 items
       0 = string: Base\\
       1 = string: Geography\\
       2 = string: Predictive Analytics\\
       3 = string: Adobe SC\\
       4 = string: Profile Name\\
   ```

1. Konfigurieren und speichern Sie die Datei [!DNL PAServer.cfg], um die Predictive Analytics-Funktion zu aktualisieren.

   Wenn Sie Predictive Analytics-Aufträge an die Server senden möchten, müssen Sie die Datei [!DNL Server > Predictive Analytics > Dataset > PAServer.cfg] konfigurieren, um serverseitige Clustering-Übermittlungen zu verwalten.

   Das benutzerdefinierte Profil sollte die Einstellungen aus dem Predictive Analytics-Konfigurationsprofil übernehmen, sodass Sie [!DNL PAServer.cfg] basierend auf der Implementierung Ihrer Site konfigurieren und speichern können.

1. Definieren Sie **[!UICONTROL Log Source ID]**.

   Das **[!UICONTROL Recording of Rows per Log Source]** wurde in **[!UICONTROL v6.04]** hinzugefügt und in der [!DNL Log Processing.cfg]-Datei des benutzerdefinierten Profils definiert, indem ein eindeutig benannter **[!UICONTROL Log Source ID]** hinzugefügt wurde.

   ```
   Log Processing.cfg
   Log Source ID = string: <Name your ID Here>
   ```

   Wenn Sie die Protokollquellen-ID nicht definiert haben, erhalten Sie den folgenden Fehler:

   ```
   Missing Log Source ID in log processing.cfg.
   Log Source ID must be defined for all log sources.
   ```

1. Da [!DNL EventMessages.dll] aktualisiert wurde, müssen Sie die Registrierung aufheben und dann die **[!UICONTROL Adobe Insight Server]** im gesamten Cluster registrieren.

   * [!DNL InsightServer64.exe /unregserver]
   * [!DNL InsightServer64.exe /regserver]

1. Starten Sie den Dienst **[!UICONTROL Adobe Insight Server]** im gesamten Cluster.

Die Serverinstallation ist jetzt abgeschlossen.

## Aktualisierung des Report Servers {#section-afd9560a446242e9b06490e5f98aaaec}

>[!IMPORTANT]
>
>Vor der Aktualisierung auf **[!UICONTROL Report Server v6.1]** müssen Sie zunächst auf **[!UICONTROL Server v6.1]** aktualisieren.

1. Laden Sie mithilfe des Profils **[!UICONTROL Software and Docs]** **[!UICONTROL v6.1]** aus dem Paket **[!UICONTROL Report Server]** in einen lokalen Ordner herunter.
1. Kopieren Sie **[!UICONTROL Report Server 6.1]** aus dem heruntergeladenen Paket und ersetzen Sie die Profilpakete.

   >[!NOTE]
   >
   >Die Datei [!DNL Insight.zbin] im Ordner [!DNL install] ist eine Sicherungsdatei, die für die Lokalisierung verwendet wird und im Verzeichnis [!DNL install] vorhanden sein muss. Diese oder andere [!DNL .zbin] Dateien werden je nach den beim Start übergebenen Befehlszeileneinstellungen verwendet.

1. (optional) Ändern Sie die Konfigurationsdatei des Berichtsservers, um Doppelbytezeichen zu unterstützen.

   Data Workbench unterstützt derzeit Englisch (-en-us) und Chinesisch (-zh-cn). Sie müssen eine Schriftart festlegen, um Einzel- und Doppelbyte-Zeichen zu unterstützen:

   ```
   Report Server.cfg - Add Fonts
      Fonts = vector: 2 items
      0 = string: SimSun
      1 = string: Arial
   ```

   Außerdem müssen die aufgelisteten Schriftarten auf dem Windows-Betriebssystem installiert sein.

1. Konfigurieren [!DNL Report Server v6.1].

   1. Beenden Sie den Dienst **[!UICONTROL Adobe Insight Report Server]**.
   1. Starten Sie eine Eingabeaufforderung als &quot;Administrator&quot;.
   1. Navigieren Sie zum Ordner Report Server [!DNL install] .
   1. Löschen Sie den Report Server-Dienst mit dem folgenden Befehl:

      ```
      ReportServer.exe /unregserver
      ```

1. Starten Sie den Dienst entsprechend den Spracheinstellungen:

   ```
   ReportServer.exe -RegServer -Locale -en-us (English)
   ReportServer.exe -RegServer -Locale -zh-cn (Simplified Chinese)
   ```

1. Um sicherzustellen, dass Report Server mit den richtigen Einstellungen ausgeführt wird, öffnen Sie **[!UICONTROL Windows Service Manager]** und klicken Sie mit der rechten Maustaste auf **[!UICONTROL Adobe Insight Report Server - Properties]**. Der Pfad zur ausführbaren Datei zeigt die aktualisierten Befehlszeileneinstellungen an.

Die Installation des Berichtsservers ist jetzt abgeschlossen.

## Client Upgrade {#section-c896e57ecd2847afb18f4d8ef7cc0e06}

>[!IMPORTANT]
>
>Vor der Aktualisierung auf **[!UICONTROL Client v6.1]** muss der Administrator zunächst auf **[!UICONTROL Server v6.1.]** aktualisieren

1. Starten Sie [!DNL Insight.exe], aber stellen Sie keine Verbindung zu Profilen her.
1. Bearbeiten Sie die Datei [!DNL Insight.cfg], um die Software nicht automatisch zu aktualisieren.

   ```
   Update Software = bool: false
   ```

1. Verbinden Sie das Profil **[!UICONTROL Software and Docs]** (Software).
1. Download [!DNL Software\Insight Client\v6.10].
1. (optional) Ändern Sie [!DNL insight.cfg], um Doppelbyte-Zeichen zu unterstützen.

   Data Workbench unterstützt derzeit sowohl Englisch als auch Vereinfachtes Chinesisch. Wählen Sie Schriftarten aus, um beide Sprachen zu unterstützen:

   ```
   Fonts = vector: 2 items
   0 = string: SimSun
   1 = string: Arial
   ```

1. Beenden Sie den Client.
1. Kopieren Sie die Dateien im heruntergeladenen Client-Paket **v6.1** in den Ordner [!DNL Install] .

   >[!NOTE]
   >
   >Die Datei [!DNL Insight.zbin] im Installationsordner ist eine Sicherungsdatei, die für die Lokalisierung verwendet wird und im Installationsverzeichnis vorhanden sein muss. Diese oder andere [!DNL .zbin] Dateien werden je nach den beim Start übergebenen Befehlszeileneinstellungen verwendet.
   >
   >Um beispielsweise vereinfachtes Chinesisch zu starten, erstellen Sie einen Tastaturbefehl, der in der Befehlszeileneinstellung übergeben wird.
   >
   >
   ```
   >Insight.exe -zh-cn
   >```
   >
   >Wenn Sie auf Englisch starten möchten (Standardeinstellung), ist keine Befehlszeilenänderung erforderlich.

1. Starten Sie [!DNL Insight.exe] für Englisch oder den Tastaturbefehl, den Sie für eine andere Sprache erstellt haben.
1. Stellen Sie eine Verbindung zu Ihrem Profil her und lassen Sie zu, dass der Client mit dem Server synchronisiert wird.
1. (Optional) Um IME zu verwenden, nehmen Sie die folgenden Änderungen an der Datei [!DNL Insight.cfg] vor:

   ```
   Localized IME = bool: true
   ```

   Mit dem Eingabemethoden-Editor (IME) können Sie internationale Zeichen eingeben.

1. (Optional) Bearbeiten Sie die [!DNL Insight.cfg]-Datei, um die Software automatisch zu aktualisieren:

   ```
   Update Software = bool: true
   ```

   Siehe Anweisungen zur Implementierung des IME.
1. Starten Sie nach der Profilsynchronisierung erneut neu, um die neueste [!DNL .zbin]-Datei zu verwenden.

Die Client-Installation ist jetzt abgeschlossen.
