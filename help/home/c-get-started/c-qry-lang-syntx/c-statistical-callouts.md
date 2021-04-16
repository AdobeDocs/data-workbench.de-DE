---
description: Statistische Berechnungen erfassen aussagekräftige Beziehungen, um versteckte Gelegenheiten und Interessensvariablen für erweiterte Data Mining-Funktionen bei der Audience-Clustering und der Bewertung der Reaktionsfähigkeit von Besuchern zu identifizieren.
title: Hinweise zu Statistiken
uuid: 04911ac4-bc3f-4813-800b-087d9668a782
exl-id: d4ed540e-f837-4db9-a81e-b8a30c15f270
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '273'
ht-degree: 23%

---

# Hinweise zu Statistiken{#statistical-callouts}

Statistische Berechnungen erfassen aussagekräftige Beziehungen, um versteckte Gelegenheiten und Interessensvariablen für erweiterte Data Mining-Funktionen bei der Audience-Clustering und der Bewertung der Reaktionsfähigkeit von Besuchern zu identifizieren.

Statistische Berechnungen erweitern die Algorithmen, sodass mehr Datentypen korreliert werden können, wie z. B. binomielle Variablen (ja/nein, 0/1 oder Käufer/Nicht-Käufer), die mit zählbaren Metriken (Besuche, Bestellungen oder Downloads) korreliert sind.

So fügen Sie statistische Berechnungen hinzu:

1. Klicken Sie in einer Tabelle mit der rechten Maustaste auf die Metriküberschrift.
1. Wählen Sie **[!UICONTROL Statistics]** aus und wählen Sie dann die Auswahlfelder für jede erforderliche Einstellung aus oder löschen Sie sie. Alle Elemente im Anzeigeaufruf sind als Standardeinstellung ausgewählt.

   ![](assets/statistical_callouts.png)

Der Callout kann statistische Werte zurückgeben, die in die Datensatzspalten einfließen.

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
   <td colname="col2"><p> Das Mittel ist der arithmetische Durchschnitt der Metrikwerte der Elemente in der Dimension, berechnet durch die Summe geteilt durch die Anzahl (Summe/Anzahl). </p></td>
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
   <td colname="col1"> Schwankung </td>
   <td colname="col2"><p> Ein Maß für die Varianz der Metrikwerte aus dem Metrikmittel für diese Dimension. Sie ist gleich dem Quadrat der Standardabweichung. </p></td>
  </tr>
 </tbody>
</table>
