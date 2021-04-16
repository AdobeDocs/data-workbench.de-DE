---
description: Unter Maskierung versteht man die Auswahl einer Teilmenge Ihrer Daten oder einer Teilmenge der Elemente in einer Dimension.
title: Maskieren von Daten
uuid: 81b5f4e0-826c-4803-9169-66a424a4ea9f
exl-id: 3029e08e-827f-40d7-b5a1-45630876a097
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '702'
ht-degree: 1%

---

# Maskieren von Daten{#mask-data}

Unter Maskierung versteht man die Auswahl einer Teilmenge Ihrer Daten oder einer Teilmenge der Elemente in einer Dimension.

Sie können die Elemente, die nicht in der Analyse enthalten sein sollen, maskieren oder ausblenden.

Data Workbench bietet zwei Methoden zum Maskieren von Dimensionselementen. Die erste Methode verwendet die Optionen, die im Menü [!DNL Mask] verfügbar sind. Mit den Menüoptionen [!DNL Mask] können Sie mit der Maus die Elemente auswählen, die angezeigt oder maskiert werden sollen, oder Sie können die Elemente mit dem höchsten Rang anzeigen, wenn Sie die Daten nach Metrik sortieren. Die zweite Methode zum Maskieren von Dimensionselementen verwendet eine Suche.

**So maskieren Sie Daten**

1. Klicken Sie mit der rechten Maustaste auf ein Element oder die Bezeichnung der gewünschten Dimension und klicken Sie auf **[!UICONTROL Mask]**.

   ![](assets/mnu_Table_Mask.png)

1. Klicken Sie auf eine der folgenden Optionen:

   * **[!UICONTROL Show all]**
   * **[!UICONTROL Show selected only]**
   * **[!UICONTROL Hide selected]**
   * **[!UICONTROL Show top > 5, 10, 25, 50, 100]** oder  **[!UICONTROL 500]** der angezeigten Elemente nach Metrik sortiert
   * **[!UICONTROL Show top > All Positive]** , um nur Werte anzuzeigen, die größer als null sind (0)
   * **[!UICONTROL Display “X more”]** , um die Anzahl der derzeit maskierten Elemente anzuzeigen
   * **[!UICONTROL At least one >]***&lt;>>*(nur bei Arbeiten mit einer denormalen Dimension verfügbar)**[!UICONTROL countable dimension name]**

      Wenn Sie mit einer denormalen Dimension arbeiten, können Sie mit dieser Option eine Dimension nach einer zählbaren Dimension maskieren. Wenn diese Option aktiviert ist, zeigt die Tabelle nur die Elemente an, die mindestens ein Element der zählbaren Dimension haben, die Sie ausgewählt haben. Die Tabelle zeigt bis zu 1.023 Elemente an.

>[!NOTE]
>
>Da die Adobe [!DNL Platform] Daten in zufälliger Reihenfolge verarbeitet, haben bei mindestens einer Maske mehr als 1.023 Elemente eine größere Wahrscheinlichkeit, dass die Elemente in die Tabelle aufgenommen werden.

Wenn Sie die Maske nach oben oder mindestens 1 maskieren, entspricht die Reihenfolge in der Tabelle standardmäßig den Werten, die von der Auswahl zu diesem Zeitpunkt beeinflusst wurden. Wenn Sie die Auswahl später ändern, ändert sich die Reihenfolge nicht mehr in der ursprünglichen Reihenfolge, es sei denn, die Tabelle wird zurückgesetzt oder die dynamische Auswahl wird aktiviert. Wenn Sie auf **[!UICONTROL Mask]** > **[!UICONTROL Dynamic Selection]** klicken, wird die Tabelle bei jeder Änderung der Auswahl neu sortiert.

**So maskieren Sie Daten mit einer Suche**

