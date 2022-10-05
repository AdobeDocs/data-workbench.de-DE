---
description: Maskieren bezeichnet die Auswahl einer Teilmenge Ihrer Daten oder einer Teilmenge der Elemente in einer Dimension.
title: Maskieren von Daten
uuid: 81b5f4e0-826c-4803-9169-66a424a4ea9f
exl-id: 3029e08e-827f-40d7-b5a1-45630876a097
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '702'
ht-degree: 1%

---

# Maskieren von Daten{#mask-data}

{{eol}}

Maskieren bezeichnet die Auswahl einer Teilmenge Ihrer Daten oder einer Teilmenge der Elemente in einer Dimension.

Sie können Elemente, die nicht in die Analyse aufgenommen werden sollen, maskieren oder ausblenden.

Data Workbench bietet zwei Methoden zum Maskieren von Dimensionselementen. Die erste Methode verwendet die im [!DNL Mask] Menü. Verwenden der [!DNL Mask] Menüoptionen verwenden, können Sie mit der Maus die Elemente auswählen, die angezeigt oder ausgeblendet werden sollen, oder Sie können die Elemente mit dem höchsten Rang anzeigen, wenn Sie die Daten nach Metrik sortieren. Die zweite Methode zum Maskieren von Dimensionselementen verwendet eine Suche.

**So maskieren Sie Daten**

1. Klicken Sie mit der rechten Maustaste auf ein Element oder den Titel der gewünschten Dimension und klicken Sie auf **[!UICONTROL Mask]**.

   ![](assets/mnu_Table_Mask.png)

1. Klicken Sie auf eine der folgenden Optionen:

   * **[!UICONTROL Show all]**
   * **[!UICONTROL Show selected only]**
   * **[!UICONTROL Hide selected]**
   * **[!UICONTROL Show top > 5, 10, 25, 50, 100]** oder **[!UICONTROL 500]** der angezeigten Elemente, sortiert nach Metrik
   * **[!UICONTROL Show top > All Positive]** , um nur Werte anzuzeigen, die größer als null (0) sind
   * **[!UICONTROL Display “X more”]** um die Anzahl der derzeit maskierten Elemente anzuzeigen
   * **[!UICONTROL At least one >]***&lt; **[!UICONTROL countable dimension name]**>*(nur verfügbar, wenn mit einer denormalen Dimension gearbeitet wird)

      Wenn Sie mit einer denormalen Dimension arbeiten, können Sie mit dieser Option eine Dimension anhand einer zählbaren Dimension maskieren. Wenn diese Option aktiviert ist, zeigt die Tabelle nur die Elemente an, die mindestens ein Element der von Ihnen ausgewählten zählbaren Dimension aufweisen. Die Tabelle zeigt bis zu 1.023 Elemente an.

>[!NOTE]
>
>Da die Adobe [!DNL Platform] verarbeitet Daten in zufälliger Reihenfolge, wenn mindestens eine Maskierung zu mehr als 1.023 Elementen führt, haben die gängigeren und größeren Elemente eine größere Wahrscheinlichkeit, in die Tabelle aufgenommen zu werden.

Wenn Sie die Maske nach oben oder mindestens 1 anzeigen, entspricht die Reihenfolge in der Tabelle standardmäßig den Werten, die von der Auswahl zu diesem Zeitpunkt beeinflusst wurden. Wenn Sie die Auswahl später ändern, ändert sich die Reihenfolge nicht von der ursprünglichen Reihenfolge, es sei denn, die Tabelle wurde neu angeordnet oder die dynamische Auswahl wird aktiviert. Wenn Sie auf **[!UICONTROL Mask]** > **[!UICONTROL Dynamic Selection]**, wird die Tabelle bei jeder Änderung der Auswahl neu sortiert.

**So maskieren Sie Daten mithilfe einer Suche**

