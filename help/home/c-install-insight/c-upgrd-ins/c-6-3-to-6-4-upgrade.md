---
description: Führen Sie die folgenden Schritte aus, um auf Data Workbench v6.4 zu aktualisieren.
title: Upgrade von 6.3 auf 6.4
uuid: 2461c1ab-cf99-4fb5-b431-d7062df7a53d
translation-type: tm+mt
source-git-commit: 72761a57e4bb9f230581b2cd37bff04ba7be8e37

---


# Upgrading 6.3 to 6.4{#upgrading-to}

Führen Sie die folgenden Schritte aus, um auf Data Workbench v6.4 zu aktualisieren.

## Upgrade-Anforderungen und Empfehlungen {#section-8704a9ac358246cd81233dd0982d534f}

Befolgen Sie diese Anforderungen und Empfehlungen bei der Aktualisierung auf Data Workbench 6.4.

>[!IMPORTANT]
>
>Es wird empfohlen, die neu installierten Standardkonfigurationsdateien zu verwenden und sie anzupassen, anstatt Dateien aus einer vorherigen Installation zu verschieben - mit folgenden Ausnahmen:

* **Fügen Sie** ***Ausgeschlossene Prozesse*** für den *MS System Center-Endpunktschutz in Windows 2012-Servern* für die folgenden ausführbaren Dateien hinzu:

   * **[!DNL InsightServer64.exe]**
   * **[!DNL ReportServer.exe]**
   * **[!DNL ExportIntegration.exe]**
   Dies erlaubt die Berechtigung &quot;Weiße Liste&quot;für diese miteinander verbundenen ausführbaren Dateien.

* **Aktualisieren Sie das *Trust_ca_cert.pem*-Zertifikat auf den Servern**.
* **Reorganisation der Zuordnungsprofile**.

   * Der Ordner *Attribution* wurde in ***Attribution - Premium*** umbenannt (in der Standardinstallation unter *Profiles*\*Attribution - Premium* enthalten).

   * Das *Premium* -Profil wurde entfernt und der Arbeitsbereich wurde in den neuen Ordner ***Attribution - Premium*** verschoben.

* **Aktualisieren Sie *die Einstellungen*Attribution-Premium**. Wenn Sie benutzerdefinierte Profile mit Parametereinstellungen haben, die das Standard- *Adobe SC* -Profil außer Kraft setzen, müssen Sie die benutzerdefinierten Felder in den folgenden Konfigurationsdateien aktualisieren:

   * **[!DNL Decoding Instructions.cfg]**
   * **[!DNL SC Fields.cfg]**

* Aufgrund dieser Neuorganisation sollten Sie die alten Ordner *Attribution* und *Premium* aus der Serverinstallation entfernen.

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

* **Aktualisieren Sie benutzerdefinierte Meta.cfg-Dateien** (falls erforderlich).

   Die **[!DNL Meta.cfg]** Dateien in **[!DNL Base\Context and AdobeSC\Context]** Ordnern wurden in dieser Version aktualisiert.

   Wenn Sie die Datei &quot; **meta.cfg** &quot;während der Installation außer Kraft setzen, muss Ihre Profilkopie mit den folgenden Parametern aktualisiert werden und der **Metadatenvektor** entsprechend eingegeben werden:

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

* **Legen Sie Report Server-Berechtigungen** zum Generieren von Microsoft Excel-Berichten auf Windows 2012-Servern fest.

   1. Legen Sie die Berechtigung für den Stammordner (**[!DNL E:\ReportServer\]**) auf *Alle = vollständige Kontrolle* fest.

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

   1. Weisen Sie &quot;SYSTEM&quot;als Eigentümer für diese Ordner zu.

* **Fügen Sie dem Berichtsserver Schriftarten hinzu.** Fügen Sie in der Datei **[!DNL ReportServer.cfg]**die folgenden Schriftarten hinzu (für alle Sprachen):

   ```
   Fonts = vector: 3 items 
     0 = string: Arial 
     1 = string: SimSun 
     2 = string: MS Mincho
   ```

* **Aktualisieren Sie Ihre Version von Microsoft Excel ** (falls erforderlich).

   Mit der Veröffentlichung von Data Workbench 6.4 wurde die Unterstützung für Excel 2007 eingestellt. Da Data Workbench nur unter Microsoft Windows für die 64-Bit-Architektur ausgeführt wird, wird empfohlen, auch eine 64-Bit-Version von Microsoft Excel zu installieren.

* **64-Bit-Architektur** erforderlich für Workstation-Installation (Client).
* **Führen Sie den Workstation-Setup-Assistenten** aus.

   Installieren Sie die neue Version der Workstation (Client), indem Sie ***InsightSetup.exe*** herunterladen und starten und die Installationsanweisungen durchlaufen. Der Setup-Assistent installiert Ihre Dateien standardmäßig an einem neuen Speicherort:

   Programmdateien werden jetzt standardmäßig gespeichert auf:

   ```
   C:\Program Files\Adobe\Adobe Analytics\Data Workbench
   ```

   Datendateien (Profile, Zertifikate, Ablaufverfolgungsprotokolle und Benutzerdateien) werden jetzt standardmäßig gespeichert auf:

   ```
   C:\Users\<username>\AppData\Local\Adobe\Adobe Analytics\Data Workbench\
   ```

* **Fügen Sie der Workstation** Schriftarten hinzu.

   Fügen Sie der **[!DNL Insight.cfg]** Datei die folgenden Schriftarten hinzu (für alle Sprachen):

   ```
   Fonts = vector: 3 items 
     0 = string: Arial 
     1 = string: SimSun 
     2 = string: MS Mincho
   ```

