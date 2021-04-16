---
description: Die Data Workbench-Client-Anwendung unterstützt jetzt vereinfachtes Chinesisch.
title: Vereinfachte chinesische lokale Anpassung
uuid: ddf4eade-7c5f-4ccf-aa9f-dd8d109a059f
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '79'
ht-degree: 1%

---


# Vereinfachte chinesische lokale Anpassung{#simplified-chinese-localization}

Die Data Workbench-Client-Anwendung unterstützt jetzt vereinfachtes Chinesisch.

**So installieren Sie vereinfachtes Chinesisch**:

Bevor Sie [!DNL Insight.exe] und unterstützende Dateien konfigurieren, müssen Sie die Clientanwendung beenden.

1. Erstellen Sie eine Verknüpfung, die die Befehlszeileneinstellung an die Datei [!DNL insight.exe] übergibt.

   ```
   Insight.exe -zh-cn
   ```

1. Konfigurieren Sie [!DNL Insight.cfg], um Einzel- und Dublette-Byte-Schriftzeichen zu unterstützen.

   Data Workbench unterstützt derzeit sowohl Englisch als auch vereinfachtes Chinesisch. Sie können Schriftarten auswählen, um beide Sprachen zu unterstützen:

   ```
   Fonts = vector: 2 items 
   0 = string: SimSun 
   1 = string: Arial 
   ```

1. Erneut starten [!DNL Insight.exe].

