---
description: Informationen zu den Elementpunktebenen-Spalten.
title: Format der Elementpunkt-Lookup-Datei
uuid: 3480b9f3-35cd-40b7-aac9-15a3e2f19c1c
exl-id: da81da9e-0567-4f3a-bc0d-ab6c5e4a23b7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 6%

---

# Format der Elementpunkt-Lookup-Datei{#element-point-lookup-file-format}

{{eol}}

Informationen zu den Elementpunktebenen-Spalten.

Die Lookup-Datei der Elementpunktebene muss mindestens die folgenden drei Spalten enthalten:

* **[!DNL Key]column:** Diese Spalte sollte allgemeine Schlüsseldaten enthalten, mit denen der Data Workbench-Server die Daten in der Lookup-Datei mit denen im Datensatz verbinden kann. Die [!DNL Key] -Spalte muss die erste Spalte in der Lookup-Datei sein. Jede Zeile in dieser Spalte identifiziert ein Element der Dimension.

* **[!DNL Longitude]column:** Diese Spalte sollte den Längengrad für jeden Datenpunkt im [!DNL Key] Spalte.

* **[!DNL Latitude]column:** Diese Spalte sollte den Breitengrad für jeden Datenpunkt im [!DNL Key] Spalte.

* **[!DNL Name]column:** (Optional). Wenn Sie einen Namen angeben möchten, der auf der Zuordnung für jeden Datenpunkt angezeigt werden soll, können Sie eine [!DNL Name] in der Lookup-Datei.

Jede Zeile im [!DNL Zip Points.txt] Die Lookup-Datei enthält eine Postleitzahl in der ersten Spalte, gefolgt von Längen- und Breitengrad sowie dem zugehörigen Stadtnamen.

```
tude, and associated city name.
ZIP_CODE LATITUDE LONGITUDE NAME
00210 +43.005895 -071.013202 PORTSMOUTH, NH
00211 +43.005895 -071.013202 PORTSMOUTH, NH
...
```
