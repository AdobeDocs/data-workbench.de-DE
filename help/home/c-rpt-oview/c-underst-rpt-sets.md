---
description: Ein Berichtssatz ist eine Sammlung von Arbeitsbereichen, die Report Server basierend auf den in einer Konfigurationsdatei "Report.cfg"angegebenen Werten generiert.
title: Grundlagen zu Berichtssätzen
uuid: 421055d7-0cf0-4664-b944-327a254a97a4
exl-id: 95609a1a-e70c-41e2-ace3-0cb09f77705a
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '146'
ht-degree: 4%

---

# Grundlagen zu Berichtssätzen{#understanding-report-sets}

{{eol}}

Ein Berichtssatz ist eine Sammlung von Arbeitsbereichen, die Report Server basierend auf den in einer Konfigurationsdatei &quot;Report.cfg&quot;angegebenen Werten generiert.

In [!DNL Insight] Installationsordner: Jeder Unterordner innerhalb des &lt;*Name des Arbeitsprofils*>\Berichte -Ordner stellt einen erstellten Berichtssatz dar. Jeder Berichtssatz verfügt über eine eigene [!DNL Report.cfg] Konfigurationsdatei innerhalb dieses Unterordners.

>[!NOTE]
>
>Im [!DNL Profile Manager] in der Data Workbench werden Berichtssätze als Unterordner innerhalb der [!DNL Reports] Ordner. Weitere Informationen zum [!DNL Profile Manager], siehe [Data Workbench-Benutzerhandbuch](https://experienceleague.adobe.com/docs/data-workbench/using/home.html#Data_Workbench_Help).

Indem Sie bestimmte Konfigurationseinstellungen für einen Berichtssatz in seiner [!DNL Report.cfg] -Datei können Sie die Erstellung und Verteilung der Berichte planen, einschließlich der Empfänger, welcher Berichte und welcher Formate.
