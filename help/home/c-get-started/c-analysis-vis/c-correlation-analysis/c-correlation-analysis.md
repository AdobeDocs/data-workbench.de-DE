---
description: Statistische Korrelationen messen aussagekräftige Beziehungen, um Chancen durch fortschrittliches Data Mining zu identifizieren.
title: Korrelationsmatrix
uuid: 7f6bdb65-dc31-4e27-9870-4c9402ee6031
exl-id: 79c23bb9-2b4b-4fe0-bfdb-52721fbbdf0c
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '815'
ht-degree: 0%

---

# Korrelationsmatrix{#correlation-matrix}

{{eol}}

Statistische Korrelationen messen aussagekräftige Beziehungen, um Chancen durch fortschrittliches Data Mining zu identifizieren.

Verwendung der [Persons Korrelationskoeffizient](../../../../home/c-get-started/c-analysis-vis/c-correlation-analysis/c-correlation-pearsons.md#concept-5996cb8c89fd4df5b47b7318e7a1d29c)enthält die Korrelationsmatrix relevante Informationen, um die nächsten Schritte einer Marketing-Kampagne besser zu identifizieren, das Site-Design zu verbessern oder die eingehende Kundenanalyse für zusätzliche Korrelationsabhängigkeiten fortzusetzen.

## Erstellen einer Korrelationsmatrix {#section-87ed12ccc1af4196a1b6534e621c4cbb}

Die Korrelationsmatrix vergleicht Metriken über eine zählbare oder nicht zählbare Dimension. Die Matrix kann dann geändert werden, um Korrelationen innerhalb der Visualisierung durch Farbauswahl hervorzuheben oder als Textkarte, Heatmap oder beides zu rendern.

1. Öffnen Sie eine Korrelationsmatrix.

   Rechtsklick [!DNL Visualization] > [!DNL Predictive Analytics] > [!DNL Correlation Matrix]. Die Dimensionstabelle wird geöffnet.

   ![](assets/correlation_matrix_2.png)

   Wählen Sie eine Dimension aus, z. B. [!DNL Time] > [!DNL Day of the Week] aus diesem Menü. Die Korrelationstabelle wird geöffnet, wobei die Dimension in der Ecke der Matrix identifiziert und die zugehörige Metrik in der Zeile und Spalte platziert wird. Für die Dimension Wochentag gilt Folgendes: **[!UICONTROL Visits]** ist die zugehörige Metrik.

   ![](assets/correlation_matrix_1.png)

   Die Korrelation beträgt 1.000, da Sie eine Metrik mit sich selbst vergleichen (was eine perfekte, aber unbrauchbare Korrelation widerspiegelt).

1. Ändern Sie eine der Metriken.

   Klicken Sie mit der rechten Maustaste und wählen Sie **[!UICONTROL Change Metric]** , um eine Metrik in der Zeile oder Spalte zu ändern. Dadurch wird eine Korrelation zwischen zwei Wertmetriken hergestellt.

   Ändern Sie für dieses Beispiel die **[!UICONTROL Visits]** Metrik in der Spalte zu **[!UICONTROL Internal Searches]**. Klicken Sie mit der rechten Maustaste und wählen Sie [!DNL Metric] > [!DNL Custom Events] > [!DNL Custom Event 1-10] > [!DNL Internal Searches].

   ![](assets/correlation_matrix_change_metric.png)

1. Fügen Sie der Korrelationsmatrix weitere Metriken hinzu.

   Klicken Sie mit der rechten Maustaste in eine Metrikspalte oder -zeile. Fügen Sie beispielsweise im Menü Metrik [!DNL Metric] > [!DNL Custom Events] > [!DNL Custom Event 1-10] > [!DNL Sign in Error].

   ![](assets/correlation_matrix_11.png)

   Die neue Metrik wird in einer Spalte mit einer Korrelationsnummer angezeigt. Sie können weitere Metriken hinzufügen, z. B. **[!UICONTROL Email Signups]**, um die Tabelle zu erstellen.

   ![](assets/correlation_matrix_6.png)

   Oder fügen Sie Zeilen Metriken hinzu, um sie mit Metriken in Spalten zu vergleichen.

   ![](assets/correlation_matrix_add_metric.png)

1. (Optional) Halten Sie eine Metrik ein, indem Sie ein Dimensionselement hinzufügen.

   Klicken Sie mit der rechten Maustaste in den Arbeitsbereich und wählen Sie **[!UICONTROL Table]**. Drücken Sie in der Tabelle &quot;Offene Dimension&quot;Strg+Alt und ziehen Sie das Element auf eine Metrik in einer Spalte oder Zeile. Das Element wird neben der Metrik in eckigen Klammern angezeigt.

   Beispiel: für die **[!UICONTROL Visits]** Metrik, können Sie sie einschränken, indem Sie die **[!UICONTROL Country]** as **[!UICONTROL New Zealand]**.

   ![](assets/correlation_matrix_dim_element.png)

   Beachten Sie, dass sich bei der Auswahl eines Dimensionselements die Korrelation in allen Metriken basierend auf dem ausgewählten Dimensionselement ändert. Nur die Besuchsmetrik wird für &quot;Neuseeland&quot;eingeschränkt, sobald das Dimensionsfenster geschlossen wird.

   >[!NOTE]
   >
   >Wenn Sie eine Metrik mit einer Dimensionsbegrenzung ändern (durch Rechtsklicken und Auswählen **[!UICONTROL Change Metric]**), geht das Dimensionselement, das die Metrik einschränkt, verloren. Sie müssen das Dimensionselement erneut hinzufügen.

1. Erstellen Sie eine [Binärfilter](../../../../home/c-get-started/c-analysis-vis/c-correlation-analysis/c-correlation-binary-filter.md#concept-24e1daff43c540f69019f236976da31c) , um die Metrik weiter einzuschränken. Klicken Sie mit der rechten Maustaste auf die Metrik in der Tabelle und wählen Sie im Menü Binärfilter aus.

## Korrelationsplanung und Analyseziele {#section-cc322da60b7e417ba29e72b0afeb6f79}

Im Folgenden finden Sie allgemeine Ziele zum Erstellen einer Korrelationsmatrix.

**Identifizieren der Beziehung zwischen zwei Metriken mit einer bestimmten Dimension**. In diesem Beispiel wurde die Matrix auf der Kerndimension Wochentag mit den Metriken Besuch, E-Mail-Anmeldungen und Sign-In-Fehler im Vergleich zu internen Suchvorgängen, Anmeldungen und aufgezeigten Survey -Metriken erstellt.

**Hypothesen zur Fokusanalyse entwickeln**. Nach der Durchführung einer Korrelationsanalyse besteht der nächste Schritt darin, nach Abhängigkeiten und Korrelationen der Metriken zu suchen. Wenn Sie beispielsweise wissen, dass interne Suchvorgänge sich auf E-Mail-Anmeldungen auswirken, können Sie über einen Pfad diese Beziehung vorhersagen und Marketingkampagnen oder das Navigationsdesign einer Website ändern.

**Identifizieren Sie Metriken, um erweiterte Data-Mining-Algorithmen einzubeziehen.**. In den meisten Fällen werden die Schlüsselmetriken identifiziert, da sie mehrere Korrelationen beeinflussen. Sie können diese Schlüsselmetriken nun verwenden und sie auf zusätzliche Data-Mining-Analysen anwenden, um tiefere Einblicke zu erhalten.

## Funktionshinweise zur Korrelationsmatrix {#section-ef3626c665ea468a9ecdad624b4132f5}

**Filtern und Auswählen von Dimensionselementen in einer Tabelle vergleichen sich wie Werte**. Wenn Sie beispielsweise die Dimension Wochentag verwenden und dann auf ein Element dieser Kerndimension klicken, z. B. auf einen bestimmten Tag in der Dimensionstabelle Wochentag klicken, wird eine 1:1-Übereinstimmung zu 100 % gerendert, was keine brauchbare Korrelation bietet. Da die Hauptdimension Tag der Woche war, ändert sich bei jeder Auswahl innerhalb der Dimensionstabelle Tag der Woche die Matrix in eine Eins-zu-Eins-Korrelation.

![](assets/correlation_matrix_10.png)

Die 1:1-Korrelation (wenn eine einzelne Auswahl aus allen Elementen besteht) ist jedoch nur an diesem bestimmten Tag verfügbar. Wenn Sie mehrere Auswahlen vornehmen, bleibt diese nicht notwendigerweise eine 1:1-Korrelation und liefert nicht immer eine 100-prozentige Übereinstimmung, unabhängig von der Auswahl von 1 oder 1+ Tagen der Woche.

**Statistische Korrelationen sind nicht gleich dem korrelierten Datenmodell**, die historische Referenz zu Adobe Analytics-Produkten. Die statistische Korrelation in Data Workbench basiert auf der [Pearson-Korrelationsmodell](../../../../home/c-get-started/c-analysis-vis/c-correlation-analysis/c-correlation-pearsons.md#concept-5996cb8c89fd4df5b47b7318e7a1d29c).

**Anzeigen der Korrelation in einem Streudiagramm**. Klicken Sie mit der rechten Maustaste auf einen Titel auf einem Streudiagramm und wählen Sie [!DNL Display Correlation] von [!DNL Visualization] Menü. Der Korrelationswert wird oben rechts im Streudiagramm angezeigt.

>[!NOTE]
>
>In der Streudiagramm- und Persons-Matrix wird &quot;Berechnungsfehler&quot;angezeigt, wenn die Anwendung die Berechnung der Persons-Korrelation nicht ausführen kann. Dies liegt normalerweise an unzureichenden Daten, was dazu führen kann, dass die Gleichung versucht, sie durch 0 zu teilen.
