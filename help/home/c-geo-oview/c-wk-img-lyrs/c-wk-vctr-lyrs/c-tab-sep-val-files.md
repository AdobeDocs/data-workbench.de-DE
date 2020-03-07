---
description: Beim Erstellen einer Vektorebene, die auf eine tabulatorgetrennte Datei (.tsv) verweist, werden die Vektordaten durch Abrufen von Zeichenanweisungen sowie von Längen- und Breitendaten aus der .tsv-Datei abgerufen.
solution: Analytics
title: Vektorebenen, die auf tabulatorgetrennte Wertedateien verweisen
topic: Data workbench
uuid: 42607b34-e9f2-420a-ba5a-05562598b480
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Vektorebenen, die auf tabulatorgetrennte Wertedateien verweisen{#vector-layers-referencing-tab-separated-values-files}

Beim Erstellen einer Vektorebene, die auf eine tabulatorgetrennte Datei (.tsv) verweist, werden die Vektordaten durch Abrufen von Zeichenanweisungen sowie von Längen- und Breitendaten aus der .tsv-Datei abgerufen.

Um eine Vektorebene zu definieren, die auf eine [!DNL .tsv] Datei verweist, müssen Sie über Folgendes verfügen:

* **Eine[!DNL .tsv]Datei** mit den Daten, die zum Zeichnen der Vektoren auf der Welt verwendet werden, einschließlich Längen- und Breitendaten. Weitere Informationen zum erforderlichen Format der [!DNL .tsv] Datei finden Sie unter [Vector TSV-Dateiformat](../../../../home/c-geo-oview/c-wk-img-lyrs/c-wk-vctr-lyrs/c-tab-sep-val-files.md#section-a29012c9ff4444ac8a6d41c68482828e).

* **Eine Ebenendatei** , die den Speicherort der [!DNL .tsv] Datei angibt. Weitere Informationen zum erforderlichen Format der Ebenendatei finden Sie unter [Vektorschichtdateiformat](../../../../home/c-geo-oview/c-wk-img-lyrs/c-wk-vctr-lyrs/c-tab-sep-val-files.md#section-c430923f341f4c93852e9f24b61e82bf).

## Vector TSV-Dateiformat {#section-a29012c9ff4444ac8a6d41c68482828e}

Die [!DNL .tsv] Datei muss die folgenden drei tabulatorgetrennten Spalten enthalten:

* **[!DNL Begin]:**Diese Spalte sollte angeben, ob eine neue Zeile beginnen soll. Die Werte in dieser Spalte können entweder 0 (keine neue Zeile beginnen) oder 1 (eine neue Zeile beginnen) sein.
* **[!DNL Longitude]:**Diese Spalte sollte Längengradwerte enthalten.
* **[!DNL Latitude]:**Diese Spalte sollte Breitenwerte enthalten.

>[!NOTE]
>
>Alle weiteren Spalten werden ignoriert.

Im Folgenden finden Sie eine Beispieldatei [!DNL .tsv] mit Daten zu einer Vektorebene:

![](assets/tsv_vectorlayer.png)

## Vektorschichtdateiformat {#section-c430923f341f4c93852e9f24b61e82bf}

Jede Vektorschichtdatei, die auf [!DNL .tsv] Dateien verweist, muss mit der folgenden Vorlage formatiert werden:

```
Layer = VectorLayer:
  TSV Files = vector: n items
    0 = string: Maps\\File Name.tsv
    1 = string: Maps\\File Name.tsv
    . . .
    n-1 = string: Maps\\File Name.tsv
  Color = v3d: color vector
  Alpha = double: alpha
  Width = double: width
  Error Factor = double: error factor
```

<table id="table_152F73536AB9403AB43854B81D6A9A15"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> TSV-Dateien </td> 
   <td colname="col2"> <p>Pfad(e) zu der bzw. den <span class="filepath"> .tsv</span> -Dateien, die die Vektordaten enthalten. </p> <p>Beispiel: <span class="filepath"> Maps\\USVectorData.tsv</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Kanalfarbe </td> 
   <td colname="col2"> Der RGB-Farbvektor, der als (rot, grün, blau) ausgedrückt wird. Für jede Farbe im Vektor können Sie einen Wert zwischen 0,0 und 1,0 eingeben. (1.0, 0.0, 0.0) ist beispielsweise hellrot und (0.5, 0.5, 0.5) grau. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Alpha </td> 
   <td colname="col2"> Steuert die Transparenz der Vektoren auf der Welt. Der Bereich liegt zwischen 0 und 1, wobei 0 der transparenteste Wert ist. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Breite </td> 
   <td colname="col2"> Optional. Legt die Breite der Daten in Pixel fest. Der empfohlene Bereich ist 1 bis 4. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Fehlerfaktor </td> 
   <td colname="col2"> Steuert, wie genau die Vektoren gezeichnet werden. Bei größeren Werten werden die Vektoren weniger genau, aber schneller gezeichnet. Der Standardwert lautet 5. </td> 
  </tr> 
 </tbody> 
</table>

