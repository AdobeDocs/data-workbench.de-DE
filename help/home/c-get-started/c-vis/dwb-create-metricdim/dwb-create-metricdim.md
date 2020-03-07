---
description: Verwenden Sie den Metrikdim-Assistenten, um eine neue Metrikdimension zu erstellen.
title: Metrik-Dim-Assistent
uuid: 77b9bc8e-7625-4fef-9de4-f113f9b2debd
translation-type: tm+mt
source-git-commit: cb3ca4b3b993f5f04f6b6cee25850600ff3d8986

---


# Metrik-Dim-Assistent{#metric-dim-wizard}

Verwenden Sie den Metrikdim-Assistenten, um eine neue Metrikdimension zu erstellen.

Ein Metrik-Dim konvertiert eine Metrik in eine neue Dimension. Beispielsweise zeigt ein Metrik-Dim, der auf einer Metrik aus Seitenansichten und Besucherebene basiert, Dimensionselemente basierend auf der Gesamtanzahl der Seitenansichten für jeden Besucher an. Damit können Sie eine aktuell definierte Metrik, die auf Dimensionselementen basiert, erweitern, um sie als neue Dimension zu erstellen und zu speichern.

## Schritt 1: Dimension und Metrik auswählen {#section-58b6ea7bbba5487ba1a3c264aa3dcb95}

1. **Öffnen Sie den Metrik-Dim-Assistenten**.

   Klicken Sie in einem Arbeitsbereich mit der rechten Maustaste und wählen Sie &quot; **Werkzeuge** &quot;> &quot;Metrikabfrage **erstellen&quot;**.

1. **Benennen Sie den Metrikstempel**.

   Standardmäßig wird das Feld &quot;Name&quot;basierend auf der Ebene- und Metrikauswahl automatisch gefüllt.

1. **Wählen Sie eine Dimensionsebene aus.** Die Dimensionsebene ist die übergeordnete Dimension, die alle Elementwerte enthält, um die Eingabe zu filtern und einen Dimensionstyp zu definieren.

   Zu den Dimensionsebenen gehören:

   * Clickthrough
   * Treffer
   * Product
   * Besuch
   * Besucher

1. **Wählen Sie eine Metrik** aus.

   Wählen Sie eine vordefinierte Metrik aus, um sie zu erweitern und als Metrik zu speichern.

   ![](assets/6_4_workstation_metricdim_metric.png)

1. (Optional) **Erstellen Sie eine Metrikformel**.

   Klicken Sie auf das Feld, um eine benutzerspezifische Metrikformel einzugeben. Der berechnete Wert für die Vorschau wird angezeigt und überprüft den Ausdruck.

   ![](assets/6_4_workstation_metricdim_create_metric.png)

   Sie können Ihren eigenen [Metrikausdruck](https://docs.adobe.com/content/help/en/data-workbench/using/client/qry-lang-syntx/c-syntx-mtrc-exp.html) hinzufügen oder einen anderen Metrik-Editor oder eine Visualisierung ausschneiden und einfügen. Syntaxfehler, Formelfehler, nicht definierte Filter und andere Fehler werden im Assistenten gemeldet.

1. Klicken Sie auf **Weiter**.

## Schritt 2: Format und Set-Behälter {#section-5bddf3cd306545d7806a501637f80f77}

Sie können das Metrikformat auswählen und die Behälterwerte für einen Dimensionsausdruck festlegen.

1. Wählen Sie ein **Format** für den neuen Metrikdim.

   ![](assets/6_4_workstation_metricdim_format_metric.png)

   Das Format definiert, wie die Metrik dargestellt wird, wenn sie in einer Visualisierung geöffnet wird. Diese Formate sind ausgewählte [Printf-Standards](http://www.cplusplus.com/reference/cstdio/printf/), wie nachfolgend definiert:

   ```
   %[flags][width][.precision][length][specifier]
   %
   0.2lf = % _ [flags] 0 [width] .2 [.precision] l [length] f[ specifier]
   ```

   Im Feld **Vorschau** wird ein Wert basierend auf der ausgewählten Metrik und dem ausgewählten Format angezeigt.

1. Ausdruck **für die** Behälterzählung hinzufügen.

   Sie können eine Metrik mit verschiedenen Bereichen oder Behältern definieren. Hiermit werden Untergruppen von Elementen basierend auf der Größe zurückgegeben, z. B. [0-4], [5-10],...). Elemente der Dimensionsebene beziehen sich auf die Elemente, deren Bereich den Wert der Metrik enthält. Siehe Beschreibung des Behälterausdrucks unter [Syntax für Dimensionsausdrücke](https://docs.adobe.com/content/help/en/data-workbench/using/client/qry-lang-syntx/c-syntx-dim-exp.html).

1. Klicken Sie auf **Vorschau** , um vor dem Speichern eine Tabelle mit Metrikdimalwerten zu öffnen.

   ![](assets/6_4_workstation_metricdim_preview.png)

   Die Metrikwerte der Tabellendetails pro Metrik dim.

1. Klicken Sie im Menü **Dimension auf** Anzeigen, um die neu erstellte Dimension der Registerkarte **Dimension** im **Finder** hinzuzufügen.
1. Klicken Sie auf **Weiter**.

## Schritt 3: beenden und speichern {#section-d9043235b18a425f9de0db668d4b1683}

1. Wählen Sie diese Option, um den Metrik-Dim-Editor, die Diagrammvisualisierung oder die Tabelle nach dem Speichern zu starten.

   | Feld | Beschreibung |
   |---|---|
   | Metrik-Dim-Editor starten | Öffnen Sie den Metrik-Dim-Editor. |
   | Startdiagramm | Starten Sie eine PNG-Grafik der Tabelle. |
   | Tabelle starten | Starten Sie eine Tabelle im Arbeitsbereich mit Werten in Spalten, die die Werte der neuen Metrik dim im Vergleich zu den Werten der ausgewählten Metrik auflisten. |

1. Klicken Sie auf **Fertig stellen** und speichern.

   Daraufhin wird ein Dialogfeld zum Speichern geöffnet, in dem Sie die Datei speichern können. Die ausgewählten Optionen zum Anzeigen von Werten werden im Arbeitsbereich geöffnet.

