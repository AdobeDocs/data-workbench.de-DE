---
description: In der Mathematik ist die Habsinsinus-Formel eine Gleichung, die Kreisabstände zwischen zwei Punkten auf einer Kugel gibt, die von ihren Längen- und Breitengraden identifiziert wird.
title: Haversine
uuid: 835fa9dd-db70-4498-a03e-59595bc041fe
exl-id: e700c0a0-1a1a-4c56-bb4f-1deb1b39b059
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 3%

---

# Haversine{#haversine}

In der Mathematik ist die Habsinsinus-Formel eine Gleichung, die Kreisabstände zwischen zwei Punkten auf einer Kugel gibt, die von ihren Längen- und Breitengraden identifiziert wird.

Wie bei der Formel erfordert die Transformation [!DNL Haversine] zwei Sätze der Einstellungen [!DNL Latitude] und [!DNL Longitude], wobei diese vier Eingaben verwendet werden, um die wahre Entfernung zwischen zwei Orten auf der Erde zu berechnen.

Diese Entfernung kann als Meilen oder Kilometer dargestellt werden, indem die Fahne &quot;In Kilometern&quot; von &quot;false&quot; in &quot;true&quot; geändert wird.

![](assets/cfg_TransformationType_Haversine.png)

| Parameter | Beschreibung | Standard |
|---|---|---|
| Name | Beschreibender Name der Transformation. Sie können hier einen beliebigen Namen eingeben. |  |
| Kommentare | Optional. Anmerkungen zur Transformation. |  |
| Bedingung | Die Bedingungen, unter denen diese Umwandlung angewendet wird. |  |
| Latitude 1, Feld | Der Breitengrad von Nummer 1. |  |
| Latitude 2, Feld | Der Breitengrad von Nummer 2. |  |
| Feld Längengrad 1 | Der Längengrad der Nummer 1. |  |
| Längengrad 2 | Der Längengrad der Nummer 2. |  |
| Ausgabe | Nach der Berechnung enthält das Feld [!DNL Output] die Abstände zwischen den als Elemente in einer Dimension bezeichneten Punkten. |  |

Beispiel: Wenn Sie in einem Breiten- und Längengrad ihres Geschäfts Lat1, Lon1 und eine IP-Suche verwenden, die für ihre Kunden lang und lang ist, können die Entfernungen zu einem Store ermittelt werden, von dem die meisten Kunden kaufen oder von dem sie kommen.

>[!NOTE]
>
>Wenn Sie Entfernungen für andere Orte identifizieren möchten, muss jeder einzelne Ort über einen eigenen Satz von langen und langen Feldern verfügen.
