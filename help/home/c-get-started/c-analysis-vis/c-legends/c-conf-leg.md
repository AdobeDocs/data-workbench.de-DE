---
description: Vertrauenslegenden helfen Ihnen, die Wahrscheinlichkeit zu ermitteln, dass die Zahlen, die Sie sehen, zufällig sind, und die möglichen Abweichungen in den Daten zu verstehen.
title: Konfidenzlegenden
uuid: 2559ff7c-6060-4fee-b509-9ae0c3912016
exl-id: 9aab169a-98b8-4e71-b74d-28e385c5c424
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '445'
ht-degree: 2%

---

# Konfidenzlegenden{#confidence-legends}

Vertrauenslegenden helfen Ihnen, die Wahrscheinlichkeit zu ermitteln, dass die Zahlen, die Sie sehen, zufällig sind, und die möglichen Abweichungen in den Daten zu verstehen.

Auch wenn Sie keine Stichprobendaten verwenden, können Sie die Zahlen aus einem bestimmten Zeitraum oder einer Teilmenge nicht mit voller Konfidenz auf andere Zeiträume oder Teilmengen extrapolieren. Mit der Konfidenzlegende können Sie die Wahrscheinlichkeit erforschen, dass die Zahlen in einen bestimmten Bereich fallen.

Wenn man reale Daten als ein großes Experiment betrachtet, ist die reale Welt immer noch mit Zufall verbunden, selbst wenn man mit exakten Zahlen arbeitet. Wenn man z. B. weiß, wie viele Personen an einem Dienstag zwischen 8 und 22 Uhr eine Transaktion abgeschlossen haben, bedeutet das nicht, dass genau dieselbe Zahl am folgenden Dienstag dies tun wird.

Die folgende Konfidenzlegende enthält Konfidenzdetails zur Konversionsmetrik, während die folgende Tabelle weitere Informationen darüber enthält, was jeder Datenpunkt bedeutet.

![](assets/lgd_ConfidenceLegend.png)

<table id="table_387F22C7EF4E4DE9AD810D3D9204676F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Feld </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Metrik oder Formel </p> </td> 
   <td colname="col2"> <p>Der Metrikname oder Metrikname, für den Sie Konfidenzinformationen Ansicht haben möchten. Jede Auswahl, die Sie in Ihrem Arbeitsbereich treffen, wird in der Legende widergespiegelt. In diesem Beispiel werden Details zur Konversionsmetrik angezeigt. </p> <p>Weitere Informationen zu Syntaxregeln für die Eingabe eines Ausdrucks finden Sie unter <a href="../../../../home/c-get-started/c-qry-lang-syntx/c-qry-lang-syntx.md#concept-15d1d3f5164a47d49468c5acb7299d9f"> Abfrage-Syntax</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Gemessener Wert </p> </td> 
   <td colname="col2"> <p>Der Wert der tatsächlich erfassten Daten. In diesem Beispiel beträgt der Konversionsrate für die aktuelle Auswahl 2,3 %. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Standardabweichung </p> </td> 
   <td colname="col2"> <p>Die Standardabweichung des gemessenen Werts. In diesem Beispiel beträgt die Standardabweichung des Konversionsraten für die aktuelle Auswahl 0,1 %. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Der Wert "true" </p> </td> 
   <td colname="col2"> <p>Die Wahrscheinlichkeit, dass der gemessene Wert in den für jede Wahrscheinlichkeit aufgelisteten Bereich fällt. In diesem Beispiel könnte man, wenn sich dieses "Experiment in der realen Welt"immer wieder wiederholt, 90 % sicher sein, dass der gemessene Wert zwischen 2,1 % und 2,4 % liegt. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Bei der Analyse der Ergebnisse von Berechnungen müssen die folgenden Einschränkungen berücksichtigt werden:
>* Die Zahlen sind Schätzungen. Wenn Sie dieselben Berechnungen mit einem anderen Datensatz wiederholen, erhalten Sie ein anderes Ergebnis. Dies wird als zufällige Variation bezeichnet.
>* Extrapolationen auf höhere Wahrscheinlichkeiten hängen von einer Annahme der Normalität ab, die nicht für alle Metriken korrekt ist. Daher sind die Werte für die 99%ige Wahrscheinlichkeit weniger zuverlässig als die Werte für die 90%ige Wahrscheinlichkeit.

>
>
Wenn Sie genauere Zahlen benötigen, sollten Sie sich an einen Experten für Statistik wenden.

## Metriken oder Formeln {#section-7f09ff84c3514f26b78d29294e1f03d9} ändern

* Klicken Sie in der Konfidenzlegende auf das Feld **[!UICONTROL Metric or Formula]** und geben Sie die gewünschte Metrik oder den gewünschten Ausdruck ein. Weitere Informationen zu Ausdruck-Syntaxregeln finden Sie unter [Abfrage-Syntax](../../../../home/c-get-started/c-qry-lang-syntx/c-qry-lang-syntx.md#concept-15d1d3f5164a47d49468c5acb7299d9f).

## Exportieren in Microsoft Excel {#section-f36e2db7273740b7af278f8a2b79d564}

Informationen zum Exportieren von Fenstern finden Sie unter [Exportieren von Fensterdaten](../../../../home/c-get-started/c-wk-win-wksp/c-exp-win-data.md#concept-8df61d64ed434cc5a499023c44197349).
