---
description: Die IPLookup-Transformation nutzt IP-Geo-Standort- oder IP-Geo-Intelligence-Daten (von jedem Anbieter dieser Daten bereitgestellt und von Adobe in ein proprietäres Format konvertiert) und wandelt die Daten in geografische Informationen um, die für die Analyse verwendet werden können.
solution: Analytics
title: IPLookup
topic: Data workbench
uuid: 6fccee39-761f-4854-a7fd-3f8b453e0698
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# IPLookup{#iplookup}

Die IPLookup-Transformation nutzt IP-Geo-Standort- oder IP-Geo-Intelligence-Daten (von jedem Anbieter dieser Daten bereitgestellt und von Adobe in ein proprietäres Format konvertiert) und wandelt die Daten in geografische Informationen um, die für die Analyse verwendet werden können.

Zwei [!DNL IPLookup] Transformationen werden im Menü Neue hinzufügen > *Transformationstyp *aufgelistet:

* [!DNL IPLookup] Zitate für [!DNL IP geo-location] Daten

* [!DNL IPLookup] Digital Envoy für [!DNL IP geo-intelligence] Daten

Wählen Sie beim Definieren einer [!DNL IPLookup] Transformation die entsprechende Transformation für Ihre [!DNL IP geo-location] oder [!DNL IP geo-intelligence] Daten.

<table id="table_C438A30AB5E64160A5C486D6887B1D7E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
   <th colname="col3" class="entry"> Standardeinstellung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Name </td> 
   <td colname="col2"> Beschreibender Name der Transformation. Sie können hier einen beliebigen Namen eingeben. </td> 
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
   <td colname="col2"> Pfad und Dateiname der Lookup-Datei. Relative Pfade beziehen sich auf den Installationsordner für den Data Workbench-Server. Diese Datei befindet sich normalerweise im Ordner "Suchen"im Installationsordner des Data Workbench-Servers. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> IP-Adresse </td> 
   <td colname="col2"> Das Feld, aus dem die IP-Adresse gelesen werden soll. </td> 
   <td colname="col3"> c-ip </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ausgaben </td> 
   <td colname="col2"> <p>Die Namen der Ausgabezeichenfolgen. </p> <p> Die <span class="wintitle"> IPLookup</span> Quova- und <span class="wintitle"> IPLookup</span> Digital Envoy-Transformationen haben unterschiedliche Ausgabeparameter. Achten Sie darauf, die entsprechende Transformation für Ihre IP-Nachschlagedaten zu verwenden. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

In diesem Beispiel werden [!DNL IP geo-location] Daten (in der Lookup-Datei [!DNL Quova.bin]) verwendet, um die aufgelisteten Ausgabefelder zu erstellen. Die Ausgaben (AOL, ASN, Bereichscode usw.) können verwendet werden, um Dimensionen für die geografische Analyse des Besucherverkehrs zu erstellen.

![](assets/cfg_TransformationType_IPLookup.png)

