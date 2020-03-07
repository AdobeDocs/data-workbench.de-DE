---
description: Die DPU-Konfigurationsdatei DPU.cfg gibt verschiedene Leistungsparameter für Insight Server an.
solution: Insight
title: DPU.cfg konfigurieren
uuid: c348622b-7d4b-4cfa-a8f8-a07d91e440d5
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# DPU.cfg konfigurieren{#configuring-dpu-cfg}

Die DPU-Konfigurationsdatei DPU.cfg gibt verschiedene Leistungsparameter für Insight Server an.

Wie Sie diese Parameter einstellen, hängt von Ihrer Datensatzgröße und vielen anderen Faktoren ab. Wenden Sie sich an Adobe Consulting Services, um Hilfe zur Leistungsoptimierung zu erhalten.

**Empfohlene Häufigkeit:** Nur bei Bedarf

**So ändern Sie die[!DNL Insight Server]Leistungseinstellungen der DPU**

1. Klicken Sie [!DNL Insight]auf der Registerkarte [!DNL Admin] > [!DNL Dataset and Profile] auf die **[!UICONTROL Servers Manager]** Miniaturansicht, um den Arbeitsbereich &quot;Server Manager&quot;zu öffnen.
1. Klicken Sie mit der rechten Maustaste auf das Symbol des zu konfigurierenden [!DNL Insight Server] Objekts und klicken Sie auf **[!UICONTROL Server Files]**.
1. Klicken Sie im [!DNL Server Files Manager]Fenster auf **[!UICONTROL Components]** , um den Inhalt anzuzeigen. Die [!DNL DPU.cfg] Datei befindet sich in diesem Ordner.
1. Klicken Sie mit der rechten Maustaste auf das Häkchen in der Spalte *Servername* für [!DNL DPU.cfg] und klicken Sie auf **[!UICONTROL Make Local]**. In der [!DNL Temp] Spalte für wird ein Häkchen angezeigt [!DNL DPU.cfg].
1. Klicken Sie mit der rechten Maustaste auf das neu erstellte Häkchen in der [!DNL Temp] Spalte und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. Klicken Sie im [!DNL DPU.cfg] Fenster auf Komponente, um deren Inhalt anzuzeigen.
1. Ändern Sie bei Bedarf die Leistungs- und Pfadeinstellungen. Eine Liste der in dieser Datei verfügbaren Parameter finden Sie unter [DPU-Leistungseinstellungen](../../../home/c-inst-svr/c-cfg-stgs-ref/c-dpu-perf-stgs.md#concept-477c4c526de44bda84176e62266c3df1).

   >[!NOTE]
   >
   >Bitte wenden Sie sich an Adobe, bevor Sie die Parameter in dieser Datei ändern.

   ![](assets/cfg_DPU_egvalues.png)

1. Speichern Sie Ihre Änderungen auf dem Server, indem Sie folgende Schritte ausführen:

   1. Klicken Sie mit der rechten Maustaste **[!UICONTROL (modified)]** am oberen Rand des Fensters und klicken Sie auf **[!UICONTROL Save]**.

   1. Klicken Sie in der [!DNL Server Files Manager]Spalte mit der rechten Maustaste auf das Häkchen für die Datei und wählen Sie [!DNL Temp] > **[!UICONTROL Save to]** &lt; *>**[!UICONTROL server name]***.

