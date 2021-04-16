---
description: Statistische Korrelationen messen aussagekräftige Beziehungen, um Chancen durch fortschrittliches Data Mining zu identifizieren.
title: 'Korrelationsmatrix '
uuid: 7f6bdb65-dc31-4e27-9870-4c9402ee6031
exl-id: 79c23bb9-2b4b-4fe0-bfdb-52721fbbdf0c
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '815'
ht-degree: 0%

---

# Korrelationsmatrix{#correlation-matrix}

Statistische Korrelationen messen aussagekräftige Beziehungen, um Chancen durch fortschrittliches Data Mining zu identifizieren.

Mithilfe des Korrelationskoeffizienten [Pearsons](../../../../home/c-get-started/c-analysis-vis/c-correlation-analysis/c-correlation-pearsons.md#concept-5996cb8c89fd4df5b47b7318e7a1d29c) stellt die Korrelationsmatrix Ihnen relevante Informationen zur Verfügung, um die nächsten Schritte in einer Marketing-Kampagne besser zu identifizieren, das Site-Design zu verbessern oder die eingehende Analyse der Kunden für weitere Korrelationsabhängigkeiten fortzusetzen.

## Erstellen einer Korrelationsmatrix {#section-87ed12ccc1af4196a1b6534e621c4cbb}

Die Korrelationsmatrix vergleicht Metriken über eine zählbare oder nicht zählbare Dimension. Die Matrix kann dann geändert werden, um Korrelationen innerhalb der Visualisierung durch Farbauswahl hervorzuheben oder um sie als Textkarte, Heatmap oder beides zu rendern.

1. Öffnen Sie eine Korrelationsmatrix.

   Rechtsklick [!DNL Visualization] > [!DNL Predictive Analytics] > [!DNL Correlation Matrix]. Die Dimensionstabelle wird geöffnet.

   ![](assets/correlation_matrix_2.png)

   Wählen Sie eine Dimension aus, z. B. [!DNL Time] > [!DNL Day of the Week] aus diesem Menü. Die Korrelationstabelle wird geöffnet, wobei die in der Ecke der Matrix identifizierte Dimension und die zugehörige Metrik in der Zeile und Spalte platziert werden. Für die Dimension Tag der Woche ist **[!UICONTROL Visits]** die zugehörige Metrik.

   ![](assets/correlation_matrix_1.png)

   Die Korrelation beträgt 1.000, da Sie eine Metrik mit sich selbst vergleichen (was eine perfekte, aber unbrauchbare Korrelation widerspiegelt).

1. Ändern Sie eine der Metriken.

   Klicken Sie mit der rechten Maustaste und wählen Sie **[!UICONTROL Change Metric]**, um eine Metrik in der Zeile oder Spalte zu ändern. Dadurch wird eine Korrelation zwischen zwei Wertmetriken hergestellt.

   Ändern Sie in diesem Beispiel die Metrik **[!UICONTROL Visits]** in der Spalte in **[!UICONTROL Internal Searches]**. Klicken Sie mit der rechten Maustaste und wählen Sie [!DNL Metric] > [!DNL Custom Events] > [!DNL Custom Event 1-10] > [!DNL Internal Searches].

   ![](assets/correlation_matrix_change_metric.png)

1. hinzufügen Sie weitere Metriken zur Korrelationsmatrix.

   Klicken Sie mit der rechten Maustaste in eine Metrikspalte oder -zeile. Fügen Sie beispielsweise im Menü Metrik [!DNL Metric] > [!DNL Custom Events] > [!DNL Custom Event 1-10] > [!DNL Sign in Error] hinzu.

   ![](assets/correlation_matrix_11.png)

   Die neue Metrik wird in einer Spalte mit einer Korrelationsnummer angezeigt. Sie können weitere Metriken hinzufügen, z. B. **[!UICONTROL Email Signups]**, um die Tabelle zu erstellen.

   ![](assets/correlation_matrix_6.png)

   Oder fügen Sie Zeilen Metriken hinzu, um sie mit Metriken in Spalten zu vergleichen.

   ![](assets/correlation_matrix_add_metric.png)

1. (Optional) Schränken Sie eine Metrik ein, indem Sie ein Dimensionselement hinzufügen.

   Klicken Sie mit der rechten Maustaste in den Arbeitsbereich und wählen Sie **[!UICONTROL Table]**. Drücken Sie in der Tabelle &quot;Offene Dimension&quot;Strg+Alt und ziehen Sie das Element über eine Metrik in einer Spalte oder Zeile. Das Element wird neben der Metrik in Klammern angezeigt.

   Für die Metrik **[!UICONTROL Visits]** können Sie sie beispielsweise einschränken, indem Sie **[!UICONTROL Country]** als **[!UICONTROL New Zealand]** auswählen.

   ![](assets/correlation_matrix_dim_element.png)

   Beachten Sie, dass sich bei der Auswahl eines Dimensionselements die Korrelation in allen Metriken je nach ausgewähltem Dimensionselement ändert. Nach dem Schließen des Dimensionsfensters wird nur die Besuchsmetrik für &quot;Neuseeland&quot;eingeschränkt.

   >[!NOTE]
   >
   >Wenn Sie eine Metrik mit einer Dimensionsbeschränkung ändern (durch Rechtsklick und Auswahl von **[!UICONTROL Change Metric]**), geht das Dimensionselement, das die Metrik einschränkt, verloren. Sie müssen das Dimensionselement erneut hinzufügen.

1. Erstellen Sie einen [Binärfilter](../../../../home/c-get-started/c-analysis-vis/c-correlation-analysis/c-correlation-binary-filter.md#concept-24e1daff43c540f69019f236976da31c), um die Metrik weiter einzuschränken. Klicken Sie mit der rechten Maustaste auf die Metrik in der Tabelle und wählen Sie Binärfilter aus dem Menü.

## Korrelationsplanungs- und Analysen-Ziele {#section-cc322da60b7e417ba29e72b0afeb6f79}

Im Folgenden finden Sie allgemeine Ziele zum Erstellen einer Korrelationsmatrix.

**Identifizieren Sie die Beziehung zwischen zwei Metriken mit einer bestimmten Dimension**. In diesem Beispiel wurde die Matrix auf der Basis der Hauptdimension, Wochentag, erstellt, wobei die Metriken &quot;Besuch&quot;, &quot;E-Mail-Anmeldungen&quot;und &quot;Anmeldefehler&quot;mit den Metrikwerten &quot;Interne Suchen&quot;, &quot;Anmelden&quot;und &quot;Umfrage angezeigt&quot;verglichen wurden.

**Entwickeln von Hypothesen zur Fokussierung der Analyse**. Nach der Ausführung einer Korrelationsmethode müssen Sie als Nächstes nach Abhängigkeiten und Korrelation der Metriken suchen. Wenn Sie beispielsweise verstehen, dass interne Suchvorgänge Auswirkungen auf E-Mail-Anmeldungen haben, können Sie diese Beziehung vorhersagen und die Marketing-Kampagnen oder das Navigationsdesign der Website ändern.

**Identifizieren Sie Metriken, um erweiterte Data Mining-Algorithmen** einzubeziehen. In den meisten Fällen werden die Schlüsselmetriken identifiziert, da sie sich auf mehrere Korrelationen auswirken. Sie können diese Schlüsselmetriken nun verwenden und sie zur tieferen Einsicht auf zusätzliche Data Mining-Analysen anwenden.

## Korrelationsmatrix - Funktionshinweise {#section-ef3626c665ea468a9ecdad624b4132f5}

**Beim Filtern und Auswählen von Dimensionselementen in einer Tabelle werden die Werte** vergleichbar. Wenn Sie beispielsweise die Dimension &quot;Wochentag&quot;verwenden und dann auf ein Element dieser Hauptdimension klicken, z. B. auf einen bestimmten Tag in der Dimensionstabelle &quot;Wochentag&quot;klicken, wird eine Übereinstimmung mit einer Übereinstimmung von 100 % gerendert, die keine brauchbare Korrelation bietet. Da die Wurzeldimension Tag der Woche war, ändert jede Auswahl innerhalb der Dimensionstabelle Tag der Woche die Matrix in eine 1-zu-1-Korrelation.

![](assets/correlation_matrix_10.png)

Die Korrelation zwischen 1 und 1 (wenn eine Auswahl aus allen Elementen besteht) ist jedoch nur an diesem bestimmten Tag vorhanden. Wenn Sie mehrere Auswahlen vornehmen, bleibt diese nicht unbedingt eine 1 bis 1 Korrelation und ergibt nicht immer eine 100%ige Übereinstimmung, unabhängig von der Auswahl von 1 oder 1+ Tagen der Woche.

**Statistische Korrelationen sind nicht gleich dem korrelierten Datenmodell**, dem historischen Referenzzeichen von Adobe Analytics-Produkten. Die statistische Korrelation in Data Workbench basiert auf dem [Pearson-Korrelationsmodell](../../../../home/c-get-started/c-analysis-vis/c-correlation-analysis/c-correlation-pearsons.md#concept-5996cb8c89fd4df5b47b7318e7a1d29c).

**Korrelation in einem Streudiagramm** anzeigen. Klicken Sie mit der rechten Maustaste auf den Titel auf einem Streudiagramm und wählen Sie [!DNL Display Correlation] aus dem Menü [!DNL Visualization]. Der Korrelationswert wird oben rechts im Streudiagramm angezeigt.

>[!NOTE]
>
>In der Streudiagramm- und Pearsons-Matrix wird &quot;Berechnungsfehler&quot;angezeigt, wenn die Anwendung die Berechnung der Pearsons-Korrelation nicht ausführen kann. Dies ist in der Regel auf ungenügende Daten zurückzuführen, die dazu führen können, dass die Gleichung durch 0 dividiert wird.
