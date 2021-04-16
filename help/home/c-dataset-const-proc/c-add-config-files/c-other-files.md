---
description: Der Ordner "DataSet"enthält zusätzliche Dateien, die entweder für den Betrieb der Adobe erforderlich sind oder zusätzliche Funktionen für die Implementierung bereitstellen.
title: Andere Dateien
uuid: 87d83fa5-df25-4da1-8b11-16639902d8d7
exl-id: 0a1fb37c-00ac-46d4-9d0a-904ebd3ccfba
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 1%

---

# Andere Dateien{#other-files}

Der Ordner &quot;DataSet&quot;enthält zusätzliche Dateien, die entweder für den Betrieb der Adobe erforderlich sind oder zusätzliche Funktionen für die Implementierung bereitstellen.

* **[!DNL Client.cfg:]** Die  [!DNL Client.cfg] Datei im Ordner &quot;DataSet&quot;für das  [!DNL Base] Profil ist für den Betrieb der Software erforderlich. Löschen oder ändern Sie keine Parameter in der Datei [!DNL Client.cfg].

* **[!DNL Cluster.cfg:]** Die  [!DNL Cluster.cfg] Datei im Ordner &quot;DataSet&quot;für das  [!DNL Base] Profil ist für den Betrieb der Software erforderlich. In der Datei [!DNL Cluster.cfg] sollten Sie nur den Parameter &quot;Server normalisieren&quot;ändern, wenn Sie einen Datensatz für die Verarbeitung auf einem Data Workbench-Servercluster konfigurieren. Anweisungen zum Ändern des Parameters Server normalisieren finden Sie unter [Erstellen eines zentralisierten Normalisierungsservers für einen Cluster](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md).

* **[!DNL Insight Transform.cfg]und  [!DNL Insight Transform Mode.cfg]:** Wenn Sie die Transformationsfunktion verwenden, stehen Ihnen zwei zusätzliche Konfigurationsdateien, die Data Workbench  [!DNL Transform.cfg] und die Data Workbench  [!DNL TransformMode.cfg], im DataSet-Ordner für das  [!DNL Transform] Profil zur Verfügung. Weitere Informationen zu diesen Dateien und ihren Parametern finden Sie unter [Transform-Funktion](https://docs.adobe.com/content/help/en/data-workbench/using/server-admin-install/transform/t-config-tfm.html).

* Die Datei **PAServer.cfg**. Wenn Sie Predictive Analytics-Clustering-Aufträge an Insight-Server senden möchten, müssen Sie die [!DNL PAServer.cfg]-Datei für die Verarbeitung serverseitiger Clustering-Übermittlungen konfigurieren.
Das benutzerdefinierte Profil sollte das [!DNL PAServer.cfg] aus dem Predictive Analytics-Profil ( [!DNL Server\Profiles\Predictive Analytics\Dataset]) übernehmen.

   >[!IMPORTANT]
   >
   >Legen Sie einen *Übergeordnet Server* in dieser Datei fest und speichern Sie [!DNL PAServer.cfg] auf der Implementierungssite.
   >
   >
   ```
   >PAServer = PAServerConfig: 
   >   Master Server = serverInfo: 
   >       Address = string: 
   >       Port = int: 80
   >       Use SSL = bool: false
   >```
