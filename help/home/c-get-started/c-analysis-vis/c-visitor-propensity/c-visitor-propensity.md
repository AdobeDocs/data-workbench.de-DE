---
description: Mithilfe der Tendenzauswertung können Sie Kunden anhand ihrer Möglichkeit einer erfolgreichen Konversion oder des Abschlusses eines bestimmten Ereignisses definieren. Sie können die potenzielle Wirkung von Bemühungen maximieren, bevor Sie einen Prozess ausführen oder eine Kampagne leiten.
title: Tendenzauswertung
uuid: 4f7163f5-6fe4-4f87-9e27-71ec8b4717af
exl-id: 832a1e6c-8eeb-4dcc-97e8-9570e1a6eb4f
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '747'
ht-degree: 24%

---

# Tendenzauswertung{#propensity-scoring}

Mithilfe der Tendenzauswertung können Sie Kunden anhand ihrer Möglichkeit einer erfolgreichen Konversion oder des Abschlusses eines bestimmten Ereignisses definieren. Sie können die potenzielle Wirkung von Bemühungen maximieren, bevor Sie einen Prozess ausführen oder eine Kampagne leiten.

## Vorteile der Tendenzauswertung  {#section-c51ece66effc42de9b754f0f46027c1b}

Mithilfe der Tendenzauswertung können Sie die Datenerfassung durchführen, um versteckte Verhaltensweisen oder Muster zu identifizieren, die in Ihren Daten vorhanden sind. Insbesondere hilft Ihnen die Tendenzauswertung dabei, Cluster ähnlicher Kunden anhand fokussierterer und objektiverer Mittel zu identifizieren, anstatt mit einfacher Segmentierung oder Filterung. Darüber hinaus können Sie mithilfe der Tendenzauswertung Prognosefunktionen zur Identifizierung des Verhaltens von Kunden mit hohem Wert für Ihr Unternehmen einrichten.

Sobald Sie die hochwertige Zielgruppe identifiziert haben, können Sie für eine größtmögliche Wirkung an sie herantreten. Wenn Sie z. B. Business-to-Business-Firma sind, haben Sie möglicherweise Interessenten für Verkaufsgespräche, mit denen Sie dann die Interessenten bewerten und deren Wahrscheinlichkeit, offline zu konvertieren, identifizieren können. Da jeder Lead die Kosten erhöht, ist die Schaffung eines Anreizes zur Identifizierung potenzieller Kunden mit der höchsten Wahrscheinlichkeit der Konvertierung in einen Verkauf die effektivste und kostengünstigste Möglichkeit, Ihre Ressourcen zu konzentrieren.

Die Tendenzauswertung bietet die Möglichkeit, diejenigen Faktoren zu identifizieren, die für ein bestimmtes Ergebnis am besten vorhersagbar sind, oder die Wahrscheinlichkeit zu erhöhen, dass ein Ereignis stattfindet. Sie kann aber auch zur Beantwortung spezifischer Fragen angewendet werden: Wird der Kunde konvertieren? Wird der Kunde auf eine E-Mail reagieren? Wird der Kunde erneut kaufen? Mithilfe der Tendenzauswertung können Sie diese Fragen beantworten und Besucher mit einer Tendenz zu Aktionen identifizieren, die dann eingerichtet und bewertet werden können.

Darüber hinaus können Sie mithilfe von Filtern eine Untergruppe von Besuchern definieren, die mit der optionalen Funktion **[!UICONTROL Training Filter]** bewertet werden sollen. Wenn kein Filter angewendet wird, werden alle Besucher als Ziel für die Bewertung ausgewählt.

## Eigenschaften der Tendenzauswertungsvisualisierung {#section-28413bc7d33b42c59cecb427c1c5a3fa}

Um die Tendenzauswertungsvisualisierung zu öffnen, klicken Sie auf **[!UICONTROL Add]** > **[!UICONTROL Visualization]** > **[!UICONTROL Predictive Analytics]** > **[!UICONTROL Scoring]** > **[!UICONTROL Propensity Score]**.

![](assets/propensity_visualization_GO.png)

Die Tendenzauswertungs-Visualisierung umfasst die folgenden Funktionen, auf die über die Symbolleiste zugegriffen werden kann:

