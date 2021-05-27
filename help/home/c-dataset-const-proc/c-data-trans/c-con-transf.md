---
description: Tabelle, die anzeigt, welche Konventionen beim Erstellen von Umwandlungen gelten.
title: Konventionen für die Zusammenstellung von Umwandlungen
uuid: 91dddca6-4c17-4107-b78b-0f8b8870ef8d
exl-id: c2552c52-c6d3-4c9f-8359-b5a58bf1a59f
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '384'
ht-degree: 2%

---

# Konventionen für die Zusammenstellung von Umwandlungen{#conventions-for-constructing-transformations}

Tabelle, die anzeigt, welche Konventionen beim Erstellen von Umwandlungen gelten.

<table id="table_BEB0F6C416D144B5A2DD3D1A21613B21"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Übereinkommen </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Sequenzielle Ausführung </td> 
   <td colname="col2"> <p>Die Umwandlungen in einer Datensatzkonfigurationsdatei werden nacheinander auf die Protokolleinträge angewendet (d. h. in der Reihenfolge, in der sie in der Konfigurationsdatei aufgeführt sind). Daher müssen Transformationen in der Reihenfolge aufgelistet werden, in der ihre Ausgaben als Eingaben in andere Transformationen verwendet werden. Wenn die Ausgabe einer Transformation als Eingabe für eine andere Transformation verwendet wird, ist es insbesondere wichtig, dass diese erste Transformation vor der letzteren Transformation in den Datensatzkonfigurationsdateien aufgeführt wird. Andernfalls erzeugt der Data Workbench-Server einen Fehler. </p> <p> Verarbeitungsphasen bieten eine Möglichkeit, die Transformationen anzuordnen, die in mehreren Datensatzaufnahme-Dateien definiert sind. Für alle Datensatzaufnahme-Dateien, die mit einer bestimmten Verarbeitungsphase verknüpft sind, werden die Umwandlungen anhand ihrer Ein- und Ausgabedaten geordnet. Wenn infolge einer Umwandlung mehrere Datensätze Dateien in einem Staging-Ausgabedaten in dasselbe Feld enthalten, erzeugt der Data Workbench-Server einen Fehler. </p> <p> Weitere Informationen zu Bühnen finden Sie unter <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md"> Konfigurationsdatei für die Protokollverarbeitung</a>, <a href="../../../home/c-dataset-const-proc/c-trans-config-file/c-abt-trans-config-file.md"> Konfigurationsdatei für Umwandlungen</a> und <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md"> Datensatzaufnahme-Dateien</a>. </p> <p>Eine <span class="wintitle"> Abhängigkeitskarte für Umwandlungen</span> kann anzeigen, wie ein Feld durch eine Reihe von Umwandlungen geändert wird. Siehe <a href="../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md"> Tools für die Datensatzkonfiguration</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ausgabenamen </td> 
   <td colname="col2"> Die meisten Umwandlungen geben ein Ausgabefeld an. Wenn es sich bei der Ausgabe um ein benutzerdefiniertes erweitertes Feld handelt, muss der Name für dieses Feld mit "x-"beginnen. Die Namen der Ausgabefelder dürfen keine Leerzeichen oder Sonderzeichen enthalten. Die Namen erweiterter Felder können aus Gründen der Lesbarkeit mit gemischten Groß-/Kleinschreibung geschrieben werden, z. B. "x-NewCampaignName"oder "x-New-Campaign-Name". Sie werden jedoch von der Software als nicht von der Groß-/Kleinschreibung abhängig behandelt. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Eingabefelder </td> 
   <td colname="col2"> <p>Eingabefelder beziehen sich auf eines der Grundlinien-Felder oder ein vom Benutzer erstelltes Feld, das aus der Ausgabe einer vorangehenden Umwandlung resultiert. Wenn eine konstante Zeichenfolge erforderlich ist, kann anstelle eines Grundlinien- oder benutzererstellten Felds eine zitierte Zeichenfolge verwendet werden. </p> <p> Eine Liste der häufig definierten Datenfelder, die der Data Workbench-Server verarbeiten kann, finden Sie unter <a href="../../../home/c-dataset-const-proc/c-ev-data-rec-fields.md"> Felder für Ereignisdatensätze</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Einfache Zeichenfolgen und Vektoren von Zeichenfolgen </td> 
   <td colname="col2"> Alle Umwandlungen werden auf Zeichenfolgen und/oder Vektoren von Zeichenfolgen ausgeführt. Einfache Zeichenfolgen sind literale Zeichenfolgen. String-Vektoren enthalten null oder mehr einfache Zeichenfolgen in einer bestimmten Reihenfolge. </td> 
  </tr> 
 </tbody> 
</table>
