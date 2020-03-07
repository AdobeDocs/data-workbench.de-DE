---
description: Zur Verwendung eines Clusters müssen Sie einen Insight-Server im Cluster als Master-Insight-Server angeben.
solution: Insight
title: Installieren des Master Insight-Servers
uuid: a73214f3-b175-4e9e-8802-7a8451d86d3a
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Installieren des Master Insight-Servers{#installing-the-master-insight-server}

Zur Verwendung eines Clusters müssen Sie einen Insight-Server im Cluster als Master-Insight-Server angeben.

Eine Client-Komponente, z. B. [!DNL Insight] oder [!DNL Report] eine Verbindung zum Master [!DNL Insight Server] zu Beginn einer Sitzung. An folgenden Punkten während der Sitzung stellt der Client möglicherweise eine Verbindung zu anderen im Cluster her, um eine Abfrage durchzuführen. [!DNL Insight Servers] Diese nachfolgenden Verbindungen zwischen dem Client und dem anderen [!DNL Insight Servers] im Cluster werden vom Master vermittelt [!DNL Insight Server] und sind für den Client transparent.

Neben dem Vermitteln von Verbindungen zwischen einem Client und anderen [!DNL Insight Servers] [!DNL Insight Server] im Cluster fungiert der Master als zentraler administrativer Punkt für den gesamten Cluster. Wenn Sie einen Cluster verwalten, aktualisieren Sie den Master [!DNL Insight Server]. Die Verwaltungsänderungen, die Sie auf dem Master vornehmen, [!DNL Insight Server] werden vom anderen [!DNL Insight Servers] im Cluster abgerufen.

**So installieren Sie den Master[!DNL Insight Server]**

1. Stellen Sie fest, welcher Computer als Master fungiert [!DNL Insight Server].
1. Installieren und konfigurieren Sie [!DNL Insight Server] (normalerweise eine [!DNL Insight Server] FSU) auf diesem Computer, wie unter [Insight Server](../../../../../../home/c-inst-svr/c-msr-server/c-msr-server.md)beschrieben.
1. Installieren [!DNL Insight] und konfigurieren Sie eine Verbindung zum Master [!DNL Insight Server] wie im *[!DNL Insight]Benutzerhandbuch *beschrieben.
