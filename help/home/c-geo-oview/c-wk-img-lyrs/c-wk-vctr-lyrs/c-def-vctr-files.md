---
description: Sie können eine Vektorebene erstellen, die auf eine oder mehrere Vektordateien (.vec) verweist, die die Daten enthält, die die Vektoren definieren, die auf der Welt gezeichnet werden sollen.
title: Definieren von Vektorebenen mit Verweis auf Vektordateien
uuid: 162d4ecc-d305-42e3-a5d4-0c1609a40f29
exl-id: c6da3cd9-f42a-4e9c-ae48-9f4ffdc42f7b
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '281'
ht-degree: 7%

---

# Definieren von Vektorebenen mit Verweis auf Vektordateien{#defining-vector-layers-referencing-vector-files}

Sie können eine Vektorebene erstellen, die auf eine oder mehrere Vektordateien (.vec) verweist, die die Daten enthält, die die Vektoren definieren, die auf der Welt gezeichnet werden sollen.

Um eine Vektorebene zu definieren, die auf eine oder mehrere [!DNL .vec]Dateien verweist, müssen Sie über Folgendes verfügen:

* Eine oder mehrere [!DNL .vec]Dateien mit den Daten, die zum Zeichnen der Vektoren auf der Welt verwendet werden.

   >[!NOTE]
   >
   >Um [!DNL .vec]-Dateien zu erhalten, die mit Ihren Vektorebenen verwendet werden sollen, wenden Sie sich an die Adobe.

* Eine Ebenendatei, die den Speicherort der [!DNL .vec]-Dateien angibt. Weitere Informationen zum erforderlichen Format der Ebenendatei finden Sie unter [Vector Layer File Format](../../../../home/c-geo-oview/c-wk-img-lyrs/c-wk-vctr-lyrs/c-def-vctr-files.md#section-530d03f41ede4a339aebbb680e15240a).

   >[!NOTE]
   >
   >Die mit dem Profil [!DNL Geography] bereitgestellte Datei [!DNL Boundaries.layer] ist eine Vektorebene, die auf die Dateien [!DNL mwnation.vec], [!DNL mwstate.vec], [!DNL mwcoast.vec], [!DNL mwlake.vec] und [!DNL mwisland.vec] verweist.

## Format der Vektorebenen-Datei {#section-530d03f41ede4a339aebbb680e15240a}

Jede Vektorebenen-Datei, die auf [!DNL .vec]Dateien verweist, muss mit der folgenden Vorlage formatiert werden:

```
Layer = VectorLayer:
  Vec Files = vector: n items
    0 = string: Maps\\.vec file 1
    1 = string: Maps\\.vec file 2
    . . .
    n-1 = string: Maps\\.vec file n
  Color = v3d: color vector
  Alpha = double: alpha
  Width = double: width
  Error Factor = double: error factor
```

| Parameter | Beschreibung |
|---|---|
| VEC-Dateien | Pfad(e) zu den [!DNL .vec]-Dateien, die die Vektordaten enthalten. |
| Farbe | Der RGB-Farbvektor, der als (rot, grün, blau) angegeben wird. Für jede Farbe im Vektor können Sie einen Wert zwischen 0,0 und 1,0 eingeben. (1,0, 0,0, 0,0) ist beispielsweise hellrot und (0,5, 0,5, 0,5) grau. |
| Alpha | Steuert die Transparenz der weltweit angezeigten Vektoren. Der Bereich liegt zwischen 0 und 1, wobei 0 der transparenteste ist. |
| Breite | Optional. Legt die Breite der Daten in Pixel fest. Der empfohlene Bereich beträgt 1 bis 4. |
| Fehlerfaktor | Steuert, wie genau die Vektoren gezeichnet werden. Bei größeren Werten werden die Vektoren weniger genau, aber schneller gezeichnet. Der Standardwert lautet 5. |

Die Datei [!DNL Boundaries.layer] ist wie folgt formatiert:

```
 Boundaries.layer file is formatted as follows:
Layer = VectorLayer:
  Vec Files = vector: 5 items
    0 = string: Maps\\mwnation.vec
    1 = string: Maps\\mwstate.vec
    2 = string: Maps\\mwcoast.vec
    3 = string: Maps\\mwlake.vec
    4 = string: Maps\\mwisland.vec
  Color = v3d: (.5,.5,1)
  Alpha = double: .5
  Error Factor = double: 4
```
