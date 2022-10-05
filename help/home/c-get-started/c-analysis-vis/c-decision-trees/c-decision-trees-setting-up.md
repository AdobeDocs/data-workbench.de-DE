---
description: Richten Sie einen Entscheidungsbaum ein, indem Sie einen positiven Fall identifizieren und Metrik- und Dimensionseingaben hinzufügen, um die Daten zu bewerten und den Entscheidungsbaum zu untersuchen.
title: Erstellen eines Entscheidungsbaums
uuid: 5790d322-5460-444d-95d8-a06696f9a55f
exl-id: 06db9e77-72ea-44c7-8451-d3f195acd196
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1110'
ht-degree: 0%

---

# Erstellen eines Entscheidungsbaums{#building-a-decision-tree}

{{eol}}

Richten Sie einen Entscheidungsbaum ein, indem Sie einen positiven Fall identifizieren und Metrik- und Dimensionseingaben hinzufügen, um die Daten zu bewerten und den Entscheidungsbaum zu untersuchen.

Führen Sie diese Schritte aus, um eine Entscheidungsstruktur zu erstellen.

1. Öffnen Sie einen neuen Arbeitsbereich.

   Nach dem Öffnen eines neuen Arbeitsbereichs müssen Sie möglicherweise auf **Hinzufügen** > **Vorübergehendes Entsperren**.

1. Um den Decision Tree Builder zu öffnen, klicken Sie mit der rechten Maustaste auf **[!UICONTROL Visualization]** > **Predictive Analytics** > **Klassifizierung** > **Decision Tree Builder**.

1. Legen Sie eine **Positiver Fall**.

   Sie können eine positive Groß-/Kleinschreibung für einen Entscheidungsbaum definieren, indem Sie Dimensionen in einem Finder oder Dimensionselemente in einer Tabelle auswählen oder im Designfilter einen Filter entwerfen. Der positive Fall kann eine Kombination aus mehreren Auswahlen im Arbeitsbereich sein, einschließlich Filtern, Dimensionen, Elementen und allen Arten von Visualisierungswerten für Data Workbenchs.

   * **Erstellen und Anwenden eines Filters** als positiven Fall. Klicken Sie mit der rechten Maustaste in den Arbeitsbereich und wählen Sie **[!UICONTROL Tools]** > **[!UICONTROL Filter Editor]** , um einen Filter zu entwerfen und anzuwenden.

   * Hinzufügen **Dimensionen** als positiven Fall. Klicken Sie im Arbeitsbereich mit der rechten Maustaste und wählen Sie **Instrumente** > **Finder** (oder wählen Sie **[!UICONTROL Add]** > **[!UICONTROL Finders]** im linken Bereich). Geben Sie einen Dimensionsnamen in die **Suche** und wählen Sie dann eine Dimension aus.

   * Hinzufügen **Metriken** als positiven Fall. Klicken Sie mit der rechten Maustaste und wählen Sie **Instrumente** > **Finder** oder wählen Sie **[!UICONTROL Add]** > **[!UICONTROL Finders]** im linken Bereich, um eine Metriktabelle zu öffnen. Wählen Sie eine Metrik als positiven Fall aus.

   * Hinzufügen **Dimensionen** als positiven Fall. Klicken Sie mit der rechten Maustaste in den Arbeitsbereich und wählen Sie **[!UICONTROL Table]** um Dimensionselemente zu öffnen, wählen Sie dann aus den Dimensionselementen aus, um Ihre positive Groß-/Kleinschreibung festzulegen.

1. Klicken Sie auf **[!UICONTROL Options]** > **[!UICONTROL Set Positive Case]**.

   Dadurch wird die positive Groß-/Kleinschreibung festgelegt und der Name kann geändert werden. Der Name wird unter dem **[!UICONTROL Positive Case]** in den Arbeitsbereich.

   >[!NOTE]
   >
   >Wenn Sie den positiven Fall festlegen, verwendet die Entscheidungsstruktur die aktuelle Arbeitsbereichsauswahl, die als Besucher (oder eine beliebige Zählung der obersten Ebene, in den meisten Fällen jedoch Besucher) definiert werden kann, die mit der aktuellen Auswahl im Arbeitsbereich übereinstimmen. Diese werden als einzelner Filter für einen einzelnen positiven Fall (nicht für mehrere positive Fälle) kombiniert.

   Klicken **[!UICONTROL Set Positive Case]** Wenn keine Auswahl erfolgt, wird der positive Fall gelöscht.