| Symbolleistenfunktion | Beschreibung |
|---|---|
| Los | Klicken Sie auf , um den Bewertungsvorgang nach dem Einrichten der Parameter auszuführen. |
| Zurücksetzen | Löschen Sie alle Einstellungen in der Visualisierung. |
| Load | Lädt ein zuvor erstelltes ScoreDim, mit dem Sie das Bewertungsmodell ändern und/oder neu erstellen können. |
| Speichern | Speichern Sie die Propensity-Scoring-Visualisierung als Dim-Datei, um sie nach Bedarf aufzurufen und zu öffnen. |
| Submit | Scoring-Aufgabe für die serverseitige Verarbeitung senden |
| Optionen | Legen Sie den Schulungsfilter fest, um die Untergruppe der Besucher einzuschränken. Der Standardfilter ist **[!UICONTROL Train on Everyone]**. Sie können ihn jedoch ändern, indem Sie Arbeitsflächen auswählen oder einen Filter mit **[!UICONTROL Filter Editor]** erstellen. |
| Zielgruppe festlegen | Legen Sie die abhängige Variable fest. |
| Metrik | hinzufügen Metriken als unabhängige Variablen. |
| Elemente | Ziehen Sie die Elemente der Dimension mit den Schlüsseln `<Ctrl>` + `<Alt>` aus den Dimensionen. |

**Siehe auch**:

* Die Diagramme [Gewinn und Steigerung](../../../../home/c-get-started/c-analysis-vis/c-visitor-propensity/c-propensity-gain-lift-chart.md#concept-0d049f6baf534f7fb97f271843ba6c4a). Diese Ansichten können von einem vollständigen Bewertungsmodell oder von [!DNL Add Visualization> Predictive Analytics > Scoring.] geöffnet werden
* Der [Modell-Viewer](../../../../home/c-get-started/c-analysis-vis/c-visitor-propensity/c-propensity-model-viewer.md#concept-d4fdf4b335c04b0ea07e70ab9a7ce9dd). Diese Ansichten können von einem vollständigen Bewertungsmodell oder von [!DNL Add Visualization> Predictive Analytics > Scoring.] geöffnet werden
* Die Funktion [Komplexe Filterbeschreibung](../../../../home/c-get-started/c-analysis-vis/c-visitor-propensity/c-propensity-complex-filter.md#concept-f9c55e54837f4b5995a00bc950ce5dff).

## Verwenden der Tendenzauswertungsvisualisierung {#section-63ced03fa2eb44f2b8a98d61a6c88122}

* **Definieren Sie einen oder mehrere Filter, um die Population des Besuchers für die Bewertung** zu definieren. Mit diesem optionalen **[!UICONTROL Training Filter]** können Sie Besucher auf Grundlage der ausgewählten Kriterien Zielgruppe werden. Wenn kein Schulungsfilter angewendet wird, werden alle Besucher für die Bewertung ausgewählt. Wenn der Schulungsfilter eingestellt ist, ist das Bewertungsergebnis für die definierte Besucher-Population aussagekräftig, obwohl jedem Besucher weiterhin eine Punktzahl zugewiesen wird.
* **Identifizieren Sie die positiven Besucher**. So definieren Sie die abhängige Variable, um einen Zielgruppe-Filter anzugeben, der die positiven Besucher identifiziert, die mit dem gewünschten Ergebnis übereinstimmen. Dies kann so einfach sein wie Umsatz > 10 USD oder ein viel komplexerer Filter.
* **Der Filter &quot;Zielgruppe&quot;darf nicht mit dem Filter** &quot;Schulung&quot;identisch sein. Logischerweise sollte der Zielgruppe-Filter eine Ergänzung zum Schulungsfilter sein, wodurch eine positive Untergruppe der Besucher-Population bewertet wird.
* **Wählen Sie Variablen von Interesse (unabhängige Variablen) als Eingaben in den Tendenzauswertungsalgorithmus** aus. Dies können Metriken oder einzelne Elemente einer Dimension sein. Tendenzauswertung bewirkt die Vorverarbeitung von Beginn genau wie in [Besucher Clustering](../../../../home/c-get-started/c-analysis-vis/c-visitor-cluster/c-visitor-cluster.md#concept-1c2406ef7b284a56a02daa38eaa2e73d). Das System beginnt mit der Erfassung einer bestimmten Anzahl von Beispielen, die der Definition des zuvor eingestellten Schulungsfilters entsprechen (sofern vorhanden). Derzeit wird die Stichprobengröße auf 10 % der Bewertungspopulation (durch Schulungsfilter definiert) festgelegt, mit mindestens 20.000 und höchstens 100.000 und ist an die Größe der bewerteten Population gebunden.

* Eine Score-Dimension verfügt über Elemente von 0 % bis 100 %, die die Wahrscheinlichkeit bestimmen, dass die Besucher mit der Variablen &quot;Zielgruppe&quot;übereinstimmen.
