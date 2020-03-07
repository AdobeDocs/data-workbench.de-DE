---
description: Die Datei "Communications configuration", Communications.cfg, enthält die Netzwerkeinstellungen des Insight-Servers und den Pfad zur Datei "Access Control.cfg".
solution: Insight
title: Konfigurieren von Mitteilungen
uuid: 04d08206-17b1-4348-a945-0c907c9a494c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Konfigurieren von Mitteilungen{#configuring-communications}

Die Datei &quot;Communications configuration&quot;, Communications.cfg, enthält die Netzwerkeinstellungen des Insight-Servers und den Pfad zur Datei &quot;Access Control.cfg&quot;.

Diese Einstellungen helfen Ihnen, eine Verbindung herzustellen [!DNL Insight Server].

**Empfohlene Häufigkeit:** Nur bei Bedarf

**So zeigen Sie die Kommunikationseinstellungen an unter[!DNL Insight]**

1. Klicken Sie [!DNL Insight]auf der Registerkarte [!DNL Admin] > [!DNL Dataset and Profile] auf die **[!UICONTROL Servers Manager]** Miniaturansicht, um den Arbeitsbereich &quot;Server Manager&quot;zu öffnen.
1. Klicken Sie mit der rechten Maustaste auf das Symbol des zu konfigurierenden [!DNL Insight Server] Objekts und klicken Sie auf **[!UICONTROL Server Files]**.
1. Klicken Sie im [!DNL Server Files Manager]Fenster auf **[!UICONTROL Components]** , um den Inhalt anzuzeigen. Die [!DNL Communications.cfg] Datei befindet sich in diesem Ordner.
1. Klicken Sie mit der rechten Maustaste auf das Häkchen in der Spalte *Servername* für [!DNL Communications.cfg] und klicken Sie auf **[!UICONTROL Make Local]**. In der [!DNL Temp] Spalte für wird ein Häkchen angezeigt [!DNL Communications.cfg].
1. Klicken Sie mit der rechten Maustaste auf das neu erstellte Häkchen in der [!DNL Temp] Spalte und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. Klicken Sie im [!DNL Communications.cfg] Fenster auf **[!UICONTROL component]** , um den Inhalt anzuzeigen.
1. Ändern Sie die Einstellungen nach Bedarf. Informationen zu den in dieser Datei verfügbaren Parametern finden Sie unter [Einstellungen](../../../home/c-inst-svr/c-cfg-stgs-ref/c-comm-cfg-stgs.md#concept-aed00587c7a1432fb487bd154aaea6b1)der Kommunikationskonfiguration.

   ![Schritt-Info](assets/cfg_communications_examplevalues.png)

1. Speichern Sie Ihre Änderungen auf dem Server, indem Sie folgende Schritte ausführen:

   1. Klicken Sie mit der rechten Maustaste **[!UICONTROL (modified)]** am oberen Rand des Fensters und klicken Sie auf **[!UICONTROL Save]**.

   1. Klicken Sie in der [!DNL Server Files Manager]Spalte mit der rechten Maustaste auf das Häkchen für die Datei und wählen Sie [!DNL Temp] > **[!UICONTROL Save to]** &lt; *>**[!UICONTROL server name]***.

