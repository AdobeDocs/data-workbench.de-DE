---
description: Mithilfe der Tendenzauswertung können Sie Kunden auf Grundlage ihrer Möglichkeit einer erfolgreichen Konversion oder des Abschlusses eines bestimmten Ereignisses definieren. Sie können die potenziellen Auswirkungen von Bemühungen maximieren, bevor Sie einen Prozess ausführen oder eine Kampagne leiten.
solution: Analytics
title: Tendenzauswertung
topic: Data workbench
uuid: 4f7163f5-6fe4-4f87-9e27-71ec8b4717af
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Tendenzauswertung{#propensity-scoring}

Mithilfe der Tendenzauswertung können Sie Kunden auf Grundlage ihrer Möglichkeit einer erfolgreichen Konversion oder des Abschlusses eines bestimmten Ereignisses definieren. Sie können die potenziellen Auswirkungen von Bemühungen maximieren, bevor Sie einen Prozess ausführen oder eine Kampagne leiten.

## Bedeutung der Tendenzauswertung {#section-c51ece66effc42de9b754f0f46027c1b}

Mithilfe der Tendenzauswertung können Sie die Datenerfassung durchführen, um versteckte Verhaltensweisen oder Muster zu identifizieren, die in Ihren Daten vorhanden sind. Die Tendenzauswertung kann Ihnen durch eine fokussiertere und objektivere Herangehensweise anstelle einer einfachen Segmentierung oder Filterung insbesondere bei der Erkennung von Clustern ähnlicher Kunden helfen. Darüber hinaus können Sie mithilfe der Tendenzauswertung vorausschauende Funktionen zur Erkennung des Verhaltens eines für Ihr Unternehmen bedeutenden Kunden einrichten.

Sobald Sie die bedeutendste Zielgruppe ermittelt haben, können Sie sie zur effektivsten Interaktion bewegen. Wenn Sie z. B. Business to Business Company sind, haben Sie möglicherweise Interessenten für Verkaufsgespräche, die es Ihnen ermöglichen, die Interessenten zu bewerten und die Wahrscheinlichkeit einer Offline-Konvertierung zu ermitteln. Da durch jeden Lead die Kosten steigen, ist das Erstellen eines Anreizes zur Ermittlung potenzieller Kunden mit der größter Wahrscheinlichkeit für die Konversion eines Verkaufs die effektivste und günstige Möglichkeit zur Konzentration Ihrer Ressourcen.

Mithilfe der Tendenzauswertung können die Faktoren, die eine bestimmte Tendenz am besten erahnen lassen, identifiziert oder die Wahrscheinlichkeit, dass ein Ereignis eintritt, erhöht werden. Darüber hinaus kann die Tendenzauswertung auch für die Beantwortung konkreter Fragen angewendet werden: Wird es beim Kunden zu einer Konversion kommen? Wird der Kunde eine E-Mail beantworten? Wird der Kunde erneut kaufen? Mithilfe der Tendenzauswertung können Sie diese Fragen beantworten und Besucher mit einer Tendenz zu einer Handlung identifizieren, die dann ausgelöst und bewertet werden kann.

Darüber hinaus können Sie Filter verwenden, um eine Untergruppe von Besuchern zu definieren, die mit der optionalen **[!UICONTROL Training Filter]** Funktion bewertet werden sollen. Wenn kein Filter angewendet wird, werden alle Besucher als Ziel für die Bewertung ausgewählt.

## Eigenschaften der Tendenzauswertungsvisualisierung {#section-28413bc7d33b42c59cecb427c1c5a3fa}

Um die Tendenzauswertungsvisualisierung zu öffnen, klicken Sie auf **[!UICONTROL Add]** > **[!UICONTROL Visualization]** > **[!UICONTROL Predictive Analytics]** > **[!UICONTROL Scoring]** > **[!UICONTROL Propensity Score]**.

![](assets/propensity_visualization_GO.png)

Die Tendenzauswertungs-Visualisierung umfasst die folgenden Funktionen, auf die über die Symbolleiste zugegriffen werden kann:

| Symbolleistenfunktion | Beschreibung |
|---|---|
| Los | Klicken Sie auf , um den Bewertungsvorgang nach dem Einrichten der Parameter auszuführen. |
| Reset | Löschen Sie alle Einstellungen in der Visualisierung. |
| Load | Lädt ein zuvor erstelltes ScoreDim, mit dem Sie das Bewertungsmodell ändern und/oder neu erstellen können. |
| Speichern | Speichern Sie die Propensity-Scoring-Visualisierung als Dim-Datei, um sie nach Bedarf aufzurufen und zu öffnen. |
| Absenden | Scoring-Aufgabe für die serverseitige Verarbeitung senden. |
| Optionen | Legen Sie den Schulungsfilter fest, um die Untergruppe der Besucher einzuschränken. Der Standardfilter ist **[!UICONTROL Train on Everyone]** festgelegt, Sie können ihn jedoch ändern, indem Sie Arbeitsflächen auswählen oder einen Filter mit der **[!UICONTROL Filter Editor]** Option erstellen. |
| Ziel festlegen | Legen Sie die abhängige Variable fest. |
| Metrik | Metriken als unabhängige Variablen hinzufügen |
| Elemente | Ziehen Sie Dimensionselemente mit den Tasten `<Ctrl>` + `<Alt>` aus den Dimensionstabellen. |

**Siehe auch**:

* Die [Gewinn- und Steigerungsdiagramme](../../../../home/c-get-started/c-analysis-vis/c-visitor-propensity/c-propensity-gain-lift-chart.md#concept-0d049f6baf534f7fb97f271843ba6c4a). Diese Ansichten können von einem vollständigen Bewertungsmodell oder von [!DNL Add Visualization> Predictive Analytics > Scoring.]
* Der [Modell-Viewer](../../../../home/c-get-started/c-analysis-vis/c-visitor-propensity/c-propensity-model-viewer.md#concept-d4fdf4b335c04b0ea07e70ab9a7ce9dd). Diese Ansichten können von einem vollständigen Bewertungsmodell oder von [!DNL Add Visualization> Predictive Analytics > Scoring.]
* Die Funktion [Komplexe Filterbeschreibung](../../../../home/c-get-started/c-analysis-vis/c-visitor-propensity/c-propensity-complex-filter.md#concept-f9c55e54837f4b5995a00bc950ce5dff) .

## Verwenden der Tendenzauswertungsvisualisierung {#section-63ced03fa2eb44f2b8a98d61a6c88122}

* **Definieren Sie einen oder mehrere Filter, um die Besucherpopulation für die Bewertung** zu definieren. Mit dieser Option **[!UICONTROL Training Filter]** können Sie Besucher auf Basis ausgewählter Kriterien als Ziel auswählen. Wenn kein Schulungsfilter angewendet wird, werden alle Besucher für die Bewertung ausgewählt. Wenn der Schulungsfilter eingestellt ist, ist das Bewertungsergebnis für die definierte Besucherpopulation aussagekräftig, obwohl jedem Besucher weiterhin ein Ergebnis zugewiesen wird.
* **Identifizieren Sie die positiven Besucher**. So definieren Sie die abhängige Variable, um einen Zielfilter anzugeben, der die positiven Besucher identifiziert, die dem gewünschten Ergebnis entsprechen. Dies kann so einfach sein wie Umsatz > 10 USD oder ein viel komplexerer Filter.
* **Der Target-Filter darf nicht mit dem Schulungsfilter**&#x200B;übereinstimmen. Logischerweise sollte der Target-Filter eine Ergänzung zum Schulungsfilter sein, wodurch eine positive Untergruppe der Besucherpopulation bewertet wird.
* **Wählen Sie Variablen von Interesse (unabhängige Variablen) als Eingaben in den Tendenzauswertungsalgorithmus** aus. Dies können Metriken oder einzelne Elemente einer Dimension sein. Die Tendenzauswertung beginnt mit der Vorverarbeitung, genau wie beim [Besuchercluster](../../../../home/c-get-started/c-analysis-vis/c-visitor-cluster/c-visitor-cluster.md#concept-1c2406ef7b284a56a02daa38eaa2e73d). Das System beginnt mit der Erfassung einer bestimmten Anzahl von Beispielen, die der Definition des zuvor eingestellten Schulungsfilters entsprechen (sofern vorhanden). Derzeit wird die Stichprobengröße auf 10 % der Bewertungspopulation (durch Schulungsfilter definiert) festgelegt, mit mindestens 20.000 und höchstens 100.000 und ist an die Größe der bewerteten Population gebunden.

* Eine Ergebnisdimension hat Elemente von 0 % bis 100 %, die die Wahrscheinlichkeit bestimmen, dass die Besucher mit der Target-Variablen übereinstimmen.

