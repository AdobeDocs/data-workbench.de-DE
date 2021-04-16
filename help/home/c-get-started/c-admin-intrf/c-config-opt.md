---
description: Mit der Option "Konfiguration"wird Ihre Datei "Insight.cfg"geöffnet, die Ihre Verbindungen zu verschiedenen Servern steuert.
title: Konfigurationsoption
uuid: 1edfcf03-b278-4d81-942c-c9024378e13c
exl-id: bb694d3c-64f7-4a74-b774-4d5145250e6d
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 2%

---

# Konfigurationsoption{#configuration-option}

Mit der Option &quot;Konfiguration&quot;wird Ihre Datei &quot;Insight.cfg&quot;geöffnet, die Ihre Verbindungen zu verschiedenen Servern steuert.

![](assets/cfg_Workstation.png)

**So bearbeiten Sie die Datei Insight.cfg**

1. Ändern Sie im Fenster [!DNL Insight.cfg] die Parameter wie gewünscht. Detaillierte Beschreibungen der Parameter in der Datei [!DNL Insight.cfg] finden Sie unter [Insight-Konfigurationsparameter](../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b).
1. Klicken Sie zum Speichern der Konfigurationseinstellungen mit der rechten Maustaste auf **[!UICONTROL Insight.cfg (modified)]** oben im Fenster und klicken Sie auf **[!UICONTROL Save as Insight.cfg]**.

**So fügen Sie neue Server hinzu**

1. Klicken Sie im Fenster [!DNL Insight.cfg] mit der rechten Maustaste auf **[!UICONTROL Servers]** und dann auf **[!UICONTROL Add new child]** > **[!UICONTROL Server]**.

   ![](assets/cfg_Workstation_AddServer.png)

1. Vervollständigen oder ändern Sie die Serverparameter, um der Data Workbench Zugriff auf den gewünschten Server zu gewähren. Detaillierte Beschreibungen der Parameter in der Datei [!DNL Insight.cfg] finden Sie unter [Insight-Konfigurationsparameter](../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b).
1. Wiederholen Sie Schritt 1 und Schritt 2 für jeden Server, auf dem Sie eine Verbindung konfigurieren möchten.
1. Klicken Sie zum Speichern der Konfigurationseinstellungen mit der rechten Maustaste auf **[!UICONTROL Insight.cfg (modified)]** oben im Fenster und klicken Sie auf **[!UICONTROL Save as Insight.cfg]**.

Data Workbench versucht, eine Verbindung zu den Servern herzustellen, indem Sie die angegebenen Einstellungen verwenden. Wird eine Verbindung hergestellt, wird in der [!DNL Servers Manager] wie unten dargestellt ein grüner Knoten angezeigt. Wenn die Data Workbench keine Serververbindung herstellen kann, wird ein roter Knoten angezeigt.

![](assets/vis_SysStat_RedGreenDots.png)
