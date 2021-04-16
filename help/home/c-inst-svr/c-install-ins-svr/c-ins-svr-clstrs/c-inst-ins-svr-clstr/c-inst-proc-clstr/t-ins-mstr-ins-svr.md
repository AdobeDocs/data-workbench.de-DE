---
description: Zur Verwendung eines Clusters müssen Sie einen Insight-Server im Cluster als Übergeordnet Insight-Server angeben.
title: Installieren des Master-Insight-Servers
uuid: a73214f3-b175-4e9e-8802-7a8451d86d3a
exl-id: 710f1ffe-f620-4920-b4f9-a644cc68d4cc
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 5%

---

# Installieren des Master-Insight-Servers{#installing-the-master-insight-server}

Zur Verwendung eines Clusters müssen Sie einen Insight-Server im Cluster als Übergeordnet Insight-Server angeben.

Eine Client-Komponente wie [!DNL Insight] oder [!DNL Report] stellt eine Verbindung zum Übergeordnet [!DNL Insight Server] zu Beginn einer Sitzung her. An folgenden Punkten während der Sitzung stellt der Client möglicherweise eine Verbindung zu anderen [!DNL Insight Servers] im Cluster her, um eine Abfrage auszuführen. Diese nachfolgenden Verbindungen zwischen dem Client und den anderen [!DNL Insight Servers] im Cluster werden vom Übergeordnet [!DNL Insight Server] vermittelt und sind für den Client transparent.

Neben dem Vermittlen von Verbindungen zwischen einem Client und anderen [!DNL Insight Servers] im Cluster fungiert das Übergeordnet [!DNL Insight Server] als zentraler Verwaltungspunkt für den gesamten Cluster. Wenn Sie einen Cluster verwalten, aktualisieren Sie den Übergeordnet [!DNL Insight Server]. Die Verwaltungsänderungen, die Sie am Übergeordnet [!DNL Insight Server] vornehmen, werden von den anderen [!DNL Insight Servers] im Cluster abgerufen.

**So installieren Sie den Übergeordnete[!DNL Insight Server]**

1. Stellen Sie fest, welcher Computer als Übergeordnet [!DNL Insight Server] fungiert.
1. Installieren und konfigurieren Sie [!DNL Insight Server] (normalerweise eine [!DNL Insight Server]-FSU) auf diesem Computer, wie unter [Insight Server](../../../../../../home/c-inst-svr/c-msr-server/c-msr-server.md) beschrieben.
1. Installieren Sie [!DNL Insight] und konfigurieren Sie eine Verbindung zum Übergeordnet [!DNL Insight Server], wie im *[!DNL Insight]Benutzerhandbuch* beschrieben.
