---
description: Die Konfigurationsdatei für Kommunikation, Communications.cfg, enthält Netzwerkeinstellungen für Insight Server und den Pfad zur Datei Access Control.cfg .
title: Konfigurieren der Kommunikation
uuid: 04d08206-17b1-4348-a945-0c907c9a494c
exl-id: af5e788e-8904-4c68-b02a-c95b523b076d
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 3%

---

# Konfigurieren der Kommunikation{#configuring-communications}

{{eol}}

Die Konfigurationsdatei für Kommunikation, Communications.cfg, enthält Netzwerkeinstellungen für Insight Server und den Pfad zur Datei Access Control.cfg .

Mithilfe dieser Einstellungen können Sie eine Verbindung zu [!DNL Insight Server].

**Empfohlene Häufigkeit:** Nur bei Bedarf

**So zeigen Sie die Kommunikationseinstellungen an und ändern sie in[!DNL Insight]**

1. In [!DNL Insight]auf [!DNL Admin] > [!DNL Dataset and Profile] klicken Sie auf die **[!UICONTROL Servers Manager]** Miniaturansicht, um den Arbeitsbereich &quot;Server Manager&quot;zu öffnen.
1. Klicken Sie mit der rechten Maustaste auf das Symbol der [!DNL Insight Server] Sie möchten konfigurieren und klicken Sie auf **[!UICONTROL Server Files]**.
1. Im [!DNL Server Files Manager]klicken **[!UICONTROL Components]** , um den Inhalt anzuzeigen. Die [!DNL Communications.cfg] -Datei befindet sich in diesem Verzeichnis.
1. Klicken Sie mit der rechten Maustaste auf das Häkchen im *Servername* Spalte für [!DNL Communications.cfg] und klicken Sie auf **[!UICONTROL Make Local]**. Ein Häkchen wird im [!DNL Temp] Spalte für [!DNL Communications.cfg].
1. Klicken Sie mit der rechten Maustaste auf das neu erstellte Häkchen im [!DNL Temp] Spalte und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. Im [!DNL Communications.cfg] Fenster, klicken Sie auf **[!UICONTROL component]** , um den Inhalt anzuzeigen.
1. Ändern Sie die Einstellungen nach Bedarf. Informationen zu den in dieser Datei verfügbaren Parametern finden Sie unter [Konfigurationseinstellungen für die Kommunikation](../../../home/c-inst-svr/c-cfg-stgs-ref/c-comm-cfg-stgs.md#concept-aed00587c7a1432fb487bd154aaea6b1).

   ![Schritt-Info](assets/cfg_communications_examplevalues.png)

1. Speichern Sie Ihre Änderungen auf dem Server, indem Sie Folgendes ausführen:

   1. Rechtsklick **[!UICONTROL (modified)]** Klicken Sie oben im Fenster auf **[!UICONTROL Save]**.

   1. Im [!DNL Server Files Manager]klicken Sie mit der rechten Maustaste auf das Häkchen für die Datei im [!DNL Temp] und wählen Sie **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.
