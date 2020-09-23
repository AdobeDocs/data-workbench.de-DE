---
description: Sie sollten Ihre Ereignis-Protokolldateien regelmäßig überwachen, um Systemmeldungen von Insight Server zu verfolgen, die bei den standardmäßig im Installationsordner von Insight Server im Ordner "Ereignisses"befindlichen Ereignis.txt-Dateien protokolliert werden.
solution: Analytics
title: Überwachen administrativer Ereignisse
uuid: 92d71478-0857-4af8-909c-0cf800b081f4
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '395'
ht-degree: 2%

---


# Überwachen administrativer Ereignisse{#monitoring-administrative-events}

Sie sollten Ihre Ereignis-Protokolldateien regelmäßig überwachen, um Systemmeldungen von Insight Server zu verfolgen, die standardmäßig im Installationsordner von Insight Server im Ordner &quot;Ereignisses&quot;bei den `<YYYYMMDD>-event.txt` Ereignissen protokolliert werden.

**Empfohlene Häufigkeit:** Alle 5-10 Minuten

Sie können diese Ereignisse mit dem [!DNL Server Files Manager] in, Ihrem automatisierten Verwaltungstool, den [!DNL Insight][!DNL *-event.txt] Dateien oder dem Windows Ereignis Viewer überwachen.

>[!NOTE]
>
>Die Verwaltungs-Ereignis-Protokolle sind vollständig vom Windows-Ereignis-Protokoll getrennt, enthalten jedoch einige der gleichen Ereignis. Die Ereignis-Protokolle für Administratoren enthalten nur Informationen zu [!DNL Insight Server] Ereignissen.

**So Ansicht Sie die Ereignisses.txt-Dateien über[!DNL Server Files Manager]**

1. Klicken Sie [!DNL Insight]auf der Registerkarte [!DNL Admin] > [!DNL Dataset and Profile] auf die **[!UICONTROL Servers Manager]** Miniaturansicht, um den Arbeitsbereich &quot;Server Manager&quot;zu öffnen.
1. Klicken Sie mit der rechten Maustaste auf das Symbol eines aktiven Elements [!DNL Insight Server] und klicken Sie auf **[!UICONTROL Server Files]**.
1. Klicken Sie im [!DNL Server Files Manager]Fenster auf , **[!UICONTROL Events]** um den Inhalt der Datei Ansicht.
1. Klicken Sie mit der rechten Maustaste auf das Häkchen in der Spalte *Servername* neben der gewünschten Datei und klicken Sie auf **[!UICONTROL Make Local]**. Neben dem Dateinamen in der [!DNL Temp] Spalte wird ein Häkchen angezeigt.
1. Klicken Sie mit der rechten Maustaste auf das Häkchen in der [!DNL Temp] Spalte und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. Die Ereignis-Datei wird in einem neuen Microsoft Windows Notepad-Fenster angezeigt.

   ![Schritt-Info](assets/vis_FileManager_eventfile.png)

   Die [!DNL Server.log] Datei im [!DNL Trace] Ordner im [!DNL Insight Server] Installationsordner enthält detailliertere Protokollinformationen.

**So Ansicht von Ereignissen über den Windows Ereignis Viewer**

* Klicken Sie auf **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**.

**So ändern Sie den Protokollordner für administrative Ereignisse**

Die Konfigurationsdatei &quot;Administrative Ereignis Logs&quot; [!DNL Administrative Events Log.cfg]gibt den Ordner an, in dem die Ereignis-Protokollierung ausgegeben wird.

1. Klicken Sie [!DNL Insight]auf der Registerkarte [!DNL Admin] > [!DNL Dataset and Profile] auf die **[!UICONTROL Servers Manager]** Miniaturansicht, um den Arbeitsbereich &quot;Server Manager&quot;zu öffnen.

1. Klicken Sie mit der rechten Maustaste auf das Symbol des zu konfigurierenden [!DNL Insight Server] Objekts und klicken Sie auf **[!UICONTROL Server Files]**.

1. Klicken Sie im [!DNL Server Files Manager]Fenster auf , **[!UICONTROL Components]** um den Inhalt der Datei Ansicht. Die [!DNL Administrative Event Logs.cfg] Datei befindet sich in diesem Ordner.

1. Klicken Sie mit der rechten Maustaste auf das Häkchen in der Spalte *Servername* für [!DNL Administrative Event Logs.cfg] und klicken Sie auf **[!UICONTROL Make Local]**. In der [!DNL Temp] Spalte für wird ein Häkchen angezeigt [!DNL Administrative Event Logs.cfg].

1. Klicken Sie mit der rechten Maustaste auf das neu erstellte Häkchen in der [!DNL Temp] Spalte und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. Klicken Sie im [!DNL Administrative Event Logs.cfg] Fenster auf **[!UICONTROL component]** , um den Inhalt des Fensters Ansicht. Der Standardpfad ist der [!DNL Events] Ordner im [!DNL Insight Server] Installationsordner.

   ![](assets/cfg_adminevents_examplevalues.png)

1. Geben Sie im Parameter &quot;Path&quot;den Namen des Ordners ein, in den Sie Ereignis-Protokolldaten ausgeben möchten.
1. Speichern Sie Ihre Änderungen auf dem Server, indem Sie folgende Schritte ausführen:

   1. Klicken Sie mit der rechten Maustaste **[!UICONTROL (modified)]** am oberen Rand des Fensters und klicken Sie auf **[!UICONTROL Save]**.
   1. Klicken Sie in der [!DNL Server Files Manager]Spalte mit der rechten Maustaste auf das Häkchen für die Datei in der [!DNL Temp] Spalte und wählen Sie **[!UICONTROL Save to]** > **[!UICONTROL server name]**.

