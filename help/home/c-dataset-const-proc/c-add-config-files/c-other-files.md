---
description: Der Ordner "DataSet"enthält zusätzliche Dateien, die entweder für den Betrieb der Adobe erforderlich sind oder zusätzliche Funktionen für die Implementierung bereitstellen.
solution: Analytics
title: Andere Dateien
topic: Data workbench
uuid: 87d83fa5-df25-4da1-8b11-16639902d8d7
translation-type: tm+mt
source-git-commit: 98452ba81d71db65c75e3d07712eefa18c003f53
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 1%

---


# Andere Dateien{#other-files}

Der Ordner &quot;DataSet&quot;enthält zusätzliche Dateien, die entweder für den Betrieb der Adobe erforderlich sind oder zusätzliche Funktionen für die Implementierung bereitstellen.

* **[!DNL Client.cfg:]** Die [!DNL Client.cfg] Datei im Ordner &quot;DataSet&quot;für das [!DNL Base] Profil ist für den Betrieb der Software erforderlich. Löschen oder ändern Sie keine Parameter in der [!DNL Client.cfg] Datei.

* **[!DNL Cluster.cfg:]** Die [!DNL Cluster.cfg] Datei im Ordner &quot;DataSet&quot;für das [!DNL Base] Profil ist für den Betrieb der Software erforderlich. In der [!DNL Cluster.cfg] Datei sollten Sie nur den Parameter &quot;Server normalisieren&quot;ändern, wenn Sie ein Dataset für die Verarbeitung auf einem Data Workbench-Servercluster konfigurieren. Anweisungen zum Ändern des Parameters Server normalisieren finden Sie unter [Erstellen eines zentralisierten Normalisierungsservers für einen Cluster](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md).

* **[!DNL Insight Transform.cfg]und[!DNL Insight Transform Mode.cfg]:** Wenn Sie die Transformationsfunktion verwenden, stehen Ihnen zwei zusätzliche Konfigurationsdateien, die Data Workbench [!DNL Transform.cfg] und die Data Workbench, [!DNL TransformMode.cfg]im Ordner &quot;DataSet&quot;für das [!DNL Transform] Profil zur Verfügung. Informationen zu diesen Dateien und ihren Parametern finden Sie unter [Transform-Funktion](https://docs.adobe.com/content/help/en/data-workbench/using/server-admin-install/transform/t-config-tfm.html).

* Die Datei **PAServer.cfg** . Wenn Sie Predictive Analytics-Clustering-Aufträge an Insight-Server senden möchten, müssen Sie die [!DNL PAServer.cfg] Datei für die Verarbeitung serverseitiger Clustering-Übermittlungen konfigurieren.
Das benutzerdefinierte Profil sollte die [!DNL PAServer.cfg] Daten aus dem Predictive Analytics-Profil übernehmen ( [!DNL Server\Profiles\Predictive Analytics\Dataset]).

   >[!IMPORTANT]
   >
   >Legen Sie in dieser Datei einen *Übergeordnet Server* fest und speichern Sie ihn auf der Implementierungssite [!DNL PAServer.cfg] .
   >
   >
   ```
   >PAServer = PAServerConfig: 
   >   Master Server = serverInfo: 
   >       Address = string: 
   >       Port = int: 80
   >       Use SSL = bool: false
   >```

