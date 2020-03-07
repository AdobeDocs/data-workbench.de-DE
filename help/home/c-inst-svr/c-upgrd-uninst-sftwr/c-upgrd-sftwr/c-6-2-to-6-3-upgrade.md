---
description: Aktualisieren von Serverkomponenten für Data Workbench 6.3
title: DWB Server-Upgrade 6.2 auf 6.3
uuid: e12b6cc1-070e-4bc7-bc64-203d11cfeae9
translation-type: tm+mt
source-git-commit: 25366087936dfa5e31c5921aac400535ec259f2e

---


# DWB Server-Aktualisierung: 6.2 bis 6.3{#dwb-server-upgrade-to}

Aktualisieren von Serverkomponenten für Data Workbench 6.3

**Upgrade-Server**

Wenn Sie benutzerdefinierte Profile haben, die Vorrang vor den im [!DNL Base] Paket bereitgestellten Standarddateien haben, müssen Sie diese benutzerdefinierten Dateien aktualisieren:

* **Aktualisieren Sie die Datei** Meta.cfg ( [!DNL E:\..\Profiles\<your custom profile>\Context\meta.cfg)]um eine aktualisierte Kennwortverschlüsselung für die Dateisystemeinheit (FSU-Server) festzulegen und Einträge für die Namenswertpaare-Transformationen hinzuzufügen, um die [Abfragezeichenfolgengruppierungen](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-2-to-6-3-upgrade.md#concept-42f74911b5714219a359b719badac8e0)zu nutzen.

   1. Öffnen Sie die [!DNL meta.cfg] Datei im FSU.
   1. Ändern Sie den Datentyp für **[!UICONTROL Proxy Password]** von &quot; [!DNL string"] in &quot; [!DNL EncryptedString]&quot;im Abschnitt *Workstation-Konfiguration* .

      ```
      Proxy User Name = string: 
      Proxy Password = EncryptedString:   ( 
      
<i>from Proxy Password = String</i>)Use Address File = bool: true&quot;

    1. Fügen Sie neue Einträge hinzu, um die neuen Seitenwerttransformationen zu aktivieren: *BuildNameValuePair* und *ExtractNameValuePairs*.
    
    Öffnen Sie einen Arbeitsbereich und klicken Sie mit der rechten Maustaste auf **Admin* > **Profile Manager**.
    
    Klicken Sie unter **Context** auf die Datei **meta.cfg** in der Spalte **Base* und dann auf **Make Local**. Klicken Sie in der Spalte Benutzertabelle mit der rechten Maustaste und wählen Sie **Öffnen* > **in Workstation**.
    
    ![](assets/meta_cfg.png)
    
    * Klicken Sie im neuen Fenster auf **metadata** und fügen Sie akzeptable untergeordnete Vorlagen hinzu.
    
    ![](assets/meta_cfg_child.png)
    
    * Öffnen Sie **transformation** und fügen Sie neue Vorlagen hinzu.
    
    ![](assets/meta_cfg_template.png)

* **Aktualisierung für schnelle Zusammenführung**. Fügen Sie den folgenden Konfigurationsdateien Parameter hinzu oder ändern Sie Werte, um die Geschwindigkeitsverbesserungen in Data Workbench während einer Transformation zu nutzen.

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

   * **Protokollverarbeitungsmodus.cfg** ( [!DNL E:\Server\Profiles\<your profile>\Dataset\Log Processing Mode.cfg])

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
   >Um die Verbesserungen der schnellen Zusammenführung zu nutzen, stellen Sie sicher, dass Sie mindestens 8 GB RAM pro DPU haben.

* **Aktualisierung** von Adobe Target mit DWB-Integration. Eine neue Exportdatei ersetzt [!DNL ExportIntegration.exe]die vorhandene [!DNL TnTSend.exe] Datei auf dem Insight Server (`E:\Server\Scripts\TnTSend.exe`). Diese neue Exportdatei unterstützt sowohl die Integration von [Adobe Target](https://www.adobe.com/marketing/target.html) als auch die Koordination mit dem neuen Master-Marketing-Profil (MMP) und [Adobe Audience Manager](https://www.adobe.com/analytics/audience-manager.html).

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
   * Ändern Sie den alten Test- und Target-Export unter [!DNL Server/Profiles/`<your profile>`/Export.]

* **Aktualisieren Sie das Adobe SC-Profil.** Änderungen an der [!DNL Exclude Hit.cfg] Datei erfordern, dass ein Feld in der zugehörigen [!DNL Decoding Instructions.cfg] Datei deklariert wird.

   >[!NOTE]
   >
   >Wenn Ihr Adobe SC-Profil eine angepasste [!DNL Decoding Instructions.cfg] Datei enthält, müssen Sie einen [!DNL DelimitedDecoder] Parameter in Ihre benutzerdefinierte Datei einfügen.

   ```
   0 = DelimitedDecoder: 
      Delimiter = string: \t 
      Fields = vector: x items 
      …  
         5 = string: 
   Changed to: 
   
   5 = string: x-hit_source
   ```

   Durch Hinzufügen des [!DNL DelimitedDecoder] Felds können Sie Funktionsaktualisierungen nutzen und mögliche Probleme bei der Protokollverarbeitung, die sich aus diesen Aktualisierungen ergeben, vermeiden.
