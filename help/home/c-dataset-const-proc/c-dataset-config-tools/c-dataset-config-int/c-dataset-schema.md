---
description: Die Oberfläche des Datensatzschemas zeigt die erweiterten Dimensionen (zählbare, einfache, n:n, numerische, denormale und zeitliche Dimensionen) an, die in jeder Konfigurationsdatei für Umwandlungsdatensätze definiert sind, sowie die Beziehungen zwischen diesen Dimensionen.
title: Datensatzschema
uuid: 4ef5f14b-dc19-4118-a2f2-d680ded8092c
exl-id: b80e6e8e-9147-46ec-8602-2d7e5d33f077
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '380'
ht-degree: 3%

---

# Datensatzschema{#dataset-schema}

Die Oberfläche des Datensatzschemas zeigt die erweiterten Dimensionen (zählbare, einfache, n:n, numerische, denormale und zeitliche Dimensionen) an, die in jeder Konfigurationsdatei für Umwandlungsdatensätze definiert sind, sowie die Beziehungen zwischen diesen Dimensionen.

Darüber hinaus zeigt die [!DNL Dataset Schema]-Schnittstelle alle von Ihnen definierten abgeleiteten Dimensionen sowie alle erweiterten Dimensionen, die als ausgeblendet konfiguriert sind.

![](assets/vis_DatasetSchema_Example.png)

In diesem Abschnitt werden die folgenden Themen behandelt:

* [So interpretieren Sie den Dimensionstyp mithilfe der Oberfläche für das Datensatzschema](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-int/c-dataset-schema.md#section-16a0a12b11334c07bec558c0b7d260b1)
* [So zeigen Sie die Standardvisualisierung für eine Dimension an](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-int/c-dataset-schema.md#section-1bbb73a5cbb34ffb844eb1932db85318)
* [So zeigen Sie eine bestimmte Visualisierung für eine Dimension an](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-int/c-dataset-schema.md#section-d46626df90bc4c44ae60c4b71eaeac7f)

## So interpretieren Sie den Typ der Dimension mithilfe der Oberfläche des Datensatzschemas {#section-16a0a12b11334c07bec558c0b7d260b1}

In der folgenden Tabelle sind die Dimensionstypen und die Farben aufgeführt, in denen ihre Namen in der [!DNL Dataset Schema]-Benutzeroberfläche angezeigt werden. Übergeordnete Elemente für die Beispieldimensionen (aus dem obigen Beispiel) werden ebenfalls notiert.

<table id="table_20D1A9EAAED247338476C475C63255F5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Dimension Typ </th> 
   <th colname="col2" class="entry"> Farbe </th> 
   <th colname="col3" class="entry"> Dimension und übergeordnetes Beispiel </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Zählbar </td> 
   <td colname="col2"> Rosa </td> 
   <td colname="col3"> <p>Besucher - In diesem Schema ist Besucher eine zählbare Stammdimension. </p> <p> Sitzung - Übergeordnetes Element ist Besucher. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Denormal </td> 
   <td colname="col2"> Gelb </td> 
   <td colname="col3"> DenormalPage - übergeordnetes Element ist "Seitenansicht". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Abgeleitet </td> 
   <td colname="col2"> Blau </td> 
   <td colname="col3"> Nächste Seite - übergeordnetes Element ist "Seitenansicht". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Viele-zu-viele </td> 
   <td colname="col2"> Rosa und Grün (der Stamm des übergeordneten Objekts ist rosa, während der Dimensionsname grün ist.) </td> 
   <td colname="col3"> Suchbegriff - Übergeordnetes Element ist Sitzung. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Numerisch </td> 
   <td colname="col2"> Grün </td> 
   <td colname="col3"> Exakte Seitendauer - Übergeordnetes Element ist "Seitenansicht". In diesem Beispiel ist die exakte Seitendauer eine ausgeblendete numerische Dimension. Siehe Dimensionstyp Ausgeblendet in dieser Tabelle. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Einfach </td> 
   <td colname="col2"> Grün </td> 
   <td colname="col3"> Seite - übergeordnetes Element ist Seitenansicht . </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Zeit </td> 
   <td colname="col2"> Grün </td> 
   <td colname="col3"> Stunde - Übergeordnetes Element ist Sitzung. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Verborgen </td> 
   <td colname="col2"> Ausgeblendete Dimensionen sind eine dunklere Version der entsprechenden Farbe des Dimensionstyps. Eine ausgeblendete numerische Dimension ist beispielsweise dunkler, weniger hell grün. </td> 
   <td colname="col3"> Exakte Seitendauer - übergeordnetes Element ist "Seitenansicht". </td> 
  </tr> 
 </tbody> 
</table>

## Anzeigen der Standardvisualisierung für eine Dimension {#section-1bbb73a5cbb34ffb844eb1932db85318}

* Klicken Sie in der [!DNL Dataset Schema]-Benutzeroberfläche auf die gewünschte Dimension. Die Standardvisualisierung wird angezeigt. Wenn es sich bei der Standardvisualisierung beispielsweise um eine Tabelle mit Sitzungen und der ausgewählten Dimension handelt und Sie auf die URI-Dimension klicken, zeigt Data Workbench eine Tabelle mit URI nach Sitzungen an.

>[!NOTE]
>
>Wenn Sie die angezeigte Standardvisualisierung ändern möchten, lesen Sie das Kapitel &quot;Configuring Interface and Analysis Features&quot;im *Data Workbench-Benutzerhandbuch*.

## So zeigen Sie eine bestimmte Visualisierung für eine Dimension an {#section-d46626df90bc4c44ae60c4b71eaeac7f}

* Klicken Sie in der [!DNL Dataset Schema]-Benutzeroberfläche mit der rechten Maustaste auf die gewünschte Dimension und klicken Sie auf **[!UICONTROL Add Visualization]** > *&lt;**[!UICONTROL visualization type]***.
