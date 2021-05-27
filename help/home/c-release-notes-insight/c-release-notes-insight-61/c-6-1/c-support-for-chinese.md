---
description: Die Data Workbench-Client-Anwendung unterstützt jetzt vereinfachtes Chinesisch.
title: Vereinfachte Chinesisch-Lokalisierung
uuid: ddf4eade-7c5f-4ccf-aa9f-dd8d109a059f
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '79'
ht-degree: 1%

---


# Vereinfachtes Chinesisch-Lokalisierung{#simplified-chinese-localization}

Die Data Workbench-Client-Anwendung unterstützt jetzt vereinfachtes Chinesisch.

**So installieren Sie Vereinfachtes Chinesisch**:

Bevor Sie [!DNL Insight.exe] und unterstützende Dateien konfigurieren, müssen Sie die Clientanwendung beenden.

1. Erstellen Sie einen Tastaturbefehl, der die Befehlszeileneinstellung an die Datei [!DNL insight.exe] übergibt.

   ```
   Insight.exe -zh-cn
   ```

1. Konfigurieren Sie [!DNL Insight.cfg], um Einzel- und Doppelbyte-Schriftzeichen zu unterstützen.

   Data Workbench unterstützt derzeit sowohl Englisch als auch Vereinfachtes Chinesisch. Sie können Schriftarten auswählen, um beide Sprachen zu unterstützen:

   ```
   Fonts = vector: 2 items 
   0 = string: SimSun 
   1 = string: Arial 
   ```

1. Erneut starten [!DNL Insight.exe].

