---
description: Die Benutzeroberfläche des Datenaset-Schemas zeigt die erweiterten Dimensionen (zählbare, einfache, viele- bis numerische, denormale und Zeitdimensionen) an, die in jeder Transformation DataSet-Konfigurationsdatei definiert sind, sowie die Beziehungen zwischen diesen Dimensionen.
solution: Analytics
title: Datenaset-Schema
topic: Data workbench
uuid: 4ef5f14b-dc19-4118-a2f2-d680ded8092c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Datenaset-Schema{#dataset-schema}

Die Benutzeroberfläche des Datenaset-Schemas zeigt die erweiterten Dimensionen (zählbare, einfache, viele- bis numerische, denormale und Zeitdimensionen) an, die in jeder Transformation DataSet-Konfigurationsdatei definiert sind, sowie die Beziehungen zwischen diesen Dimensionen.

Darüber hinaus zeigt die [!DNL Dataset Schema] Oberfläche alle von Ihnen definierten abgeleiteten Dimensionen sowie alle erweiterten Dimensionen, die für das Ausblenden konfiguriert sind.

![](assets/vis_DatasetSchema_Example.png)

In diesem Abschnitt werden die folgenden Themen behandelt:

* [So interpretieren Sie den Dimensionstyp mithilfe der DataSet-Schemaoberfläche](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-int/c-dataset-schema.md#section-16a0a12b11334c07bec558c0b7d260b1)
* [So zeigen Sie die Standardvisualisierung für eine Dimension an](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-int/c-dataset-schema.md#section-1bbb73a5cbb34ffb844eb1932db85318)
* [So zeigen Sie eine bestimmte Visualisierung für eine Dimension an](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-int/c-dataset-schema.md#section-d46626df90bc4c44ae60c4b71eaeac7f)

## So interpretieren Sie den Dimensionstyp mithilfe der DataSet-Schemaschnittstelle {#section-16a0a12b11334c07bec558c0b7d260b1}

In der folgenden Tabelle sind die Dimensionstypen und die Farben aufgeführt, in denen ihre Namen auf der [!DNL Dataset Schema] Oberfläche angezeigt werden. Übergeordnete Elemente für die Musterabmessungen (aus dem obigen Beispiel) werden ebenfalls vermerkt.

<table id="table_20D1A9EAAED247338476C475C63255F5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Dimensionstyp </th> 
   <th colname="col2" class="entry"> Kanalfarbe </th> 
   <th colname="col3" class="entry"> Beispieldimension und übergeordnetes Element </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Zählbar </td> 
   <td colname="col2"> Rosa </td> 
   <td colname="col3"> <p>Besucher - In diesem Schema ist der Besucher eine zählbare Dimension für die Stammebene. </p> <p> Sitzung - übergeordnetes Element ist Besucher. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Denormal </td> 
   <td colname="col2"> Gelb </td> 
   <td colname="col3"> DenormalPage - übergeordnetes Element ist "Seitenansicht". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Abgeleitet </td> 
   <td colname="col2"> Blau </td> 
   <td colname="col3"> Nächste Seite - übergeordnetes Element ist Seitenansicht. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Viele-zu-viele </td> 
   <td colname="col2"> Rosa und Grün (Der Stamm des übergeordneten Elements ist rosa, während der Dimensionsname grün ist.) </td> 
   <td colname="col3"> Suchbegriff - übergeordnetes Element ist Sitzung. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Numerisch </td> 
   <td colname="col2"> Grün </td> 
   <td colname="col3"> Exakte Seitendauer - übergeordnetes Element ist Seitenansicht In diesem Beispiel ist die exakte Seitendauer eine verborgene numerische Dimension. Siehe Dimensionstyp "Ausgeblendet"in dieser Tabelle. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Einfach </td> 
   <td colname="col2"> Grün </td> 
   <td colname="col3"> Seite - übergeordnetes Element ist Seitenansicht. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Zeit </td> 
   <td colname="col2"> Grün </td> 
   <td colname="col3"> Stunde - Elternteil ist Sitzung. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Verborgen </td> 
   <td colname="col2"> Ausgeblendete Dimensionen sind eine dunklere Version der entsprechenden Farbe des Dimensionstyps. Eine verborgene numerische Dimension ist beispielsweise ein dunklerer, weniger helles Grün. </td> 
   <td colname="col3"> Exakte Seitendauer - übergeordnetes Element ist "Seitenansicht". </td> 
  </tr> 
 </tbody> 
</table>

## So zeigen Sie die Standardvisualisierung für eine Dimension an {#section-1bbb73a5cbb34ffb844eb1932db85318}

* Klicken Sie in der [!DNL Dataset Schema] Oberfläche auf die gewünschte Dimension. Die Standardvisualisierung wird angezeigt. Wenn die Standardvisualisierung beispielsweise eine Tabelle mit Sitzungen und der ausgewählten Dimension ist und Sie auf die URI-Dimension klicken, zeigt Data Workbench eine Tabelle mit URI nach Sitzungen an.

>[!NOTE]
>
>Wenn Sie die angezeigte Standardvisualisierung ändern möchten, lesen Sie das Kapitel &quot;Konfigurierungs-Oberfläche und Analysefunktionen&quot;im *Data Workbench-Benutzerhandbuch*.

## So zeigen Sie eine bestimmte Visualisierung für eine Dimension an {#section-d46626df90bc4c44ae60c4b71eaeac7f}

* Klicken Sie in der [!DNL Dataset Schema] Oberfläche mit der rechten Maustaste auf die gewünschte Dimension und klicken Sie auf **[!UICONTROL Add Visualization]** > *&lt;**[!UICONTROL visualization type]**>*.

