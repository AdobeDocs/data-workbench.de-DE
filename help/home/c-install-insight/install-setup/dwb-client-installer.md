---
description: Data Workbench bietet einen Assistenten zum Einrichten der Workstation-Anwendung (Client).
title: Workstation-Einrichtungsassistent
uuid: e2bf6606-e7ba-439f-b50c-118706ab5b7d
translation-type: tm+mt
source-git-commit: 8f5c69541bdd97aefbad3840f75f06846615f222
workflow-type: tm+mt
source-wordcount: '563'
ht-degree: 1%

---


# Workstation-Einrichtungsassistent{#workstation-setup-wizard}

Data Workbench bietet einen Assistenten zum Einrichten der Workstation-Anwendung (Client).

## Installieren der Workstation mit dem Setup-Assistenten {#section-58da9bb6196c46eab3b54146913fdcb8}

Starten Sie die ausführbare Datei des Installationsassistenten und gehen Sie durch jeden Schritt, um das Client-Programm der Workstation zu installieren. Nach der Installation der Workstation können Sie eine Verbindung zu Servern und Profilen herstellen.

1. Klicken Sie mit der Dublette auf die ausführbare Datei des Workstation-Installationsprogramms.
1. Klicken Sie auf **Ja** , um die Installation des Programms unter Windows zuzulassen.
1. Wählen Sie eine **Sprache** für den Einrichtungsassistenten aus.

   Der Assistent wird geöffnet:

   ![](assets/6_4_workstation_wizard.png)

1. Klicken Sie im Dialogfeld &quot;Willkommen beim Setup-Assistenten für Data Workbenchs&quot;auf **Weiter****** .

1. Wählen Sie zum Installieren einer **neuen Installation** oder zum **Aktualisieren oder Reparieren** einer vorhandenen Installation.

   **Die neue Installation** überschreibt alle zuvor installierten Dateien.

   **Aktualisieren** Sie Ihre Workstation auf die neueste Version oder können Sie eine vorhandene Installation reparieren. Data Workbench vergleicht installierte **Insight.exe** -Dateien und führt den Workstation Setup Wizard aus, wenn eine neuere Clientversion verfügbar ist.

1. Installationsspeicherort auswählen:

   **Normalerweise** wird ein Standardordner und ein Standardspeicherort installiert.

   * Programm-Dateien werden standardmäßig wie folgt gespeichert:

      ```
      C:\Program Files\Adobe\Adobe Analytics\Data Workbench
      ```

   * Datendateien (Profile, Zertifikate, Ablaufverfolgungsprotokolle und Benutzerdateien) werden standardmäßig gespeichert in:

      ```
      C:\Users\<username>\AppData\Local\Adobe\Adobe Analytics\Data Workbench\
      ```

      >[!IMPORTANT]
      >
      >Eine generische ***Insight.cfg*** -Datei ohne Serverdetails wird zunächst installiert. Es wird empfohlen, die neu installierte ***Insight.cfg*** -Datei zu verwenden und anzupassen, anstatt eine Datei aus einer vorherigen Installation zu verschieben. Da sich der Pfad zum Installieren der Workstation geändert hat, wird empfohlen, Schriftarten hinzuzufügen, den *Benutzerordner* zu entfernen und die *TraceFileComponent * zu entfernen.

1. (Optional) Wählen Sie &quot; **Benutzerdefiniert** &quot;, um das Sprachpaket und den Speicherort der Programm- und Datendateien auszuwählen.
1. Wählen Sie im Menü &quot;Beginn&quot;die Position für **Tastaturbefehle** aus.

   ![](assets/6_4_workstation_wizard_folder.png)

   Klicken Sie auf **Erstellen Sie keinen Beginn-Menüordner** , um keine Verknüpfung im Menü Windows-Beginn zu installieren.

1. Klicken Sie auf **Weiter.** Eine Zusammenfassung der ausgewählten Dateispeicherorte und Sprachen wird angezeigt. Click **Install.**

1. Suchen Sie nach dem **Data Workbenchs-Zertifikat**.

   Wenn der Installationsassistent das Zertifikat während der Installation nicht finden kann, wird ein Dialogfeld geöffnet, in dem Sie zum Speicherort des Zertifikats (standardmäßig eine **.pem** -Data Workbench im Ordner &quot;Client- **Zertifikate** &quot;) navigieren können, oder Sie klicken auf &quot; **Überspringen** &quot;, um das Zertifikat nach der Installation zu suchen.

   Klicken Sie auf **Installieren** , nachdem Sie das Zertifikat gefunden haben.

1. Nachdem der Setup-Assistent abgeschlossen und die Data Workbench installiert ist, klicken Sie auf **Fertig stellen** , um das Setup abzuschließen.

   >[!NOTE]
   >
   >Der Standardspeicherort für das Protokoll des Workstation-Setup-Assistenten unter `C:\Users\<userName>\AppData\Local\Temp`.

   Aktivieren Sie das Kontrollkästchen Anwendung **starten** , um die Workbench nach dem Setup zu öffnen.

1. **Konfigurieren Sie Verbindungen** zu Servern in der **[!DNL Insight.cfg]** Datei.

   Nach der Installation der Workstation wird der Enhanced Workstation Configuration Experience Workspace mit zusätzlichen Informationen zur [Eingabe von Serververbindungsinformationen](/help/home/c-get-started/c-insght-config-param.md) in die Datei *Insight.cfg* und einer Option zur Auswahl eines Profils aus der Dropdown-Liste geöffnet. Sie können den Verbindungsstatus auch an Ihre Server Ansicht haben.

   ![](assets/6_4_workstation_install_conf_conn.png)

## Installationsordner {#section-b5ea5a3b3ecb4622aef713972f3f8ebd}

Die Ordnerstruktur der Data Workbench umfasst zwei Installationsspeicherorte:

* **Programm-Dateien** Die **Insight.exe** und die zugehörigen Clientdateien (**Insight.ini**) befinden sich jetzt standardmäßig unter

   ```
   C:\Program Files\Adobe\Analytics\DataWorkbench
   ```

* Der **Appdata** -Ordner.

   **Insight.cfg**, Profile, Zertifikate, Ablaufverfolgungsprotokolle und Benutzerdateien befinden sich jetzt standardmäßig unter

   ```
   C:\Users\<Winuser>\AppData\Adobe\Analytics\DataWorkbench\ 
   ```

   Sie können den Pfad für den **Appdata** -Ordner in der `Insight.ini` Datei festlegen:

   ```
   [InitialSettings] 
   AppDataFolder=C:\Users\mhiatt\AppData\Local\Adobe\Adobe Analytics\Data Workbench\ 
   Locale=en-us
   ```

## Deinstallieren der Workstation {#section-5ce2e233fe4348469ef1b3c451dd5b70}

Die Data Workbench enthält jetzt eine ausführbare Datei zum Deinstallieren der Workstation (standardmäßig unter **`Program Files\Adobe\Adobe Analytics\Data Workbench\ unins000.exe`**).

Starten Sie die Data Workbench Workstation-Dateien und führen Sie die entsprechenden Schritte aus, um sie von Ihrer Festplatte zu entfernen.

>[!NOTE]
>
>Sie können die ausführbare Datei &quot; **unins000.exe** &quot;aus dem Ordner über die Verknüpfung &quot;Data Workbench **** deinstallieren&quot;im Menü &quot;Beginn&quot;oder über **[!UICONTROL Control Panel]** > **[!UICONTROL Program and Features]** starten.