1. (optional) Wählen Sie **[!UICONTROL Set Population Filters]** , um die zu klassifizierende Besucherpopulation zu definieren.

   Wenn kein Populationsfilter angewendet wird, wird der Trainings-Satz aus allen Besuchern gezogen (der Standardwert lautet &quot;Alle&quot;).

   >[!NOTE]
   >
   >Klicken Sie auf **[!UICONTROL Show Complex Filter Description]** um die Filterskripten für den Filter Positive Groß-/Kleinschreibung und Population anzuzeigen.

1. Hinzufügen **Metriken**, **Dimensionen** und **Dimensionen** als Eingaben.

   Sie können Eingaben auswählen, indem Sie sie aus den Finder-Bedienfeldern oder aus Tabellen für einzelne Dimensionselemente ziehen und ablegen. Sie können auch aus dem **[!UICONTROL Metrics]** in der Symbolleiste.

   * Hinzufügen **Metriken** als Eingaben.

      Wählen Sie in der Symbolleiste Metriken aus. Presse **Strg** + **Alt** , um eine oder mehrere Metriken in den Entscheidungsbaum-Builder zu ziehen.

      Die Metrik wird im **Liste &quot;Eingabe&quot;(Metriken)** als Eingabe mit einzigartiger Farbcodierung.

      ![](assets/decision_tree_add_Metrics_inputs.png)

   * Hinzufügen **Dimensionen** als Eingaben.

      Klicken Sie im Arbeitsbereich mit der rechten Maustaste und wählen Sie **Instrumente** > **Finder** und geben Sie den Dimensionsnamen in die **Suche** -Feld. Presse **Strg** + **Alt**, wählen Sie eine Dimension aus und ziehen Sie die Dimension in den Entscheidungsbaum-Builder.

      Die Dimension wird im **Eingabe (Dimensionen)** Liste mit einer eindeutigen Farbcodierung.

   * Hinzufügen **Dimensionen** als Eingaben.

      Klicken Sie im Arbeitsbereich mit der rechten Maustaste und wählen Sie eine Dimension-Tabelle aus. Dimension Elements auswählen, drücken Sie die **Strg** + **Alt** und ziehen Sie die ausgewählten Elemente in den Entscheidungsbaum-Builder.

      Die Dimensionselemente werden im **Eingabe (Elemente)** Liste mit einer eindeutigen Farbcodierung.
   >[!IMPORTANT]
   >
   >Sie können bis zu vierzehn zu bewertende Eingaben auswählen. Wenn zu viele Eingaben hinzugefügt werden, wird eine Fehlermeldung angezeigt.

1. Auswählen **[!UICONTROL Go]** aus der Symbolleiste.

   Der Entscheidungsbaum wird auf der Grundlage der ausgewählten Dimensionen und Metriken erstellt. Einfache Metriken wie Zusätze zum Warenkorb werden schnell erstellt, während komplexe Dimensionen wie die Besuchsdauer mit mehreren Datenpunkten langsamer aufgebaut werden und ein Prozentsatz des Abschlusses bei der Konvertierung angezeigt wird. Die Baumdiagrammdarstellung schneidet dann und öffnet sich für Benutzerinteraktionen. Die Eingaben von Dimensionen und Metriken sind farbcodiert und entsprechen den Knotennamen.

   ![](assets/decision_tree_builder.png)

   Der Blattknoten wird als grün (true) oder rot (false) angezeigt, wenn der Baum beschnitten wurde und eine Prognose für **True** oder **False** nach den zerschnittenen Zweigen.

   >[!NOTE]
   >
   >Das Schulungsbeispiel wird aus dem Datensatz abgerufen, damit der Baum-Builder verwendet werden kann. Data Workbench verwendet 80 Prozent der Probe zum Erstellen des Baums und die restlichen 20 Prozent, um die Genauigkeit des Baummodells zu bewerten.

