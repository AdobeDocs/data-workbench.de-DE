---
description: Ein verarbeitender Insight-Server ist mit einem Übergeordnet Insight-Server identisch, mit Ausnahme des Komponentenverzeichnisses.
title: Installieren und Konfigurieren der verarbeitenden Insight Server
uuid: 186675f7-8b63-4675-89ec-51b0837a64d8
exl-id: 21f7e31b-a2fb-4257-972e-5228bb1efa01
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 5%

---

# Installieren und Konfigurieren der verarbeitenden Insight Server{#installing-and-configuring-the-processing-insight-servers}

Ein verarbeitender Insight-Server ist mit einem Übergeordnet Insight-Server identisch, mit Ausnahme des Komponentenverzeichnisses.

Der Komponentenordner auf einem verarbeitenden [!DNL Insight Server] enthält einen speziellen Satz von Dateien, die speziell für die Verarbeitung von [!DNL Insight Servers] konfiguriert sind. Diese Dateien werden aus dem Ordner &quot;Components for Processing Servers&quot;auf dem Übergeordnet [!DNL Insight Server] abgeleitet.

Wenn Sie eine Verarbeitung von [!DNL Insight Server] installieren, führen Sie die folgenden Schritte aus, um den Komponentenordner einzurichten:

1. Löschen Sie den ursprünglichen Komponentenordner auf der verarbeitenden [!DNL Insight Server].
1. Benennen Sie die Komponenten für den Ordner &quot;Verarbeitungsserver&quot;in &quot;Komponenten&quot;um.
1. Ändern Sie [!DNL Synchronize.cfg] im Komponentenverzeichnis so, dass sie auf das Übergeordnet [!DNL Insight Server] zeigen.

**So installieren und konfigurieren Sie eine Verarbeitung[!DNL Insight Server]**

1. Installieren Sie die [!DNL Insight Server]-Programm-Dateien, wie unter [Installieren der Insight Server-Programm-Dateien](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-install-prgm-files.md#task-1e6251fd39714186baa40d38f23d0088) beschrieben. Stellen Sie sicher, dass die Ordnerstruktur, die auf dem Übergeordnet [!DNL Insight Server] verwendet wurde, Duplikat wird. Wenn [!DNL Insight Server] beispielsweise in [!DNL C:\Adobe\Server] auf dem Übergeordnet [!DNL Insight Server] installiert ist, müssen Sie es auch in [!DNL C:\Adobe\Server] auf der Verarbeitung [!DNL Insight Servers] installieren.
1. Installieren Sie das von der Adobe für diese bestimmte Verarbeitung ausgestellte digitale Zertifikat [!DNL Insight Server]. Anweisungen finden Sie unter [Herunterladen und Installieren der digitalen Zertifikate](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17).
1. Führen Sie in Windows Explorer bei der Verarbeitung von [!DNL Insight Server] folgende Schritte aus:

   1. Löschen Sie den Ordner **[!UICONTROL Components]**.
   1. Benennen Sie den Ordner [!DNL Components for Processing Servers] in Komponenten um.

1. Öffnen Sie mit einem Texteditor wie Notepad die Datei [!DNL Synchronize.cfg] im Komponentenverzeichnis der Verarbeitung [!DNL Insight Server].
1. hinzufügen die IP-Adresse des Übergeordnet (primären) [!DNL Insight Server] zur zweiten Zeile dieser Datei, wie im folgenden Dateifragment dargestellt. Bearbeiten Sie nichts anderes in dieser Datei.

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
1. Beginn Sie das [!DNL Insight Server], wie unter [Registering Insight Server as a Windows Service](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540) beschrieben.

   Sie haben die Installation des [!DNL Insight Server]-Clusters abgeschlossen. Konfigurieren Sie anschließend das DataSet-Profil für die Ausführung auf dem Cluster, wie im folgenden Abschnitt beschrieben.
