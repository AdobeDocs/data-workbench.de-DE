---
description: Sie sollten Ihre Ereignis-Protokolldateien regelmäßig überwachen, um Systemmeldungen von Insight Server zu verfolgen, die bei den standardmäßig im Installationsordner von Insight Server im Ordner "Ereignisses"befindlichen Ereignis.txt-Dateien protokolliert werden.
title: Überwachen administrativer Ereignisse
uuid: 92d71478-0857-4af8-909c-0cf800b081f4
exl-id: e468a7d0-ed09-4367-88ce-b68964511e76
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '395'
ht-degree: 2%

---

# Überwachen administrativer Ereignisse{#monitoring-administrative-events}

Sie sollten Ihre Ereignis-Protokolldateien regelmäßig überwachen, um Systemmeldungen von Insight Server zu verfolgen, die standardmäßig im Installationsordner von Insight Server im Ordner &quot;Ereignisses&quot;bei den `<YYYYMMDD>-event.txt`-Ereignissen protokolliert werden.

**Empfohlene Häufigkeit:** alle 5-10 Minuten

Sie können diese Ereignisse mit den [!DNL Server Files Manager] in [!DNL Insight], Ihrem automatisierten Verwaltungstool, den [!DNL *-event.txt]-Dateien oder dem Windows Ereignis Viewer überwachen.

>[!NOTE]
>
>Die Verwaltungs-Ereignis-Protokolle sind vollständig vom Windows-Ereignis-Protokoll getrennt, enthalten jedoch einige der gleichen Ereignis. Die Ereignis-Protokolle für Administratoren enthalten nur Informationen zu [!DNL Insight Server]-Ereignissen.

**So Ansicht Sie die Ereignisses.txt-Dateien über[!DNL Server Files Manager]**

1. Klicken Sie in [!DNL Insight] auf der Registerkarte [!DNL Admin] > [!DNL Dataset and Profile] auf die Miniaturansicht **[!UICONTROL Servers Manager]**, um den Arbeitsbereich &quot;Server Manager&quot;zu öffnen.
1. Klicken Sie mit der rechten Maustaste auf das Symbol eines aktiven [!DNL Insight Server] und klicken Sie auf **[!UICONTROL Server Files]**.
1. Klicken Sie in [!DNL Server Files Manager] auf **[!UICONTROL Events]**, um den Inhalt Ansicht.
1. Klicken Sie mit der rechten Maustaste auf das Häkchen in der Spalte *Servername* neben der gewünschten Datei und klicken Sie auf **[!UICONTROL Make Local]**. Neben dem Dateinamen wird in der Spalte [!DNL Temp] ein Häkchen angezeigt.
1. Klicken Sie mit der rechten Maustaste auf das Häkchen in der Spalte [!DNL Temp] und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. Die Ereignis-Datei wird in einem neuen Microsoft Windows Notepad-Fenster angezeigt.

   ![Schritt-Info](assets/vis_FileManager_eventfile.png)

   Die Datei [!DNL Server.log] im Ordner [!DNL Trace] im Installationsordner [!DNL Insight Server] enthält detailliertere Protokollinformationen.

**So Ansicht von Ereignissen über den Windows Ereignis Viewer**

* Klicken Sie auf **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**.

**So ändern Sie den Protokollordner für administrative Ereignisse**

Die Konfigurationsdatei [!DNL Administrative Events Log.cfg] &quot;Administrative Ereignis Logs&quot;gibt den Ordner an, in dem die Ereignis-Protokollierung ausgegeben wird.

1. Klicken Sie in [!DNL Insight] auf der Registerkarte [!DNL Admin] > [!DNL Dataset and Profile] auf die Miniaturansicht **[!UICONTROL Servers Manager]**, um den Arbeitsbereich &quot;Server Manager&quot;zu öffnen.

1. Klicken Sie mit der rechten Maustaste auf das Symbol des zu konfigurierenden [!DNL Insight Server] und klicken Sie auf **[!UICONTROL Server Files]**.

1. Klicken Sie in [!DNL Server Files Manager] auf **[!UICONTROL Components]**, um den Inhalt Ansicht. Die Datei [!DNL Administrative Event Logs.cfg] befindet sich in diesem Verzeichnis.

1. Klicken Sie mit der rechten Maustaste auf das Häkchen in der Spalte *Servername* für [!DNL Administrative Event Logs.cfg] und klicken Sie auf **[!UICONTROL Make Local]**. In der Spalte [!DNL Temp] für [!DNL Administrative Event Logs.cfg] wird ein Häkchen angezeigt.

1. Klicken Sie mit der rechten Maustaste auf das neu erstellte Häkchen in der Spalte [!DNL Temp] und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. Klicken Sie im Fenster [!DNL Administrative Event Logs.cfg] auf **[!UICONTROL component]**, um den Inhalt Ansicht. Der Standardpfad ist der Ordner [!DNL Events] im Installationsordner [!DNL Insight Server].

   ![](assets/cfg_adminevents_examplevalues.png)

1. Geben Sie im Parameter &quot;Path&quot;den Namen des Ordners ein, in den Sie Ereignis-Protokolldaten ausgeben möchten.
1. Speichern Sie Ihre Änderungen auf dem Server, indem Sie folgende Schritte ausführen:

   1. Klicken Sie mit der rechten Maustaste auf **[!UICONTROL (modified)]** oben im Fenster und klicken Sie auf **[!UICONTROL Save]**.
   1. Klicken Sie in der Spalte [!DNL Server Files Manager] mit der rechten Maustaste auf das Häkchen für die Datei in der Spalte [!DNL Temp] und wählen Sie **[!UICONTROL Save to]** > **[!UICONTROL server name]**.
