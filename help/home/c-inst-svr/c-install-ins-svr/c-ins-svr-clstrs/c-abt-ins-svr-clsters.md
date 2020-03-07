---
description: Ein Insight Server-Cluster ist erforderlich, wenn die Datenmenge, die Sie verarbeiten und für Ihre Benutzer von Insight und Report verfügbar machen möchten, die Kapazität eines einzelnen Insight-Servers übersteigt.
solution: Insight
title: Info zu Insight Server-Clustern
uuid: d65e0fe5-f87d-4d8e-a208-9192e9d62fb5
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Info zu Insight Server-Clustern{#about-insight-server-clusters}

Ein Insight Server-Cluster ist erforderlich, wenn die Datenmenge, die Sie verarbeiten und für Ihre Benutzer von Insight und Report verfügbar machen möchten, die Kapazität eines einzelnen Insight-Servers übersteigt.

Durch die Einrichtung eines [!DNL Insight Server] Clusters können Sie einen einzigen Analysedatensatz auf mehrere Computer in einem Cluster verteilen, um die Verarbeitungsleistung mehrerer Geräte zu nutzen [!DNL Insight Servers].

Der erste Schritt bei der Implementierung eines [!DNL Insight Server] Clusters besteht darin, die Computer im Cluster zuzuordnen [!DNL Insight Server] . Der erste [!DNL Insight Server] Rechner, den Sie eingerichtet haben, ist Ihr Master [!DNL Insight Server] (manchmal auch als Ihr primärer Computer bezeichnet [!DNL Insight Server]).

>[!NOTE]
>
>Wenn Sie eine [!DNL Insight Server] File Server Unit (FSU) verwenden, empfiehlt Adobe, die FSU als Master zu konfigurieren [!DNL Insight Server]. Weitere Informationen zum Konfigurieren eines FSU finden Sie im Handbuch zur Konfiguration von *Datasets*.

Der Master [!DNL Insight Server] verwaltet die Kommunikation zwischen dem anderen [!DNL Insight Servers] im Cluster (als Verarbeitungsserver oder manchmal als Abfrageserver bezeichnet) und Instanzen von [!DNL Insight] und [!DNL Report]. Bei einem bestimmten Datensatz erfolgt die Verarbeitung der Protokolldatei auf dem (einem oder mehreren) angegebenen [!DNL Insight Servers] (Master- oder Verarbeitungs-)Datensatz, wie in den [!DNL Insight Server] Konfigurationsdateien angegeben. Bei der Arbeit in einer Clusterumgebung werden [!DNL Insight] Installationen für den Zugriff auf den Master konfiguriert. Abfragen können jedoch von jedem [!DNL Insight Server][!DNL Insight Servers] Cluster verarbeitet werden.

>[!NOTE]
>
>Die Datei **PAServer.cfg** . Wenn Sie Predictive Analytics-Clustering-Aufträge an Insight-Server senden möchten, müssen Sie die [!DNL PAServer.cfg] Datei für die Verarbeitung serverseitiger Clustering-Übermittlungen konfigurieren. Das benutzerdefinierte Profil sollte das [!DNL PAServer.cfg] Profil aus dem Predictive Analytics-Profil übernehmen ( [!DNL Server\Profiles\Predictive Analytics\Dataset]). Legen Sie einen *Master-Server* in dieser Datei fest und speichern Sie ihn auf der Implementierungssite [!DNL PAServer.cfg] . >
>
```>
>PAServer = PAServerConfig: 
>   Master Server = serverInfo: 
>       Address = string: 
>       Port = int: 80
>       Use SSL = bool: false
>```>



>[!IMPORTANT]
>
>Die Anweisungen in diesem Kapitel gelten nicht für die Erstellung eines [!DNL Insight Server] Clusters, der aus mehr als fünf (5) besteht [!DNL Insight Servers]. Wenden Sie sich an Adobe, um die Systemanforderungen und Profilkonfigurationsempfehlungen für Cluster zu erhalten, die größer als fünf sind [!DNL Insight Servers].

