---
description: Der Ressourcenmonitor-Vektor enthält den Memory Budget Monitor und die Anzahl der Queries Monitor.
title: Ressourcenüberwachungen für die Abfragewarteschlage
uuid: 6b516bed-7f9a-4821-869e-19e720f20313
exl-id: 6d445a4d-a415-41ce-9d45-1bdd0e726edd
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '399'
ht-degree: 3%

---

# Ressourcenüberwachungen für die Abfragewarteschlage{#query-queue-resource-monitors}

{{eol}}

Der Ressourcenmonitor-Vektor enthält den Memory Budget Monitor und die Anzahl der Queries Monitor.

In der folgenden Tabelle werden die für die Abfragewarteschlange verwendeten Felder für den Ressourcenmonitor beschrieben.

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
   <td colname="col1"> <p>Memory Budget Monitor </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>Überwachen des von der aktuellen Benutzergruppe verwendeten Abfragespeichers. Wenn die aktuelle Auslastung zwischen dem niedrigen Schwellenwert und dem hohen Schwellenwert liegt, werden keine neuen Bundches geplant, bis die Speicherauslastung wieder unter den niedrigen Schwellenwert zurückfällt, z. B. weil Benutzer ihre Arbeitsbereiche schließen. Geplante Bundches können erweitert werden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Hoher Schwellenwert </p> </td> 
   <td colname="col2"> <p>double </p> </td> 
   <td colname="col3"> <p>Der hohe Schwellenwert für die Speichernutzung (Byte). Wenn die Speicherbelegung über diesem Wert liegt, erfolgt keine Zeitplanung und die mit der niedrigsten Priorität geplanten Bundches werden jeweils für einen bestimmten Zeitraum ungeplant, bis die Speicherbelegung unter diesen Wert zurückgeführt wird. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Geringer Schwellenwert </p> </td> 
   <td colname="col2"> <p>double </p> </td> 
   <td colname="col3"> <p>Der niedrige Schwellenwert für die Speicherbelegung (Byte). Wenn <span class="wintitle"> Memory Budget Monitor</span> unterhalb dieses Werts steht, können neue Bundches geplant werden und geplante Bundches können erweitert werden. Beispielsweise werden Bundles erweitert, wenn ein Benutzer eine Visualisierung zu einem Arbeitsbereich hinzufügt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Reaktionszeit </p> </td> 
   <td colname="col2"> <p>double </p> </td> 
   <td colname="col3"> <p>Die Zeitkonstante für die Glättung der Speichernutzung schätzt. Ausgleichungswerte vermeiden Reaktionen auf Nutzungsspitzen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Anzahl der Abfragen </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>Überwachen Sie die Gesamtzahl der Abfragen, die derzeit für das Profil geplant sind. Mit diesem Ressourcenmonitor können Sie eine Bündelung planen, wenn die Gesamtzahl der Abfragen unter dem Wert im Feld Geringer Schwellenwert bleibt. Dieser Monitor ermöglicht das Vergrößern von derzeit geplanten Bundles, wenn die Gesamtanzahl der Abfragen unter dem Wert im Feld Hoher Schwellenwert bleibt. Zusätzlich entfernt dieser Monitor Bundles mit niedriger Priorität, um die Planung oder Erweiterung von Bundles mit höherer Priorität zu ermöglichen. Diese Einstellung verhindert jedoch keine Bundles mit einer Priorität, die über der im Feld Unberührbare Priorität angegebenen Priorität liegt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Hoher Schwellenwert </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>Der hohe Schwellenwert für die Speichernutzung (Byte). Wenn die Speicherbelegung über diesem Wert liegt, erfolgt keine Zeitplanung und die mit der niedrigsten Priorität geplanten Bundles werden über einen bestimmten Zeitraum ungeplant, bis die Speicherbelegung unter diesen Wert zurückgeführt wird. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Geringer Schwellenwert </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>Der niedrige Schwellenwert für die Speicherbelegung (Byte). Wenn <span class="wintitle"> Memory Budget Monitor</span> unterhalb dieses Werts steht, können neue Bundches geplant und geplante Bundches können größer werden. </p> </td> 
  </tr> 
 </tbody> 
</table>
