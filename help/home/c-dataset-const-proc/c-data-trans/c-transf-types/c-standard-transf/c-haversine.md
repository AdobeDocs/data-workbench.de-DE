---
description: In der Mathematik ist die Habsinsinus-Formel eine Gleichung, die Kreisabstände zwischen zwei Punkten auf einer Kugel gibt, die von ihren Längen- und Breitengraden identifiziert wird.
solution: Analytics
title: Haversin
topic: Data workbench
uuid: 835fa9dd-db70-4498-a03e-59595bc041fe
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Haversin{#haversine}

In der Mathematik ist die Habsinsinus-Formel eine Gleichung, die Kreisabstände zwischen zwei Punkten auf einer Kugel gibt, die von ihren Längen- und Breitengraden identifiziert wird.

Wie bei der Formel erfordert die [!DNL Haversine] Transformation zwei Sätze [!DNL Latitude] und [!DNL Longitude] Einstellungen, wobei diese vier Eingänge verwendet werden, um die wahre Entfernung zwischen zwei Orten zu berechnen.

Diese Entfernung kann als Meilen oder Kilometer dargestellt werden, indem die Fahne &quot;In Kilometern&quot; von &quot;false&quot; in &quot;true&quot; geändert wird.

![](assets/cfg_TransformationType_Haversine.png)

| Parameter | Beschreibung | Standardeinstellung |
|---|---|---|
| Name | Beschreibender Name der Transformation. Sie können hier einen beliebigen Namen eingeben. |  |
| Kommentare | Optional. Anmerkungen zur Transformation. |  |
| Bedingung | Die Bedingungen, unter denen diese Umwandlung angewendet wird. |  |
| Latitude 1, Feld | Der Breitengrad von Nummer 1. |  |
| Latitude 2, Feld | Der Breitengrad von Nummer 2. |  |
| Feld Längengrad 1 | Der Längengrad der Nummer 1. |  |
| Längengrad 2 | Der Längengrad der Nummer 2. |  |
| Ausgabe | Nach der Berechnung enthält das [!DNL Output] Feld die Abstände zwischen den als Elemente in einer Dimension bezeichneten Punkten. |  |

Beispiel: Wenn Sie in einem Breiten- und Längengrad ihres Geschäfts Lat1, Lon1 und eine IP-Suche verwenden, die für ihre Kunden lang und lang ist, können die Entfernungen zu einem Store ermittelt werden, von dem die meisten Kunden kaufen oder von dem sie kommen.

>[!NOTE]
>
>Wenn Sie Entfernungen für andere Orte identifizieren möchten, muss jeder einzelne Ort über einen eigenen Satz von langen und langen Feldern verfügen.

