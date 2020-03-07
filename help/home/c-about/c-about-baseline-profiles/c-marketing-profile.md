---
description: Die Kampagnendimension ist im Site-Marketing-Profil definiert, um Kampagnenanalysefunktionen bereitzustellen.
solution: Analytics
title: Marketing-Profildimensionen
topic: Data workbench
uuid: 034b4318-58e6-4638-9b13-fac83ff9f826
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Marketing-Profildimensionen{#marketing-profile-dimensions}

Die Kampagnendimension ist im Site-Marketing-Profil definiert, um Kampagnenanalysefunktionen bereitzustellen.

<table id="table_27A4B8247F6D4E18BD61041CED7D8805"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Dimension </th> 
   <th colname="col2" class="entry"> Typ </th> 
   <th colname="col3" class="entry"> Ebene </th> 
   <th colname="col4" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Kampagne </td> 
   <td colname="col2"> Umbenannt - einfach </td> 
   <td colname="col3">Sitzung <p>VORGANG DER ERSTEN ZEILE </p></td> 
   <td colname="col4"> Die Kampagnen-ID, die aus einem Wert in der ersten Anforderung des Besuchers extrahiert wird. </td> 
  </tr> 
 </tbody> 
</table>

**Beispiele für benutzerdefinierte Marketing-Profildimensionen**

Sie können zusätzliche Datendimensionen für die weitere Analyse einbeziehen. Diese Dimensionen werden hinzugefügt, indem zusätzliche Informationen in den Datenstrom aufgenommen werden, der für die Analyse erfasst wird. Die folgende Tabelle enthält beispielsweise einige der benutzerdefinierten Marketingdimensionen, die in Implementierungen für Kunden in verschiedenen Branchen hinzugefügt wurden:

| Dimension (benutzerdefiniert) | Beschreibung |
|---|---|
| Datum der E-Mail-Kampagne | Analysiert das Kampagnendatum (den ersten Wert) aus den Abfragezeichenfolgen der E-Mail-Kampagne. |
| E-Mail-Kampagnendetails | Erfasst die Wertzeichenfolge, die an die Abfragezeichenfolgenvariable der E-Mail-Kampagne angehängt ist. |
| E-Mail-Kampagnensegment | Parst das Kampagnensegment (dritter Wert) aus den Abfragezeichenfolgen der E-Mail-Kampagne. |
| E-Mail-Kampagnentyp | Analysiert den Kampagnentyp (den zweiten Wert) aus den Abfragezeichenfolgen der E-Mail-Kampagne. |
| Marketing-Kampagnendetails | Erfasst die Wertzeichenfolge, die an die Abfragezeichenfolgenvariablen der Marketing-Kampagne angehängt wird. |
| Inhaber der Marketing-Kampagne | Parst den Kampagneninhaber (vierten Wert) aus den Abfragezeichenfolgen der Marketing-Kampagne. |
| Marketingkampagnenquelle | Analysiert die Kampagnenquelle (den ersten Wert) aus den Abfragezeichenfolgen der Marketing-Kampagne. |
| Marketingkampagnentyp | Parst den Kampagnentyp (den zweiten Wert) aus den Abfragezeichenfolgen der Marketing-Kampagne. |
| Details zur PPC-Kampagne | Erfasst die Wertzeichenfolge, die an die Abfragezeichenfolgenvariable ppc angehängt ist. |

