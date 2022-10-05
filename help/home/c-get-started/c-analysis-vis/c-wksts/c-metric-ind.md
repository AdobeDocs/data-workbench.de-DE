---
description: Sie können Arbeitsblätter verwenden, um anzugeben, dass eine Metrik einen definierten Schwellenwert erreicht hat.
title: Erstellen von Metrik-Indikatoren
uuid: da304004-ef45-4c89-8c91-dd5158172dd6
exl-id: 5713f3dd-85ef-407c-b21c-80e9b4390b6d
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '601'
ht-degree: 2%

---

# Erstellen von Metrik-Indikatoren{#create-a-metric-indicator}

{{eol}}

Sie können Arbeitsblätter verwenden, um anzugeben, dass eine Metrik einen definierten Schwellenwert erreicht hat.

Darüber hinaus können Sie [!DNL Report] automatisch einen Bericht zu erstellen und zu verteilen, wenn eine Metrik innerhalb eines bestimmten Zeitraums einen definierten Schwellenwert erreicht.

Weitere Informationen finden Sie unter [!DNL Report], siehe *Data Workbench-Berichtanleitung*.

* [Anzeige nach oben oder unten](../../../../home/c-get-started/c-analysis-vis/c-wksts/c-metric-ind.md#section-40d7a2c3df0d40d4a7bb1a7e856abcba)
* [Indikator überprüfen](../../../../home/c-get-started/c-analysis-vis/c-wksts/c-metric-ind.md#section-98c5298a74f34dcbaaf151549fcc7090)

**So erstellen Sie einen Metrikindikator mithilfe eines Arbeitsblatts**

1. Definieren Sie den Inhalt der Zellen des Arbeitsblatts.

   1. Geben Sie in Spalte A den Namen der gewünschten Metrik ein (z. B. [!DNL Visitors]).
   1. Geben Sie in Spalte B den Wert der gewünschten Metrik ein (z. B. [!DNL =Visitors]).
   1. Geben Sie in Spalte C den unteren Schwellenwert der Metrik ein.
   1. Geben Sie in Spalte D den hohen Schwellenwert der Metrik ein.
   1. Geben Sie in Spalte E eine entsprechende Formel ein. Beispiele finden Sie unter [Anzeige nach oben oder unten](../../../../home/c-get-started/c-analysis-vis/c-wksts/c-metric-ind.md#section-40d7a2c3df0d40d4a7bb1a7e856abcba) oder [Indikator überprüfen](../../../../home/c-get-started/c-analysis-vis/c-wksts/c-metric-ind.md#section-98c5298a74f34dcbaaf151549fcc7090).
   1. Klicken Sie in der Formelzelle (Spalte E) mit der rechten Maustaste und klicken Sie auf **[!UICONTROL Format]** > **[!UICONTROL Indicator]** und klicken Sie dann auf einen der folgenden Punkte:

      * **[!UICONTROL None]**: Führt die genaue Berechnung anstelle eines Indikators auf.
      * **[!UICONTROL Check]**: Verwendet ein Häkchen oder ein X, um anzugeben, dass der Wert je nach Formel entweder über oder unter dem festgelegten Schwellenwert liegt. Siehe [Indikator überprüfen](../../../../home/c-get-started/c-analysis-vis/c-wksts/c-metric-ind.md#section-98c5298a74f34dcbaaf151549fcc7090).
      * **[!UICONTROL Up or Down]**: Verwendet einen Nach-oben- oder Nach-unten-Pfeil, um anzugeben, ob der Wert unter dem unteren Schwellenwert (Pfeil nach unten), über dem hohen Schwellenwert (Pfeil nach oben) oder zwischen dem unteren und dem hohen Schwellenwert (leer) liegt. Siehe [Anzeige nach oben oder unten](../../../../home/c-get-started/c-analysis-vis/c-wksts/c-metric-ind.md#section-40d7a2c3df0d40d4a7bb1a7e856abcba).

1. Wiederholen Sie Schritt 1 für andere Metriken, für die Sie Indikatoren erstellen möchten.

Das resultierende Arbeitsblatt würde ungefähr wie im folgenden Beispiel aussehen:

![](assets/vis_Worksheet_Alerts.png)

## Anzeige nach oben oder unten {#section-40d7a2c3df0d40d4a7bb1a7e856abcba}

Für [!DNL Up] oder [!DNL Down indicator]verwenden Sie die folgende Formel:

[!DNL (metric value - low threshold)/(high threshold - low threshold)*2 - 1]

Beispiel: [!DNL =(b2-c2)/(d2-c2)*2-1]

Bei Verwendung dieser Formel mit der Variablen [!DNL Up] oder [!DNL Down indicator]:

* Wenn der Metrikwert zwischen dem unteren und dem hohen Schwellenwert liegt, wird die Formel zu einer Zahl zwischen -1 und 1 ausgewertet (ausschließlich). Der Nach-oben- oder Nach-unten-Pfeil wird nicht im Arbeitsblatt angezeigt.
* Wenn der Metrikwert kleiner oder gleich dem unteren Schwellenwert ist, wird die Formel als Wert kleiner oder gleich -1 ausgewertet. Die Metrikanzeige ändert sich in einen Abwärtspfeil.
* Wenn der Metrikwert größer oder gleich dem hohen Schwellenwert ist, wird die Formel zu einer Zahl größer oder gleich 1 ausgewertet. Die Metrikanzeige ändert sich in einen Aufwärtspfeil.

Die folgende Tabelle zeigt die Beispielformel [!DNL =(b2-c2)/(d2-c2)*2-1] würde Folgendes anzeigen:

![](assets/vis_Worksheet_Alerts_UpDown.png)

## Prüfungsanzeiger {#section-98c5298a74f34dcbaaf151549fcc7090}

Für [!DNL Check indicator]verwenden, verwenden Sie eine Formel, die anzeigt, ob Sie benachrichtigt werden möchten, wenn der Metrikwert über oder unter dem angegebenen Schwellenwert liegt. Beispiel:

* Wenn Sie benachrichtigt werden möchten, wenn der Wert unter dem von Ihnen festgelegten Schwellenwert liegt, können Sie das folgende Format verwenden:

   * [!DNL threshold - metric]

      Beispiel: [!DNL =(c2-b2)]

* Wenn Sie benachrichtigt werden möchten, wenn der Wert über dem festgelegten Schwellenwert liegt, können Sie die folgende Formel verwenden:

   * [!DNL metric - threshold]

      Beispiel: [!DNL =(b3-c3)]

Wenn ein Häkchen angezeigt wird, wird die Formel zu einer positiven Zahl ausgewertet. Wenn ein X angezeigt wird, wird die Formel zu einer negativen Zahl ausgewertet.

Bei Verwendung der Variablen [!DNL Check indicator]:

* Wenn die Formel anzeigt, dass es wünschenswert ist, den Metrikwert über dem Schwellenwert zu halten, wird ein Häkchen angezeigt, wenn der Metrikwert größer oder gleich dem Schwellenwert ist, und ein X, wenn der Wert kleiner als der Schwellenwert ist.
* Wenn die Formel anzeigt, dass es wünschenswert ist, den Metrikwert unter dem Schwellenwert zu halten, wird ein Häkchen angezeigt, wenn der Metrikwert kleiner oder gleich dem Schwellenwert ist, und ein X, wenn der Wert größer als der Schwellenwert ist.

Das folgende Arbeitsblatt zeigt die Beispielformeln [!DNL =(c2-b2)] und [!DNL =(b3-c3)] würde Folgendes anzeigen:

![](assets/vis_Worksheet_Alerts_Check.png)
