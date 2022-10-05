---
description: Eine Wertlegende zeigt definierte Wertereignisse an.
title: Wertlegenden
uuid: 7779f442-2f45-4bf8-a62a-585aaceaeb3a
exl-id: b28ba604-93ef-4081-ae55-937fb537c068
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '648'
ht-degree: 2%

---

# Wertlegenden{#value-legends}

{{eol}}

Eine Wertlegende zeigt definierte Wertereignisse an.

Die Wertlegende wird nur in der HBX konfiguriert und [!DNL Site] Anwendungen, aber sie können für andere Anwendungen konfiguriert werden. Weitere Informationen erhalten Sie von Adobe Consulting Services.

HBX und [!DNL Site], wird ein Wertereignis als Sitzung definiert, die einen Geschäftswert generiert hat. Beispielsweise können die Ereignisdatensätze, die bestimmten Seitenansichten zugeordnet sind (z. B. eine Dankeseite für die Bestellung oder eine Seite zur Anwendungsfertigstellung), Wertereignisse für eine Geschäftsorganisation darstellen.

Mit Wertereignissen können Sie die von der Website generierte Wertmenge messen und verfolgen. Sie können den Geschäftswert für jedes Ereignis in Dollar bewerten und Fragen wie z. B. folgende beantworten:

* Welcher ist der profitabelste Pfad durch die Website?
* Welcher Referrer oder welche Kampagne hat den höchsten Wert generiert?

Für jedes Ereignis zeigt die Legende den Einheitenwert (Wert pro Ereignis) des Ereignisses und den vom Ereignis generierten Gesamtwert an. Mit der Legende können Sie Wertereignisse definieren und ändern und ihnen Einheitenwerte zuweisen.

In der folgenden Tabelle sind die Metriken im Zusammenhang mit Wertereignissen aufgeführt.

| Metrik | Beschreibung |
|---|---|
| Konversion  | Der Prozentsatz der Sitzungen, die einen Geschäftswert generiert haben |
| Wert | Der generierte Geschäftswert in Dollar |
| Durchschnittl. Wert | Der durchschnittliche Geschäftswert, der pro Sitzung in Dollar generiert wurde |

Sie können einfach alles, was Besucher auf der Website tun, als Wertereignis definieren: Senden einer Kundendienstanfrage, Abschließen einer Anwendung, Anzeigen eines Inhalts oder Abschließen eines Kaufs. Jedes Wertereignis entspricht einem Benutzer, der auf eine bestimmte Seite oder einen bestimmten Satz von Seiten auf der Website zugreift, und ist mit einem Geschäftswert in Dollar verknüpft. Sie können beispielsweise davon ausgehen, dass jeder Benutzer, der die Seite &quot;Vielen Dank für Ihren Einkauf&quot;erreicht, eine Beitragsmarge von durchschnittlich 20 USD generiert. Sie würden ein Wertereignis für diese Seite mit einem Wert von 20 USD definieren.

## Definieren neuer Wertereignisse {#section-2ea4d168336e4d2e98b22b636ed43853}

**So definieren Sie ein neues Wertereignis in HBX oder[!DNL Site]**

Wenn Sie ein Wertereignis erstellen, ziehen Sie Website-Seiten, die einen Wert darstellen, aus einer Visualisierung in eine Wertlegende.

1. Öffnen Sie eine Wertlegende.

   ![](assets/lgd_ValueLegend.png)

1. Fügen Sie der Legende aus Prozesskarten, URI-Seitentabellen oder Seitenhierarchieansichten Wertereignisse hinzu:

   * Ziehen Sie aus einer Prozesszuordnung Knoten aus der Prozesszuordnung in die Legende.
   * Drücken Sie in einer URI-Seitentabelle Strg+Alt und ziehen Sie eine Seite aus der Tabelle in die Legende.
   * Klicken Sie in einer Seitenhierarchieansicht auf die linke Ecke eines Knotens (Ordner, Seite oder Gruppe) und ziehen Sie ihn auf die Legende.

   ![](assets/client-leg.png)

   Ihr Mauszeiger zeigt das Wort &quot;Nein&quot; an, bis Ihre Maus die Legende erreicht.

1. Weisen Sie in der Wertlegende jeder Sitzung, für die das Ereignis eintritt, einen Geschäftswert zu:

   1. Im [!DNL Value per Event] klicken Sie auf die Zelle, die der Seite entspricht, die Sie als Wert-Ereignis hinzugefügt haben.
   1. Geben Sie den Dollarbetrag ein, der für den Wert dieses Ereignisses zugewiesen werden soll, und drücken Sie die Eingabetaste.

   ![](assets/lgd_ValueLegend_Value.png)

   Standardmäßig wird die URL der Seite, die Sie als Wertereignis definiert haben, in der Wertlegende angezeigt. Bei Bedarf können Sie auf diese URL in der Legende doppelklicken, um in den Bearbeitungsmodus zu wechseln und das Ereignis umzubenennen. Sie können auch den Wert eines bestimmten Ereignisses jederzeit bearbeiten. Der Data Workbench-Server berechnet automatisch wertereignisbasierte Metriken wie Durchschnittswert und Konversion neu.

Nachdem Sie mindestens ein Wertereignis definiert haben, steht die Dimension Wertsegment zur Verwendung zur Verfügung. Diese Dimension stellt den Gesamtwert dar, den ein Besucher in allen Sitzungen generiert hat.

## Wertereignisse entfernen {#section-25cd90a859384ca183c0fc0998f888cf}

* Klicken Sie mit der rechten Maustaste auf das gewünschte Ereignis und klicken Sie auf **[!UICONTROL Delete Event]**.

   ![](assets/lgd_ValueLegend_deleteEvent.png)

>[!NOTE]
>
>Der Data Workbench-Server berechnet Metriken für den gesamten Datensatz, auf den das von Ihnen verwendete Profil zugreifen kann. Standardmäßig wird die [!DNL Data Workbench Server] berechnet Metriken wie Werte-, Wertereignisse-, Durchschnittswert- und Konversionsmetriken für alle Daten im Analysedatensatz, selbst wenn die Daten nicht aus derselben logischen Quelle stammen.

## Exportieren in Microsoft Excel {#section-feaa7a8eb8124fafbc74169bebaed6d8}

Informationen zum Exportieren von Fenstern finden Sie unter [Exportieren von Fensterdaten](../../../../home/c-get-started/c-wk-win-wksp/c-exp-win-data.md#concept-8df61d64ed434cc5a499023c44197349).
