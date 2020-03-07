---
description: Best Fit Attribution ist ein maschineller Lernansatz zum Zuweisen von Zuordnungswerten über die verschiedenen Kanäle eines erfolgreichen Konversionsereignisses. Data Workbench bewertet automatisch Beiträge zum Erfolg in einem Zeitfenster pro Kanal und erstellt dann ein Zuordnungsmodell basierend auf den tatsächlichen Interaktionsmustern Ihrer Kunden.
title: Best Fit Attribution
uuid: 0c51beb3-8f74-4f8e-9722-0c885140c8ce
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Best Fit Attribution{#best-fit-attribution}

Best Fit Attribution ist ein maschineller Lernansatz zum Zuweisen von Zuordnungswerten über die verschiedenen Kanäle eines erfolgreichen Konversionsereignisses. Data Workbench bewertet automatisch Beiträge zum Erfolg in einem Zeitfenster pro Kanal und erstellt dann ein Zuordnungsmodell basierend auf den tatsächlichen Interaktionsmustern Ihrer Kunden.

**[!UICONTROL Best Fit Attribution]** ermöglicht Ihnen den Vergleich der Interaktionen oder Touches, die zu einem erfolgreichen Verkauf, einer E-Mail-Anmeldung oder anderen Leistungsindikatoren beigetragen haben. Die Zuordnungsanalyse weist den wichtigsten Kontakten automatisch Gewicht zu und bietet ein Zuordnungsmodell pro Kanal, das auf Ihren Daten basiert und auf Ihren Markt- und internen Protokollen reagiert.

![](assets/attrib_windows_5.png)

Wenn ein Kunde beispielsweise Ihre Site über eine kostenlose Suche besucht, dann mit einer Kampagne interagiert und sich dann für eine E-Mail anmeldet, wird die [regelbasierte Zuordnung](/help/home/c-get-started/c-attribution-profiles/c-rules-attrib/c-rules-attrib.md) die erste oder letzte Berührung identifizieren oder die Erfolgszuordnung mithilfe von vorgegebenen Zuordnungsmodellen gleichmäßig über alle Berührungspunkte verteilen. Wenn die regelbasierte Zuordnung vom Benutzer definiert wird, legt das Attribut &quot;Beste Übereinstimmung&quot;Werte durch einen Algorithmus fest, indem die Wahrscheinlichkeit einer Konvertierung als Funktion der beobachteten Berührungspunkte berechnet wird.

>[!NOTE]
>
>Um die **Zuordnung** &quot;Beste Übereinstimmung&quot;in Data Workbench auszuführen, müssen Sie Ihr Serverzertifikat ( [!DNL .pem file]) aktualisieren, um Adobe Analytics Premium zu unterstützen. Sie müssen außerdem **Premium** zu Ihrem benutzerdefinierten [!DNL Profile.cfg] Client hinzufügen und neue Zertifikate von Adobe ClientCare für Server und Report Server erhalten.

## Einfache Einrichtung {#section-db597eaee462412ea7280d1426366c61}

Eine schrittweise Anleitung finden Sie unter [Erstellen einer Zuordnung](../../../../home/c-get-started/c-attribution-profiles/c-attrib-algorithmic/c-attrib-building.md#concept-fede6fc4f592475fa8b351b1765a522d) mit der besten Eignung.

**Legen Sie die Erfolgsmetrik** fest Definieren Sie eine Metrik, die ein Erfolgsereignis darstellt.

![](assets/attrib_windows_1.png)

Die Erfolgsmetrik ist häufig &quot; *Bestellungen*&quot;, obwohl Sie mit Data Workbench eine sehr komplizierte Erfolgsmetrik in Verbindung mit dem Erfolgsfenster definieren können.

**Touch-Metrik** festlegen (optional)

Identifizieren Sie die zu verfolgenden Interaktionen, die zu einer erfolgreichen Konversion führten, und stellen Sie dann die Touch-Metrik ein, über die die Zuordnung berechnet wird.

>[!NOTE]
>
>Das Festlegen einer Touch-Metrik ist nur erforderlich, wenn Sie damit Kanalmetriken aus Drag &amp; Drop-Dimensionselementen ableiten, anstatt vorhandene Kanalmetriken zu verwenden.

Wenn Sie keine Metrik für Kampagnen oder Kanäle definiert haben, aber Dimensionen haben, die Kanäle darstellen, kann die Zuordnung &quot;Beste Übereinstimmung&quot;diese automatisch basierend auf der Touch-Metrik erstellen.

Wenn die Touch-Metrik beispielsweise als *Treffer* festgelegt ist und eine Dimension namens *Medientyp* mit Elementen wie *E-Mail*, *Pressemitteilung*, *Druckanzeige***[!DNL Hits where Media Type = Email] undSocial Mediaangegeben wird, generiert die Visualisierung Kanalmetriken des Formulars, wenn Sie die Elemente per Drag &amp; Drop in die Visualisierung ziehen.

![](assets/attrib_windows_2.png)

Die Touch-Metrik bestimmt dann die Zuordnung von Zuordnungswerten, um Marketinginteraktionen zu identifizieren, die als für den Erfolg relevant erachtet werden. So können Sie Marketingkontakte für die im Erfolgsfenster identifizierte Population qualifizieren. Sie können Metriken wie *Seitenansichten* oder *Treffer* festlegen oder benutzerspezifische Touch-Metriken für Ihre Anforderungen verwenden.

In vielen Fällen sollte das Touch-Fenster das Erfolgsfenster enthalten, um eine lange Vorlaufzeit im Verkaufszyklus zu bewerten.

**Legen Sie die Umsatzmetrik fest.**

Sie können den Umsatz auch über Touchpoints hinweg identifizieren, indem Sie eine entsprechende Umsatzmetrik festlegen. Wenn angegeben, zeigt das Modell die Verteilung des Umsatzes über die Eingabekanäle an. ![](assets/attrib_windows_6.png)

Sie können eine Umsatzmetrik mit Währungsdatentypen festlegen, um den Erfolg über alle definierten und analysierten Top-Touchpoints hinweg zuzuordnen. Diese Metrik unterteilt die endgültigen Umsätze und weist sie basierend auf der vom Algorithmus zugewiesenen Gewichtung zu.

**Legen Sie &quot;Erfolg&quot;und &quot;Touch Windows&quot;fest.**

Das Fenster Erfolg definiert die Population, die geprüft werden soll, sowie den Zeitraum für erfolgreiche Ereignisse, sodass Sie die Zeitfenster und die Populationsbreite angeben können, die für die Analyse über eine Arbeitsbereichsauswahl berücksichtigt werden sollen. Im Fenster &quot; **Erfolg** &quot;werden der Zeitraum und die Population definiert, die auf Erfolgsereignisse untersucht werden sollen. Im **Touch** -Fenster wird der historische Zeitraum angegeben, in dem nach Kanalinteraktionen zu untersuchen ist, die zu den Erfolgsereignissen führen.

>[!NOTE]
>
>Das Festlegen einer Touch-Metrik ist nur erforderlich, wenn Sie versuchen, Erfolgsmetriken automatisch zu erstellen, indem Sie Dimensionselemente in die Visualisierung ziehen.

Sie können einen Tag, einen Monat, ein Jahr oder einen beliebigen verfügbaren Zeitraum festlegen, um Ihre Beurteilung von Erfolgs- und Berührungsereignissen über den gesamten Verkaufszyklus oder für bestimmte Zielgruppen, die Ihre Site aufrufen, zu beschränken. Wenn Sie Fenster zur Begrenzung der Zuordnung erstellen, können Sie Ihre Analyse auf die relevanten Zeiträume für Ihre spezifischen Anforderungen konzentrieren.

![](assets/attrib_windows_4.png)

In vielen Fällen möchten Sie, dass das Touch-Fenster das Erfolgsfenster enthält, damit Sie Ihre Analyse basierend auf Ihrem Verkaufsfenster über eine lange Vorlaufzeit verlängern können. Oder Sie können Berührungen getrennt vom Erfolgsereignis verfolgen und analysieren.

**Wählen Sie die Kanäle aus.**

Bei der Eingabe von Kanälen haben Sie zwei Möglichkeiten.

**Hinzufügen der Touch-Metrik und Hinzufügen von Dimensionselementen zu den Kanälen**

In vielen Fällen sollten Sie die Top-Berührungspunkte nach Dimensionselementen unterteilen, um bestimmte Kanäle zu definieren. Basierend auf den Elementwerten, wählt die Best Fit Attribution automatisch die leistungsstärksten Elemente aus, sortiert sie nach Prozentsatz und zeigt sie in einer Diagrammvisualisierung an.

![](assets/attrib_windows_7.png)

Ein Zuordnungsmodell wird erstellt, indem die Besucher, die während des Erfolgsfensters interagiert haben, und die Kanalberührungen während des Touch-Fensters, die zu einem erfolgreichen Ereignis führten oder nicht, untersucht werden.

## Unterteilen nach Kanälen {#section-a30592b84bc84f57bd2b988824e852d4}

Beim Eingeben von Kanälen stehen Ihnen zwei Optionen zur Verfügung:

* Fügen Sie eine **Touch-Metrik** hinzu und fügen Sie dann **Dimensionselemente** für die Kanäle hinzu.

   **oder**

* Erstellen Sie Metriken, die nach den Kanalelementen filtern, die Sie bewerten möchten.

**Option 1: Fügen Sie eine Touch-Metrik hinzu und fügen Sie Dimensionselemente für Kanäle** hinzu.

Das ist der einfachere Ansatz. Die beste Zuordnung erstellt die Metriken automatisch zur Bewertung der Zuordnung. Im Beispiel unter der Touch-Metrik sind ***Treffer*** und Kanäle: ***Display-Kampagnen***, ***E-Mail-Kampagnen*** und ***SEM-Kampagnen***.

Mit dieser Methode erstellt die Zuordnung der besten Größe eine Metrik im Hintergrund, um die Zuordnung über die Kanäle zu bewerten (die automatisch generierte Metrik wird jedoch nie angezeigt und nicht gespeichert). Im unten stehenden Beispiel werden drei Metriken erstellt, bei denen Treffer für jeden der drei Kanäle gefiltert werden (z. B. *Display-Kampagnen*, *E-Mail-Kampagnen* und *SEM-Kampagnen*). Dies ist der einfachste Fall, da Sie die Metriken mit der besten Zuordnung erstellen lassen.

![](assets/attrib_touch_add_dims.png)

**Option 2: Erstellen Sie eine Metrik**.

Bei der zweiten Option erstellen und speichern Sie die Metriken für die Kanäle, die Sie durch Filtern eines bestimmten Kanals bewerten möchten. Ein Beispiel für eine solche Metrik ist unten dargestellt.

![](assets/attrib_create_metric.png)

Anstatt für die Kanäle die Elemente &quot;Touch-Metrik&quot;und &quot;Dimension&quot;einzugeben, können Sie in der Visualisierung auf die Menüleiste klicken und **Einstiege** > Kanal **hinzufügen** auswählen und dann die von Ihnen erstellten Metriken auswählen.

![](assets/attrib_results_2.png)

Siehe Beispiel der zweiten Methode unten. Sie können sehen, dass die Ergebnisse beider Optionen identisch sind.
