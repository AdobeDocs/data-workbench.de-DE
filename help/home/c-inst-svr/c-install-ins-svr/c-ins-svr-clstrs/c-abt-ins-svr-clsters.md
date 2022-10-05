---
description: Ein Insight Server-Cluster ist erforderlich, wenn die Datenmenge, die Sie verarbeiten und für Ihre Benutzer von Insight und Report bereitstellen möchten, die Kapazität eines einzelnen Insight-Servers übersteigt.
title: Über Insight Server-Cluster
uuid: d65e0fe5-f87d-4d8e-a208-9192e9d62fb5
exl-id: b26e0f63-76db-461d-91e7-0968624aa0f7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 2%

---

# Über Insight Server-Cluster{#about-insight-server-clusters}

{{eol}}

Ein Insight Server-Cluster ist erforderlich, wenn die Datenmenge, die Sie verarbeiten und für Ihre Benutzer von Insight und Report bereitstellen möchten, die Kapazität eines einzelnen Insight-Servers übersteigt.

Durch Einrichtung einer [!DNL Insight Server] Cluster, können Sie einen einzigen Analysedatensatz auf mehrere Computer in einem Cluster verteilen, um die Verarbeitungsleistung mehrerer [!DNL Insight Servers].

Der erste Schritt bei der Umsetzung eines [!DNL Insight Server] Der Cluster muss die [!DNL Insight Server] Computer in Ihrem Cluster. Die erste [!DNL Insight Server] Der von Ihnen eingerichtete Computer ist Ihr Übergeordneter [!DNL Insight Server] (manchmal auch als primäre Instanz bezeichnet) [!DNL Insight Server]).

>[!NOTE]
>
>Wenn Sie eine [!DNL Insight Server] File Server Unit (FSU), empfiehlt Adobe, die FSU als Ihre Übergeordnete [!DNL Insight Server]. Informationen zum Konfigurieren einer FSU finden Sie unter *Anleitung zur Datensatzkonfiguration*.

Die Übergeordneten [!DNL Insight Server] die Kommunikation zwischen den [!DNL Insight Servers] im Cluster (als Verarbeitungsserver oder manchmal als Abfrageserver bezeichnet) und Instanzen von [!DNL Insight] und [!DNL Report]. Für einen bestimmten Datensatz erfolgt die Verarbeitung der Protokolldatei in der (einem oder mehreren) festgelegten [!DNL Insight Servers] (Übergeordnet oder Verarbeitung) gemäß den Angaben in [!DNL Insight Server] Konfigurationsdateien. Wenn Sie in einer Clusterumgebung arbeiten, [!DNL Insight] -Installationen sind so konfiguriert, dass sie auf die Übergeordneten [!DNL Insight Server], aber Abfragen können von jedem der [!DNL Insight Servers] innerhalb des Clusters.

>[!NOTE]
>
>Die **PAServer.cfg** -Datei. Wenn Sie Predictive Analytics-Clustering-Aufträge an Insight Server senden möchten, müssen Sie die [!DNL PAServer.cfg] -Datei für die Verarbeitung von serverseitigen Clustering-Übermittlungen. Das benutzerdefinierte Profil sollte die [!DNL PAServer.cfg] aus dem Predictive Analytics-Profil ([!DNL Server\Profiles\Predictive Analytics\Dataset]). Legen Sie eine *Übergeordneter Server* in dieser Datei speichern Sie die [!DNL PAServer.cfg] zur Implementierungs-Site.
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
>Die Anweisungen in diesem Kapitel gelten nicht für die Erstellung eines [!DNL Insight Server] Cluster, bestehend aus mehr als fünf (5) [!DNL Insight Servers]. Wenden Sie sich an die Adobe, um Empfehlungen zu Systemanforderungen und Profilkonfigurationen für Cluster zu erhalten, die größer als fünf sind [!DNL Insight Servers].
