---
description: Erstellen Sie mithilfe eines schrittweisen Assistenten Dimensionen, die durch Metrikattribute definiert wurden (Metrikdimensionen). Testen, zeigen Sie die neue Metrikdimension in der Liste der Dimensionen an und speichern Sie sie.
title: Assistent für Metrikdimensionen
uuid: 411b2e28-0958-43bb-a853-7de7b3063818
exl-id: 4d283a00-409c-4d74-a558-40744caba71c
source-git-commit: 79981e92dd1c2e552f958716626a632ead940973
workflow-type: tm+mt
source-wordcount: '485'
ht-degree: 2%

---

# Assistent für Metrikdimensionen{#metric-dim-wizard}

Erstellen Sie mithilfe eines schrittweisen Assistenten Dimensionen, die durch Metrikattribute definiert wurden (Metrikdimensionen). Testen, zeigen Sie die neue Metrikdimension in der Liste der Dimensionen an und speichern Sie sie.

Eine Metrikdimension konvertiert eine Metrik in eine neue Dimension. Beispielsweise zeigt eine Metrikdimension, die auf einer Metrik aus Seitenansichten und Besucherebene basiert, Dimensionselemente basierend auf der Gesamtanzahl der Seitenansichten für jeden Besucher an. Damit können Sie eine aktuell definierte Metrik basierend auf Dimensionselementen erweitern, um sie als neue Dimension zu erstellen und zu speichern.

## Schritt 1: Dimension und Metrik auswählen {#section-58b6ea7bbba5487ba1a3c264aa3dcb95}

1. Öffnen Sie den Assistenten für Metrikdimensionen .

   Klicken Sie in einem Arbeitsbereich mit der rechten Maustaste und wählen Sie **[!UICONTROL Tools]** > **[!UICONTROL Create Metric Dim]** aus.

1. Benennen Sie die Metrikdimension.

   Standardmäßig wird das Feld &quot;Name&quot;basierend auf der Auswahl von Ebene und Metrik automatisch ausgefüllt.

1. Wählen Sie eine Dimension Level aus.

   Die Dimensionsebene ist die übergeordnete Dimension, die alle Elementwerte enthält, die eingegeben und definiert werden sollen, um einen Dimensionstyp zu definieren.

   Zu den Dimensionen gehören:

   * Clickthrough
   * Treffer
   * Produkt
   * Besuch
   * Besucher.

1. Wählen Sie eine Metrik aus.

   Wählen Sie eine vordefinierte Metrik aus, um sie zu erweitern und als Metrik-Dim zu speichern.

   ![](assets/6_4_workstation_metricdim_metric.png)

1. (optional) Erstellen Sie eine Metrikformel.

   Klicken Sie auf das Feld, um eine benutzerdefinierte Metrikformel einzugeben. Der berechnete Vorschauwert erscheint, der den Ausdruck validiert.

   ![](assets/6_4_workstation_metricdim_create_metric.png)

   Sie können Ihren eigenen [Metrikausdruck](https://experienceleague.adobe.com/docs/data-workbench/using/client/qry-lang-syntx/c-syntx-mtrc-exp.html) hinzufügen oder aus einem anderen Metrik-Editor oder einer anderen Visualisierung ausschneiden und einfügen. Syntaxfehler, Formelfehler, nicht definierte Filter und andere Fehler werden im Assistenten gemeldet.

1. Klicken Sie auf **[!UICONTROL Next]**.

## Schritt 2: Formatieren und Festlegen von Buckets {#section-5bddf3cd306545d7806a501637f80f77}

1. Wählen Sie ein Format für die neue Metrikabmessung aus.

   ![](assets/6_4_workstation_metricdim_format_metric.png)

   Das Format definiert, wie die Metrik angezeigt wird, wenn sie in einer Visualisierung geöffnet wird. Diese Formate werden ausgewählt [printf standards](https://www.cplusplus.com/reference/cstdio/printf/), wie unten definiert:

   ```
   %[flags][width][.precision][length][specifier]
   % 0.2lf = % _ [flags] 0 [width] .2 [.precision] l [length] f[ specifier]
   ```

   Im Feld **[!UICONTROL Preview]** wird ein Wert basierend auf der ausgewählten Metrik und dem ausgewählten Format angezeigt.

1. Ausdruck für die Behälteranzahl hinzufügen.

   Sie können einen Metrikdim mit verschiedenen Bereichen oder Behältern definieren. Gibt Teilmengen von Elementen basierend auf der Größe zurück, z. B. [0-4], [5-10],...). Elemente der Dimension-Ebene beziehen sich auf die Elemente, deren Bereich den Metrikwert enthält. Siehe Beschreibung des Behälterausdrucks unter [Syntax für Dimension-Ausdrücke](https://experienceleague.adobe.com/docs/data-workbench/using/client/qry-lang-syntx/c-syntx-dim-exp.html).

1. Klicken Sie auf **[!UICONTROL Preview]** , um die Tabelle der Metrikdimensionswerte vor dem Speichern zu öffnen.

   ![](assets/6_4_workstation_metricdim_preview.png)

   In der Tabelle werden die Metrikwerte pro Metrikdim detailliert beschrieben.

1. Klicken Sie auf **[!UICONTROL Show in Dimension Menu]** , um die neu erstellte Dimension der Registerkarte **Dimension** im **Finder** hinzuzufügen.

1. Klicken Sie auf **[!UICONTROL Next]**.

## Schritt 3: Fertigstellen und Speichern {#section-d9043235b18a425f9de0db668d4b1683}

1. Wählen Sie diese Option aus, um nach dem Speichern den Metrik-Dim-Editor, die Diagrammvisualisierung oder die Tabelle zu starten.

   | Feld | Beschreibung |
   |---|---|
   | **[!UICONTROL Launch Metric Dim Editor]** | Öffnen Sie den Metrikdimensionen-Editor. |
   | **[!UICONTROL Launch Graph]** | Starten Sie eine PNG-Grafik der Tabelle. |
   | **[!UICONTROL Launch Table]** | Starten Sie eine Tabelle im Arbeitsbereich mit Werten in Spalten, die Werte des neuen Metrikabstands im Vergleich zu den Werten der ausgewählten Metrik auflisten. |

1. Klicken Sie auf **[!UICONTROL Finish]** und speichern Sie.

   Daraufhin wird ein Dialogfeld zum Speichern geöffnet, in dem Sie die Datei speichern können. Die ausgewählten Optionen zum Anzeigen von Werten werden im Arbeitsbereich geöffnet.
