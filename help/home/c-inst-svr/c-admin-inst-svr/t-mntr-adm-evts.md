---
description: Sie sollten Ihre Ereignisprotokolldateien regelmäßig überwachen, um Insight Server-Systemereignismeldungen zu verfolgen, die in den Dateien <JJJJMMTT>-event.txt protokolliert werden, die sich standardmäßig im Ordner "Events"im Installationsordner von Insight Server befinden.
title: Überwachen administrativer Ereignisse
uuid: 92d71478-0857-4af8-909c-0cf800b081f4
exl-id: e468a7d0-ed09-4367-88ce-b68964511e76
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '395'
ht-degree: 2%

---

# Überwachen administrativer Ereignisse{#monitoring-administrative-events}

Sie sollten Ihre Ereignisprotokolldateien regelmäßig überwachen, um Insight Server-Systemereignismeldungen zu verfolgen, die in den `<YYYYMMDD>-event.txt` -Dateien protokolliert werden, die sich standardmäßig im Ordner &quot;Events&quot;im Installationsordner von Insight Server befinden.

**Empfohlene Häufigkeit:** Alle 5-10 Minuten

Sie können diese Ereignisse mithilfe von [!DNL Server Files Manager] in [!DNL Insight], Ihrem automatisierten Verwaltungstool, den [!DNL *-event.txt]-Dateien oder dem Windows Event Viewer überwachen.

>[!NOTE]
>
>Die administrativen Ereignisprotokolle unterscheiden sich vollständig von Ihrem Windows-Ereignisprotokoll, enthalten jedoch einige der gleichen Ereignisse. Die administrativen Ereignisprotokolle enthalten nur Informationen zu [!DNL Insight Server] -Ereignissen.

**So zeigen Sie die Dateien &quot;events.txt&quot;über die[!DNL Server Files Manager]**

1. Klicken Sie in [!DNL Insight] auf der Registerkarte [!DNL Admin] > [!DNL Dataset and Profile] auf die Miniaturansicht **[!UICONTROL Servers Manager]** , um den Arbeitsbereich &quot;Server Manager&quot;zu öffnen.
1. Klicken Sie mit der rechten Maustaste auf das Symbol eines aktiven [!DNL Insight Server] und klicken Sie auf **[!UICONTROL Server Files]**.
1. Klicken Sie in [!DNL Server Files Manager] auf **[!UICONTROL Events]** , um den Inhalt anzuzeigen.
1. Klicken Sie mit der rechten Maustaste auf das Häkchen in der Spalte *Servername* neben der gewünschten Datei und klicken Sie auf **[!UICONTROL Make Local]**. Neben dem Dateinamen wird in der Spalte [!DNL Temp] ein Häkchen angezeigt.
1. Klicken Sie mit der rechten Maustaste auf das Häkchen in der Spalte [!DNL Temp] und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. Die Ereignisdatei wird in einem neuen Fenster von Microsoft Windows Notepad angezeigt.

   ![Schritt-Info](assets/vis_FileManager_eventfile.png)

   Die Datei [!DNL Server.log] im Ordner [!DNL Trace] im Installationsverzeichnis [!DNL Insight Server] enthält detailliertere Protokollinformationen.

**So zeigen Sie Ereignisse über den Windows Event Viewer an**

* Klicken Sie auf **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**.

**So ändern Sie den Ordner &quot;Administrative Events Log&quot;**

Die Konfigurationsdatei &quot;Administrative Event Logs&quot;, [!DNL Administrative Events Log.cfg], gibt den Ordner an, in dem die Ereignisprotokollierung ausgegeben wird.

1. Klicken Sie in [!DNL Insight] auf der Registerkarte [!DNL Admin] > [!DNL Dataset and Profile] auf die Miniaturansicht **[!UICONTROL Servers Manager]** , um den Arbeitsbereich &quot;Server Manager&quot;zu öffnen.

1. Klicken Sie mit der rechten Maustaste auf das Symbol des zu konfigurierenden [!DNL Insight Server] und klicken Sie auf **[!UICONTROL Server Files]**.

1. Klicken Sie in [!DNL Server Files Manager] auf **[!UICONTROL Components]** , um den Inhalt anzuzeigen. Die Datei [!DNL Administrative Event Logs.cfg] befindet sich in diesem Verzeichnis.

1. Klicken Sie mit der rechten Maustaste auf das Häkchen in der Spalte *Servername* für [!DNL Administrative Event Logs.cfg] und klicken Sie auf **[!UICONTROL Make Local]**. In der Spalte [!DNL Temp] für [!DNL Administrative Event Logs.cfg] wird ein Häkchen angezeigt.

1. Klicken Sie mit der rechten Maustaste auf das neu erstellte Häkchen in der Spalte [!DNL Temp] und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. Klicken Sie im Fenster [!DNL Administrative Event Logs.cfg] auf **[!UICONTROL component]** , um den Inhalt anzuzeigen. Der Standardpfad ist der Ordner [!DNL Events] im Installationsverzeichnis von [!DNL Insight Server].

   ![](assets/cfg_adminevents_examplevalues.png)

1. Geben Sie im Parameter Pfad den Namen des Ordners ein, in den Sie Ereignisprotokollierungsdaten ausgeben möchten.
1. Speichern Sie Ihre Änderungen auf dem Server, indem Sie Folgendes ausführen:

   1. Klicken Sie oben im Fenster mit der rechten Maustaste auf **[!UICONTROL (modified)]** und klicken Sie auf **[!UICONTROL Save]**.
   1. Klicken Sie in der Spalte [!DNL Server Files Manager] mit der rechten Maustaste auf das Häkchen für die Datei in der Spalte [!DNL Temp] und wählen Sie **[!UICONTROL Save to]** > **[!UICONTROL server name]** aus.
