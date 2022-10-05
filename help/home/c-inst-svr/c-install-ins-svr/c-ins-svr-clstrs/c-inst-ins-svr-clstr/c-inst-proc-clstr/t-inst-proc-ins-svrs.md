---
description: Ein verarbeitender Insight Server ist mit einem Übergeordneten Insight Server identisch, mit Ausnahme der Inhalte seines Komponentenordners.
title: Installieren und Konfigurieren der verarbeitenden Insight Server
uuid: 186675f7-8b63-4675-89ec-51b0837a64d8
exl-id: 21f7e31b-a2fb-4257-972e-5228bb1efa01
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 5%

---

# Installieren und Konfigurieren der verarbeitenden Insight Server{#installing-and-configuring-the-processing-insight-servers}

{{eol}}

Ein verarbeitender Insight Server ist mit einem Übergeordneten Insight Server identisch, mit Ausnahme der Inhalte seines Komponentenordners.

Das Komponentenverzeichnis auf einer Verarbeitung [!DNL Insight Server] enthält einen speziellen Satz von Dateien, die speziell für die Verarbeitung konfiguriert sind [!DNL Insight Servers]. Diese Dateien werden aus dem Ordner &quot;Components for Processing Servers&quot;auf dem Übergeordneten [!DNL Insight Server].

Beim Installieren einer Verarbeitung [!DNL Insight Server]führen Sie die folgenden Schritte aus, um den Komponentenordner einzurichten:

1. Löschen Sie das Verzeichnis der ursprünglichen Komponenten auf der verarbeitenden Seite. [!DNL Insight Server].
1. Benennen Sie den Ordner &quot;Komponenten für Verarbeitungsserver&quot;in &quot;Komponenten&quot;um.
1. Ändern Sie die [!DNL Synchronize.cfg] im Komponentenverzeichnis, um auf das Übergeordnete zu verweisen [!DNL Insight Server].

**So installieren und konfigurieren Sie eine Verarbeitung[!DNL Insight Server]**

1. Installieren Sie die [!DNL Insight Server] Programmdateien, wie unter [Installieren der Insight Server-Programmdateien](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-install-prgm-files.md#task-1e6251fd39714186baa40d38f23d0088). Duplizieren Sie unbedingt die Verzeichnisstruktur, die auf dem Übergeordneten [!DNL Insight Server]. Wenn beispielsweise [!DNL Insight Server] installiert in [!DNL C:\Adobe\Server] zum Übergeordneten [!DNL Insight Server], müssen Sie es in [!DNL C:\Adobe\Server] über die Verarbeitung [!DNL Insight Servers] sowie
1. Installieren Sie das digitale Zertifikat, das die Adobe für diese bestimmte Verarbeitung ausgestellt hat. [!DNL Insight Server]. Siehe [Herunterladen und Installieren der digitalen Zertifikate](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17) für Anweisungen.
1. Führen Sie in Windows Explorer bei der Verarbeitung die folgenden Schritte aus [!DNL Insight Server]:

   1. Löschen Sie die **[!UICONTROL Components]** Ordner.
   1. Benennen Sie die [!DNL Components for Processing Servers] Ordner zu Komponenten.

1. Öffnen Sie mithilfe eines Texteditors wie Notepad die [!DNL Synchronize.cfg] -Datei im Komponentenverzeichnis auf der verarbeitenden Seite [!DNL Insight Server].
1. Hinzufügen der IP-Adresse des Übergeordneten (primären) [!DNL Insight Server] in die zweite Zeile dieser Datei, wie im folgenden Dateifragment dargestellt. Bearbeiten Sie nichts anderes in dieser Datei.

   ```
   component = SynchronizeComponent:
     Cluster Primary Server Address = string: PrimaryIPAddress
     Directories = vector: 7 items
       0 = SynchronizeDir:
         Local Path = string: Profiles\\
         Remote URI = string: /Profiles/
       1 = SynchronizeDir:
         Local Path = string: Lookups\\
         Remote URI = string: /Lookups/
       . . .
   ```

1. Speichern Sie die Datei.
1. Starten Sie die [!DNL Insight Server] wie in [Registrieren von Insight Server als Windows-Dienst](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540).

   Sie haben jetzt die Installation Ihrer [!DNL Insight Server] Cluster. Konfigurieren Sie anschließend das Datensatzprofil für die Ausführung auf dem Cluster, wie im folgenden Abschnitt beschrieben.
