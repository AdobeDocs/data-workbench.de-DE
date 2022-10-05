---
description: Das Datensatzverzeichnis enthält zusätzliche Dateien, die entweder für den Betrieb der Adobe erforderlich sind oder zusätzliche Funktionen für Ihre Softwareimplementierung bieten.
title: Andere Dateien
uuid: 87d83fa5-df25-4da1-8b11-16639902d8d7
exl-id: 0a1fb37c-00ac-46d4-9d0a-904ebd3ccfba
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '236'
ht-degree: 1%

---

# Andere Dateien{#other-files}

{{eol}}

Das Datensatzverzeichnis enthält zusätzliche Dateien, die entweder für den Betrieb der Adobe erforderlich sind oder zusätzliche Funktionen für Ihre Softwareimplementierung bieten.

* **[!DNL Client.cfg:]** Die [!DNL Client.cfg] -Datei im Datensatzverzeichnis für die [!DNL Base] Profil ist für den Betrieb der Software erforderlich. Löschen oder ändern Sie keine der Parameter im [!DNL Client.cfg] -Datei.

* **[!DNL Cluster.cfg:]** Die [!DNL Cluster.cfg] -Datei im Datensatzverzeichnis für die [!DNL Base] Profil ist für den Betrieb der Software erforderlich. Im [!DNL Cluster.cfg] ändern Sie nur den Parameter Server normalisieren , wenn Sie einen Datensatz konfigurieren, der auf einem Data Workbench-Servercluster verarbeitet werden soll. Anweisungen zum Ändern des Parameters Server normalisieren finden Sie unter [Erstellen eines zentralen Normalisierungsservers für einen Cluster](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md).

* **[!DNL Insight Transform.cfg]und [!DNL Insight Transform Mode.cfg]:** Wenn Sie die Umwandlungsfunktion verwenden, haben Sie zwei zusätzliche Konfigurationsdateien, Data Workbench [!DNL Transform.cfg] und Data Workbench [!DNL TransformMode.cfg]im Datensatzverzeichnis für die [!DNL Transform] Profil. Informationen zu diesen Dateien und ihren Parametern finden Sie unter [Umwandlungsfunktion](https://experienceleague.adobe.com/docs/data-workbench/using/server-admin-install/transform/t-config-tfm.html).

* Die **PAServer.cfg** -Datei. Wenn Sie Predictive Analytics-Clustering-Aufträge an Insight Server senden möchten, müssen Sie die [!DNL PAServer.cfg] -Datei für die Verarbeitung von serverseitigen Clustering-Übermittlungen.
Das benutzerdefinierte Profil sollte die [!DNL PAServer.cfg] aus dem Predictive Analytics-Profil ( [!DNL Server\Profiles\Predictive Analytics\Dataset]).

   >[!IMPORTANT]
   >
   >Legen Sie eine *Übergeordneter Server* in dieser Datei speichern Sie die [!DNL PAServer.cfg] zur Implementierungs-Site.
   >
   >
   ```
   >PAServer = PAServerConfig: 
   >   Master Server = serverInfo: 
   >       Address = string: 
   >       Port = int: 80
   >       Use SSL = bool: false
   >```
