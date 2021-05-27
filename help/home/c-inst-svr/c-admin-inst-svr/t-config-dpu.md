---
description: Die DPU-Konfigurationsdatei DPU.cfg gibt verschiedene Leistungsparameter für Insight Server an.
title: Konfigurieren der Datei „DPU.cfg“
uuid: c348622b-7d4b-4cfa-a8f8-a07d91e440d5
exl-id: 55e4ea7f-fee3-4af7-9cbc-d121e79e6ab2
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 1%

---

# Konfigurieren der Datei „DPU.cfg“{#configuring-dpu-cfg}

Die DPU-Konfigurationsdatei DPU.cfg gibt verschiedene Leistungsparameter für Insight Server an.

Wie Sie diese Parameter festlegen, hängt von Ihrer Datensatzgröße und vielen anderen Faktoren ab. Wenden Sie sich an Adobe Consulting Services, um Hilfe bei der Leistungsoptimierung zu erhalten.

**Empfohlene Häufigkeit:** Nur bei Bedarf

**So ändern Sie die  [!DNL Insight Server] DPU-Leistungseinstellungen**

1. Klicken Sie in [!DNL Insight] auf der Registerkarte [!DNL Admin] > [!DNL Dataset and Profile] auf die Miniaturansicht **[!UICONTROL Servers Manager]** , um den Arbeitsbereich &quot;Server Manager&quot;zu öffnen.
1. Klicken Sie mit der rechten Maustaste auf das Symbol des zu konfigurierenden [!DNL Insight Server] und klicken Sie auf **[!UICONTROL Server Files]**.
1. Klicken Sie in [!DNL Server Files Manager] auf **[!UICONTROL Components]** , um den Inhalt anzuzeigen. Die Datei [!DNL DPU.cfg] befindet sich in diesem Verzeichnis.
1. Klicken Sie mit der rechten Maustaste auf das Häkchen in der Spalte *Servername* für [!DNL DPU.cfg] und klicken Sie auf **[!UICONTROL Make Local]**. In der Spalte [!DNL Temp] für [!DNL DPU.cfg] wird ein Häkchen angezeigt.
1. Klicken Sie mit der rechten Maustaste auf das neu erstellte Häkchen in der Spalte [!DNL Temp] und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. Klicken Sie im Fenster [!DNL DPU.cfg] auf Komponente , um den Inhalt anzuzeigen.
1. Ändern Sie bei Bedarf die Leistungs- und Pfadeinstellungen. Eine Liste der in dieser Datei verfügbaren Parameter finden Sie unter [DPU-Leistungseinstellungen](../../../home/c-inst-svr/c-cfg-stgs-ref/c-dpu-perf-stgs.md#concept-477c4c526de44bda84176e62266c3df1).

   >[!NOTE]
   >
   >Wenden Sie sich an die Adobe, bevor Sie einen der Parameter in dieser Datei ändern.

   ![](assets/cfg_DPU_egvalues.png)

1. Speichern Sie Ihre Änderungen auf dem Server, indem Sie Folgendes ausführen:

   1. Klicken Sie oben im Fenster mit der rechten Maustaste auf **[!UICONTROL (modified)]** und klicken Sie auf **[!UICONTROL Save]**.

   1. Klicken Sie in der Spalte [!DNL Server Files Manager] mit der rechten Maustaste auf das Häkchen für die Datei in der Spalte [!DNL Temp] und wählen Sie **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]***.
