---
description: Der Ressourcenmonitor-Vektor enthält die Speicherbudgetüberwachung und die Anzahl der Abfragemonitore.
solution: Analytics
title: Abfragewarteschlangen-Ressourcenmonitore
topic: Data workbench
uuid: 6b516bed-7f9a-4821-869e-19e720f20313
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Abfragewarteschlangen-Ressourcenmonitore{#query-queue-resource-monitors}

Der Ressourcenmonitor-Vektor enthält die Speicherbudgetüberwachung und die Anzahl der Abfragemonitore.

In der folgenden Tabelle werden die Felder für den Ressourcenmonitor beschrieben, die für die Abfragewarteschlange verwendet werden.

<table id="table_9991EED2647A460FACA2DC80D4973A8E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Feld </th> 
   <th colname="col2" class="entry"> Typ </th> 
   <th colname="col3" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Speicherbudgetüberwachung </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>Überwacht den von der aktuellen Benutzergruppe verwendeten Abfragespeicher. Wenn die aktuelle Nutzung zwischen dem niedrigen Schwellenwert und dem hohen Schwellenwert liegt, werden keine neuen Bundches geplant, bis die Speicherbelegung wieder unter den niedrigen Schwellenwert zurückfällt, z. B. weil Benutzer ihre Arbeitsflächen schließen. Geplante Stapel dürfen wachsen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Hoher Schwellenwert </p> </td> 
   <td colname="col2"> <p>double </p> </td> 
   <td colname="col3"> <p>Der hohe Schwellenwert für die Speicherbelegung (Byte). Wenn die Speicherbelegung über diesem Wert liegt, erfolgt keine Zeitplanung und die Bundles mit der niedrigsten Priorität werden einzeln über einen bestimmten Zeitraum hinweg ungeplant, bis die Speicherbelegung unter diesen Wert zurückgeführt wird. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Niedriger Schwellenwert </p> </td> 
   <td colname="col2"> <p>double </p> </td> 
   <td colname="col3"> <p>Der niedrige Schwellenwert für die Speicherbelegung (Byte). Wenn der Wert für die <span class="wintitle"> Speicherbudgetüberwachung</span> unter diesem Wert liegt, können neue Bundches geplant und geplante Bundches können erweitert werden. Beispielsweise werden Bundles erweitert, wenn ein Benutzer einer Arbeitsfläche eine Visualisierung hinzufügt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Reaktionszeit </p> </td> 
   <td colname="col2"> <p>double </p> </td> 
   <td colname="col3"> <p>Die Zeitkonstante für die Glättung der Speicherbelegungsschätzung. Bei der Ausgleichung werden Reaktionen auf Spitzen vermieden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Anzahl der Abfragemonitore </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>Überwacht die Gesamtzahl der Abfragen, die derzeit für das Profil geplant sind. Mit diesem Ressourcenmonitor können Sie Bundles planen, wenn die Gesamtanzahl der Abfragen unter dem Wert im Feld "niedriger Schwellenwert"bleibt. Dieser Monitor ermöglicht das Vergrößern der aktuell geplanten Stapel, wenn die Gesamtanzahl der Abfragen unter dem Wert im Feld "Hoher Schwellenwert"bleibt. Zusätzlich entfernt dieser Monitor Bundches mit niedriger Priorität, um Bundches mit höherer Priorität planen oder wachsen zu lassen. Diese Einstellung verhindert jedoch nicht, dass Bundles mit einer Priorität größer sind, als im Feld "Unberührbare Priorität"angegeben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Hoher Schwellenwert </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>Der hohe Schwellenwert für die Speicherbelegung (Byte). Wenn die Speicherbelegung über diesem Wert liegt, erfolgt keine Planung. Die niedrigste Priorität für geplante Bundles wird jeweils für einen Zeitraum ungeplant, bis die Speicherbelegung unter diesen Wert zurückgeführt wird. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Niedriger Schwellenwert </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>Der niedrige Schwellenwert für die Speicherbelegung (Byte). Wenn der Wert <span class="wintitle"> für die Speicherbudgetüberwachung</span> unter diesem Wert liegt, können neue Bundches geplant und geplante Bundches erweitert werden. </p> </td> 
  </tr> 
 </tbody> 
</table>

