---
description: Prüfprotokolldateien verfolgen alle versuchten Verbindungen mit dem Insight-Server und deren Entfernung vom Server. Jede dieser Verbindungen ist in den Dateien "<JJJMMTT>-access.txt"protokolliert, die sich standardmäßig im Ordner "Audit"im Installationsordner von Insight Server befinden.
solution: Insight
title: Prüfprotokolle überwachen
uuid: 38af9328-3f72-48a4-a0de-bf7477fedc25
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Prüfprotokolle überwachen{#monitoring-audit-logs}

Prüfprotokolldateien verfolgen alle versuchten Verbindungen zu Insight Server und deren Entfernung vom Server, die standardmäßig im Ordner &quot;Audit&quot;des Installationsordners von Insight Server angemeldet sind und sich in den `<YYYYMMDD>-access.txt` Dateien befinden.

**Empfohlene Häufigkeit:** Täglich oder nach Bedarf zur Fehlerbehebung

Prüfprotokolle können bei der Fehlerbehebung von Verbindungsproblemen sehr hilfreich sein [!DNL Insight Server]. Sie können diese Protokolle mit Ihrem automatisierten Verwaltungstool oder durch direkte Anzeige der [!DNL access.txt] Dateien überwachen.

**So zeigen Sie die &quot;access.txt&quot;-Dateien über[!DNL Server Files Manager]**

1. Klicken Sie [!DNL Insight]auf der Registerkarte [!DNL Admin] > [!DNL Dataset and Profile] auf die **[!UICONTROL Servers Manager]** Miniaturansicht, um den Arbeitsbereich &quot;Server Manager&quot;zu öffnen.
1. Klicken Sie mit der rechten Maustaste auf das Symbol eines aktiven Elements [!DNL Insight Server] und klicken Sie auf **[!UICONTROL Server Files]**.
1. Klicken Sie im [!DNL Server Files Manager]Fenster auf **[!UICONTROL Audit]** , um den Inhalt anzuzeigen.
1. Klicken Sie mit der rechten Maustaste auf das Häkchen in der Spalte *Servername* neben der gewünschten Datei und klicken Sie auf **[!UICONTROL Make Local]**. Neben dem Dateinamen in der [!DNL Temp] Spalte wird ein Häkchen angezeigt.
1. Klicken Sie mit der rechten Maustaste auf das neue Häkchen in der [!DNL Temp] Spalte und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. Das Prüfprotokoll wird in einem neuen Fenster von Microsoft Windows Notepad angezeigt.

   ![Schritt-Info](assets/cfg_accesscontrol_accessFile.png)