* Sie können Daten mit einer der folgenden Suchoptionen maskieren:

   * Klicken Sie mit der rechten Maustaste auf ein Element oder die Bezeichnung der gewünschten Dimension, klicken Sie auf **[!UICONTROL Mask]** und geben Sie dann im Feld [!DNL Search] den Begriff ein, nach dem Sie suchen möchten.

      ![](assets/mnu_Table_MaskSearch.png)

   * Klicken Sie mit der rechten Maustaste auf ein Element oder die Bezeichnung der gewünschten Dimension, klicken Sie auf **[!UICONTROL Mask]** > **[!UICONTROL Display search bar]** und geben Sie dann in das Suchfeld, das in der Zelle der Dimensionsbeschriftung angezeigt wird, die Wortgruppe ein, nach der Sie suchen möchten.

      ![](assets/vis_Table_Mask_searchBar.png)

      Während Sie einen Suchbegriff eingeben, aktualisiert Data Workbench die Dimension, um Übereinstimmungen wiederzugeben.

Um die Maskierung während einer Suche weiter einzuschränken, können Sie eine der folgenden Methoden verwenden:

* Sie können &quot;re:&quot;in das Feld oder die Leiste eingeben, damit der Suchbegriff als regulärer Ausdruck interpretiert wird. [!DNL search] Sie können eine beliebige Syntax verwenden, die regulären Ausdrücken in Ihrem Suchbegriff zugeordnet ist. Weitere Informationen zu regulären Ausdrücken finden Sie im Anhang Regulärer Ausdruck im *Handbuch zur Datenkonfiguration*.
* Sie können das $-Symbol als erstes Zeichen in Ihrer Suchzeichenfolge eingeben, um nach Wortgruppen zu suchen, die mit der eingegebenen Zeichenfolge beginnen, oder als letztes Zeichen, um Wortgruppen zu finden, die mit der eingegebenen Zeichenfolge enden.
* Sie können ein Leerzeichen als erstes Zeichen in Ihrer Suchzeichenfolge eingeben, um Wörter in einer Wortgruppe zu finden, die mit der eingegebenen Zeichenfolge beginnen, oder als letztes Zeichen, um Wörter in einer Wortgruppe zu finden, die mit der eingegebenen Zeichenfolge enden.

Im Folgenden finden Sie Beispiele für verschiedene Möglichkeiten, eine Tabelle mit der Zeichenfolge &quot;on&quot;in einer Suche zu maskieren:

* Bei Eingabe von &quot;on&quot;werden alle Phrasen angezeigt, die die Zeichenfolge &quot;on&quot;an einer beliebigen Stelle in der Phrase enthalten: &quot;**on** line banking,&quot; &quot;c **on** tact käufer,&quot; &quot;bulli **on** Münzen&quot;, &quot;bank **on** line&quot;, &quot;gold opti **on** s&quot;und &quot;silber bulli **on**.&quot;
* Bei Eingabe von &quot;$on&quot;werden alle Wortgruppen angezeigt, die mit der Zeichenfolge &quot;on&quot;beginnen:

   &quot;**on** line banking&quot; und &quot;**on**-line Payment&quot;.

* Bei Eingabe von &quot;on$&quot;werden alle Phrasen angezeigt, die mit der Zeichenfolge &quot;on&quot;enden:

   &quot;silbernes Bulli **on**&quot;und &quot;gold opti **on**&quot;.

* Bei Eingabe von &quot;on&quot;werden alle Wortgruppen angezeigt, die ein Wort enthalten, das mit der Zeichenfolge &quot;on&quot;beginnt:

   &quot;**on** line banking&quot; und &quot;bank **on** line.&quot;

* Bei Eingabe von &quot;on&quot;werden alle Wortgruppen angezeigt, die ein Wort enthalten, das mit der Zeichenfolge &quot;on&quot;endet:

   &quot;bulli **auf**-Münzen&quot;und &quot;silbernes Bulli **auf**&quot;

* Bei Verwendung von &quot;on&quot;wird jede Wortgruppe mit der Zeichenfolge &quot;on&quot;als Wort angezeigt:

   &quot;**on** line banking&quot; und &quot;bank **on** line.&quot;
