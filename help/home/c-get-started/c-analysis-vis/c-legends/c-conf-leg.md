---
description: Konfidenzlegenden helfen Ihnen dabei, die Wahrscheinlichkeit zu ermitteln, dass die Zahlen, die Sie sehen, auf Zufälle zurückzuführen sind, und die möglichen Abweichungen in den Daten zu verstehen.
title: Konfidenzlegenden
uuid: 2559ff7c-6060-4fee-b509-9ae0c3912016
exl-id: 9aab169a-98b8-4e71-b74d-28e385c5c424
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '445'
ht-degree: 2%

---

# Konfidenzlegenden{#confidence-legends}

{{eol}}

Konfidenzlegenden helfen Ihnen dabei, die Wahrscheinlichkeit zu ermitteln, dass die Zahlen, die Sie sehen, auf Zufälle zurückzuführen sind, und die möglichen Abweichungen in den Daten zu verstehen.

Selbst wenn Sie keine Sampling-Daten sind, können Sie die Zahlen aus einem bestimmten Zeitraum oder einer Teilmenge nicht mit voller Konfidenz auf andere Zeiträume oder Teilmengen extrapolieren. Mit der Konfidenzlegende können Sie die Wahrscheinlichkeit untersuchen, mit der die Zahlen in einen bestimmten Bereich fallen.

Wenn man reale Daten als ein großes Experiment betrachtet, bedeutet die reale Welt immer noch Zufall, selbst wenn man mit exakten Zahlen arbeitet. Wenn Sie beispielsweise wissen, wie viele Personen eine Transaktion zwischen 8:00 und 22:00 Uhr an einem Dienstag abgeschlossen haben, bedeutet dies nicht, dass genau dieselbe Zahl am folgenden Dienstag ausgeführt wird.

Die folgende Konfidenzlegende zeigt Konfidenzdetails zur Konversionsmetrik an, während die folgende Tabelle weitere Informationen darüber enthält, was jeder Datenpunkt bedeutet.

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
   <td colname="col2"> <p>Der Metrikname oder Metrikausdruck, für den Sie Konfidenzinformationen anzeigen möchten. Jede Auswahl, die Sie in Ihrem Arbeitsbereich treffen, wird in der Legende widergespiegelt. In diesem Beispiel werden Details zur Konversionsmetrik angezeigt. </p> <p>Informationen zu Syntaxregeln für die Eingabe eines Ausdrucks finden Sie unter <a href="../../../../home/c-get-started/c-qry-lang-syntx/c-qry-lang-syntx.md#concept-15d1d3f5164a47d49468c5acb7299d9f"> Syntax der Abfragesprache</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Gemessener Wert </p> </td> 
   <td colname="col2"> <p>Der Wert der tatsächlich erfassten Daten. In diesem Beispiel beträgt die Konversionsrate für die aktuelle Auswahl 2,3 %. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Standardabweichung </p> </td> 
   <td colname="col2"> <p>Die Standardabweichung des gemessenen Werts. In diesem Beispiel beträgt die Standardabweichung der Konversionsrate für die aktuelle Auswahl 0,1 %. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Der Wert "true" </p> </td> 
   <td colname="col2"> <p>Die Wahrscheinlichkeit, dass der gemessene Wert in den für jede Wahrscheinlichkeit aufgelisteten Bereich fällt. In diesem Beispiel, wenn dieses "reale Experiment"immer wieder wiederholt würde, könnten Sie 90 % sicher sein, dass der gemessene Wert zwischen 2,1 % und 2,4 % liegt. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Bei der Analyse der Ergebnisse von Berechnungen müssen die folgenden Einschränkungen berücksichtigt werden:
>* Die Zahlen sind Schätzungen. Wenn Sie dieselben Berechnungen mit einem anderen Datensatz wiederholt haben, erhalten Sie ein anderes Ergebnis. Dies wird als zufällige Variante bezeichnet.
>* Extrapolationen auf höhere Wahrscheinlichkeiten hängen von der Annahme der Normalität ab, die nicht für alle Metriken korrekt ist. Daher sind die Werte für 99% Wahrscheinlichkeit weniger zuverlässig als die Werte für 90% Wahrscheinlichkeit.
>
>Wenn Sie genauere Zahlen benötigen, sollten Sie sich an einen Experten für Statistik wenden.

## Metriken oder Formeln ändern {#section-7f09ff84c3514f26b78d29294e1f03d9}

* Klicken Sie in der Konfidenzlegende auf die Schaltfläche **[!UICONTROL Metric or Formula]** und geben Sie die gewünschte Metrik oder den Ausdruck ein. Informationen zu Syntax-Regeln für Ausdrücke finden Sie unter [Syntax der Abfragesprache](../../../../home/c-get-started/c-qry-lang-syntx/c-qry-lang-syntx.md#concept-15d1d3f5164a47d49468c5acb7299d9f).

## Exportieren in Microsoft Excel {#section-f36e2db7273740b7af278f8a2b79d564}

Informationen zum Exportieren von Fenstern finden Sie unter [Exportieren von Fensterdaten](../../../../home/c-get-started/c-wk-win-wksp/c-exp-win-data.md#concept-8df61d64ed434cc5a499023c44197349).
