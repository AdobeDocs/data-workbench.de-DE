---
description: Zeigt, wie Sie Titel, Profil, Dimension, Metrik, Filter, Anzeigenkopf, Sortierung nach und Zeitraum konfigurieren.
title: Konfigurieren von Visualisierungen
uuid: aca77188-8f28-4554-8913-412b252f688c
exl-id: 153adf94-5689-4917-9d71-625caef49903
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '795'
ht-degree: 1%

---

# Konfigurieren von Visualisierungen{#configuring-visualizations}

Zeigt, wie Sie Titel, Profil, Dimension, Metrik, Filter, Anzeigenkopf, Sortierung nach und Zeitraum konfigurieren.

Jede Visualisierung auf der Arbeitsfläche des Dashboards hat eine eigene Konfiguration. Wenn eine Visualisierung zum ersten Mal der Arbeitsfläche des Dashboards hinzugefügt wird, wird das Konfigurationsfenster automatisch angezeigt. Nach der Konfiguration kann die Visualisierung jederzeit geändert werden, indem Sie auf das Zahnradsymbol oben rechts im Visualisierungsfenster klicken.

>[!NOTE]
>
>Die Konfigurationsoptionen variieren je nach Art der angezeigten Visualisierung geringfügig.

## Visualisierungstitel {#section-0414844283d745ae912e85f8ea14a51d}

Mit diesem Feld können Sie den Titel anpassen, der oben in der Visualisierung angezeigt wird. Standardmäßig ist der Titel auf **[!UICONTROL Automatic Title]** eingestellt, wodurch automatisch ein Titel für das Visualisierungsfenster generiert wird. Durch Löschen der Schaltfläche **[!UICONTROL Automatic Title]** können Sie einen beliebigen Titel in dieses Feld setzen. (Dieses Feld gilt für alle Visualisierungen.)

![](assets/title.png)

## Profil {#section-16eb0def0a2d4eb289f5bb9200d14754}

In diesem Feld können Sie auswählen, aus welchem Profil Daten visualisiert werden sollen. Durch Klicken auf das Dropdown-Menü erhalten Sie eine Liste der Profil, auf die Sie Zugriff haben. (Dieses Feld gilt nicht für Rich-Text-Visualisierungen.)

Profil sind in Data Workbench definierte Datensätze, die Daten über eine bestimmte Domäne sowie die Dimensionen, Metriken und Filter enthalten, die die Daten begleiten. Ein Profil ist häufig auf die Erfüllung eines bestimmten Zwecks (z. B. Marketing oder Website-Traffic) ausgelegt.

>[!NOTE]
>
>Sie können nur die Profil sehen, für die Ihnen Zugriff gewährt wurde. Weitere Informationen finden Sie unter Zugriffskontrollen.

![](assets/profile.png)

## Dimension {#section-4ebb8c4308a146c3a35c7ac7ab6b579f}

Hier können Sie die Dimension auswählen, die Sie visualisieren möchten. Die Liste wird aus der Liste der Dimensionen gefüllt, die aus dem im Feld &quot;Profil&quot;ausgewählten Profil verfügbar sind. Klicken Sie auf die gewünschte Dimension und dann auf die Schaltfläche Auswählen. (Dieses Feld gilt nicht für Metrik-Legenden und Rich-Text-Visualisierungen.)

Dimensionen sind Kategorien ähnlicher Datentypen. Die Dimension &quot;Wochentage&quot;setzt sich beispielsweise aus den folgenden Datenelementen zusammen: Sonntag, Montag, Dienstag, Mittwoch, Donnerstag, Freitag und Samstag. Dimensionen zeigen, was gemessen wird.

![](assets/dimension.png)

## Metrik(en) {#section-7d46f2f1b9fe4e539b5eb0a0dc6e5ad3}

Hier können Sie die zu visualisierenden Metriken auswählen. Metriken sind quantitative Objekte und werden durch einen quantifizierbaren Ausdruck definiert. Beispielsweise werden die Ansichten der Seite pro Sitzung vom Ausdruck der Anzahl der Ansichten der Seite dividiert durch die Anzahl der Sitzungen abgeleitet. Metriken beantworten die Frage &quot;Wie viele?&quot;

Visualisierungen mit einer Metrik haben ein Auswahlfenster mit einer Metrik:

![](assets/metrics2.png)

Visualisierungen mit mehreren Metriken verfügen über ein Auswahlfenster mit mehreren Metriken:

![](assets/metrics.png)

Die Liste wird aus der Liste der Metriken gefüllt, die aus dem im Feld Profil ausgewählten Profil verfügbar sind.

Klicken Sie auf die gewünschten Metriken und dann auf **[!UICONTROL Select]**. (Dieses Feld gilt nicht für Rich-Text-Visualisierungen.)

## Filter {#section-f8619ae2f8e54735a2c1b0fbb8bb1281}

Wählen Sie die Filter aus, die Sie auf Ihre Visualisierung anwenden möchten. Im Filterauswahlfenster können Sie mehrere Filter aus der Liste auswählen. Die Liste wird aus der Liste der Filter gefüllt, die aus dem im Profil ausgewählten Profil verfügbar sind. Klicken Sie auf den gewünschten Filter und dann auf **[!UICONTROL Select]**.

>[!NOTE]
>
>Hier angewendete Filter werden nur auf die entsprechende Visualisierung angewendet, nicht auf das gesamte Dashboard. Dies ist hilfreich, um die Ergebnisse zweier verschiedener Visualisierungen mit verschiedenen angewendeten Filtern zu vergleichen.

![](assets/filter.png)

## Anzeigen von Tops {#section-7ce71cb0fa6446998b710b427e68b133}

Visualisierungen im Dashboard sind nicht so ausgelegt, dass sie die Gesamtheit der Daten anzeigen. Sie ermöglichen es Ihnen vielmehr, die Anzahl der Dimensionsdatensätze anzugeben, die Sie in der Visualisierung anzeigen möchten. Dies zeigt die höchste Anzahl von Dimensionen in Abhängigkeit vom unten angegebenen Sortierwert an. (Dieses Feld gilt nicht für Tabellen-, Metrik- und Rich-Text-Visualisierungen.)

![](assets/display_top.png)

## Sortieren nach {#section-f686249e20444359bff87c00cc2ba29f}

Auf diese Weise können Sie festlegen, wie die Daten sortiert werden sollen, wenn sie in der Visualisierung angezeigt werden. (Dieses Feld gilt nicht für Tabellen-, Metrik- und Rich-Text-Visualisierungen.) Es gibt mehrere Sortieroptionen:

* **[!UICONTROL Default]** - Geben Sie die nicht sortierten Daten basierend auf der in Data Workbench gespeicherten Sortierreihenfolge zurück. Diese Option ist für zeitbasierte Daten wie Stunde, Tag, Woche oder Monat verfügbar.
* **[!UICONTROL Dimension]** -Sortieren Sie die Daten nach dem alphanumerischen Dimensionswert.
* **[!UICONTROL Metric]** - Sortieren Sie die Daten basierend auf dem Metrikwert und eignen Sie sich für eine schnelle Visualisierung der obersten Dimensionen.
* **[!UICONTROL Descending]** - Sortieren Sie die Daten in absteigender Reihenfolge.
* **[!UICONTROL Ascending]** - Sortieren Sie die Daten in aufsteigender Reihenfolge.

![](assets/sort_by.png)

## Zeitraum {#section-6220368e9e524b46ac735add6ab9edb0}

Mit dieser Visualisierung können Sie den gewünschten Beginn und/oder das Enddatum der Daten angeben, die in der Visualisierung angezeigt werden sollen.

Durch Auswahl von **[!UICONTROL All Dates]**wird der gesamte im Profil verfügbare Datumsbereich angezeigt.

Wenn Sie **[!UICONTROL Range]** auswählen, werden nur die Daten angezeigt, die innerhalb eines bestimmten Bereichs liegen. Zur Eingabe des Datumsbereichs können Sie das Start- und/oder Enddatum eingeben oder eine Kalendereingabe über das Kalendersymbol eingeben.

(Dieses Feld gilt nicht für Rich-Text-Visualisierungen.)

>[!NOTE]
>
>Hier angewendete Datumsbereiche werden nur auf die entsprechende Visualisierung angewendet, nicht auf das gesamte Dashboard. Dies ist nützlich, um die Ergebnisse zweier verschiedener Visualisierungen mit unterschiedlichen Datumsbereichen zu vergleichen.

![](assets/time_period.png)
