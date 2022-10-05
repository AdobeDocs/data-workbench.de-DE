---
description: Die beste Fit Attribution ist ein maschinelles Lernen, um Attributionswerte über die verschiedenen Kanäle eines erfolgreichen Konversionsereignisses hinweg zuzuweisen. Data Workbench wertet automatisch Beiträge zum Erfolg über ein Zeitfenster pro Kanal aus und erstellt dann ein Attributionsmodell basierend auf den tatsächlichen Interaktionsmustern Ihrer Kunden.
title: Best Fit Attribution
uuid: 0c51beb3-8f74-4f8e-9722-0c885140c8ce
exl-id: 225a54d0-370c-4274-8a87-dc287bbb8201
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1141'
ht-degree: 0%

---

# Best Fit Attribution{#best-fit-attribution}

{{eol}}

Die beste Fit Attribution ist ein maschinelles Lernen, um Attributionswerte über die verschiedenen Kanäle eines erfolgreichen Konversionsereignisses hinweg zuzuweisen. Data Workbench wertet automatisch Beiträge zum Erfolg über ein Zeitfenster pro Kanal aus und erstellt dann ein Attributionsmodell basierend auf den tatsächlichen Interaktionsmustern Ihrer Kunden.

**[!UICONTROL Best Fit Attribution]** ermöglicht Ihnen, die Interaktionen oder Änderungen zu vergleichen, die zu einem erfolgreichen Verkauf, einer E-Mail-Anmeldung oder anderen Leistungsindikatoren beigetragen haben. Die Attributionsanalyse weist den wichtigsten Kontakten automatisch Gewichtung zu und bietet ein Attributionsmodell pro Kanal, das auf Ihren Daten basiert und auf Ihrem Markt und Ihren internen Protokollen reagiert.

![](assets/attrib_windows_5.png)

Wenn beispielsweise ein Kunde Ihre Site über eine organische Suche besucht, dann mit einer Kampagne interagiert und sich dann für eine E-Mail anmeldet, [regelbasierte Zuordnung](/help/home/c-get-started/c-attribution-profiles/c-rules-attrib/c-rules-attrib.md) würde den Erstkontakt oder Letztkontakt identifizieren oder die Erfolgszuordnung mithilfe von vordefinierten Attributionsmodellen gleichmäßig über alle Touchpoints verteilen. Wenn regelbasierte Attribution durch den Benutzer definiert wird, legt die Best Fit-Attribute Werte durch einen Algorithmus fest, indem die Wahrscheinlichkeit einer Konversion als Funktion der beobachteten Touchpoints berechnet wird.

>[!NOTE]
>
>Zum Ausführen **Best Fit Attribution** in Data Workbench müssen Sie Ihr Serverzertifikat aktualisieren ( [!DNL .pem file]), um Adobe Analytics Premium zu unterstützen. Sie müssen auch **Premium** zu Ihrer benutzerdefinierten [!DNL Profile.cfg] für den Client und erhalten neue Zertifikate von Adobe ClientCare für Server und Report Server.

## Grundeinstellungen {#section-db597eaee462412ea7280d1426366c61}

