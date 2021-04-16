---
description: Prüfprotokolldateien verfolgen alle versuchten Verbindungen mit dem Insight-Server und deren Entfernung vom Server. Jede dieser Verbindungen ist in den Dateien "<JJJMMTT>-access.txt"protokolliert, die sich standardmäßig im Ordner "Audit"im Installationsordner von Insight Server befinden.
title: Überwachen von Auditprotokollen
uuid: 38af9328-3f72-48a4-a0de-bf7477fedc25
exl-id: 220330da-e5dc-4ac0-9b70-42b08ccb3577
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 4%

---

# Überwachen von Auditprotokollen{#monitoring-audit-logs}

Prüfprotokolldateien verfolgen alle versuchten Verbindungen zu Insight Server und deren Entfernung vom Server. Jede dieser Verbindungen ist in den `<YYYYMMDD>-access.txt`-Dateien protokolliert, die sich standardmäßig im Ordner &quot;Audit&quot;im Installationsordner von Insight Server befinden.

**Empfohlene Häufigkeit:** Täglich oder nach Bedarf zur Fehlerbehebung

Prüfprotokolle können bei der Fehlerbehebung von Problemen, die mit [!DNL Insight Server] verbunden sind, sehr hilfreich sein. Sie können diese Protokolle mit Ihrem automatisierten Verwaltungstool oder durch direkte Anzeige der [!DNL access.txt]-Dateien überwachen.

**So erstellen Sie die Ansicht &quot;access.txt&quot;[!DNL Server Files Manager]**

1. Klicken Sie in [!DNL Insight] auf der Registerkarte [!DNL Admin] > [!DNL Dataset and Profile] auf die Miniaturansicht **[!UICONTROL Servers Manager]**, um den Arbeitsbereich &quot;Server Manager&quot;zu öffnen.
1. Klicken Sie mit der rechten Maustaste auf das Symbol eines aktiven [!DNL Insight Server] und klicken Sie auf **[!UICONTROL Server Files]**.
1. Klicken Sie in [!DNL Server Files Manager] auf **[!UICONTROL Audit]**, um den Inhalt Ansicht.
1. Klicken Sie mit der rechten Maustaste auf das Häkchen in der Spalte *Servername* neben der gewünschten Datei und klicken Sie auf **[!UICONTROL Make Local]**. Neben dem Dateinamen wird in der Spalte [!DNL Temp] ein Häkchen angezeigt.
1. Klicken Sie mit der rechten Maustaste auf das neue Häkchen in der Spalte [!DNL Temp] und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. Das Prüfprotokoll wird in einem neuen Fenster von Microsoft Windows Notepad angezeigt.

   ![Schritt-Info](assets/cfg_accesscontrol_accessFile.png)
