---
description: Um einen Cluster zu verwenden, müssen Sie einen Insight Server im Cluster als Übergeordneten Insight Server festlegen.
title: Installieren des Master-Insight-Servers
uuid: a73214f3-b175-4e9e-8802-7a8451d86d3a
exl-id: 710f1ffe-f620-4920-b4f9-a644cc68d4cc
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 5%

---

# Installieren des Master-Insight-Servers{#installing-the-master-insight-server}

{{eol}}

Um einen Cluster zu verwenden, müssen Sie einen Insight Server im Cluster als Übergeordneten Insight Server festlegen.

Eine Client-Komponente wie [!DNL Insight] oder [!DNL Report] Verbindungen zu den Übergeordneten [!DNL Insight Server] zu Beginn einer Sitzung. An nachfolgenden Punkten während der Sitzung stellt der Client möglicherweise eine Verbindung zu anderen [!DNL Insight Servers] im Cluster, um eine Abfrage auszuführen. Diese nachfolgenden Verbindungen zwischen dem Client und der anderen [!DNL Insight Servers] im Cluster werden von den Übergeordneten [!DNL Insight Server] und für den Client transparent sind.

Neben der Vermittlung von Verbindungen zwischen einem Client und anderen [!DNL Insight Servers] im Cluster die Übergeordnete [!DNL Insight Server] fungiert als zentraler Verwaltungspunkt für den gesamten Cluster. Wenn Sie einen Cluster verwalten, aktualisieren Sie den Übergeordneten [!DNL Insight Server]. Die Verwaltungsänderungen, die Sie an den Übergeordneten [!DNL Insight Server] von der anderen abgerufen werden [!DNL Insight Servers] im Cluster.

**So installieren Sie den Übergeordneten[!DNL Insight Server]**

1. Bestimmen, welcher Computer als Übergeordnet fungiert [!DNL Insight Server].
1. Installieren und Konfigurieren [!DNL Insight Server] (normalerweise wird eine [!DNL Insight Server] FSU) auf dieser Maschine, wie unter [Insight Server](../../../../../../home/c-inst-svr/c-msr-server/c-msr-server.md).
1. Installieren [!DNL Insight] und konfigurieren Sie eine Verbindung zum Übergeordneten [!DNL Insight Server] wie in *[!DNL Insight]Benutzerhandbuch*.
