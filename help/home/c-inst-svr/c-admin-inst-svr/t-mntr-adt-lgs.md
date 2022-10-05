---
description: Audit-Protokolldateien verfolgen alle versucht Verbindungen zu Insight Server und unterbrechen diese, die jeweils im <yyyymmdd>-access.txt-Dateien, die sich standardmäßig im Ordner "Verfolgung"im Installationsordner von Insight Server befinden.
title: Überwachen von Auditprotokollen
uuid: 38af9328-3f72-48a4-a0de-bf7477fedc25
exl-id: 220330da-e5dc-4ac0-9b70-42b08ccb3577
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 4%

---

# Überwachen von Auditprotokollen{#monitoring-audit-logs}

{{eol}}

Audit-Protokolldateien verfolgen alle versucht Verbindungen zu Insight Server und unterbrechen diese, die jeweils im `<YYYYMMDD>-access.txt` Dateien, die sich standardmäßig im Ordner &quot;Verfolgung&quot;im Installationsordner von Insight Server befinden.

**Empfohlene Häufigkeit:** Täglich oder nach Bedarf zur Fehlerbehebung

Auditprotokolle können bei der Fehlerbehebung von Problemen beim Herstellen einer Verbindung zu sehr hilfreich sein. [!DNL Insight Server]. Sie können diese Protokolle mit Ihrem automatisierten Verwaltungstool überwachen oder die [!DNL access.txt] -Dateien direkt.

**So zeigen Sie access.txt-Dateien über die[!DNL Server Files Manager]**

1. In [!DNL Insight]auf [!DNL Admin] > [!DNL Dataset and Profile] klicken Sie auf die **[!UICONTROL Servers Manager]** Miniaturansicht, um den Arbeitsbereich &quot;Server Manager&quot;zu öffnen.
1. Klicken Sie mit der rechten Maustaste auf das Symbol eines aktiven [!DNL Insight Server] und klicken Sie auf **[!UICONTROL Server Files]**.
1. Im [!DNL Server Files Manager]klicken **[!UICONTROL Audit]** , um den Inhalt anzuzeigen.
1. Klicken Sie mit der rechten Maustaste auf das Häkchen im *Servername* neben der gewünschten Datei klicken und **[!UICONTROL Make Local]**. Neben dem Dateinamen wird im [!DNL Temp] Spalte.
1. Klicken Sie mit der rechten Maustaste auf das neue Häkchen im [!DNL Temp] Spalte und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. Das Auditprotokoll wird in einem neuen Fenster von Microsoft Windows Notepad angezeigt.

   ![Schritt-Info](assets/cfg_accesscontrol_accessFile.png)
