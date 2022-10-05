---
description: Führen Sie die folgenden Schritte aus, um auf Data Workbench v6.4 zu aktualisieren.
title: Upgrade von Version 6.3 auf 6.4
uuid: 2461c1ab-cf99-4fb5-b431-d7062df7a53d
exl-id: 540deb86-2463-4820-b67a-a32d68b4346e
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '426'
ht-degree: 0%

---

# Upgrade von Version 6.3 auf 6.4{#upgrading-to}

{{eol}}

Führen Sie die folgenden Schritte aus, um auf Data Workbench v6.4 zu aktualisieren.

## Upgrade-Anforderungen und Recommendations {#section-8704a9ac358246cd81233dd0982d534f}

Befolgen Sie diese Anforderungen und Empfehlungen bei der Aktualisierung auf Data Workbench 6.4.

>[!IMPORTANT]
>
>Es wird empfohlen, die neu installierten Standardkonfigurationsdateien zu verwenden und anzupassen, anstatt Dateien aus einer vorherigen Installation zu verschieben - mit folgenden Ausnahmen:

* **Hinzufügen** ***Ausgeschlossene Prozesse*** für *MS System Center Endpoint Protection in Windows 2012-Servern* für die folgenden ausführbaren Dateien:

   * **[!DNL InsightServer64.exe]**
   * **[!DNL ReportServer.exe]**
   * **[!DNL ExportIntegration.exe]**

   Dadurch werden die Berechtigungen der Zulassungsliste für diese miteinander verbundenen ausführbaren Dateien aktiviert.

* **Aktualisieren Sie die *Trust_ca_cert.pem* Zertifikat auf den Servern**.
* **Neuorganisation von Attributionsprofilen**.

   * Die *Attribution* Ordner wurde in ***Attribution - Premium*** (in der Standardinstallation unter *Profile*\*Attribution - Premium*).

   * Die *Premium* Das Profil wurde entfernt und der Arbeitsbereich wurde in das neue ***Attribution - Premium*** Ordner.

* **Aktualisieren *Attribution-Premium* settings**. Wenn Sie benutzerdefinierte Profile mit Parametereinstellungen haben, die die Standardeinstellung überschreiben *Adobe SC* Profil erstellen, müssen Sie die benutzerdefinierten Felder in diesen Konfigurationsdateien aktualisieren:

   * **[!DNL Decoding Instructions.cfg]**
   * **[!DNL SC Fields.cfg]**

* Aufgrund dieser Umstrukturierung sollten Sie die alte *Attribution* und *Premium* Ordner von Ihrer Serverinstallation.

   **Diese Einstellungen ändern**

   ```
   Profile = profileInfo:  
     Active = bool: true 
     Directories = vector: 6 items 
       0 = string: Base\\ 
       1 = string: Geography\\ 
       2 = string: Predictive Analytics\\ 
       3 = string: Adobe SC\\ 
   
       4 = string: Attribution\\ 
       5 = string: Premium\\
   ```

   zu diesen Einstellungen hinzufügen:

   ```
   Profile = profileInfo:  
     Active = bool: true 
     Directories = vector: 5 items 
       0 = string: Base\\ 
       1 = string: Geography\\ 
       2 = string: Predictive Analytics\\ 
       3 = string: Adobe SC\
       4 = string: Attribution - Premium\\
   ```

* **Aktualisieren benutzerdefinierter Meta.cfg-Dateien** (falls erforderlich).

   Die **[!DNL Meta.cfg]** Dateien in **[!DNL Base\Context and AdobeSC\Context]** -Ordner wurden in dieser Version aktualisiert.

   Wenn Sie die **meta.cfg** während der Installation zu speichern, muss Ihre Profilkopie mit diesen Parametern und der **Metadatenvektor** entsprechend eingegeben wurde:

   ```
   94 = meta: 
     path = string: SegmentExport:CRS Configuration/CRS Attributes 
     acceptable children = vector: 1 items 
       0 = Template: 
         name = string: CRS Attributes 
         value = CRSAttributeConfiguration: 
           Attribute Name = string: 
           Attribute Type(int,string) = string: 
           Field Name = string: 
   
   95 = meta: 
     path = string: SegmentExportQuery:CRS Configuration/Report Suite 
     acceptable children = vector: 1 items 
       0 = Template 
         name = string: Add Report Suite 
         value = string:
   ```

* **Festlegen von Report Server-Berechtigungen** , um Microsoft Excel-Berichte auf Windows 2012-Servern zu erstellen.

   1. Legen Sie die Berechtigung für den Stammordner fest (**[!DNL E:\ReportServer\]**) zu *Alle = vollständige Kontrolle*.

   1. Erstellen Sie die folgenden Ordner mit den entsprechenden Berechtigungen:

      ```
      C:\Windows\SysWOW64\config\systemprofile\AppData\Local\Microsoft\Windows\INetCac‌he 
      C:\Windows\System32\config\systemprofile\AppData\Local\Microsoft\Windows\INetCac‌he 
      C:\Windows\System32\config\systemprofile\Desktop 
      C:\Windows\SysWOW64\config\systemprofile\Desktop
      ```

      >[!NOTE]
      >
      >Wenn Sie Report Server unter Windows Server 2012 ausführen, muss Windows Server 2012 R2 installiert sein.

   1. Weisen Sie für diese Ordner &quot;SYSTEM&quot;als Eigentümer zu.

* **Fügen Sie dem Report Server Schriftarten hinzu.** Im **[!DNL ReportServer.cfg]**Datei, fügen Sie diese Schriftarten hinzu (für alle Sprachen):

   ```
   Fonts = vector: 3 items 
     0 = string: Arial 
     1 = string: SimSun 
     2 = string: MS Mincho
   ```

* **Aktualisieren Sie Ihre Version von Microsoft Excel ** (falls erforderlich).

   Mit der Veröffentlichung von Data Workbench 6.4 wurde die Unterstützung für Excel 2007 eingestellt. Da die Data Workbench nur unter Microsoft Windows für die 64-Bit-Architektur ausgeführt wird, wird empfohlen, auch eine 64-Bit-Version von Microsoft Excel zu installieren.

* **64-Bit-Architektur** erforderlich für Workstation-Installation (Client).
* **Ausführen des Workstation-Einrichtungs-Assistenten**.

   Installieren Sie die neue Version der Workstation (Client), indem Sie sie herunterladen und starten. ***InsightSetup.exe*** und durch die Einrichtungsanweisungen gehen. Der Setup-Assistent installiert Ihre Dateien standardmäßig an einem neuen Speicherort:

   Die Programmdateien werden jetzt standardmäßig wie folgt gespeichert:

   ```
   C:\Program Files\Adobe\Adobe Analytics\Data Workbench
   ```

   Datendateien (Profile, Zertifikate, Ablaufverfolgungsprotokolle und Benutzerdateien) werden jetzt standardmäßig wie folgt gespeichert:

   ```
   C:\Users\<username>\AppData\Local\Adobe\Adobe Analytics\Data Workbench\
   ```

* **Schriftarten zur Workstation hinzufügen**.

   Im **[!DNL Insight.cfg]** hinzufügen, fügen Sie die folgenden Schriftarten hinzu (für alle Sprachen):

   ```
   Fonts = vector: 3 items 
     0 = string: Arial 
     1 = string: SimSun 
     2 = string: MS Mincho
   ```
