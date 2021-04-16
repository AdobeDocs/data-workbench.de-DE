---
description: Data Workbench umfasst integrierte Dimensionen.
title: Integrierte Dimensionen
uuid: 0aabbc52-266d-46c1-a4b3-dd575c0f2c72
exl-id: c08a487d-60b8-4db7-8776-7ae1b9f1f27c
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '100'
ht-degree: 14%

---

# Integrierte Dimensionen{#built-in-dimensions}

Data Workbench umfasst integrierte Dimensionen.

In der folgenden Tabelle werden die verfügbaren integrierten Dimensionen für Data Workbench Liste:

<table id="table_40796088B3484F98889859C59D525AD7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Name </th> 
   <th colname="col2" class="entry"> Details </th> 
   <th colname="col3" class="entry"> Ebene </th> 
   <th colname="col4" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Keine </td> 
   <td colname="col2"> Abgeleitet </td> 
   <td colname="col3"> Nicht angegeben </td> 
   <td colname="col4">Enthält ein einzelnes Element "", das sich auf alle Elemente aller Dimensionen bezieht. Die Bewertung einer Metrik über "Keine"ist wie die Bewertung über keine Dimension. <p>Der Filter <span class="filepath"> [None="]</span> entspricht <span class="filepath"> [true]</span>. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Eins (ausgeblendet) </td> 
   <td colname="col2"> Numerisch </td> 
   <td colname="col3"> Nicht angegeben </td> 
   <td colname="col4">Das Element "1", das auch den Ordnungswert <span class="filepath"> = 1</span> hat, bezieht sich auf alle Elemente aller Dimensionen. Die One-Dimension wird normalerweise verwendet, um Zählungen anhand der folgenden Syntax zu erstellen: <p><span class="filepath"> sum(one,Countable_Dimension)</span></p></td> 
  </tr> 
 </tbody> 
</table>
