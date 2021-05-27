---
description: Um einen Cluster zu verwenden, müssen Sie einen Insight Server im Cluster als Übergeordneten Insight Server festlegen.
title: Installieren des Master-Insight-Servers
uuid: a73214f3-b175-4e9e-8802-7a8451d86d3a
exl-id: 710f1ffe-f620-4920-b4f9-a644cc68d4cc
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 5%

---

# Installieren des Master-Insight-Servers{#installing-the-master-insight-server}

Um einen Cluster zu verwenden, müssen Sie einen Insight Server im Cluster als Übergeordneten Insight Server festlegen.

Eine Client-Komponente wie [!DNL Insight] oder [!DNL Report] stellt eine Verbindung zum Übergeordneten [!DNL Insight Server] zu Beginn einer Sitzung her. An nachfolgenden Punkten während der Sitzung stellt der Client möglicherweise eine Verbindung zu anderen [!DNL Insight Servers] im Cluster her, um eine Abfrage durchzuführen. Diese nachfolgenden Verbindungen zwischen dem Client und den anderen [!DNL Insight Servers] im Cluster werden vom Übergeordneten [!DNL Insight Server] vermitteln und sind für den Client transparent.

Neben der Vermittlung von Verbindungen zwischen einem Client und anderen [!DNL Insight Servers] im Cluster fungiert das Übergeordnete [!DNL Insight Server] als zentraler Verwaltungspunkt für den gesamten Cluster. Wenn Sie einen Cluster verwalten, aktualisieren Sie den Übergeordneten [!DNL Insight Server]. Die Verwaltungsänderungen, die Sie am Übergeordneten [!DNL Insight Server] vornehmen, werden von den anderen [!DNL Insight Servers] im Cluster abgerufen.

**So installieren Sie den Übergeordneten[!DNL Insight Server]**

1. Bestimmen Sie, welcher Computer als Übergeordnetes [!DNL Insight Server] fungiert.
1. Installieren und konfigurieren Sie [!DNL Insight Server] (normalerweise eine [!DNL Insight Server] FSU) auf diesem Computer, wie unter [Insight Server](../../../../../../home/c-inst-svr/c-msr-server/c-msr-server.md) beschrieben.
1. Installieren Sie [!DNL Insight] und konfigurieren Sie eine Verbindung zum Übergeordneten [!DNL Insight Server], wie im *[!DNL Insight]Benutzerhandbuch* beschrieben.
