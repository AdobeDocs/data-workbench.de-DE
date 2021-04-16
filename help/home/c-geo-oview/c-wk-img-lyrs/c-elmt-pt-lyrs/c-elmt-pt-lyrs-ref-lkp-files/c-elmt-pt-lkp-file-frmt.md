---
description: Informationen zu den Elementpunktschichtspalten.
title: Format der Elementpunkt-Lookup-Datei
uuid: 3480b9f3-35cd-40b7-aac9-15a3e2f19c1c
exl-id: da81da9e-0567-4f3a-bc0d-ab6c5e4a23b7
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 6%

---

# Format der Elementpunkt-Lookup-Datei{#element-point-lookup-file-format}

Informationen zu den Elementpunktschichtspalten.

Die Abfragedatei der Elementpunktebene muss mindestens die folgenden drei Spalten enthalten:

* **[!DNL Key]column:** Diese Spalte sollte allgemeine Schlüsseldaten enthalten, die es dem Data Workbench-Server ermöglichen, die Daten in der Lookup-Datei mit denen im Datensatz zu verbinden. Die Spalte [!DNL Key] muss die erste Spalte in der Lookup-Datei sein. Jede Zeile in dieser Spalte identifiziert ein Element der Dimension.

* **[!DNL Longitude]column:** Diese Spalte sollte den Längengrad für jeden Datenpunkt in der  [!DNL Key] Spalte enthalten.

* **[!DNL Latitude]column:** Diese Spalte sollte den Breitengrad für jeden Datenpunkt in der  [!DNL Key] Spalte enthalten.

* **[!DNL Name]column:** (Optional). Wenn Sie einen Namen angeben möchten, der auf der Zuordnung für jeden Datenpunkt angezeigt werden soll, können Sie eine Spalte [!DNL Name] in die Lookup-Datei einfügen.

Jede Zeile in der Lookup-Datei enthält einen Postleitzahl in der ersten Spalte gefolgt von Längen- und Breitengrad sowie dem zugehörigen Ortsnamen.[!DNL Zip Points.txt]

```
tude, and associated city name.
ZIP_CODE LATITUDE LONGITUDE NAME
00210 +43.005895 -071.013202 PORTSMOUTH, NH
00211 +43.005895 -071.013202 PORTSMOUTH, NH
...
```
