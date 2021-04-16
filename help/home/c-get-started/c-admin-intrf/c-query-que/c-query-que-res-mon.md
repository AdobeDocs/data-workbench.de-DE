---
description: Der Ressourcenmonitor-Vektor enthält die Speicherbudgetüberwachung und die Anzahl der Abfragen-Überwachung.
title: Ressourcenüberwachungen für die Abfragewarteschlage
uuid: 6b516bed-7f9a-4821-869e-19e720f20313
exl-id: 6d445a4d-a415-41ce-9d45-1bdd0e726edd
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '399'
ht-degree: 3%

---

# Ressourcenüberwachungen für die Abfragewarteschlage{#query-queue-resource-monitors}

Der Ressourcenmonitor-Vektor enthält die Speicherbudgetüberwachung und die Anzahl der Abfragen-Überwachung.

In der folgenden Tabelle sind die Ressourcenüberwachungsfelder für die Warteschlange von Abfragen beschrieben.

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
   <td colname="col3"> <p>Überwacht den von der aktuellen Benutzergruppe verwendeten Arbeitsspeicher der Abfrage. Wenn die aktuelle Nutzung zwischen dem niedrigen Schwellenwert und dem hohen Schwellenwert liegt, werden keine neuen Bundches geplant, bis die Speicherbelegung wieder unter den niedrigen Schwellenwert zurückfällt, z. B. weil Benutzer ihre Arbeitsflächen schließen. Geplante Stapel dürfen wachsen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Hoher Schwellenwert </p> </td> 
   <td colname="col2"> <p>double </p> </td> 
   <td colname="col3"> <p>Der hohe Schwellenwert für die Speicherbelegung (Byte). Wenn die Speicherbelegung über diesem Wert liegt, erfolgt keine Zeitplanung und die Bundles mit der niedrigsten Priorität werden einzeln über einen bestimmten Zeitraum hinweg ungeplant, bis die Speicherbelegung unter diesen Wert zurückgeführt wird. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Niedriger Schwellenwert </p> </td> 
   <td colname="col2"> <p>Dublette </p> </td> 
   <td colname="col3"> <p>Der niedrige Schwellenwert für die Speicherbelegung (Byte). Wenn der Wert <span class="wintitle"> des Speicherbudgetbildschirms</span> unter diesem Wert liegt, sind neue Bundches geplant und geplante Bundches dürfen erweitert werden. Beispielsweise werden Bundles erweitert, wenn ein Benutzer einer Arbeitsfläche eine Visualisierung hinzufügt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Reaktionszeit </p> </td> 
   <td colname="col2"> <p>Dublette </p> </td> 
   <td colname="col3"> <p>Die Zeitkonstante für die Glättung der Speicherbelegungsschätzung. Bei der Ausgleichung werden Reaktionen auf Spitzen vermieden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Anzahl der Abfragen überwachen </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>Überprüft die Gesamtanzahl der Abfragen, die derzeit für das Profil geplant sind. Mit diesem Ressourcenmonitor können Sie Bundles planen, wenn die Gesamtanzahl der Abfragen unter dem Wert im Feld "niedriger Schwellenwert"bleibt. Dieser Monitor ermöglicht das Vergrößern der aktuell geplanten Stapel, wenn die Gesamtanzahl der Abfragen unter dem Wert im Feld "Hoher Schwellenwert"bleibt. Zusätzlich entfernt dieser Monitor Bundches mit niedriger Priorität, um Bundches mit höherer Priorität planen oder wachsen zu lassen. Diese Einstellung verhindert jedoch nicht, dass Bundles mit einer Priorität größer sind, als im Feld "Unberührbare Priorität"angegeben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Hoher Schwellenwert </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>Der hohe Schwellenwert für die Speicherbelegung (Byte). Wenn die Speicherbelegung über diesem Wert liegt, erfolgt keine Planung. Die niedrigste Priorität für geplante Bundles wird jeweils für einen Zeitraum ungeplant, bis die Speicherbelegung unter diesen Wert zurückgeführt wird. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Niedriger Schwellenwert </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>Der niedrige Schwellenwert für die Speicherbelegung (Byte). Wenn der Wert <span class="wintitle"> des Speicherbudgetbildschirms</span> unter diesem Wert liegt, können neue Bundches geplant und geplante Bundches können erweitert werden. </p> </td> 
  </tr> 
 </tbody> 
</table>
