---
description: Sie können eine Vektorebene erstellen, die auf eine oder mehrere Vektordateien (.vec) verweist, die die Daten enthält, die die Vektoren definieren, die auf der Welt gezeichnet werden sollen.
title: Definieren von Vektorebenen mit Verweis auf Vektordateien
uuid: fe6639fb-98fb-4246-9cc1-1a928df6ae0a
exl-id: d78fa7ea-e2a9-42b7-9071-5f72409c5b7a
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '281'
ht-degree: 7%

---

# Definieren von Vektorebenen mit Verweis auf Vektordateien{#define-vector-layers-referencing-vector-files}

{{eol}}

Sie können eine Vektorebene erstellen, die auf eine oder mehrere Vektordateien (.vec) verweist, die die Daten enthält, die die Vektoren definieren, die auf der Welt gezeichnet werden sollen.

So definieren Sie eine Vektorebene mit Verweisen auf eine oder mehrere [!DNL .vec] -Dateien, müssen Sie über Folgendes verfügen:

* **Ein oder mehrere [!DNL .vec] files** die die Daten enthalten, die zum Zeichnen der Vektoren auf der Welt verwendet werden.

   >[!NOTE]
   >
   >So erhalten Sie [!DNL .vec] Dateien, die mit Ihren Vektorebenen verwendet werden sollen, kontaktieren Sie die Adobe.

* **Ebenendatei** , der den Speicherort der [!DNL .vec] Dateien. Weitere Informationen zum erforderlichen Format der Ebenendatei finden Sie unter [Vektorschichtdateiformat](../../../../home/c-get-started/c-im-layers/c-vctr-layers/c-ref-vctr-files.md#section-83a0077cf0c8479b9e7b2939bc761af1).

   >[!NOTE]
   >
   >Die [!DNL Boundaries.layer] -Datei, die mit der [!DNL Geography] profile ist eine Vektorebene, die auf die [!DNL mwnation.vec], [!DNL mwstate.vec], [!DNL mwcoast.vec], [!DNL mwlake.vec]und [!DNL mwisland.vec] Dateien.

## Vektorschichtdateiformat {#section-83a0077cf0c8479b9e7b2939bc761af1}

Jede Vektorebenen-Datei referenziert [!DNL .vec] -Dateien müssen mit der folgenden Vorlage formatiert werden:

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
| VEC-Dateien | Pfad(e) zum [!DNL .vec] -Datei(en), die die Vektordaten enthält. |
| Farbe | Der Farbvektor der RGB, der als (rot, grün, blau) angegeben wird. Für jede Farbe im Vektor können Sie einen Wert zwischen 0,0 und 1,0 eingeben. (1,0, 0,0, 0,0) ist beispielsweise hellrot und (0,5, 0,5, 0,5) grau. |
| Alpha | Steuert die Transparenz der weltweit angezeigten Vektoren. Der Bereich liegt zwischen 0 und 1, wobei 0 der transparenteste ist. |
| Breite | Optional. Legt die Breite der Daten in Pixel fest. Der empfohlene Bereich beträgt 1 bis 4. |
| Fehlerfaktor | Steuert, wie genau die Vektoren gezeichnet werden. Bei größeren Werten werden die Vektoren weniger genau, aber schneller gezeichnet. Der Standardwert lautet 5. |

Die [!DNL Boundaries.layer] -Datei wie folgt formatiert:

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
