---
description: Die Data Workbench-Client-Anwendung unterstützt jetzt vereinfachtes Chinesisch.
solution: Analytics
title: Vereinfachte Chinesisch-Lokalisierung
topic: Data workbench
uuid: ddf4eade-7c5f-4ccf-aa9f-dd8d109a059f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Vereinfachte Chinesisch-Lokalisierung{#simplified-chinese-localization}

Die Data Workbench-Client-Anwendung unterstützt jetzt vereinfachtes Chinesisch.

**So installieren Sie vereinfachtes Chinesisch**:

Bevor Sie Dateien konfigurieren [!DNL Insight.exe] und unterstützen, müssen Sie die Clientanwendung beenden.

1. Erstellen Sie eine Verknüpfung, die die Befehlszeileneinstellung an die [!DNL insight.exe] Datei übergibt.

   ```
   Insight.exe -zh-cn
   ```

1. Konfigurieren Sie [!DNL Insight.cfg] die Unterstützung von Einzel- und Doppelbyte-Schriftzeichen.

   Data Workbench unterstützt derzeit sowohl Englisch als auch vereinfachtes Chinesisch. Sie können Schriftarten auswählen, um beide Sprachen zu unterstützen:

   ```
   Fonts = vector: 2 items 
   0 = string: SimSun 
   1 = string: Arial 
   ```

1. Erneut starten [!DNL Insight.exe].

