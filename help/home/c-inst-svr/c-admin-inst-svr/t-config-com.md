---
description: Die Kommunikationskonfigurationsdatei "Communications.cfg"enthält die Netzwerkeinstellungen des Insight-Servers und den Pfad zur Datei "Zugriffskontrolle.cfg".
title: Konfigurieren der Kommunikation
uuid: 04d08206-17b1-4348-a945-0c907c9a494c
exl-id: af5e788e-8904-4c68-b02a-c95b523b076d
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 3%

---

# Konfigurieren der Kommunikation{#configuring-communications}

Die Kommunikationskonfigurationsdatei &quot;Communications.cfg&quot;enthält die Netzwerkeinstellungen des Insight-Servers und den Pfad zur Datei &quot;Zugriffskontrolle.cfg&quot;.

Diese Einstellungen helfen Ihnen, eine Verbindung zu [!DNL Insight Server] herzustellen.

**Empfohlene Häufigkeit:** Nur bei Bedarf

**So ändern Sie die Kommunikationseinstellungen in[!DNL Insight]**

1. Klicken Sie in [!DNL Insight] auf der Registerkarte [!DNL Admin] > [!DNL Dataset and Profile] auf die Miniaturansicht **[!UICONTROL Servers Manager]**, um den Arbeitsbereich &quot;Server Manager&quot;zu öffnen.
1. Klicken Sie mit der rechten Maustaste auf das Symbol des zu konfigurierenden [!DNL Insight Server] und klicken Sie auf **[!UICONTROL Server Files]**.
1. Klicken Sie in [!DNL Server Files Manager] auf **[!UICONTROL Components]**, um den Inhalt Ansicht. Die Datei [!DNL Communications.cfg] befindet sich in diesem Verzeichnis.
1. Klicken Sie mit der rechten Maustaste auf das Häkchen in der Spalte *Servername* für [!DNL Communications.cfg] und klicken Sie auf **[!UICONTROL Make Local]**. In der Spalte [!DNL Temp] für [!DNL Communications.cfg] wird ein Häkchen angezeigt.
1. Klicken Sie mit der rechten Maustaste auf das neu erstellte Häkchen in der Spalte [!DNL Temp] und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. Klicken Sie im Fenster [!DNL Communications.cfg] auf **[!UICONTROL component]**, um den Inhalt Ansicht.
1. Ändern Sie die Einstellungen nach Bedarf. Informationen zu den in dieser Datei verfügbaren Parametern finden Sie unter [Konfigurationseinstellungen für Kommunikation](../../../home/c-inst-svr/c-cfg-stgs-ref/c-comm-cfg-stgs.md#concept-aed00587c7a1432fb487bd154aaea6b1).

   ![Schritt-Info](assets/cfg_communications_examplevalues.png)

1. Speichern Sie Ihre Änderungen auf dem Server, indem Sie folgende Schritte ausführen:

   1. Klicken Sie mit der rechten Maustaste auf **[!UICONTROL (modified)]** oben im Fenster und klicken Sie auf **[!UICONTROL Save]**.

   1. Klicken Sie in der Spalte [!DNL Server Files Manager] mit der rechten Maustaste auf das Häkchen für die Datei in der Spalte [!DNL Temp] und wählen Sie **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]***.
