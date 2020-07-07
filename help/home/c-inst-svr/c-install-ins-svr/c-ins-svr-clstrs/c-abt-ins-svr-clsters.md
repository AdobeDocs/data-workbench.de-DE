---
description: Ein Insight Server-Cluster ist erforderlich, wenn die Datenmenge, die Sie verarbeiten und für Ihre Benutzer von Insight und Report verfügbar machen möchten, die Kapazität eines einzelnen Insight-Servers übersteigt.
solution: Insight
title: Info zu Insight Server-Clustern
uuid: d65e0fe5-f87d-4d8e-a208-9192e9d62fb5
translation-type: tm+mt
source-git-commit: 2c1b2adfe8bf479c2a8cbd150ed006be2336022c
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 0%

---


# Info zu Insight Server-Clustern{#about-insight-server-clusters}

Ein Insight Server-Cluster ist erforderlich, wenn die Datenmenge, die Sie verarbeiten und für Ihre Benutzer von Insight und Report verfügbar machen möchten, die Kapazität eines einzelnen Insight-Servers übersteigt.

Durch die Einrichtung eines [!DNL Insight Server] Clusters können Sie ein einzelnes Dataset auf mehreren Analysen in einem Cluster verteilen, um die Verarbeitungsleistung mehrerer Rechner zu nutzen [!DNL Insight Servers].

Der erste Schritt bei der Implementierung eines [!DNL Insight Server] Clusters besteht darin, die Computer im Cluster zuzuordnen [!DNL Insight Server] . Der erste [!DNL Insight Server] Rechner, den Sie eingerichtet haben, ist Ihr Master [!DNL Insight Server] (manchmal auch als Ihr primärer Computer bezeichnet [!DNL Insight Server]).

>[!NOTE]
>
>Wenn Sie eine [!DNL Insight Server] File Server Unit (FSU) verwenden, empfiehlt Adobe, die FSU als Master zu konfigurieren [!DNL Insight Server]. Weitere Informationen zum Konfigurieren eines FSU finden Sie im Handbuch zur Konfiguration von *Datasets*.

Der Master [!DNL Insight Server] verwaltet die Kommunikation zwischen den anderen im Cluster (als Verarbeitungsserver oder manchmal als Abfrage-Server bezeichnet) und Instanzen von [!DNL Insight Servers] und [!DNL Insight] [!DNL Report]. Bei einem bestimmten Datensatz erfolgt die Verarbeitung der Protokolldatei auf dem (einem oder mehreren) angegebenen [!DNL Insight Servers] (Master- oder Verarbeitungs-)Datensatz, wie in den [!DNL Insight Server] Konfigurationsdateien angegeben. Bei der Arbeit in einer Clustersoftware werden [!DNL Insight] Installationen für den Zugriff auf den Master konfiguriert. [!DNL Insight Server]Abfragen können jedoch von einem beliebigen [!DNL Insight Servers] Cluster verarbeitet werden.

>[!NOTE]
>
>Die Datei **PAServer.cfg** . Wenn Sie Predictive Analytics-Clustering-Aufträge an Insight-Server senden möchten, müssen Sie die [!DNL PAServer.cfg] Datei für die Verarbeitung serverseitiger Clustering-Übermittlungen konfigurieren. Das benutzerdefinierte Profil sollte die [!DNL PAServer.cfg] Daten aus dem Predictive Analytics Profil ([!DNL Server\Profiles\Predictive Analytics\Dataset]) übernehmen. Legen Sie einen *Master-Server* in dieser Datei fest und speichern Sie ihn auf der Implementierungssite [!DNL PAServer.cfg] .
>
>
```
>PAServer = PAServerConfig: 
>   Master Server = serverInfo: 
>       Address = string: 
>       Port = int: 80
>       Use SSL = bool: false
>```

>[!IMPORTANT]
>
>Die Anweisungen in diesem Kapitel gelten nicht für die Erstellung eines [!DNL Insight Server] Clusters, der aus mehr als fünf (5) besteht [!DNL Insight Servers]. Wenden Sie sich an Adobe, um Systemanforderungen und Profil-Konfigurationsempfehlungen für Cluster zu erhalten, die größer als fünf sind [!DNL Insight Servers].
