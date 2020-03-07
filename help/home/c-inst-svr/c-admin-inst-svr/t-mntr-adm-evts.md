---
description: Sie sollten Ihre Ereignisprotokolldateien regelmäßig überwachen, um Systemereignismeldungen von Insight Server zu verfolgen, die standardmäßig im Ordner "Events"des Installationsordners von Insight Server mit den Dateien "<JJJMMTT>-event.txt"protokolliert werden.
solution: Insight
title: Überwachen von Verwaltungsereignissen
uuid: 92d71478-0857-4af8-909c-0cf800b081f4
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Überwachen von Verwaltungsereignissen{#monitoring-administrative-events}

Sie sollten Ihre Ereignisprotokolldateien regelmäßig überwachen, um Systemereignismeldungen von Insight Server zu verfolgen, die standardmäßig im Installationsordner von Insight Server im Ordner &quot;Ereignisse&quot;bei den `<YYYYMMDD>-event.txt` Dateien protokolliert werden.

**Empfohlene Häufigkeit:** Alle 5-10 Minuten

Sie können diese Ereignisse mit dem [!DNL Server Files Manager] in, Ihrem automatisierten Verwaltungstool, den [!DNL Insight][!DNL *-event.txt] Dateien oder dem Windows-Ereignis-Viewer überwachen.

>[!NOTE]
>
>Die Verwaltungs-Ereignisprotokolle sind vollständig vom Windows-Ereignisprotokoll getrennt, enthalten jedoch einige der gleichen Ereignisse. Die Protokolle für administrative Ereignisse enthalten nur Informationen zu [!DNL Insight Server] Ereignissen.

**So zeigen Sie events.txt-Dateien über die[!DNL Server Files Manager]**

1. Klicken Sie [!DNL Insight]auf der Registerkarte [!DNL Admin] > [!DNL Dataset and Profile] auf die **[!UICONTROL Servers Manager]** Miniaturansicht, um den Arbeitsbereich &quot;Server Manager&quot;zu öffnen.
1. Klicken Sie mit der rechten Maustaste auf das Symbol eines aktiven Elements [!DNL Insight Server] und klicken Sie auf **[!UICONTROL Server Files]**.
1. Klicken Sie im [!DNL Server Files Manager]Fenster auf **[!UICONTROL Events]** , um den Inhalt anzuzeigen.
1. Klicken Sie mit der rechten Maustaste auf das Häkchen in der Spalte *Servername* neben der gewünschten Datei und klicken Sie auf **[!UICONTROL Make Local]**. Neben dem Dateinamen in der [!DNL Temp] Spalte wird ein Häkchen angezeigt.
1. Klicken Sie mit der rechten Maustaste auf das Häkchen in der [!DNL Temp] Spalte und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. Die Ereignisdatei wird in einem neuen Microsoft Windows Notepad-Fenster angezeigt.

   ![Schritt-Info](assets/vis_FileManager_eventfile.png)

   Die [!DNL Server.log] Datei im [!DNL Trace] Ordner im [!DNL Insight Server] Installationsordner enthält detailliertere Protokollinformationen.

**So zeigen Sie Ereignisse über den Windows-Ereignis-Viewer an**

* Klicken Sie auf **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**.

**So ändern Sie den Protokollordner für administrative Ereignisse**

Die Konfigurationsdatei &quot;Administrative Event Logs&quot;gibt [!DNL Administrative Events Log.cfg]den Ordner an, in dem die Ereignisprotokollierung ausgegeben wird.

1. Klicken Sie [!DNL Insight]auf der Registerkarte [!DNL Admin] > [!DNL Dataset and Profile] auf die **[!UICONTROL Servers Manager]** Miniaturansicht, um den Arbeitsbereich &quot;Server Manager&quot;zu öffnen.

1. Klicken Sie mit der rechten Maustaste auf das Symbol des zu konfigurierenden [!DNL Insight Server] Objekts und klicken Sie auf **[!UICONTROL Server Files]**.

1. Klicken Sie im [!DNL Server Files Manager]Fenster auf **[!UICONTROL Components]** , um den Inhalt anzuzeigen. Die [!DNL Administrative Event Logs.cfg] Datei befindet sich in diesem Ordner.

1. Klicken Sie mit der rechten Maustaste auf das Häkchen in der Spalte *Servername* für [!DNL Administrative Event Logs.cfg] und klicken Sie auf **[!UICONTROL Make Local]**. In der [!DNL Temp] Spalte für wird ein Häkchen angezeigt [!DNL Administrative Event Logs.cfg].

1. Klicken Sie mit der rechten Maustaste auf das neu erstellte Häkchen in der [!DNL Temp] Spalte und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. Klicken Sie im [!DNL Administrative Event Logs.cfg] Fenster auf **[!UICONTROL component]** , um den Inhalt anzuzeigen. Der Standardpfad ist der [!DNL Events] Ordner im [!DNL Insight Server] Installationsordner.

   ![](assets/cfg_adminevents_examplevalues.png)

1. Geben Sie im Parameter &quot;Path&quot;den Namen des Ordners ein, in den die Ereignisprotokolldaten ausgegeben werden sollen.
1. Speichern Sie Ihre Änderungen auf dem Server, indem Sie folgende Schritte ausführen:

   1. Klicken Sie mit der rechten Maustaste **[!UICONTROL (modified)]** am oberen Rand des Fensters und klicken Sie auf **[!UICONTROL Save]**.
   1. Klicken Sie in der [!DNL Server Files Manager]Spalte mit der rechten Maustaste auf das Häkchen für die Datei in der [!DNL Temp] Spalte und wählen Sie **[!UICONTROL Save to]** > **[!UICONTROL server name]**.

