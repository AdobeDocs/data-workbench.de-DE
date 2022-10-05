---
description: Aktualisieren von Serverkomponenten für Data Workbench 6.3
title: DWB-Server-Upgrade 6.2 auf 6.3
uuid: e12b6cc1-070e-4bc7-bc64-203d11cfeae9
exl-id: 5106d9a3-179a-49f1-915a-c03b36ed5257
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '380'
ht-degree: 2%

---

# DWB-Server-Upgrade: 6.2 auf 6.3{#dwb-server-upgrade-to}

{{eol}}

Aktualisieren von Serverkomponenten für Data Workbench 6.3

**Upgrade-Server**

Wenn Sie benutzerdefinierte Profile haben, die Vorrang vor den Standarddateien haben, die in der [!DNL Base] -Paket erstellen, müssen Sie diese benutzerdefinierten Dateien aktualisieren:

* **Aktualisieren der Datei &quot;Meta.cfg&quot;** ( [!DNL E:\..\Profiles\<your custom profile>\Context\meta.cfg)], um eine aktualisierte Kennwortverschlüsselung für die Dateisystemeinheit (FSU-Server) festzulegen und Einträge für die Transformationen des Namenswertpaars hinzuzufügen, um von [Gruppierungen von Abfragezeichenfolgen](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-2-to-6-3-upgrade.md#concept-42f74911b5714219a359b719badac8e0).

   1. Öffnen Sie die [!DNL meta.cfg] -Datei auf der FSU.
   1. Datentyp ändern für **[!UICONTROL Proxy Password]** von &quot; [!DNL string"] zu &quot; [!DNL EncryptedString]&quot; in der *Workstation-Konfiguration* Abschnitt.

      ```
        Proxy User Name = string:
        Proxy Password = EncryptedString:   (
        from Proxy Password = String)
        Use Address File = bool: true
      ```

   1. Fügen Sie neue Einträge hinzu, um die neuen Transformationen des Namenswertpaars zu aktivieren: *BuildNameValuePair* und *ExtractNameValuePairs*.

      Öffnen Sie einen Arbeitsbereich und klicken Sie mit der rechten Maustaste **Admin** > **Profil-Manager**.

      under **Kontext**, klicken Sie auf die **meta.cfg** in der Datei **Basis** und klicken Sie anschließend auf **Lokal machen**. Klicken Sie in der Spalte Benutzertabelle mit der rechten Maustaste auf und wählen Sie **Öffnen** > **in Workstation**.

      ![](assets/meta_cfg.png)

      * Klicken Sie im neuen Fenster auf **Metadaten** und fügen Sie akzeptable untergeordnete Vorlagen hinzu.

         ![](assets/meta_cfg_child.png)

      * Öffnen **Umwandlung** und fügen Sie neue Vorlagen hinzu.

         ![](assets/meta_cfg_template.png)

* **Aktualisierung für schnelle Zusammenführungsverbesserungen**. Fügen Sie Parameter hinzu oder ändern Sie Werte in die folgenden Konfigurationsdateien, um die Geschwindigkeitsverbesserungen bei der Data Workbench während einer Umwandlung zu nutzen.

   * **Communications.cfg** ( [!DNL E:\Server\Components\Communications.cfg])

      ```
      18 = SourceListServer:
          URI = string: /SourceListServer/
          Listing Interval = int: 10 (
      <new>)
      ```

   * **Disk Files.cfg** (at [!DNL E:\Server\Components] und [!DNL E:\Server\Components for Processing Servers])

      ```
      Disk Cache Size (MB) = double: 1024
      <(from double: 256)>
      Disk Cache Read Limit (MB) = double: 768
      <(new)>
      ```

   * **Log Processing Mode.cfg** ( [!DNL E:\Server\Profiles\<your profile>\Dataset\Log Processing Mode.cfg])

      ```
      <(changed)
      Batch Bytes = int: 268435456
      Cloud Bytes = int: 268435456
      Real Time FIFO Bytes = int: 268435456
      ```

      ```
      (
      <new>)
      Cache Bytes = int: 32000000
      Fast Input Decision Ratio = double: 200
      Fast Input FIFO Bytes = int: 268435456
      FIFO Hash Mask = int: 16383
      Fast Merge Buffer Bytes = int: 536870912
      Slow Merge Buffer Bytes = int: 268435456
      Fast Merge Fan In = int: 64
      Key Cache Size Logarithm = int: 21
      Max Seeks = int: 512
      Output Old Buffer Bytes = int: 536870912
      Overflow FIFO Bytes = int: 67108864
      Paused = bool: false
      ```
   >[!NOTE]
   >
   >Um die Vorteile der Fast Merge-Verbesserungen zu nutzen, stellen Sie sicher, dass Sie mindestens 8 GB RAM pro DPU haben.

* **Aktualisierung der Adobe Target-Integration mit DWB-Integration**. eine neue Exportdatei, [!DNL ExportIntegration.exe]ersetzt die vorhandene [!DNL TnTSend.exe] Datei auf dem Insight Server (`E:\Server\Scripts\TnTSend.exe`). Diese neue Exportdatei unterstützt beide [Adobe Target](https://www.adobe.com/marketing/target.html) Integration und Koordinierung mit dem neuen Übergeordnet Marketing Profile (MMP) und [Adobe Audience Manager](https://www.adobe.com/analytics/audience-manager.html).

   Sie müssen die folgenden Befehle für Adobe Target-Exporte aktualisieren.

   `Command = string: TnTSend.exe`

   auf 

   ```
   <filepath>
   Command = string: ExportIntegration.exe
   </filepath>
   ```

   >[!NOTE]
   >
   >Dies betrifft nur Exporte, die vor Version 6.3 erstellt wurden.

   Sie können auch Folgendes versuchen, um den alten Exportvorgang zu verwenden:

   * Erstellen Sie einen neuen Test- und Target-Export auf der Workstation.
   * Ändern Sie den alten Test- und Target-Export, der unter [!DNL Server/Profiles/`<your profile>`/Export.]

* **Aktualisieren Sie das SC-Profil der Adobe.** Änderungen an [!DNL Exclude Hit.cfg] -Datei erfordert, dass ein Feld im zugehörigen [!DNL Decoding Instructions.cfg] -Datei.

   >[!NOTE]
   >
   >Wenn Ihr Adobe SC-Profil eine benutzerdefinierte [!DNL Decoding Instructions.cfg] -Datei, müssen Sie eine [!DNL DelimitedDecoder] -Parameter in Ihre angepasste -Datei.

   ```
   0 = DelimitedDecoder:
      Delimiter = string: \t
      Fields = vector: x items
      …
         5 = string:
   Changed to:
   
   5 = string: x-hit_source
   ```

   Hinzufügen der [!DNL DelimitedDecoder] -Feld können Sie Funktionsaktualisierungen nutzen und mögliche Probleme bei der Protokollverarbeitung vermeiden, die sich aus diesen Aktualisierungen ergeben.
