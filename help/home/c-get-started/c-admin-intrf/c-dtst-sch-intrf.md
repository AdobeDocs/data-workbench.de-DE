---
description: Die Oberfläche des Datensatzschemas zeigt die erweiterten Dimensionen (zählbare, einfache, n:n, numerische, denormale und Zeitdimensionen) an, die in jeder Konfigurationsdatei eines Transformationsdatensatzes definiert sind, und bietet einen Überblick über die Beziehungen zwischen diesen Dimensionen.
title: Oberfläche zum Datensatzschema
uuid: 3726e568-d3ea-47f8-8ac4-582c97fbbe0a
exl-id: a8d4cf02-4ff7-4fcc-9062-425c1fe1fb28
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '414'
ht-degree: 3%

---

# Oberfläche zum Datensatzschema{#dataset-schema-interface}

{{eol}}

Die Oberfläche des Datensatzschemas zeigt die erweiterten Dimensionen (zählbare, einfache, n:n, numerische, denormale und Zeitdimensionen) an, die in jeder Konfigurationsdatei eines Transformationsdatensatzes definiert sind, und bietet einen Überblick über die Beziehungen zwischen diesen Dimensionen.

Darüber hinaus wird die [!DNL Dataset Schema] -Schnittstelle zeigt alle von Ihnen definierten abgeleiteten Dimensionen sowie alle erweiterten Dimensionen, die für ausgeblendet konfiguriert sind.

![](assets/vis_DatasetSchema_Example2.png)

>[!NOTE]
>
>Sie können im Schemadiagramm nach Dimensionen suchen. Der Name der durch die Suchzeichenfolge gefundenen Dimensionen wird hervorgehoben und die Zeilen der übergeordneten Klasse ändern die Farbe für alle Treffer, die in Untergeordneten untergeordneten Dimensionen gefunden werden. Die zählbaren Dimensionen bleiben beim Bildlauf sichtbar, um eine sichtbare Hierarchie und einen sichtbaren Kontext zu bieten.

**So interpretieren Sie einen Dimensionstyp mit dem [!DNL Dataset Schema] Benutzeroberfläche**

In der folgenden Tabelle sind die Dimensionstypen und die Farben aufgeführt, in denen ihre Namen in der [!DNL Dataset Schema] -Schnittstelle. Übergeordnete Elemente für die Beispieldimensionen (aus dem obigen Beispiel) werden ebenfalls notiert.

<table id="table_CF888522626E49A4A10D87085CAB5CC1"> 
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
   <td colname="col3"> <p>Besucher - In diesem Schema ist Besucher eine zählbare Stammdimension. </p> <p>Sitzung - übergeordnetes Element ist Besucher </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Denormal </td> 
   <td colname="col2"> Gelb </td> 
   <td colname="col3"> DenormalPage - parent is Page View </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Abgeleitet </td> 
   <td colname="col2"> Blau </td> 
   <td colname="col3"> Nächste Seite - übergeordnetes Element ist Seitenansicht </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Viele-zu-viele </td> 
   <td colname="col2"> Rosa und Grün (der Stamm des übergeordneten Objekts ist rosa, während der Dimensionsname grün ist.) </td> 
   <td colname="col3"> Suchbegriff - Übergeordnetes Element ist Sitzung </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Numerisch </td> 
   <td colname="col2"> Grün </td> 
   <td colname="col3"> Exakte Seitendauer - übergeordnetes Element ist "Seitenansicht". In diesem Beispiel ist die exakte Seitendauer eine ausgeblendete numerische Dimension. Siehe Dimensionstyp Ausgeblendet in dieser Tabelle. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Einfach </td> 
   <td colname="col2"> Grün </td> 
   <td colname="col3"> Seite - übergeordnetes Element ist Seitenansicht </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Zeit </td> 
   <td colname="col2"> Grün </td> 
   <td colname="col3"> Stunde - übergeordnetes Element ist Sitzung </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ausgeblendet </td> 
   <td colname="col2"> Ausgeblendete Dimensionen sind eine dunklere Version der entsprechenden Farbe des Dimensionstyps. Eine ausgeblendete numerische Dimension ist beispielsweise dunkler, weniger hell grün. </td> 
   <td colname="col3"> Exakte Seitendauer - übergeordnetes Element ist Seitenansicht </td> 
  </tr> 
 </tbody> 
</table>

Weitere Informationen zu diesen Dimensionstypen finden Sie unter *Anleitung zur Datensatzkonfiguration*.

**So zeigen Sie die Standardvisualisierung für eine Dimension an**

* Im [!DNL Dataset Schema] auf die gewünschte Dimension klicken. Die Standardvisualisierung wird angezeigt. Wenn es sich bei der Standardvisualisierung beispielsweise um eine Tabelle mit Sitzungen und der ausgewählten Dimension handelt und Sie auf die URI-Dimension klicken, zeigt Data Workbench eine Tabelle mit URI nach Sitzungen an.

   >[!NOTE]
   >
   >Wenn Sie die angezeigte Standardvisualisierung ändern möchten, lesen Sie [Die Oberfläche des Datensatzschemas](../../../home/c-get-started/c-admin-intrf/c-dtst-sch-intrf.md#concept-e147b3a5b542453ca2b121e1c85bb175).

**So zeigen Sie eine bestimmte Visualisierung für eine Dimension an**

* Im [!DNL Dataset Schema] Benutzeroberfläche, klicken Sie mit der rechten Maustaste auf die gewünschte Dimension und klicken Sie auf **[!UICONTROL Add Visualization]** > *&lt;**[!UICONTROL visualization type]**>*.
