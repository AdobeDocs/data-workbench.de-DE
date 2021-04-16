---
description: Tabelle, die zeigt, welche Konventionen beim Erstellen von Transformationen gelten.
title: Konventionen für die Zusammenstellung von Umwandlungen
uuid: 91dddca6-4c17-4107-b78b-0f8b8870ef8d
exl-id: c2552c52-c6d3-4c9f-8359-b5a58bf1a59f
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '384'
ht-degree: 2%

---

# Konventionen für die Zusammenstellung von Umwandlungen{#conventions-for-constructing-transformations}

Tabelle, die zeigt, welche Konventionen beim Erstellen von Transformationen gelten.

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
   <td colname="col2"> <p>Die Transformationen in einer Datensatzkonfigurationsdatei werden nacheinander auf die Protokolleinträge angewendet (d. h. in der Reihenfolge, in der sie in der Konfigurationsdatei aufgeführt sind). Daher müssen Transformationen in der Reihenfolge aufgeführt werden, in der ihre Ergebnisse als Input für andere Transformationen verwendet werden. Wenn die Ausgabe einer Transformation als Eingabe für eine andere Transformation verwendet wird, ist es insbesondere wichtig, dass diese erste Transformation vor der letzteren Transformation in den Datenaset-Konfigurationsdateien aufgeführt wird. Andernfalls erzeugt der Data Workbench-Server einen Fehler. </p> <p> Verarbeitungsschritte bieten eine Möglichkeit, die Konvertierungen anzuordnen, die in mehreren Datensätzen definiert sind, einschließlich Dateien. Für alle Datensätze enthalten Dateien, die mit einer bestimmten Verarbeitungsstufe verknüpft sind, werden die Transformationen basierend auf ihren Ein- und Ausgängen sortiert. Wenn aufgrund einer Transformation mehrere Datensätze Dateien in ein und demselben Feld enthalten, erzeugt der Data Workbench-Server einen Fehler. </p> <p> Weitere Informationen zu Phasen finden Sie unter <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md"> Konfigurationsdatei für die Protokollverarbeitung</a>, <a href="../../../home/c-dataset-const-proc/c-trans-config-file/c-abt-trans-config-file.md">-Konfigurationsdatei für die Transformation</a> und <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md"> Datensatz Dateien einschließen</a>. </p> <p>Eine <span class="wintitle"> Transformation Dependency Map</span> kann anzeigen, wie ein Feld durch eine Reihe von Transformationen verändert wird. Siehe <a href="../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md"> DataSet-Konfigurationstools</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ausgabenamen </td> 
   <td colname="col2"> Die meisten Transformationen geben ein Ausgabefeld an. Wenn es sich bei der Ausgabe um ein benutzerdefiniertes erweitertes Feld handelt, muss der Feldname mit "x-"Beginn werden. Die Namen der Ausgabefelder dürfen keine Leerzeichen oder Sonderzeichen enthalten. Die Namen erweiterter Felder können zur Lesbarkeit mit Groß- und Kleinschreibung geschrieben werden, wie z. B. "x-NewCampaignName"oder "x-New-Kampagne-Name", wobei jedoch die Groß- und Kleinschreibung nicht beachtet wird. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Eingabefelder </td> 
   <td colname="col2"> <p>Eingabefelder beziehen sich auf eines der Grundlinienfelder oder ein vom Benutzer erstelltes Feld, das sich aus der Ausgabe einer vorherigen Transformation ergibt. Wenn eine konstante Zeichenfolge benötigt wird, kann anstelle eines Grundlinienfelds oder eines vom Benutzer erstellten Felds eine Zeichenfolge mit Anführungszeichen verwendet werden. </p> <p> Eine Liste einiger häufig definierter Datenfelder, die vom Data Workbench-Server verarbeitet werden können, finden Sie unter <a href="../../../home/c-dataset-const-proc/c-ev-data-rec-fields.md"> Ereignis Data Record Fields</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Einfache Zeichenfolgen und Vektoren von Zeichenfolgen </td> 
   <td colname="col2"> Alle Transformationen werden auf Zeichenfolgen und/oder Vektoren von Zeichenfolgen ausgeführt. Einfache Zeichenfolgen sind wörtliche Zeichenfolgen. String-Vektoren enthalten Null oder mehr einfache Zeichenfolgen in einer bestimmten Reihenfolge. </td> 
  </tr> 
 </tbody> 
</table>
