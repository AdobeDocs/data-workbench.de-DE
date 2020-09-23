---
description: Ein verarbeitender Insight-Server ist mit einem Übergeordnet Insight-Server identisch, mit Ausnahme des Komponentenverzeichnisses.
solution: Analytics
title: Installieren und Konfigurieren der verarbeitenden Insight Server
uuid: 186675f7-8b63-4675-89ec-51b0837a64d8
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 5%

---


# Installieren und Konfigurieren der verarbeitenden Insight Server{#installing-and-configuring-the-processing-insight-servers}

Ein verarbeitender Insight-Server ist mit einem Übergeordnet Insight-Server identisch, mit Ausnahme des Komponentenverzeichnisses.

Der Komponentenordner einer Verarbeitung [!DNL Insight Server] enthält einen speziellen Satz von Dateien, die speziell für die Verarbeitung konfiguriert wurden [!DNL Insight Servers]. Diese Dateien werden aus dem Ordner &quot;Komponenten für Verarbeitungsserver&quot;auf dem Übergeordnete abgeleitet [!DNL Insight Server].

Wenn Sie eine Verarbeitung installieren, [!DNL Insight Server]führen Sie die folgenden Schritte aus, um den Komponentenordner einzurichten:

1. Löschen Sie den ursprünglichen Komponentenordner bei der Verarbeitung [!DNL Insight Server].
1. Benennen Sie die Komponenten für den Ordner &quot;Verarbeitungsserver&quot;in &quot;Komponenten&quot;um.
1. Ändern Sie die [!DNL Synchronize.cfg] Variable im Komponentenverzeichnis so, dass sie auf den Übergeordnete verweist [!DNL Insight Server].

**So installieren und konfigurieren Sie eine Verarbeitung[!DNL Insight Server]**

1. Installieren Sie die [!DNL Insight Server] Programm-Dateien, wie unter [Installieren der Insight Server-Programm-Dateien](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-install-prgm-files.md#task-1e6251fd39714186baa40d38f23d0088)beschrieben. Stellen Sie sicher, dass die Ordnerstruktur, die auf dem Übergeordnete verwendet wurde, Duplikat wird [!DNL Insight Server]. Wenn [!DNL Insight Server] die Software beispielsweise [!DNL C:\Adobe\Server] auf dem Übergeordnete installiert ist [!DNL Insight Server], müssen Sie sie auch [!DNL C:\Adobe\Server] auf der Verarbeitung installieren [!DNL Insight Servers] .
1. Installieren Sie das von der Adobe für diese bestimmte Verarbeitung ausgestellte digitale Zertifikat [!DNL Insight Server]. Anweisungen finden Sie unter [Herunterladen und Installieren der digitalen Zertifikate](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17) .
1. Führen Sie in Windows Explorer bei der Verarbeitung die folgenden Schritte aus [!DNL Insight Server]:

   1. Delete the **[!UICONTROL Components]** folder.
   1. Benennen Sie den [!DNL Components for Processing Servers] Ordner in Komponenten um.

1. Öffnen Sie die [!DNL Synchronize.cfg] Datei mit einem Texteditor wie Notepad im Komponentenverzeichnis der Verarbeitung [!DNL Insight Server].
1. hinzufügen die IP-Adresse des Übergeordneten (primär) [!DNL Insight Server] zur zweiten Zeile dieser Datei, wie im folgenden Dateifragment dargestellt. Bearbeiten Sie nichts anderes in dieser Datei.

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
1. Beginn [!DNL Insight Server] wie unter [Registering Insight Server as a Windows Service](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540)beschrieben.

   Sie haben die Installation des [!DNL Insight Server] Clusters abgeschlossen. Konfigurieren Sie anschließend das DataSet-Profil für die Ausführung auf dem Cluster, wie im folgenden Abschnitt beschrieben.