* Sie können Daten mit einer der folgenden Suchoptionen maskieren:

   * Klicken Sie mit der rechten Maustaste auf ein Element oder den Titel der gewünschten Dimension und klicken Sie auf **[!UICONTROL Mask]**, dann in der [!DNL Search] -Feld den Satz eingeben, nach dem Sie suchen möchten.

      ![](assets/mnu_Table_MaskSearch.png)

   * Klicken Sie mit der rechten Maustaste auf ein Element oder den Titel der gewünschten Dimension und klicken Sie auf **[!UICONTROL Mask]** > **[!UICONTROL Display search bar]** und geben Sie dann in das Suchfeld, das in der Zelle mit den Dimensionsbezeichnungen angezeigt wird, die Wortgruppe ein, nach der Sie suchen möchten.

      ![](assets/vis_Table_Mask_searchBar.png)

      Wenn Sie einen Suchbegriff eingeben, aktualisiert Data Workbench die Dimension, um Übereinstimmungen widerzuspiegeln.

Um die Maskierung während einer Suche weiter einzuschränken, können Sie eine der folgenden Methoden verwenden:

* Sie können &quot;re:&quot;im [!DNL search] -Feld oder -Leiste verwenden, damit der Suchbegriff als regulärer Ausdruck interpretiert wird. Sie können eine beliebige Syntax verwenden, die regulären Ausdrücken in Ihrem Suchausdruck zugeordnet ist. Weitere Informationen zu regulären Ausdrücken finden Sie im Anhang Regulärer Ausdruck im *Anleitung zur Datensatzkonfiguration*.
* Sie können das $-Symbol als erstes Zeichen in Ihrer Suchzeichenfolge eingeben, um Suchbegriffe zu finden, die mit der eingegebenen Zeichenfolge beginnen, oder als das letzte Zeichen, um Suchbegriffe zu finden, die mit der eingegebenen Zeichenfolge enden.
* Sie können ein Leerzeichen als erstes Zeichen in der Suchzeichenfolge eingeben, um beliebige Wörter in einer Wortgruppe zu finden, die mit der eingegebenen Zeichenfolge beginnen, oder als letztes Zeichen, um nach Wörtern in einer Wortgruppe zu suchen, die mit der eingegebenen Zeichenfolge enden.

Im Folgenden finden Sie Beispiele für verschiedene Möglichkeiten, eine Tabelle mit der Zeichenfolge &quot;on&quot;in einer Suche zu maskieren:

* Durch die Eingabe von &quot;on&quot;wird jeder Satz angezeigt, der die Zeichenfolge &quot;on&quot;an einer beliebigen Stelle im Satz enthält: &quot;**on** Line Banking&quot; &quot;c **on** Tact-Käufer, &quot;bulli&quot;**on** Münzen&quot; &quot;Bank **on** Linie&quot; &quot;Goldopti **on** s&quot; und &quot;silbernes Bulli&quot;**on**.&quot;
* Durch Eingabe von &quot;$on&quot;werden alle Wortgruppen angezeigt, die mit der Zeichenfolge &quot;on&quot;beginnen:

   &quot;**on**&quot;Line Banking&quot;und &quot;**on**-Online-Zahlung.&quot;

* Durch Eingabe von &quot;on$&quot;werden alle Phrasen angezeigt, die mit der Zeichenfolge &quot;on&quot;enden:

   &quot;Silberbulli **on**&quot;und &quot;Goldopti **on**.&quot;

* Durch die Eingabe von &quot;on&quot;wird jeder Satz angezeigt, der ein Wort enthält, das mit der Zeichenfolge &quot;on&quot;beginnt:

   &quot;**on** Bankgeschäfte und Banken **on** Zeile.&quot;

* Durch die Eingabe von &quot;on&quot;wird jeder Satz angezeigt, der ein Wort enthält, das mit der Zeichenfolge &quot;on&quot;endet:

   &quot;bulli **on** Münzen und &quot;Silberbulli&quot;**on**.&quot;

* Bei Verwendung von &quot;on&quot;wird jede Wortgruppe, die die Zeichenfolge &quot;on&quot;enthält, als Wort angezeigt:

   &quot;**on** Bankgeschäfte und Banken **on** Zeile.&quot;
