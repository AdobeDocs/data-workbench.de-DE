---
description: Beim Erstellen einer Vektorebene, die auf eine tabulatorgetrennte Datei (.tsv) verweist, werden die Vektordaten durch Abrufen von Zeichenanweisungen sowie Längen- und Breitengraddaten aus der .tsv-Datei abgerufen.
title: Vektorebenen mit Verweis auf Dateien mit tabulatorgetrennten Werten
uuid: 42607b34-e9f2-420a-ba5a-05562598b480
exl-id: be16ba73-4a98-472b-98f1-1b32e671b763
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '352'
ht-degree: 6%

---

# Vektorebenen mit Verweis auf Dateien mit tabulatorgetrennten Werten{#vector-layers-referencing-tab-separated-values-files}

{{eol}}

Beim Erstellen einer Vektorebene, die auf eine tabulatorgetrennte Datei (.tsv) verweist, werden die Vektordaten durch Abrufen von Zeichenanweisungen sowie Längen- und Breitengraddaten aus der .tsv-Datei abgerufen.

So definieren Sie eine Vektorebene, die auf eine [!DNL .tsv] -Dateien, müssen Sie über Folgendes verfügen:

* **A [!DNL .tsv] file** enthält die Daten, die zum Zeichnen der Vektoren auf der Welt verwendet werden, einschließlich Längen- und Breitengraddaten. Weitere Informationen zum erforderlichen Format der [!DNL .tsv] -Datei, siehe [Vector TSV File Format](../../../../home/c-geo-oview/c-wk-img-lyrs/c-wk-vctr-lyrs/c-tab-sep-val-files.md#section-a29012c9ff4444ac8a6d41c68482828e).

* **Ebenendatei** , der den Speicherort der [!DNL .tsv] -Datei. Weitere Informationen zum erforderlichen Format der Ebenendatei finden Sie unter [Vektorschichtdateiformat](../../../../home/c-geo-oview/c-wk-img-lyrs/c-wk-vctr-lyrs/c-tab-sep-val-files.md#section-c430923f341f4c93852e9f24b61e82bf).

## Vector TSV-Dateiformat {#section-a29012c9ff4444ac8a6d41c68482828e}

Die [!DNL .tsv] -Datei muss die folgenden drei tabulatorgetrennten Spalten enthalten:

* **[!DNL Begin]:** Diese Spalte sollte angeben, ob eine neue Zeile beginnen soll. Die Werte in dieser Spalte können entweder 0 (keine neue Zeile beginnen) oder 1 (eine neue Zeile beginnen) sein.
* **[!DNL Longitude]:** Diese Spalte sollte Längengradwerte enthalten.
* **[!DNL Latitude]:** Diese Spalte sollte Breitenwerte enthalten.

>[!NOTE]
>
>Alle weiteren Spalten werden ignoriert.

Im Folgenden finden Sie ein Beispiel [!DNL .tsv] -Datei, die Daten für eine Vektorebene enthält:

![](assets/tsv_vectorlayer.png)

## Vektorschichtdateiformat {#section-c430923f341f4c93852e9f24b61e82bf}

Jede Vektorebenen-Datei referenziert [!DNL .tsv] -Dateien müssen mit der folgenden Vorlage formatiert werden:

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
   <td colname="col2"> <p>Pfad(e) zum <span class="filepath"> .tsv</span> -Datei(en), die die Vektordaten enthält. </p> <p>Beispiel: <span class="filepath"> Maps\\USVectorData.tsv</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Farbe </td> 
   <td colname="col2"> Der Farbvektor der RGB, der als (rot, grün, blau) angegeben wird. Für jede Farbe im Vektor können Sie einen Wert zwischen 0,0 und 1,0 eingeben. (1,0, 0,0, 0,0) ist beispielsweise hellrot und (0,5, 0,5, 0,5) grau. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Alpha </td> 
   <td colname="col2"> Steuert die Transparenz der weltweit angezeigten Vektoren. Der Bereich liegt zwischen 0 und 1, wobei 0 der transparenteste ist. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Breite </td> 
   <td colname="col2"> Optional. Legt die Breite der Daten in Pixel fest. Der empfohlene Bereich beträgt 1 bis 4. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Fehlerfaktor </td> 
   <td colname="col2"> Steuert, wie genau die Vektoren gezeichnet werden. Bei größeren Werten werden die Vektoren weniger genau, aber schneller gezeichnet. Der Standardwert lautet 5. </td> 
  </tr> 
 </tbody> 
</table>
