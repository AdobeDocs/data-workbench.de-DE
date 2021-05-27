---
description: Informationen zu den Elementpunktebenen-Spalten.
title: Format der Elementpunkt-Lookup-Datei
uuid: 3480b9f3-35cd-40b7-aac9-15a3e2f19c1c
exl-id: da81da9e-0567-4f3a-bc0d-ab6c5e4a23b7
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 6%

---

# Format der Elementpunkt-Lookup-Datei{#element-point-lookup-file-format}

Informationen zu den Elementpunktebenen-Spalten.

Die Lookup-Datei der Elementpunktebene muss mindestens die folgenden drei Spalten enthalten:

* **[!DNL Key]column:** Diese Spalte sollte allgemeine Schlüsseldaten enthalten, mit denen der Data Workbench-Server die Daten in der Lookup-Datei mit denen im Datensatz verbinden kann. Die Spalte [!DNL Key] muss die erste Spalte in der Lookup-Datei sein. Jede Zeile in dieser Spalte identifiziert ein Element der Dimension.

* **[!DNL Longitude]column:** Diese Spalte sollte den Längengrad für jeden Datenpunkt in der  [!DNL Key] Spalte enthalten.

* **[!DNL Latitude]column:** Diese Spalte sollte den Breitengrad für jeden Datenpunkt in der  [!DNL Key] Spalte enthalten.

* **[!DNL Name]Spalte:**  (Optional). Wenn Sie für jeden Datenpunkt einen Namen angeben möchten, der auf der Karte angezeigt werden soll, können Sie eine [!DNL Name] -Spalte in die Lookup-Datei aufnehmen.

Jede Zeile in der Lookup-Datei [!DNL Zip Points.txt] enthält in der ersten Spalte eine ZIP-Code-Zeile, gefolgt von Längen- und Breitengrad und dem zugehörigen Stadtnamen.

```
tude, and associated city name.
ZIP_CODE LATITUDE LONGITUDE NAME
00210 +43.005895 -071.013202 PORTSMOUTH, NH
00211 +43.005895 -071.013202 PORTSMOUTH, NH
...
```
