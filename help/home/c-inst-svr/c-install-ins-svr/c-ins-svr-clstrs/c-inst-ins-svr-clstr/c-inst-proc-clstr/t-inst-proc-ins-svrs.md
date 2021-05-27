---
description: Ein verarbeitender Insight Server ist mit einem Übergeordneten Insight Server identisch, mit Ausnahme der Inhalte seines Komponentenordners.
title: Installieren und Konfigurieren der verarbeitenden Insight Server
uuid: 186675f7-8b63-4675-89ec-51b0837a64d8
exl-id: 21f7e31b-a2fb-4257-972e-5228bb1efa01
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 5%

---

# Installieren und Konfigurieren der verarbeitenden Insight Server{#installing-and-configuring-the-processing-insight-servers}

Ein verarbeitender Insight Server ist mit einem Übergeordneten Insight Server identisch, mit Ausnahme der Inhalte seines Komponentenordners.

Das Komponentenverzeichnis auf einem verarbeitenden [!DNL Insight Server] enthält einen speziellen Satz von Dateien, die speziell für die Verarbeitung von [!DNL Insight Servers] konfiguriert sind. Diese Dateien werden aus dem Verzeichnis &quot;Components for Processing Servers&quot;auf dem Übergeordneten Ordner [!DNL Insight Server] abgeleitet.

Wenn Sie eine Verarbeitung installieren, führen Sie die folgenden Schritte aus, um den Komponentenordner einzurichten:[!DNL Insight Server]

1. Löschen Sie das ursprüngliche Komponentenverzeichnis bei der Verarbeitung [!DNL Insight Server].
1. Benennen Sie den Ordner &quot;Komponenten für Verarbeitungsserver&quot;in &quot;Komponenten&quot;um.
1. Ändern Sie [!DNL Synchronize.cfg] im Komponentenverzeichnis so, dass auf das Übergeordnete [!DNL Insight Server] verwiesen wird.

**So installieren und konfigurieren Sie eine Verarbeitung[!DNL Insight Server]**

1. Installieren Sie die [!DNL Insight Server] -Programmdateien wie unter [Installieren der Insight Server-Programmdateien](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-install-prgm-files.md#task-1e6251fd39714186baa40d38f23d0088) beschrieben. Stellen Sie sicher, dass Sie die Verzeichnisstruktur duplizieren, die auf dem Übergeordneten [!DNL Insight Server] verwendet wurde. Wenn beispielsweise [!DNL Insight Server] in [!DNL C:\Adobe\Server] auf dem Übergeordneten [!DNL Insight Server] installiert ist, müssen Sie es auch in [!DNL C:\Adobe\Server] auf der Verarbeitung [!DNL Insight Servers] installieren.
1. Installieren Sie das digitale Zertifikat, das die Adobe für diese Verarbeitung ausgestellt hat [!DNL Insight Server]. Anweisungen finden Sie unter [Herunterladen und Installieren der digitalen Zertifikate](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17) .
1. Führen Sie in Windows Explorer bei der Verarbeitung von [!DNL Insight Server] folgende Schritte durch:

   1. Löschen Sie den Ordner **[!UICONTROL Components]** .
   1. Benennen Sie den Ordner [!DNL Components for Processing Servers] in Komponenten um.

1. Öffnen Sie mithilfe eines Texteditors wie Notepad die Datei [!DNL Synchronize.cfg] im Komponentenverzeichnis der Verarbeitung [!DNL Insight Server].
1. Fügen Sie die IP-Adresse des Übergeordneten (primären) [!DNL Insight Server] zur zweiten Zeile dieser Datei hinzu, wie im folgenden Dateifragment dargestellt. Bearbeiten Sie nichts anderes in dieser Datei.

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
1. Starten Sie [!DNL Insight Server] wie unter [Registrieren von Insight Server als Windows-Dienst](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540) beschrieben.

   Sie haben jetzt die Installation Ihres [!DNL Insight Server] Clusters abgeschlossen. Konfigurieren Sie anschließend das Datensatzprofil für die Ausführung auf dem Cluster, wie im folgenden Abschnitt beschrieben.
