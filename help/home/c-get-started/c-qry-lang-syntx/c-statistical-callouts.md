---
description: Statistische Berechnungen messen aussagekräftige Beziehungen, um versteckte Gelegenheiten und Variablen von Interesse für erweiterte Data-Mining-Funktionen im Zielgruppen-Clustering und der Bewertung der Besucherantworten zu identifizieren.
title: Hinweise zu Statistiken
uuid: 04911ac4-bc3f-4813-800b-087d9668a782
exl-id: d4ed540e-f837-4db9-a81e-b8a30c15f270
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '273'
ht-degree: 22%

---

# Hinweise zu Statistiken{#statistical-callouts}

{{eol}}

Statistische Berechnungen messen aussagekräftige Beziehungen, um versteckte Gelegenheiten und Variablen von Interesse für erweiterte Data-Mining-Funktionen im Zielgruppen-Clustering und der Bewertung der Besucherantworten zu identifizieren.

Statistische Berechnungen erweitern die Algorithmen, sodass mehr Datentypen korreliert werden können, wie z. B. Binärvariablen (Ja/Nein, 0/1 oder Käufer/Nicht-Käufer), die mit zählbaren Metriken (Besuche, Bestellungen oder Downloads) korreliert sind.

So fügen Sie statistische Berechnungen hinzu:

1. Klicken Sie in einer Tabelle mit der rechten Maustaste auf die Metrikkopfzeile.
1. Auswählen **[!UICONTROL Statistics]** und aktivieren bzw. deaktivieren Sie dann die Häkchen für jede erforderliche Einstellung. Alle im Anzeigekalender sind als Standardeinstellung ausgewählt.

   ![](assets/statistical_callouts.png)

Die Berechnung kann statistische Werte zurückgeben, die in die Datensatzspalten einfließen.

<table id="table_B2A4F9D5938D4756A81ACF6F4D77E63D">
 <thead>
  <tr>
   <th colname="col1" class="entry"> Berechnung </th>
   <th colname="col2" class="entry"> Beschreibung </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> Anzahl </td>
   <td colname="col2"><p>Anzahl der Reihen in einem Datensatz. </p></td>
  </tr>
  <tr>
   <td colname="col1"> Maximum </td>
   <td colname="col2"><p> Identifiziert den maximalen Metrikwert für alle Elemente der Dimension. </p></td>
  </tr>
  <tr>
   <td colname="col1"> Minimum </td>
   <td colname="col2"><p> Identifiziert den Mindestmetrikwert für alle Elemente der Dimension. </p></td>
  </tr>
  <tr>
   <td colname="col1"> Mittel </td>
   <td colname="col2"><p> Der Mittelwert ist der arithmetische Mittelwert der Metrikwerte der Elemente in der Dimension, berechnet durch die Summe geteilt durch die Anzahl (Summe/Anzahl). </p></td>
  </tr>
  <tr>
   <td colname="col1"> Standardabweichung </td>
   <td colname="col2"> Dieser Wert gibt die Abweichung vom erwarteten arithmetischen Mittelwert an. Je geringer die Abweichung, desto näher liegen die Datenpunkte am Mittel. Eine hohe Abweichung bedeutet, dass die Datenpunkte über einen großen Wertebereich verteilt sind. </td>
  </tr>
  <tr>
   <td colname="col1"> Gesamt </td>
   <td colname="col2"><p> Gibt die Gesamtsumme der Metrikwerte zurück. </p></td>
  </tr>
  <tr>
   <td colname="col1"> Abweichung </td>
   <td colname="col2"><p> Ein Maß für die Varianz der Metrikwerte vom Metrikmittelwert für diese Dimension. Sie entspricht dem Quadrat der Standardabweichung. </p></td>
  </tr>
 </tbody>
</table>
