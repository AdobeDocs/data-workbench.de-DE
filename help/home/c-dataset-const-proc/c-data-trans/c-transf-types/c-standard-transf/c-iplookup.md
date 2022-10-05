---
description: Die IPLookup-Transformation nutzt IP-Geostandort- oder IP-Geo-Intelligence-Daten (bereitgestellt von jedem Anbieter dieser Daten und konvertiert sie durch Adobe in ein proprietäres Format) und wandelt die Daten in geografische Informationen um, die für die Analyse verwendet werden können.
title: IPLookup
uuid: 6fccee39-761f-4854-a7fd-3f8b453e0698
exl-id: 3e9dba44-8d31-49af-8ce0-fecaf92edeb7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '257'
ht-degree: 4%

---

# IPLookup{#iplookup}

{{eol}}

Die IPLookup-Transformation nutzt IP-Geostandort- oder IP-Geo-Intelligence-Daten (bereitgestellt von jedem Anbieter dieser Daten und konvertiert sie durch Adobe in ein proprietäres Format) und wandelt die Daten in geografische Informationen um, die für die Analyse verwendet werden können.

Zwei [!DNL IPLookup] Transformationen werden im Menü Neu hinzufügen > *Transformationstyp *aufgelistet:

* [!DNL IPLookup] Quova für [!DNL IP geo-location] data

* [!DNL IPLookup] Digital Envoy für [!DNL IP geo-intelligence] data

Beim Definieren einer [!DNL IPLookup] Transformation, wählen Sie die passende Transformation für Ihre [!DNL IP geo-location] oder [!DNL IP geo-intelligence] Daten.

<table id="table_C438A30AB5E64160A5C486D6887B1D7E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
   <th colname="col3" class="entry"> Standard </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Name </td> 
   <td colname="col2"> Deskriptiver Name der Transformation. Hier können Sie einen beliebigen Namen eingeben. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Kommentare </td> 
   <td colname="col2"> Optional. Anmerkungen zur Transformation. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Bedingung </td> 
   <td colname="col2"> Die Bedingungen, unter denen diese Umwandlung angewendet wird. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Datei </td> 
   <td colname="col2"> Pfad und Dateiname der Lookup-Datei. Relative Pfade beziehen sich auf den Installationsordner für den Data Workbench-Server. Diese Datei befindet sich normalerweise im Ordner Suchen im Installationsordner des Data Workbench-Servers. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> IP-Adresse </td> 
   <td colname="col2"> Das Feld, aus dem die IP-Adresse gelesen werden soll. </td> 
   <td colname="col3"> c-ip </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ausgaben </td> 
   <td colname="col2"> <p>Die Namen der Ausgabezeichenfolgen. </p> <p> Die <span class="wintitle"> IPLookup</span> Quova und <span class="wintitle"> IPLookup</span> Digital Envoy-Transformationen haben unterschiedliche Ausgabeparameter. Stellen Sie sicher, dass Sie die entsprechende Transformation für Ihre IP-Lookup-Daten verwenden. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

In diesem Beispiel [!DNL IP geo-location] Daten (in der Lookup-Datei) [!DNL Quova.bin]) verwendet, um die aufgelisteten Ausgabefelder zu erstellen. Die Ausgaben (AOL, ASN, Gebiets-Code usw.) können verwendet werden, um Dimensionen für die geografische Analyse des Besucher-Traffics zu erstellen.

![](assets/cfg_TransformationType_IPLookup.png)
