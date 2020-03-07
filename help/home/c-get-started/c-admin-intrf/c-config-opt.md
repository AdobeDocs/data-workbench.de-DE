---
description: Mit der Option "Konfiguration"wird Ihre Datei "Insight.cfg"geöffnet, die Ihre Verbindungen zu verschiedenen Servern steuert.
solution: Analytics
title: Konfigurationsoption
topic: Data workbench
uuid: 1edfcf03-b278-4d81-942c-c9024378e13c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Konfigurationsoption{#configuration-option}

Mit der Option &quot;Konfiguration&quot;wird Ihre Datei &quot;Insight.cfg&quot;geöffnet, die Ihre Verbindungen zu verschiedenen Servern steuert.

![](assets/cfg_Workstation.png)

**So bearbeiten Sie die Datei Insight.cfg**

1. Ändern Sie die Parameter im [!DNL Insight.cfg] Fenster nach Bedarf. Detaillierte Beschreibungen der Parameter in der [!DNL Insight.cfg] Datei finden Sie unter [Insight-Konfigurationsparameter](../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b).
1. Klicken Sie zum Speichern der Konfigurationseinstellungen mit der rechten Maustaste **[!UICONTROL Insight.cfg (modified)]** oben im Fenster und klicken Sie auf **[!UICONTROL Save as Insight.cfg]**.

**So fügen Sie neue Server hinzu**

1. Klicken Sie im [!DNL Insight.cfg] Fenster mit der rechten Maustaste **[!UICONTROL Servers]** und klicken Sie auf **[!UICONTROL Add new child]** > **[!UICONTROL Server]**.

   ![](assets/cfg_Workstation_AddServer.png)

1. Vervollständigen oder ändern Sie die Serverparameter, um Data Workbench Zugriff auf den gewünschten Server zu gewähren. Detaillierte Beschreibungen der Parameter in der [!DNL Insight.cfg] Datei finden Sie unter [Insight-Konfigurationsparameter](../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b).
1. Wiederholen Sie Schritt 1 und Schritt 2 für jeden Server, auf dem Sie eine Verbindung konfigurieren möchten.
1. Klicken Sie zum Speichern der Konfigurationseinstellungen mit der rechten Maustaste **[!UICONTROL Insight.cfg (modified)]** oben im Fenster und klicken Sie auf **[!UICONTROL Save as Insight.cfg]**.

Data Workbench versucht, eine Verbindung zu den Servern herzustellen, indem Sie die angegebenen Einstellungen verwenden. Wenn eine Verbindung hergestellt wird, wird in der [!DNL Servers Manager] wie unten dargestellt eine grüne Node angezeigt. Wenn Data Workbench keine Verbindung zum Server herstellen kann, wird ein roter Knoten angezeigt.

![](assets/vis_SysStat_RedGreenDots.png)

