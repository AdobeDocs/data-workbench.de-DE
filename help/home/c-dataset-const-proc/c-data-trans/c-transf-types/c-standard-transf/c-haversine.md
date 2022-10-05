---
description: In der Mathematik ist die haversinine-Formel eine Gleichung, die Kreisabstände zwischen zwei Punkten auf einer Kugel angibt, die von ihren Längen- und Breitengraden identifiziert wird.
title: Haversine
uuid: 835fa9dd-db70-4498-a03e-59595bc041fe
exl-id: e700c0a0-1a1a-4c56-bb4f-1deb1b39b059
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 4%

---

# Haversine{#haversine}

{{eol}}

In der Mathematik ist die haversinine-Formel eine Gleichung, die Kreisabstände zwischen zwei Punkten auf einer Kugel angibt, die von ihren Längen- und Breitengraden identifiziert wird.

Wie bei der Formel wird die [!DNL Haversine] Transformation erfordert zwei Sätze von [!DNL Latitude] und [!DNL Longitude] Einstellungen, wobei diese vier Eingaben verwendet werden, um die wahre Entfernung zwischen zwei Orten auf der Erde zu berechnen.

Diese Entfernung kann als Meilen oder Kilometer dargestellt werden, indem die Flagge &quot;In Kilometern&quot; von &quot;false&quot; in &quot;true&quot; geändert wird.

![](assets/cfg_TransformationType_Haversine.png)

| Parameter | Beschreibung | Standard |
|---|---|---|
| Name | Deskriptiver Name der Transformation. Hier können Sie einen beliebigen Namen eingeben. |  |
| Kommentare | Optional. Anmerkungen zur Transformation. |  |
| Bedingung | Die Bedingungen, unter denen diese Umwandlung angewendet wird. |  |
| Latitude 1-Feld | Der Breitengrad von Nummer 1. |  |
| Latitude 2, Feld | Der Breitengrad von Nummer 2. |  |
| Längengrad 1 Feld | Der Längengrad der Nummer 1. |  |
| Längengrad 2 Feld | Der Längengrad der Nummer 2. |  |
| Ausgabe | Nach der Berechnung wird die [!DNL Output] -Feld enthält Entfernungen zwischen den Punkten, die als Elemente in einer Dimension bezeichnet werden. |  |

Wenn Sie beispielsweise in einem Breiten- und Längengrad ihres Stores Lat1, Lon1 codieren und für ihre Kunden eine IP-Suche am Ende und lang verwenden, können die Entfernungen zu einem Store ermittelt werden, von dem die meisten Kunden kaufen oder von diesem kommen.

>[!NOTE]
>
>Wenn Sie Entfernungen für andere Standorte identifizieren möchten, muss jeder einzelne Standort über einen eigenen Satz von Breiten- und Langfeldern verfügen.
