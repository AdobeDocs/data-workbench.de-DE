---
description: Unter Maskierung versteht man die Auswahl einer Teilmenge Ihrer Daten oder einer Teilmenge der Elemente in einer Dimension.
solution: Analytics
title: Daten maskieren
topic: Data workbench
uuid: 81b5f4e0-826c-4803-9169-66a424a4ea9f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Daten maskieren{#mask-data}

Unter Maskierung versteht man die Auswahl einer Teilmenge Ihrer Daten oder einer Teilmenge der Elemente in einer Dimension.

Sie können die Elemente, die nicht in die Analyse einbezogen werden sollen, maskieren oder ausblenden.

Data Workbench bietet zwei Methoden zum Maskieren von Dimensionselementen. Bei der ersten Methode werden die im [!DNL Mask] Menü verfügbaren Optionen verwendet. Mithilfe der [!DNL Mask] Menüoptionen können Sie mit der Maus die Elemente auswählen, die angezeigt oder maskiert werden sollen, oder Sie können die Elemente mit dem höchsten Rang anzeigen, wenn Sie die Daten nach Metrik sortieren. Die zweite Methode zum Maskieren von Dimensionselementen verwendet eine Suche.

**So maskieren Sie Daten**

1. Klicken Sie mit der rechten Maustaste auf ein Element oder die Bezeichnung der gewünschten Dimension und klicken Sie auf **[!UICONTROL Mask]**.

   ![](assets/mnu_Table_Mask.png)

1. Klicken Sie auf eine der folgenden Optionen:

   * **[!UICONTROL Show all]**
   * **[!UICONTROL Show selected only]**
   * **[!UICONTROL Hide selected]**
   * **[!UICONTROL Show top > 5, 10, 25, 50, 100]** oder **[!UICONTROL 500]** der angezeigten Elemente nach Metrik sortiert
   * **[!UICONTROL Show top > All Positive]** , um nur Werte anzuzeigen, die größer als null sind (0)
   * **[!UICONTROL Display “X more”]** , um die Anzahl der derzeit maskierten Elemente anzuzeigen
   * **[!UICONTROL At least one >]***&lt; **[!UICONTROL countable dimension name]**>*(nur verfügbar, wenn eine denormale Dimension verwendet wird)

      Wenn Sie mit einer denormalen Dimension arbeiten, können Sie mit dieser Option eine Dimension nach einer zählbaren Dimension maskieren. Wenn diese Option aktiviert ist, zeigt die Tabelle nur die Elemente an, die mindestens ein Element der zählbaren Dimension haben, die Sie ausgewählt haben. Die Tabelle zeigt bis zu 1.023 Elemente an.

>[!NOTE]
>
>Da Adobe Daten in zufälliger Reihenfolge verarbeitet, haben die häufiger verwendeten und größeren Elemente eine größere Wahrscheinlichkeit, in die Tabelle aufgenommen zu werden, wenn mindestens eine Maske zu mehr als 1.023 Elementen führt. [!DNL Platform]

Wenn Sie die Maske nach oben oder mindestens 1 maskieren, entspricht die Reihenfolge in der Tabelle standardmäßig den Werten, die von der Auswahl zu diesem Zeitpunkt beeinflusst wurden. Wenn Sie die Auswahl später ändern, ändert sich die Reihenfolge nicht mehr in der ursprünglichen Reihenfolge, es sei denn, die Tabelle wird zurückgesetzt oder die dynamische Auswahl wird aktiviert. Wenn Sie auf **[!UICONTROL Mask]** > **[!UICONTROL Dynamic Selection]** klicken, wird die Tabelle bei jeder Änderung der Auswahl neu sortiert.

**So maskieren Sie Daten mit einer Suche**

* Sie können Daten mit einer der folgenden Suchoptionen maskieren:

   * Klicken Sie mit der rechten Maustaste auf ein Element oder die Bezeichnung der gewünschten Dimension, klicken Sie auf **[!UICONTROL Mask]** und geben Sie dann im [!DNL Search] Feld die Wortgruppe ein, nach der Sie suchen möchten.

      ![](assets/mnu_Table_MaskSearch.png)

   * Klicken Sie mit der rechten Maustaste auf ein Element oder die Bezeichnung der gewünschten Dimension, klicken Sie auf **[!UICONTROL Mask]** > **[!UICONTROL Display search bar]**, und geben Sie dann in das Suchfeld, das in der Zelle für die Dimensionsbeschriftung angezeigt wird, die Wortgruppe ein, nach der Sie suchen möchten.

      ![](assets/vis_Table_Mask_searchBar.png)

      Während Sie einen Suchbegriff eingeben, aktualisiert Data Workbench die Dimension, um Übereinstimmungen wiederzugeben.

Um die Maskierung während einer Suche weiter einzuschränken, können Sie eine der folgenden Methoden verwenden:

* Sie können &quot;re:&quot;in das [!DNL search] Feld oder die Leiste eingeben, damit der Suchbegriff als regulärer Ausdruck interpretiert wird. Sie können eine beliebige Syntax verwenden, die regulären Ausdrücken in Ihrem Suchbegriff zugeordnet ist. Weitere Informationen zu regulären Ausdrücken finden Sie im Anhang &quot;Regulärer Ausdruck&quot;im *DataSet-Konfigurationshandbuch*.
* Sie können das $-Symbol als erstes Zeichen in Ihrer Suchzeichenfolge eingeben, um nach Wortgruppen zu suchen, die mit der eingegebenen Zeichenfolge beginnen, oder als letztes Zeichen, um Wortgruppen zu finden, die mit der eingegebenen Zeichenfolge enden.
* Sie können ein Leerzeichen als erstes Zeichen in Ihrer Suchzeichenfolge eingeben, um Wörter in einer Wortgruppe zu finden, die mit der eingegebenen Zeichenfolge beginnen, oder als letztes Zeichen, um Wörter in einer Wortgruppe zu finden, die mit der eingegebenen Zeichenfolge enden.

Im Folgenden finden Sie Beispiele für verschiedene Möglichkeiten, eine Tabelle mit der Zeichenfolge &quot;on&quot;in einer Suche zu maskieren:

* Bei Eingabe von &quot;on&quot;werden alle Phrasen angezeigt, die die Zeichenfolge &quot;on&quot;an einer beliebigen Stelle in der Phrase enthalten: &quot;**** Online-Banking&quot;, &quot;**** Kontaktkäufer&quot;, &quot;**Goldmünzen** &quot;, &quot;Bank **** online&quot;, &quot;Gold-**** Optionen&quot;und &quot;Silber-**Bullion**&quot;.
* Bei Eingabe von &quot;$on&quot;werden alle Wortgruppen angezeigt, die mit der Zeichenfolge &quot;on&quot;beginnen:

   &quot;**** Online-Banking&quot;und &quot;**Onlinezahlung**&quot;.

* Bei Eingabe von &quot;on$&quot;werden alle Phrasen angezeigt, die mit der Zeichenfolge &quot;on&quot;enden:

   &quot;Silber-**Bullion**&quot;und &quot;Gold-**Option**&quot;.

* Bei Eingabe von &quot;on&quot;werden alle Wortgruppen angezeigt, die ein Wort enthalten, das mit der Zeichenfolge &quot;on&quot;beginnt:

   &quot;**** Online-Banking&quot;und &quot;Bank **** online&quot;.

* Bei Eingabe von &quot;on&quot;werden alle Wortgruppen angezeigt, die ein Wort enthalten, das mit der Zeichenfolge &quot;on&quot;endet:

   &quot;**Bullenmünzen** &quot;und &quot;Silberbullion ****&quot;.

* Bei Verwendung von &quot;on&quot;wird jede Wortgruppe mit der Zeichenfolge &quot;on&quot;als Wort angezeigt:

   &quot;**Online-Banking&quot;und &quot;Bank** on **** -line&quot;.