Siehe [Erstellen einer am besten geeigneten Attribution](../../../../home/c-get-started/c-attribution-profiles/c-attrib-algorithmic/c-attrib-building.md#concept-fede6fc4f592475fa8b351b1765a522d) für schrittweise Anweisungen.

**Festlegen der Erfolgsmetrik**
Definieren Sie eine Metrik, die ein Erfolgsereignis darstellt.

![](assets/attrib_windows_1.png)

Die Erfolgsmetrik ist häufig *Bestellungen*, obwohl Sie Data Workbench nutzen können, um in Verbindung mit dem Erfolgsfenster eine sehr komplizierte Erfolgsmetrik zu definieren.

**Touch-Metrik festlegen** (optional)

Identifizieren Sie die zu verfolgenden Interaktionen, die zu einer erfolgreichen Konvertierung geführt haben, und legen Sie dann die Touch-Metrik fest, über die die Attribution berechnet wird.

>[!NOTE]
>
>Das Festlegen einer Touch-Metrik ist nur erforderlich, wenn Sie damit Kanalmetriken aus Drag-and-Drop-Dimension-Elementen ableiten, anstatt bestehende Kanalmetriken zu verwenden.

Wenn Sie keine Metrik für Kampagnen oder Kanäle definiert haben, aber Dimensionen für Kanäle aufweisen, kann die Zuordnung &quot;Am besten anpassen&quot;sie basierend auf der Touch-Metrik automatisch für Sie erstellen.

Beispielsweise mit der Touch-Metrik als *Treffer* und eine Dimension namens *Medientyp* mit Elementen, die *Email*, *Pressemitteilung*, *Druckanzeige* und *Social Media*, generiert die Visualisierung die Kanalmetriken des Formulars [!DNL Hits where Media Type = Email] wenn Sie die Elemente per Drag-and-Drop in die Visualisierung ziehen.

![](assets/attrib_windows_2.png)

Die Touch-Metrik bestimmt dann die Zuordnung von Attributionsbewertungen, um Marketing-Interaktionen zu identifizieren, die als für den Erfolg relevant angesehen werden. So können Sie Marketing-Touches für die im Erfolgsfenster identifizierte Population qualifizieren. Sie können Metriken wie *Seitenansichten* oder *Treffer* oder verwenden Sie benutzerspezifische Touchmetriken, die Ihren Anforderungen entsprechen.

In vielen Fällen sollte das Touch-Fenster das Erfolgsfenster enthalten, um eine lange Vorlaufzeit im Verkaufszyklus zu bewerten.

**Legen Sie die Umsatzmetrik fest.**

Sie können den Umsatz über Touchpoints hinweg identifizieren, indem Sie eine entsprechende Umsatzmetrik festlegen. Falls angegeben, zeigt das Modell die Verteilung des Umsatzes über die Eingabekanäle an. ![](assets/attrib_windows_6.png)

Sie können eine Umsatzmetrik mit Währungs-Datentypen festlegen, um den Erfolg über alle definierten und analysierten Top-Touchpoints hinweg zuzuordnen. Diese Metrik schlüsselt den endgültigen Umsatz auf und verteilt ihn auf der Grundlage der vom Algorithmus zugewiesenen Gewichtung.

**Legen Sie die Option &quot;Erfolg&quot;fest und tippen Sie auf &quot;Windows&quot;.**

Im Fenster Erfolg werden die zu prüfende Population sowie der Zeitraum für erfolgreiche Ereignisse definiert, sodass Sie über eine Workspace-Auswahl die Zeitfenster und die Populationsbreite angeben können, die für die Analyse berücksichtigt werden sollen. Die **Erfolg** definiert den Zeitraum und die Population, die auf Erfolgsereignisse untersucht werden sollen. Die **Touch** gibt den historischen Zeitraum an, der auf Kanalinteraktionen untersucht werden soll, die zu den Erfolgsereignissen führen.

>[!NOTE]
>
>Das Festlegen einer Touch-Metrik ist nur erforderlich, wenn Sie versuchen, Erfolgsmetriken automatisch zu erstellen, indem Sie Dimensionselemente in die Visualisierung ziehen.

Sie können einen Tag, einen Monat, ein Jahr oder einen beliebigen verfügbaren Zeitrahmen festlegen, um Ihre Bewertung von Erfolgs- und Touchereignissen über den Verkaufszyklus oder für bestimmte Zielgruppen, die Ihre Site betreten, zu beschränken. Wenn Sie Fenster zur Begrenzung der Attribution erstellen, können Sie Ihre Analyse auf die relevanten Zeiträume für Ihre spezifischen Anforderungen konzentrieren.

![](assets/attrib_windows_4.png)

In vielen Fällen möchten Sie, dass das Touch-Fenster das Erfolgsfenster enthält, damit Sie Ihre Analyse basierend auf Ihrem Verkaufsfenster über eine lange Vorlaufzeit verlängern können. Sie können auch vom Erfolgsereignis getrennte Touches verfolgen und analysieren.

**Wählen Sie die Kanäle aus.**

Beim Einstieg in Kanäle haben Sie zwei Möglichkeiten.

**Fügen Sie die Touch-Metrik hinzu und fügen Sie den Kanälen Dimension-Elemente hinzu.**

In vielen Fällen möchten Sie die Top-Touchpoints nach Dimensionselementen aufschlüsseln, um bestimmte Kanäle zu definieren. Basierend auf den Elementwerten wählt die beste Zuordnung automatisch die besten Ergebnisse aus, sortiert sie nach Prozentsatz und zeigt sie in einer Diagrammvisualisierung an.

![](assets/attrib_windows_7.png)

Ein Attributionsmodell wird erstellt, indem die Besucher verwendet werden, die während Ihres Erfolgsfensters interagiert haben, und indem die Kanalberührungen während des Touch-Fensters untersucht werden, die zu einem erfolgreichen Ereignis geführt haben oder nicht.

## Aufschlüsseln nach Kanälen {#section-a30592b84bc84f57bd2b988824e852d4}

Beim Einstieg in Kanäle stehen Ihnen zwei Optionen zur Verfügung:

* Hinzufügen einer **Touch-Metrik** und fügen Sie **Dimensionen** für die Kanäle.

   **oder**

* Erstellen Sie Metriken, die nach den Kanalelementen filtern, die Sie auswerten möchten.

**Option 1: Hinzufügen einer Touch-Metrik und Hinzufügen von Dimension-Elementen für Kanäle**.

Dies ist der einfachere Ansatz. Die beste Zuordnung erstellt die Metriken automatisch, um sie für die Attribution auszuwerten. Im Beispiel unter ist die Touchmetrik ***Treffer*** und Kanäle sind: ***Anzeigen von Kampagnen***, ***E-Mail-Kampagnen*** und ***SEM-Kampagnen***.

Mit dieser Methode erstellt die Best Fit Attribution eine Metrik im Hintergrund zur Bewertung der Kanalzuordnung (die automatisch generierte Metrik wird jedoch nie angezeigt und nicht gespeichert). Im folgenden Beispiel werden drei Metriken erstellt, bei denen Treffer für jeden der drei Kanäle gefiltert werden (z. B. *Anzeigen von Kampagnen*, *E-Mail-Kampagnen* und *SEM-Kampagnen*). Dies ist der einfachste Fall, da Sie die Metriken mit der besten Zuordnung erstellen lassen.

![](assets/attrib_touch_add_dims.png)

**Option 2: Erstellen einer Metrik**.

In der zweiten Option erstellen und speichern Sie die Metriken für die Kanäle, die Sie auswerten möchten, indem Sie einen bestimmten Kanal filtern. Nachfolgend finden Sie ein Beispiel für eine solche Metrik.

![](assets/attrib_create_metric.png)

Anstatt dann eine Touch-Metrik und Kanalelemente für die Dimensionen einzugeben, können Sie auf die Menüleiste in der Visualisierung klicken und die Option **Eingaben** > **Kanal hinzufügen** und wählen Sie dann die von Ihnen erstellten Metriken aus.

![](assets/attrib_results_2.png)

Siehe Beispiel der zweiten Methode unten. Sie können sehen, dass die Ergebnisse beider Optionen identisch sind.
