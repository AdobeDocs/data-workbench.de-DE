---
description: Mit der Option Konfiguration wird Ihre Datei Insight.cfg geöffnet, die Ihre Verbindungen zu verschiedenen Servern steuert.
title: Konfigurationsoption
uuid: 1edfcf03-b278-4d81-942c-c9024378e13c
exl-id: bb694d3c-64f7-4a74-b774-4d5145250e6d
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 2%

---

# Konfigurationsoption{#configuration-option}

{{eol}}

Mit der Option Konfiguration wird Ihre Datei Insight.cfg geöffnet, die Ihre Verbindungen zu verschiedenen Servern steuert.

![](assets/cfg_Workstation.png)

**Bearbeiten der Datei Insight.cfg**

1. Im [!DNL Insight.cfg] ändern Sie die Parameter nach Bedarf. Detaillierte Beschreibungen der Parameter im Abschnitt [!DNL Insight.cfg] -Datei, siehe [Insight-Konfigurationsparameter](../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b).
1. Um Ihre Konfigurationseinstellungen zu speichern, klicken Sie mit der rechten Maustaste auf **[!UICONTROL Insight.cfg (modified)]** Klicken Sie oben im Fenster auf **[!UICONTROL Save as Insight.cfg]**.

**Hinzufügen neuer Server**

1. Im [!DNL Insight.cfg] Fenster, Rechtsklick **[!UICONTROL Servers]** und klicken Sie auf **[!UICONTROL Add new child]** > **[!UICONTROL Server]**.

   ![](assets/cfg_Workstation_AddServer.png)

1. Vervollständigen oder ändern Sie die Serverparameter, um der Data Workbench Zugriff auf den gewünschten Server zu gewähren. Detaillierte Beschreibungen der Parameter im Abschnitt [!DNL Insight.cfg] -Datei, siehe [Insight-Konfigurationsparameter](../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b).
1. Wiederholen Sie Schritt 1 und Schritt 2 für jeden Server, zu dem Sie eine Verbindung konfigurieren möchten.
1. Um Ihre Konfigurationseinstellungen zu speichern, klicken Sie mit der rechten Maustaste auf **[!UICONTROL Insight.cfg (modified)]** Klicken Sie oben im Fenster auf **[!UICONTROL Save as Insight.cfg]**.

Data Workbench versucht, mithilfe der von Ihnen angegebenen Einstellungen eine Verbindung zu den Servern herzustellen. Wenn eine Verbindung hergestellt wurde, wird ein grüner Knoten im [!DNL Servers Manager] wie unten dargestellt. Wenn die Data Workbench keine Verbindung zum Server herstellen kann, wird ein roter Knoten angezeigt.

![](assets/vis_SysStat_RedGreenDots.png)
