---
description: Sie können Arbeitsblätter verwenden, um anzugeben, dass eine Metrik einen definierten Schwellenwert erreicht hat.
title: Erstellen von Metrik-Indikatoren
uuid: da304004-ef45-4c89-8c91-dd5158172dd6
exl-id: 5713f3dd-85ef-407c-b21c-80e9b4390b6d
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '601'
ht-degree: 2%

---

# Erstellen von Metrik-Indikatoren{#create-a-metric-indicator}

Sie können Arbeitsblätter verwenden, um anzugeben, dass eine Metrik einen definierten Schwellenwert erreicht hat.

Darüber hinaus können Sie [!DNL Report] verwenden, um automatisch einen Bericht zu erstellen und zu verteilen, wenn eine Metrik innerhalb eines bestimmten Zeitraums einen definierten Schwellenwert erreicht.

Weitere Informationen zu [!DNL Report] finden Sie im *Data Workbench Report Guide*.

* [Aufwärts- oder Abwärtsindikator](../../../../home/c-get-started/c-analysis-vis/c-wksts/c-metric-ind.md#section-40d7a2c3df0d40d4a7bb1a7e856abcba)
* [Prüfungsanzeiger](../../../../home/c-get-started/c-analysis-vis/c-wksts/c-metric-ind.md#section-98c5298a74f34dcbaaf151549fcc7090)

**So erstellen Sie einen Metrikindikator mithilfe eines Arbeitsblatts**

1. Definieren Sie den Inhalt der Zellen des Arbeitsblatts.

   1. Geben Sie in Spalte A den Namen der gewünschten Metrik ein (z. B. [!DNL Visitors]).
   1. Geben Sie in Spalte B den Wert der gewünschten Metrik ein (z. B. [!DNL =Visitors]).
   1. Geben Sie in Spalte C den unteren Schwellenwert der Metrik ein.
   1. Geben Sie in Spalte D den oberen Schwellenwert der Metrik ein.
   1. Geben Sie in Spalte E eine entsprechende Formel ein. Beispiele finden Sie unter [Nach-oben- oder Nach-unten-Indikator](../../../../home/c-get-started/c-analysis-vis/c-wksts/c-metric-ind.md#section-40d7a2c3df0d40d4a7bb1a7e856abcba) oder [Prüfindikator](../../../../home/c-get-started/c-analysis-vis/c-wksts/c-metric-ind.md#section-98c5298a74f34dcbaaf151549fcc7090).
   1. Klicken Sie in der Formelzelle (Spalte E) mit der rechten Maustaste und klicken Sie auf **[!UICONTROL Format]** > **[!UICONTROL Indicator]** und klicken Sie dann auf einen der folgenden Schritte:

      * **[!UICONTROL None]**: Liste der genauen Berechnung anstelle eines Indikators.
      * **[!UICONTROL Check]**: Verwendet ein Häkchen oder ein X, um anzugeben, dass der Wert je nach Formel über oder unter dem von Ihnen festgelegten Schwellenwert liegt. Siehe [Check Indicator](../../../../home/c-get-started/c-analysis-vis/c-wksts/c-metric-ind.md#section-98c5298a74f34dcbaaf151549fcc7090).
      * **[!UICONTROL Up or Down]**: Verwendet einen Nach-oben- oder Nach-unten-Pfeil, um anzugeben, ob der Wert unter dem unteren Schwellenwert (Pfeil nach unten), über dem oberen Schwellenwert (Pfeil nach oben) oder zwischen den unteren und oberen Schwellenwerten (leer) liegt. Siehe [Aufwärts- oder Abwärtsindikator](../../../../home/c-get-started/c-analysis-vis/c-wksts/c-metric-ind.md#section-40d7a2c3df0d40d4a7bb1a7e856abcba).

1. Wiederholen Sie Schritt 1 für andere Metriken, für die Sie Indikatoren erstellen möchten.

Das resultierende Arbeitsblatt würde etwa wie folgt aussehen:

![](assets/vis_Worksheet_Alerts.png)

## Nach oben oder unten Indikator {#section-40d7a2c3df0d40d4a7bb1a7e856abcba}

Verwenden Sie für [!DNL Up] oder [!DNL Down indicator] die folgende Formel:

[!DNL (metric value - low threshold)/(high threshold - low threshold)*2 - 1]

Beispiel: [!DNL =(b2-c2)/(d2-c2)*2-1]

Bei Verwendung dieser Formel mit dem [!DNL Up] oder [!DNL Down indicator] sind für jede Metrik drei Ergebnisse möglich:

* Wenn der Metrikwert zwischen den niedrigen und hohen Schwellenwerten liegt, wird die Formel als Zahl zwischen -1 und 1 ausgewertet (ausschließlich). Der Pfeil nach oben oder unten wird nicht im Arbeitsblatt angezeigt.
* Wenn der Metrikwert kleiner als oder gleich dem unteren Schwellenwert ist, wird die Formel als Wert kleiner oder gleich -1 ausgewertet. Der Metrikindikator ändert sich in einen Pfeil nach unten.
* Wenn der Metrikwert größer oder gleich dem hohen Schwellenwert ist, wird die Formel als Zahl größer oder gleich 1 ausgewertet. Der Metrikindikator ändert sich in einen Pfeil nach oben.

Das folgende Arbeitsblatt zeigt, was die Beispielformel [!DNL =(b2-c2)/(d2-c2)*2-1] anzeigen würde:

![](assets/vis_Worksheet_Alerts_UpDown.png)

## Indikator {#section-98c5298a74f34dcbaaf151549fcc7090}

Für das [!DNL Check indicator] verwenden Sie eine Formel, die angibt, ob Sie benachrichtigt werden möchten, wenn der Metrikwert über oder unter dem angegebenen Schwellenwert liegt. Beispiel:

* Wenn Sie benachrichtigt werden möchten, wenn der Wert unter dem von Ihnen festgelegten Schwellenwert liegt, können Sie das folgende Format verwenden:

   * [!DNL threshold - metric]

      Beispiel: [!DNL =(c2-b2)]

* Wenn Sie benachrichtigt werden möchten, wenn der Wert über dem von Ihnen festgelegten Schwellenwert liegt, können Sie die folgende Formel verwenden:

   * [!DNL metric - threshold]

      Beispiel: [!DNL =(b3-c3)]

Wenn ein Häkchen angezeigt wird, wird die Formel als positive Zahl ausgewertet. Wenn ein X angezeigt wird, wird die Formel als negative Zahl ausgewertet.

Bei Verwendung von [!DNL Check indicator] gibt es zwei mögliche Ergebnisse für jede Metrik:

* Wenn die Formel angibt, dass es wünschenswert ist, den Metrikwert über dem Schwellenwert zu halten, wird ein Häkchen angezeigt, wenn der Metrikwert größer oder gleich dem Schwellenwert ist, und ein X, wenn der Wert unter dem Schwellenwert liegt.
* Wenn die Formel angibt, dass das Halten des Metrikwerts unter dem Schwellenwert wünschenswert ist, wird ein Häkchen angezeigt, wenn der Metrikwert kleiner oder gleich dem Schwellenwert ist, und ein X, wenn der Wert größer als der Schwellenwert ist.

Das folgende Arbeitsblatt veranschaulicht, was die Beispielformeln [!DNL =(c2-b2)] und [!DNL =(b3-c3)] anzeigen würden:

![](assets/vis_Worksheet_Alerts_Check.png)
