---
description: Eine Wertelegende zeigt Ereignis mit definierten Werten an.
title: Wertlegenden
uuid: 7779f442-2f45-4bf8-a62a-585aaceaeb3a
exl-id: b28ba604-93ef-4081-ae55-937fb537c068
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '648'
ht-degree: 2%

---

# Wertlegenden{#value-legends}

Eine Wertelegende zeigt Ereignis mit definierten Werten an.

Die Wertelegende wird nur in den HBX- und [!DNL Site]-Anwendungen konfiguriert, kann aber auch für andere Anwendungen konfiguriert werden. Weitere Informationen erhalten Sie bei Adobe Consulting Services.

In HBX und [!DNL Site] wird ein value-Ereignis als Sitzung definiert, die einen Geschäftswert generiert hat. Beispielsweise können die mit bestimmten Ansichten verknüpften Ereignis-Datendatensätze (z. B. eine Danksagungsseite für die Bestellung oder eine Antragsabschlussseite) für eine Geschäftsorganisation wertvolle Ereignis darstellen.

Mit Value Ereignisses können Sie die von der Website generierte Wertschöpfung messen und nachverfolgen. Sie können den Geschäftswert in Dollar für jedes Ereignis bewerten und z. B. folgende Fragen beantworten:

* Welcher ist der rentabelste Pfad durch die Website?
* Welcher Werber oder welche Kampagne hat den meisten Wert generiert?

Für jedes Ereignis zeigt die Legende den Einheitenwert des Ereignisses (Wert pro Ereignis) und den vom Ereignis generierten Gesamtwert an. Mit der Legende können Sie Wertewerte definieren und ändern sowie Ereignis von Einheiten zuweisen.

In der folgenden Tabelle werden die Metriken zu Ereignissen mit Werten Liste.

| Metrik | Beschreibung |
|---|---|
| Konversion  | Der Prozentsatz der Sitzungen, die einen Geschäftswert generiert haben |
| Wert | Der generierte Geschäftswert insgesamt in Dollar |
| Durchschnittl. Wert | Der durchschnittliche Geschäftswert, der pro Sitzung in Dollar generiert wurde |

Sie können einfach alles, was Besucher auf der Website tun, als Ereignis mit Werten definieren: Senden einer Kundendienstanfrage, Ausfüllen einer Anwendung, Anzeigen eines Inhalts oder Abschluss eines Kaufs. Jedes value-Ereignis entspricht einem Benutzer, der auf eine bestimmte Seite oder einen Seitensatz auf der Website zugreift, und ist mit einem Geschäftswert in Dollar verknüpft. Sie können beispielsweise davon ausgehen, dass jeder Benutzer, der die Seite &quot;Vielen Dank für Ihren Einkauf&quot;aufruft, eine Beitragsmarge von durchschnittlich 20 USD erzielt. Sie würden ein Ereignis mit einem Wert von $20 für diese Seite definieren.

## Definieren Sie neue Ereignis {#section-2ea4d168336e4d2e98b22b636ed43853}

**So definieren Sie ein neues Ereignis in HBX oder[!DNL Site]**

Wenn Sie ein Wertseiten-Ereignis erstellen, ziehen Sie die Wertseiten einer Visualisierung in eine Wertelegende.

1. Öffnen Sie eine Wertelegende.

   ![](assets/lgd_ValueLegend.png)

1. hinzufügen Sie Werte-Ereignis aus Prozesszuordnungen, URI-Seitentabellen oder Ansichten der Seitenhierarchie in die Legende ein:

   * Ziehen Sie aus einer Prozesszuordnung Knoten aus der Prozesszuordnung in die Legende.
   * Drücken Sie in einer Tabelle der URI-Seite Strg+Alt und ziehen Sie eine Seite aus der Tabelle in die Legende.
   * Klicken Sie in einer Ansicht für die Seitenhierarchie auf die linke Seite eines Knotens (Ordners,  oder Gruppen) und ziehen Sie ihn auf die Legende.

   ![](assets/client-leg.png)

   Ihr Mauszeiger zeigt das Wort &quot;Nein&quot; an, bis die Maus zur Legende gelangt.

1. Weisen Sie in der Wertesammlung jeder Sitzung, für die das Ereignis auftritt, einen Geschäftswert zu:

   1. Klicken Sie in der Spalte [!DNL Value per Event] auf die Zelle, die der Seite entspricht, die Sie als value-Ereignis hinzugefügt haben.
   1. Geben Sie den Dollarbetrag ein, der dem Wert des Ereignisses zugewiesen werden soll, und drücken Sie die Eingabetaste.

   ![](assets/lgd_ValueLegend_Value.png)

   Standardmäßig wird die URL der Seite, die Sie als value-Ereignis definiert haben, in der Wertelegende angezeigt. Falls gewünscht, können Sie mit der Dublette auf diese URL in der Legende klicken, um in den Bearbeitungsmodus zu wechseln und das Ereignis umzubenennen. Sie können den Wert eines bestimmten Ereignisses jederzeit bearbeiten. Der Data Workbench-Server führt automatisch eine Neuberechnung wertbasierter Ereignis-Metriken wie Durchschnittswert und Konversion durch.

Nachdem Sie mindestens ein Wertesegment definiert haben, steht die Dimension &quot;Wertsegment&quot;zur Verwendung zur Verfügung. Diese Dimension stellt den Gesamtwert dar, den ein Besucher in allen Sitzungen generiert hat.

## Ereignis {#section-25cd90a859384ca183c0fc0998f888cf} entfernen

* Klicken Sie mit der rechten Maustaste auf das gewünschte Ereignis und klicken Sie auf **[!UICONTROL Delete Event]**.

   ![](assets/lgd_ValueLegend_deleteEvent.png)

>[!NOTE]
>
>Der Data Workbench-Server errechnet Metriken über den gesamten Datensatz, auf den das von Ihnen verwendete Profil zugreifen kann. Standardmäßig berechnet das [!DNL Data Workbench Server] Metriken wie &quot;Ereignis&quot;, &quot;Wert&quot;, &quot;Durchschnittswert&quot;und &quot;Umrechnung&quot;für alle Daten im Dataset &quot;Analyse&quot;, auch wenn die Daten nicht aus derselben logischen Quelle stammen.

## Exportieren in Microsoft Excel {#section-feaa7a8eb8124fafbc74169bebaed6d8}

Informationen zum Exportieren von Fenstern finden Sie unter [Exportieren von Fensterdaten](../../../../home/c-get-started/c-wk-win-wksp/c-exp-win-data.md#concept-8df61d64ed434cc5a499023c44197349).
