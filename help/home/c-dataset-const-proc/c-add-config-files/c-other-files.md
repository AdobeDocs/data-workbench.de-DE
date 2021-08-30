---
description: Das Datensatzverzeichnis enthält zusätzliche Dateien, die entweder für den Betrieb der Adobe erforderlich sind oder zusätzliche Funktionen für Ihre Softwareimplementierung bieten.
title: Andere Dateien
uuid: 87d83fa5-df25-4da1-8b11-16639902d8d7
exl-id: 0a1fb37c-00ac-46d4-9d0a-904ebd3ccfba
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '236'
ht-degree: 1%

---

# Andere Dateien{#other-files}

Das Datensatzverzeichnis enthält zusätzliche Dateien, die entweder für den Betrieb der Adobe erforderlich sind oder zusätzliche Funktionen für Ihre Softwareimplementierung bieten.

* **[!DNL Client.cfg:]** Die  [!DNL Client.cfg] Datei im Datensatzverzeichnis für das  [!DNL Base] Profil ist für den Betrieb der Software erforderlich. Löschen oder ändern Sie keine der Parameter in der Datei [!DNL Client.cfg].

* **[!DNL Cluster.cfg:]** Die  [!DNL Cluster.cfg] Datei im Datensatzverzeichnis für das  [!DNL Base] Profil ist für den Betrieb der Software erforderlich. In der Datei [!DNL Cluster.cfg] sollten Sie nur den Parameter Server normalisieren ändern, wenn Sie einen Datensatz konfigurieren, der auf einem Data Workbench-Servercluster verarbeitet werden soll. Anweisungen zum Ändern des Parameters Server normalisieren finden Sie unter [Erstellen eines zentralen Normalisierungsservers für einen Cluster](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md).

* **[!DNL Insight Transform.cfg]und  [!DNL Insight Transform Mode.cfg]:** Wenn Sie die Umwandlungsfunktion verwenden, stehen Ihnen zwei zusätzliche Konfigurationsdateien, Data Workbench  [!DNL Transform.cfg] und Data Workbench,  [!DNL TransformMode.cfg]im Datensatzverzeichnis für das  [!DNL Transform] Profil zur Verfügung. Weitere Informationen zu diesen Dateien und ihren Parametern finden Sie unter [Umwandlungsfunktion](https://experienceleague.adobe.com/docs/data-workbench/using/server-admin-install/transform/t-config-tfm.html).

* Die Datei **PAServer.cfg**. Wenn Sie Predictive Analytics-Clustering-Aufträge an Insight Server senden möchten, müssen Sie die [!DNL PAServer.cfg]-Datei für die Verarbeitung serverseitiger Clustering-Übermittlungen konfigurieren.
Das benutzerdefinierte Profil sollte das [!DNL PAServer.cfg] vom Predictive Analytics-Profil ( [!DNL Server\Profiles\Predictive Analytics\Dataset]) übernehmen.

   >[!IMPORTANT]
   >
   >Legen Sie einen *Übergeordneten Server* in dieser Datei fest und speichern Sie die [!DNL PAServer.cfg] auf der Implementierungs-Site.
   >
   >
   ```
   >PAServer = PAServerConfig: 
   >   Master Server = serverInfo: 
   >       Address = string: 
   >       Port = int: 80
   >       Use SSL = bool: false
   >```