1. Überprüfen der Genauigkeit mithilfe der **[!UICONTROL Confusion Matrix]**.

   Klicken **[!UICONTROL Options]** > **[!UICONTROL Confusion Matrix]** um die Werte für Genauigkeit, Recall, Genauigkeit und F-Score anzuzeigen. Je näher 100 Prozent sind, desto besser ist das Ergebnis.

   Die Konfusionsmatrix gibt vier Genauigkeitszähler des Modells anhand einer Kombination von Werten an:

   * Tatsächliche positive Werte (AP)
   * Prognostiziertes positives (PP)
   * Tatsächliche Negative (AN)
   * Prognostizierte Negative (PN)

   >[!TIP]
   >
   >Diese Zahlen erhalten Sie durch Anwendung des resultierenden Scoring-Modells der 20 Prozent zurückbehaltenen Testdaten, die bereits als wahre Antwort bezeichnet werden. Wenn der Wert größer als 50 Prozent ist, wird er als positiver Fall prognostiziert (der mit dem definierten Filter übereinstimmt). Dann, Genauigkeit = (TP + TN)/(TP + FP + TN + FN), Recall = TP / (TP + FN) und Precision = TP / (TP + FP).

1. **Entscheidungsstruktur durchsuchen**.

   Nach dem Generieren einer Entscheidungsstruktur können Sie den Pfad der Prognose anzeigen und alle Besucher identifizieren, die die definierten Kriterien erfüllen. Der Baum identifiziert die Eingabeaufteilung für jeden Zweig anhand seiner Position und Farbkodierung. Wenn Sie beispielsweise den Knoten Referrer-Domäne auswählen, werden die Knoten, die zu dieser Aufspaltung führen, nach Farbcode links vom Baum aufgelistet.

   Sie können die Blattknoten auswählen, um Zweige (Regelsätze) des Entscheidungsbaums auszuwählen.

   Beispiel: Wenn die Besuchsdauer weniger als 1 beträgt, gibt es keine Kampagne, es gibt mindestens einen Seitenaufruf, keine E-Mail-Anmeldungen und es gab mindestens einen Besuch. Die Projektionen für diese Kriterien und die Bestellung sind **94,73** Prozent.

   ![](assets/decision_tree_explore.png)

   **Interaktion mit Entscheidungsbaum**: Sie können mehrere Knoten im Baum mithilfe des Standardmodus **Strg-Klick** oder **Umschalt+Klick** zu löschen.

   **Farbkodierte Knoten**: Die Knotenfarbe entspricht der Farbe der Eingabedimensionen und Metriken, die der Data Workbench zugewiesen sind.

   Helle grüne und rote Knoten auf der Blattebene eines gepflückten Zweigs prognostizieren den Knoten als True oder False.

   | ![](assets/decision_tree_node_true.png) Hellgrün | Identifiziert, dass der Knoten &quot;true&quot;ist und dass alle Bedingungen erfüllt sind. |
   |---|---|
   | ![](assets/decision_tree_node_false.png) Hell rot | Identifiziert, dass der Knoten &quot;false&quot;ist und nicht alle Bedingungen erfüllt sind. |

1. **Entscheidungsbaum speichern**.

   Sie können die Entscheidungsstruktur in verschiedenen Formaten speichern:

   ![](assets/decison_tree_save.png)

   * Prädiktive Markup-Sprache (**PMML**), ein XML-basiertes Dateiformat, das von Anwendungen zur Beschreibung und zum Austausch von Entscheidungsbaummodellen verwendet wird.
   * **Text** einfache Spalten und Zeilen mit dem Wert &quot;true&quot;oder &quot;false&quot;, Prozentwerte, Anzahl der Mitglieder und Eingabewerte anzeigen.
   * A **Dimension** mit Zweigen, die den prognostizierten Ergebniselementen entsprechen.
