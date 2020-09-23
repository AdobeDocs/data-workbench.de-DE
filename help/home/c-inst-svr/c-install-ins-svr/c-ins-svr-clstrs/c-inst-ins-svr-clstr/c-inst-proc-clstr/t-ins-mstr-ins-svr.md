---
description: Zur Verwendung eines Clusters müssen Sie einen Insight-Server im Cluster als Übergeordnet Insight-Server angeben.
solution: Analytics
title: Installieren des Master-Insight-Servers
uuid: a73214f3-b175-4e9e-8802-7a8451d86d3a
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 5%

---


# Installieren des Master-Insight-Servers{#installing-the-master-insight-server}

Zur Verwendung eines Clusters müssen Sie einen Insight-Server im Cluster als Übergeordnet Insight-Server angeben.

Eine Client-Komponente, z. B. [!DNL Insight] oder [!DNL Report] eine Verbindung zum Übergeordnete [!DNL Insight Server] zu Beginn einer Sitzung. An folgenden Punkten während der Sitzung stellt der Client möglicherweise eine Verbindung zu anderen [!DNL Insight Servers] im Cluster her, um eine Abfrage durchzuführen. Diese nachfolgenden Verbindungen zwischen dem Client und dem anderen [!DNL Insight Servers] im Cluster werden vom Übergeordnet vermittelt [!DNL Insight Server] und sind für den Client transparent.

Der Übergeordnet fungiert nicht nur als Vermittler von Verbindungen zwischen einem Client und anderen [!DNL Insight Servers] [!DNL Insight Server] im Cluster, sondern dient auch als zentraler Verwaltungspunkt für den gesamten Cluster. Wenn Sie einen Cluster verwalten, aktualisieren Sie den Übergeordnete [!DNL Insight Server]. Die Verwaltungsänderungen, die Sie auf dem Übergeordnete vornehmen, [!DNL Insight Server] werden vom anderen [!DNL Insight Servers] im Cluster abgerufen.

**So installieren Sie den Übergeordnete[!DNL Insight Server]**

1. Stellen Sie fest, welche Maschine als Übergeordnet fungiert [!DNL Insight Server].
1. Installieren und konfigurieren Sie [!DNL Insight Server] (normalerweise eine [!DNL Insight Server] FSU) auf diesem Computer, wie unter [Insight Server](../../../../../../home/c-inst-svr/c-msr-server/c-msr-server.md)beschrieben.
1. Installieren [!DNL Insight] und konfigurieren Sie eine Verbindung zum Übergeordnete [!DNL Insight Server] , wie im *[!DNL Insight]Benutzerhandbuch* beschrieben.
