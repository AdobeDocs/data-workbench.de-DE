---
description: Informationen zu den Elementpunktschichtspalten.
solution: Analytics
title: Elementpunkt-Suchdateiformat
topic: Data workbench
uuid: 3480b9f3-35cd-40b7-aac9-15a3e2f19c1c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Elementpunkt-Suchdateiformat{#element-point-lookup-file-format}

Informationen zu den Elementpunktschichtspalten.

Die Abfragedatei der Elementpunktebene muss mindestens die folgenden drei Spalten enthalten:

* **[!DNL Key]column:**Diese Spalte sollte allgemeine Schlüsseldaten enthalten, die es dem Data Workbench-Server ermöglichen, die Daten in der Abfragedatei mit denen im Datensatz zu verbinden. Die[!DNL Key]Spalte muss die erste Spalte in der Lookup-Datei sein. Jede Zeile in dieser Spalte identifiziert ein Element der Dimension.

* **[!DNL Longitude]column:**Diese Spalte sollte den Längengrad für jeden Datenpunkt in der[!DNL Key]Spalte enthalten.

* **[!DNL Latitude]column:**Diese Spalte sollte den Breitengrad für jeden Datenpunkt in der[!DNL Key]Spalte enthalten.

* **[!DNL Name]column:**(Optional). Wenn Sie für jeden Datenpunkt einen Namen angeben möchten, der auf der Zuordnung angezeigt werden soll, können Sie eine[!DNL Name]Spalte in die Lookup-Datei einfügen.

Jede Zeile in der [!DNL Zip Points.txt] Abfragedatei enthält einen Postleitzahl in der ersten Spalte gefolgt von Längen- und Breitengrad sowie dem zugehörigen Ortsnamen.

```
tude, and associated city name.
ZIP_CODE LATITUDE LONGITUDE NAME
00210 +43.005895 -071.013202 PORTSMOUTH, NH
00211 +43.005895 -071.013202 PORTSMOUTH, NH
...
```

