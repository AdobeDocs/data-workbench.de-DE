---
description: Richten Sie eine Entscheidungsstruktur ein, indem Sie einen positiven Fall identifizieren und Metrik- und Dimensionseingaben hinzufügen, um die Daten zu bewerten und die Entscheidungsstruktur zu untersuchen.
title: Erstellen einer Entscheidungsstruktur
uuid: 5790d322-5460-444d-95d8-a06696f9a55f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Erstellen einer Entscheidungsstruktur{#building-a-decision-tree}

Richten Sie eine Entscheidungsstruktur ein, indem Sie einen positiven Fall identifizieren und Metrik- und Dimensionseingaben hinzufügen, um die Daten zu bewerten und die Entscheidungsstruktur zu untersuchen.

Führen Sie die folgenden Schritte aus, um einen Entscheidungsbaum zu erstellen.

1. Öffnen Sie eine neue Arbeitsfläche.

   Nach dem Öffnen eines neuen Arbeitsbereichs müssen Sie möglicherweise auf **Hinzufügen** > **Vorübergehend entsperren** klicken.

1. Um den Entscheidungsbaum-Builder zu öffnen, klicken Sie mit der rechten Maustaste auf **[!UICONTROL Visualization]** > **Predictive Analytics** > **Classification** > **Decision Tree Builder**.

1. Legen Sie einen **positiven Fall** fest.

   Sie können eine positive Groß-/Kleinschreibung für eine Entscheidungsstruktur definieren, indem Sie Dimensionen in einem Finder oder Dimensionselemente in einer Tabelle auswählen oder indem Sie einen Filter im Designfilter entwerfen. Der positive Fall kann eine Kombination aus mehreren Auswahlen im Arbeitsbereich sein, einschließlich Filtern, Dimensionen, Elementen und allen Arten von Data Workbench-Visualisierungswerten.

   * **Entwerfen und Anwenden eines Filters** als positiver Fall. Klicken Sie mit der rechten Maustaste in den Arbeitsbereich und wählen Sie **[!UICONTROL Tools]** > **[!UICONTROL Filter Editor]** , um einen Filter anzuwenden.

   * Fügen Sie **Dimensionen** als positiven Fall hinzu. Klicken Sie im Arbeitsbereich mit der rechten Maustaste und wählen Sie **Werkzeuge** > **Finder** (oder wählen Sie **[!UICONTROL Add]** > **[!UICONTROL Finders]** im linken Bereich). Geben Sie einen Dimensionsnamen in das Feld **Suchen** ein und wählen Sie dann eine Dimension aus.

   * Fügen Sie **Metriken** als positiven Fall hinzu. Klicken Sie mit der rechten Maustaste und wählen Sie **Werkzeuge** > **Finder** oder wählen Sie **[!UICONTROL Add]** > **[!UICONTROL Finders]** im linken Bereich, um eine Metriktabelle zu öffnen. Wählen Sie eine Metrik als positiven Fall aus.

   * Fügen Sie **Dimensionselemente** als positiven Fall hinzu. Klicken Sie mit der rechten Maustaste in den Arbeitsbereich und wählen Sie **[!UICONTROL Table]** zum Öffnen von Dimensionselementen und wählen Sie dann aus den Dimensionselementen aus, um die positive Groß-/Kleinschreibung festzulegen.

1. Klicken Sie auf **[!UICONTROL Options]** > **[!UICONTROL Set Positive Case]**.

   Dadurch wird die positive Groß-/Kleinschreibung festgelegt und der Name wird angezeigt. Der Name wird unter der **[!UICONTROL Positive Case]** Überschrift im Arbeitsbereich angezeigt.

   >[!NOTE]
   >
   >Wenn Sie die positive Groß-/Kleinschreibung einstellen, verwendet die Entscheidungsstruktur die aktuelle Workspace-Auswahl, die als Besucher definiert werden kann (oder eine beliebige Zählung auf der obersten Ebene, in den meisten Fällen jedoch als Besucher), die mit der aktuellen Auswahl im Arbeitsbereich übereinstimmen. Diese kombinieren sich als einzelner Filter für einen einzigen positiven Fall (nicht mehrere positive Fälle).

   Wenn Sie **[!UICONTROL Set Positive Case]** auf klicken, wenn keine Auswahl vorhanden ist, wird der positive Fall gelöscht.

1. (Optional) Wählen Sie **[!UICONTROL Set Population Filters]** die zu klassifizierende Besucherpopulation aus.

   Wenn kein Populationsfilter angewendet wird, wird der Schulungssatz von allen Besuchern gezeichnet (Standard ist &quot;Alle&quot;).

   >[!NOTE]
   >
   >Klicken Sie auf **[!UICONTROL Show Complex Filter Description]** , um die Filterskripte für den Filter Positive Groß- und Kleinschreibung und Population anzuzeigen.

1. Fügen Sie **Metriken**, **Dimensionen** und **Dimensionselemente** als Eingaben hinzu.

   Sie können Eingaben durch Ziehen und Ablegen aus den Finder-Bereichen oder aus Tabellen für einzelne Dimensionselemente auswählen. Sie können auch aus dem **[!UICONTROL Metrics]** Menü in der Symbolleiste auswählen.

   * Fügen Sie **Metriken** als Eingaben hinzu.

      Wählen Sie in der Symbolleiste Metriken aus. Drücken Sie **Strg** + **Alt** , um eine oder mehrere Metriken in den Entscheidungsbaumaufbau zu ziehen.

      Die Metrik wird in der Liste **&quot;** Eingabe (Metriken)&quot;als Eingabe mit eindeutiger Farbkodierung angezeigt.

      ![](assets/decision_tree_add_Metrics_inputs.png)

   * Fügen Sie **Dimensionen** als Eingaben hinzu.

      Klicken Sie im Arbeitsbereich mit der rechten Maustaste und wählen Sie **Werkzeuge** > **Finder** und geben Sie den Dimensionsnamen in das Feld **Suchen** ein. Drücken Sie **Strg** + **Alt**, wählen Sie eine Dimension aus und ziehen Sie die Dimension in den Entscheidungsbaumaufbau.

      Die Dimension wird in der Liste &quot; **Eingabe (Dimensionen)** &quot;mit einer eindeutigen Farbcodierung angezeigt.

   * Fügen Sie **Dimensionselemente** als Eingaben hinzu.

      Klicken Sie im Arbeitsbereich mit der rechten Maustaste und wählen Sie eine Dimensionstabelle aus. Wählen Sie Dimensionselemente aus, drücken Sie **Strg** + **Alt** und ziehen Sie die ausgewählten Elemente in den Entscheidungsbaumaufbau.

      Die Dimensionselemente werden mit einer eindeutigen Farbcodierung in der Liste &quot; **Eingabe (Elemente)** &quot;angezeigt.
   >[!IMPORTANT]
   >
   >Sie können bis zu vierzehn zu evaluierende Eingaben auswählen. Wenn zu viele Eingaben hinzugefügt wurden, wird eine Fehlermeldung angezeigt.

1. Wählen Sie **[!UICONTROL Go]** in der Symbolleiste aus.

   Die Entscheidungsstruktur basiert auf den ausgewählten Dimensionen und Metriken. Einfache Metriken wie Zusätze zum Warenkorb werden schnell erstellt, während komplexe Dimensionen wie die Besuchsdauer mit mehreren Datenpunkten langsamer aufgebaut werden, während ein Prozentsatz des Abschlusses angezeigt wird, während er konvertiert wird. Die Baumstruktur wird dann prune und zur Benutzerinteraktion geöffnet. Die Eingaben für Dimension und Metrik werden farblich entsprechend den Knotennamen codiert.

   ![](assets/decision_tree_builder.png)

   Der Blattknoten wird grün (true) oder rot (false) angezeigt, wenn die Struktur beschnitten wurde und nach den gepflückten Zweigen eine Prognose von **True** oder **False** vorliegt.

   >[!NOTE]
   >
   >Das Schulungsmuster wird aus dem Datensatz gezogen, damit der Baum-Builder verwendet werden kann. Data Workbench verwendet 80 Prozent des Musters, um den Baum zu erstellen, und die restlichen 20 Prozent, um die Genauigkeit des Baummodells zu bewerten.

1. Überprüfen Sie die Genauigkeit mithilfe der **[!UICONTROL Confusion Matrix]**.

   Klicken Sie auf **[!UICONTROL Options]** > **[!UICONTROL Confusion Matrix]** , um die Werte für Genauigkeit, Rückruf, Genauigkeit und F-Ergebnis anzuzeigen. Je näher 100 Prozent liegen, desto besser ist das Ergebnis.

   Die Verwechslungsmatrix gibt vier Werte für die Genauigkeit des Modells anhand einer Kombination von Werten an:

   * Tatsächlich positiv (AP)
   * Vorhersage positiv (PP)
   * Tatsächliche Negative (AN)
   * Predicted Negative (PN)
   >[!TIP]
   >
   >Diese Zahlen werden durch Anwendung des Ergebnisbewertungsmodells der 20 % zurückbehaltenen Testdaten ermittelt, die bereits als wahre Antwort bezeichnet werden. Wenn das Ergebnis größer als 50 Prozent ist, wird es als positiver Fall vorhergesagt (der mit dem definierten Filter übereinstimmt). Dann, Genauigkeit = (TP + TN)/(TP + FP + TN + FN), Recall = TP / (TP + FN) und Precision = TP / (TP + FP).

1. **Entdecke den Entscheidungsbaum**.

   Nachdem Sie eine Entscheidungsstruktur erstellt haben, können Sie den Pfad der Prognose anzeigen und alle Besucher identifizieren, die die definierten Kriterien erfüllen. Der Baum identifiziert die Eingabe-Aufteilung für jede Verzweigung anhand ihrer Position und Farbkodierung. Wenn Sie beispielsweise den Knoten Verweisende Domäne auswählen, werden die zu dieser Aufteilung führenden Knoten nach Farbcode links neben der Struktur aufgelistet.

   Sie können die Blattknoten auswählen, um Verzweigungen (Regelsätze) der Entscheidungsstruktur auszuwählen.

   Für dieses Beispiel: Wenn die Besuchsdauer kleiner als 1 ist, gibt es keine Kampagne, es gibt mindestens eine Seitenansicht, keine E-Mail-Anmeldungen und es gab mindestens einen Besuch. Die Projektionen für dieses Kriterium und die Bestellung liegen bei **94,73** Prozent.

   ![](assets/decision_tree_explore.png)

   **Interaktion** mit der Entscheidungsstruktur: Sie können mehrere Knoten in der Struktur auswählen, indem Sie die **Strg-Taste** verwenden, um sie hinzuzufügen, oder indem Sie **Umschalttaste gedrückt halten und zum Löschen klicken** .

   **Farbkodierte Nodes**: Die Farbe der Nodes stimmt mit der Farbe der von Data Workbench zugewiesenen Eingabedimensionen und Metriken überein.

   Helle grüne und rote Knoten auf Blattebene einer gepflückten Verzweigung sagen den Knoten als True oder False voraus.

   | ![](assets/decision_tree_node_true.png) Hellgrün | Identifiziert, dass der Knoten &quot;true&quot;ist und dass alle Bedingungen erfüllt sind. |
   |---|---|
   | ![](assets/decision_tree_node_false.png) Hellrot | Identifiziert, dass der Knoten false ist und nicht alle Bedingungen erfüllt sind. |

1. **Speichern Sie die Entscheidungsstruktur**.

   Sie können die Entscheidungsstruktur in verschiedenen Formaten speichern:

   ![](assets/decison_tree_save.png)

   * Predictive Markup Language (**PMML**), ein XML-basiertes Dateiformat, das von Anwendungen zum Beschreiben und Austauschen von Entscheidungsbaummodellen verwendet wird.
   * **Text** mit einfachen Spalten und Zeilen mit true oder false, Prozentwerten, Anzahl der Mitglieder und Eingabewerten.
   * Eine **Dimension** mit Verzweigungen, die den prognostizierten Ergebniselementen entsprechen.

