---
description: Die Verarbeitungslegende enthält detaillierte Informationen zur Datenverarbeitung und -umwandlung eines bestimmten Servers und ermöglicht es Ihnen, den Fortschritt von Daten zu verfolgen, die erneut verarbeitet und umtransformiert werden.
title: Verarbeitungslegende
uuid: 6c082c8f-fbb3-4e48-a249-2a13345fda86
exl-id: a83ce514-c92b-4cf8-a3cc-bff4e2ba63f1
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 2%

---

# Verarbeitungslegende{#processing-legend}

Die Verarbeitungslegende enthält detaillierte Informationen zur Datenverarbeitung und -umwandlung eines bestimmten Servers und ermöglicht es Ihnen, den Fortschritt von Daten zu verfolgen, die erneut verarbeitet und umtransformiert werden.

![](assets/vis_ProcessingLegend.png)

In der folgenden Tabelle sind die Aufgaben aufgeführt, die mit [!DNL Processing Legend] ausgeführt werden können.

<table id="table_6149250C44B14C44A3CB1CEF68B280C6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Um diese Aufgabe auszuführen... </th> 
   <th colname="col2" class="entry"> Führen Sie folgende Schritte aus... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>So zeigen Sie die Gesamtgröße aller Daten an </p> </td> 
   <td colname="col2"> <p>Überprüfen Sie die Werte in den Feldern <span class="wintitle"> Gesamtprotokolleinträge</span> und <span class="wintitle"> Protokollbyte-Gesamtsumme</span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>So überprüfen Sie, ob die Filterung funktioniert </p> </td> 
   <td colname="col2"> <p>Überprüfen Sie die Werte in den Feldern <span class="wintitle"> Gesamte gefilterte Protokolleinträge</span> . Wenn der Wert 0 beträgt, funktioniert die Filterung nicht und Sie müssen Ihre Konfiguration überprüfen, um das Problem zu beheben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>So überprüfen Sie den Fortschritt der Protokollverarbeitung </p> </td> 
   <td colname="col2"> <p>Überprüfen Sie den Wert im Feld <span class="wintitle"> Log Processing Progress</span> . Dieser Prozentsatz gibt an, wie viel der Neuverarbeitungsprozess abgeschlossen ist. </p> <p>Bei der Neuverarbeitung zur Verfeinerung Ihres Datensatzes sollten Sie die Anzahl der <span class="wintitle"> Gesamtanzahl der entschlüsselten Protokolleinträge</span> im Vergleich zur Anzahl der <span class="wintitle"> gefilterten Gesamtprotokolleinträge</span> im Auge behalten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Überprüfen des Transformationsfortschritts </p> </td> 
   <td colname="col2"> <p>Überprüfen Sie den Wert im Feld <span class="wintitle"> Transformation Progress</span> . Dieser Prozentsatz gibt an, wie viel der Umwandlungsvorgang abgeschlossen ist. </p> </td> 
  </tr> 
 </tbody> 
</table>
