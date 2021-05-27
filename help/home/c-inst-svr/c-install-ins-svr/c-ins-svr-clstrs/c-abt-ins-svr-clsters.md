---
description: Ein Insight Server-Cluster ist erforderlich, wenn die Datenmenge, die Sie verarbeiten und für Ihre Benutzer von Insight und Report bereitstellen möchten, die Kapazität eines einzelnen Insight-Servers übersteigt.
title: Über Insight Server-Cluster
uuid: d65e0fe5-f87d-4d8e-a208-9192e9d62fb5
exl-id: b26e0f63-76db-461d-91e7-0968624aa0f7
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 2%

---

# Über Insight Server-Cluster{#about-insight-server-clusters}

Ein Insight Server-Cluster ist erforderlich, wenn die Datenmenge, die Sie verarbeiten und für Ihre Benutzer von Insight und Report bereitstellen möchten, die Kapazität eines einzelnen Insight-Servers übersteigt.

Durch die Einrichtung eines [!DNL Insight Server]-Clusters können Sie einen einzigen Analysedatensatz auf mehrere Computer in einem Cluster verteilen, um die Verarbeitungsleistung mehrerer [!DNL Insight Servers] zu nutzen.

Der erste Schritt bei der Implementierung eines [!DNL Insight Server]-Clusters besteht darin, die [!DNL Insight Server]-Computer in Ihrem Cluster zuzuweisen. Der erste [!DNL Insight Server]-Computer, den Sie eingerichtet haben, ist Ihr Übergeordneter [!DNL Insight Server] (manchmal auch als Ihr primärer [!DNL Insight Server] bezeichnet).

>[!NOTE]
>
>Wenn Sie eine [!DNL Insight Server] File Server Unit (FSU) verwenden, empfiehlt Adobe, die FSU als Übergeordnete [!DNL Insight Server] zu konfigurieren. Informationen zum Konfigurieren einer FSU finden Sie im *Handbuch zur Datensatzkonfiguration*.

Der Übergeordnete [!DNL Insight Server] verwaltet die Kommunikation zwischen den anderen [!DNL Insight Servers] im Cluster (als Verarbeitungsserver oder manchmal als Abfrageserver bezeichnet) und Instanzen von [!DNL Insight] und [!DNL Report]. Für einen bestimmten Datensatz erfolgt die Verarbeitung der Protokolldatei in dem (einem oder mehreren) bezeichneten [!DNL Insight Servers] (Übergeordnet oder Verarbeitung), wie in den Konfigurationsdateien [!DNL Insight Server] angegeben. Bei der Arbeit in einer Clusterumgebung sind [!DNL Insight] -Installationen für den Zugriff auf das Übergeordnete [!DNL Insight Server] konfiguriert. Abfragen können jedoch von jedem der [!DNL Insight Servers] im Cluster verarbeitet werden.

>[!NOTE]
>
>Die Datei **PAServer.cfg**. Wenn Sie Predictive Analytics-Clustering-Aufträge an Insight Server senden möchten, müssen Sie die [!DNL PAServer.cfg]-Datei für die Verarbeitung serverseitiger Clustering-Übermittlungen konfigurieren. Das benutzerdefinierte Profil sollte das [!DNL PAServer.cfg] vom Predictive Analytics-Profil ([!DNL Server\Profiles\Predictive Analytics\Dataset]) übernehmen. Legen Sie einen *Übergeordneten Server* in dieser Datei fest und speichern Sie die [!DNL PAServer.cfg] auf der Implementierungs-Site.
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
>Die Anweisungen in diesem Kapitel gelten nicht für die Erstellung eines [!DNL Insight Server] Clusters, der aus mehr als fünf (5) [!DNL Insight Servers] besteht. Wenden Sie sich an die Adobe, um die Systemanforderungen und Profilkonfigurationsempfehlungen für Cluster zu erhalten, die größer als fünf [!DNL Insight Servers] sind.
