---
description: Ein Berichtssatz ist eine Sammlung von Arbeitsbereichen, die Report Server basierend auf den in einer Konfigurationsdatei "Report.cfg"angegebenen Werten generiert.
title: Grundlagen zu Berichtssätzen
uuid: 421055d7-0cf0-4664-b944-327a254a97a4
exl-id: 95609a1a-e70c-41e2-ace3-0cb09f77705a
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '146'
ht-degree: 4%

---

# Grundlagen zu Berichtssätzen{#understanding-report-sets}

Ein Berichtssatz ist eine Sammlung von Arbeitsbereichen, die Report Server basierend auf den in einer Konfigurationsdatei &quot;Report.cfg&quot;angegebenen Werten generiert.

Im Installationsordner von [!DNL Insight] stellt jeder Unterordner im Ordner &lt;*Name des Arbeitsprofils*\Reports einen erstellten Berichtssatz dar. Jeder Berichtssatz verfügt über eine eigene [!DNL Report.cfg] -Konfigurationsdatei in diesem Unterordner.

>[!NOTE]
>
>In der Data Workbench [!DNL Profile Manager] werden Berichtssätze als Unterordner im Ordner [!DNL Reports] angezeigt. Weitere Informationen zu [!DNL Profile Manager] finden Sie im [Data Workbench-Benutzerhandbuch](https://experienceleague.adobe.com/docs/data-workbench/using/home.html#Data_Workbench_Help).

Durch Definition spezifischer Konfigurationseinstellungen für einen Berichtssatz in der Datei [!DNL Report.cfg] können Sie die Erstellung und Verteilung der Berichte planen, einschließlich der Empfänger, welche Berichte und in welchen Formaten.
