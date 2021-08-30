---
description: Verwenden Sie den Metrikdimensionsassistenten, um eine neue Metrik-Dimension zu erstellen.
title: Assistent für Metrikdimensionen
uuid: 77b9bc8e-7625-4fef-9de4-f113f9b2debd
exl-id: 109fbefc-5608-493d-aec9-8337f21eaa70
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '493'
ht-degree: 3%

---

# Assistent für Metrikdimensionen{#metric-dim-wizard}

Verwenden Sie den Metrikdimensionsassistenten, um eine neue Metrik-Dimension zu erstellen.

Eine Metrikdimension konvertiert eine Metrik in eine neue Dimension. Beispielsweise zeigt eine Metrikdimension, die auf einer Metrik aus Seitenansichten und Besucherebene basiert, Dimensionselemente basierend auf der Gesamtanzahl der Seitenansichten für jeden Besucher an. Damit können Sie eine aktuell definierte Metrik basierend auf Dimensionselementen erweitern, um sie als neue Dimension zu erstellen und zu speichern.

## Schritt 1: Dimension und Metrik auswählen {#section-58b6ea7bbba5487ba1a3c264aa3dcb95}

1. **Öffnen Sie den Assistenten für Metrikdimensionen**.

   Klicken Sie in einem Arbeitsbereich mit der rechten Maustaste und wählen Sie **Tools** > **Metrikdimension** erstellen.

1. **Benennen Sie die Metrikdimension**.

   Standardmäßig wird das Feld &quot;Name&quot;basierend auf der Auswahl von Ebene und Metrik automatisch ausgefüllt.

1. **Wählen Sie eine Dimension Level aus.** Die Dimensionsebene ist die übergeordnete Dimension, die alle Elementwerte enthält, die eingegeben und definiert werden sollen, um einen Dimensionstyp zu definieren.

   Zu den Dimensionen gehören:

   * Clickthrough
   * Treffer
   * Produkt
   * Besuch
   * Besucher.

1. **Wählen Sie eine Metrik** aus.

   Wählen Sie eine vordefinierte Metrik aus, um sie zu erweitern und als Metrik-Dim zu speichern.

   ![](assets/6_4_workstation_metricdim_metric.png)

1. (optional) **Erstellen Sie eine Metrikformel**.

   Klicken Sie auf das Feld, um eine benutzerdefinierte Metrikformel einzugeben. Der berechnete Vorschauwert erscheint, der den Ausdruck validiert.

   ![](assets/6_4_workstation_metricdim_create_metric.png)

   Sie können Ihren eigenen [Metrikausdruck](https://experienceleague.adobe.com/docs/data-workbench/using/client/qry-lang-syntx/c-syntx-mtrc-exp.html) hinzufügen oder aus einem anderen Metrik-Editor oder einer anderen Visualisierung ausschneiden und einfügen. Syntaxfehler, Formelfehler, nicht definierte Filter und andere Fehler werden im Assistenten gemeldet.

1. Klicken Sie auf **Weiter**.

## Schritt 2: Buckets formatieren und festlegen {#section-5bddf3cd306545d7806a501637f80f77}

Sie können das Metrikformat auswählen und die Behälterwerte für einen Dimensionsausdruck festlegen.

1. Wählen Sie ein **Format** für den neuen Metrikdim aus.

   ![](assets/6_4_workstation_metricdim_format_metric.png)

   Das Format definiert, wie die Metrik angezeigt wird, wenn sie in einer Visualisierung geöffnet wird. Diese Formate werden ausgewählt [printf standards](http://www.cplusplus.com/reference/cstdio/printf/), wie unten definiert:

   ```
   %[flags][width][.precision][length][specifier]
   %
   0.2lf = % _ [flags] 0 [width] .2 [.precision] l [length] f[ specifier]
   ```

   Im Feld **Vorschau** wird ein Wert basierend auf der ausgewählten Metrik und dem ausgewählten Format angezeigt.

1. Fügen Sie den Ausdruck **Bucket Count** hinzu.

   Sie können einen Metrikdim mit verschiedenen Bereichen oder Behältern definieren. Gibt Teilmengen von Elementen basierend auf der Größe zurück, z. B. [0-4], [5-10],...). Elemente der Dimension-Ebene beziehen sich auf die Elemente, deren Bereich den Metrikwert enthält. Siehe Beschreibung des Behälterausdrucks unter [Syntax für Dimension-Ausdrücke](https://experienceleague.adobe.com/docs/data-workbench/using/client/qry-lang-syntx/c-syntx-dim-exp.html).

1. Klicken Sie auf **Vorschau** , um die Tabelle der Metrikdimensionswerte vor dem Speichern zu öffnen.

   ![](assets/6_4_workstation_metricdim_preview.png)

   In der Tabelle werden die Metrikwerte pro Metrikdim detailliert beschrieben.

1. Klicken Sie auf **Im Dimension-Menü anzeigen** , um die neu erstellte Dimension der Registerkarte **Dimension** im **Finder** hinzuzufügen.
1. Klicken Sie auf **Weiter**.

## Schritt 3: beenden und speichern {#section-d9043235b18a425f9de0db668d4b1683}

1. Wählen Sie diese Option aus, um nach dem Speichern den Metrik-Dim-Editor, die Diagrammvisualisierung oder die Tabelle zu starten.

   | Feld | Beschreibung |
   |---|---|
   | Metrikdimensionen-Editor starten | Öffnen Sie den Metrikdimensionen-Editor. |
   | Startdiagramm | Starten Sie eine PNG-Grafik der Tabelle. |
   | Launch-Tabelle | Starten Sie eine Tabelle im Arbeitsbereich mit Werten in Spalten, die Werte des neuen Metrikabstands im Vergleich zu den Werten der ausgewählten Metrik auflisten. |

1. Klicken Sie auf **Finish** und speichern Sie.

   Daraufhin wird ein Dialogfeld zum Speichern geöffnet, in dem Sie die Datei speichern können. Die ausgewählten Optionen zum Anzeigen von Werten werden im Arbeitsbereich geöffnet.
