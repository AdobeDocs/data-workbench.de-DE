---
description: Sie sollten Ihre Ereignisprotokolldateien regelmäßig überwachen, um Insight Server-Systemereignismeldungen zu verfolgen, die beim <yyyymmdd>-event.txt-Dateien, die sich standardmäßig im Ordner "Events"im Installationsordner von Insight Server befinden.
title: Überwachen administrativer Ereignisse (Insight Server)
uuid: 92d71478-0857-4af8-909c-0cf800b081f4
exl-id: e468a7d0-ed09-4367-88ce-b68964511e76
source-git-commit: 235b8816c7397ac1ab71df650a1d4c2d681b3b2d
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 1%

---

# Überwachen administrativer Ereignisse{#monitoring-administrative-events}

Sie sollten Ihre Ereignisprotokolldateien regelmäßig überwachen, um Insight Server-Systemereignismeldungen zu verfolgen, die beim `<YYYYMMDD>-event.txt` Dateien, die sich standardmäßig im Ordner &quot;Events&quot;im Installationsordner von Insight Server befinden.

**Empfohlene Häufigkeit:** Alle 5-10 Minuten

Sie können diese Ereignisse mithilfe der [!DNL Server Files Manager] in [!DNL Insight], Ihrem automatisierten Verwaltungstool, der [!DNL *-event.txt] -Dateien oder der Windows Event Viewer.

>[!NOTE]
>
>Die administrativen Ereignisprotokolle unterscheiden sich vollständig von Ihrem Windows-Ereignisprotokoll, enthalten jedoch einige der gleichen Ereignisse. Die administrativen Ereignisprotokolle enthalten nur Informationen zu [!DNL Insight Server] -Ereignisse.

**So zeigen Sie die Dateien &quot;events.txt&quot;über die[!DNL Server Files Manager]**

1. In [!DNL Insight]auf [!DNL Admin] > [!DNL Dataset and Profile] klicken Sie auf die **[!UICONTROL Servers Manager]** Miniaturansicht, um den Arbeitsbereich &quot;Server Manager&quot;zu öffnen.
1. Klicken Sie mit der rechten Maustaste auf das Symbol eines aktiven [!DNL Insight Server] und klicken Sie auf **[!UICONTROL Server Files]**.
1. Im [!DNL Server Files Manager]klicken **[!UICONTROL Events]** , um den Inhalt anzuzeigen.
1. Klicken Sie mit der rechten Maustaste auf das Häkchen im *Servername* neben der gewünschten Datei klicken und **[!UICONTROL Make Local]**. Neben dem Dateinamen wird im [!DNL Temp] Spalte.
1. Klicken Sie mit der rechten Maustaste auf das Häkchen im [!DNL Temp] Spalte und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. Die Ereignisdatei wird in einem neuen Fenster des Microsoft Windows Notepad angezeigt.

   ![Schritt-Info](assets/vis_FileManager_eventfile.png)

   Die [!DNL Server.log] in der Datei [!DNL Trace] -Ordner in [!DNL Insight Server] Das Installationsverzeichnis enthält detailliertere Protokollierungsinformationen.

**So zeigen Sie Ereignisse über den Windows Event Viewer an**

* Klicken Sie auf **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**.

**So ändern Sie den Ordner &quot;Administrative Events Log&quot;**

Konfigurationsdatei &quot;Administrative Event Logs&quot;, [!DNL Administrative Events Log.cfg], gibt den Ordner an, in dem die Ereignisprotokollierung ausgegeben wird.

1. In [!DNL Insight]auf [!DNL Admin] > [!DNL Dataset and Profile] klicken Sie auf die **[!UICONTROL Servers Manager]** Miniaturansicht, um den Arbeitsbereich &quot;Server Manager&quot;zu öffnen.

1. Klicken Sie mit der rechten Maustaste auf das Symbol der [!DNL Insight Server] Sie möchten konfigurieren und klicken Sie auf **[!UICONTROL Server Files]**.

1. Im [!DNL Server Files Manager]klicken **[!UICONTROL Components]** , um den Inhalt anzuzeigen. Die [!DNL Administrative Event Logs.cfg] -Datei befindet sich in diesem Verzeichnis.

1. Klicken Sie mit der rechten Maustaste auf das Häkchen im *Servername* Spalte für [!DNL Administrative Event Logs.cfg] und klicken Sie auf **[!UICONTROL Make Local]**. Ein Häkchen wird im [!DNL Temp] Spalte für [!DNL Administrative Event Logs.cfg].

1. Klicken Sie mit der rechten Maustaste auf das neu erstellte Häkchen im [!DNL Temp] Spalte und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. Im [!DNL Administrative Event Logs.cfg] Fenster, klicken Sie auf **[!UICONTROL component]** , um den Inhalt anzuzeigen. Der Standardpfad ist die [!DNL Events] -Ordner in [!DNL Insight Server] Installationsverzeichnis.

   ![](assets/cfg_adminevents_examplevalues.png)

1. Geben Sie im Parameter Pfad den Namen des Ordners ein, in den Sie Ereignisprotokollierungsdaten ausgeben möchten.
1. Speichern Sie Ihre Änderungen auf dem Server, indem Sie Folgendes ausführen:

   1. Rechtsklick **[!UICONTROL (modified)]** Klicken Sie oben im Fenster auf **[!UICONTROL Save]**.
   1. Im [!DNL Server Files Manager]klicken Sie mit der rechten Maustaste auf das Häkchen für die Datei im [!DNL Temp] und wählen Sie **[!UICONTROL Save to]** > **[!UICONTROL server name]**.
