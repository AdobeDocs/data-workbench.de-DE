---
description: Legenden sind Fenster, die Sie einem Arbeitsbereich hinzufügen, um die Aufmerksamkeit auf ein bestimmtes Dimensionselement zu lenken, indem Sie eine neue Visualisierung mit einer virtuellen Auswahl dieses Elements erstellen.
title: Hinzufügen von Hinweisen zu einem Arbeitsbereich
uuid: fb3dd74d-da20-40cb-bc96-e56d25003e48
exl-id: fcdb9231-d44a-4287-b799-6a66f7f79432
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 2%

---

# Hinzufügen von Hinweisen zu einem Arbeitsbereich{#adding-callouts-to-a-workspace}

{{eol}}

Legenden sind Fenster, die Sie einem Arbeitsbereich hinzufügen, um die Aufmerksamkeit auf ein bestimmtes Dimensionselement zu lenken, indem Sie eine neue Visualisierung mit einer virtuellen Auswahl dieses Elements erstellen.

Data Workbench wird mit einem Standardsatz von Callout-Typen bereitgestellt. Da Ihre Implementierung vollständig angepasst werden kann, unterscheiden sich die verfügbaren Callout-Typen, die in Ihrer Implementierung angezeigt werden, möglicherweise von den in diesem Handbuch beschriebenen Typen.

Standardmäßig bietet Data Workbench die folgenden Legenden:

* [Anmerkung](../../../home/c-get-started/c-vis/c-call-wkspc.md#section-7b6742160b3f4aed872a09c8c023f90d)
* [Leeres Liniendiagramm](../../../home/c-get-started/c-vis/c-call-wkspc.md#section-5dcc0504bdb64ed4976f880e2f7b277f)
* [Leerlauf-Streudiagramm](../../../home/c-get-started/c-vis/c-call-wkspc.md#section-5dcc0504bdb64ed4976f880e2f7b277f)
* [Leere Tabelle](../../../home/c-get-started/c-vis/c-call-wkspc.md#section-5dcc0504bdb64ed4976f880e2f7b277f)
* [Konfidenzlegende](../../../home/c-get-started/c-vis/c-call-wkspc.md#section-386d1293ddc24a0c9cccb332e20db791)
* [Metriklegende](../../../home/c-get-started/c-vis/c-call-wkspc.md#section-daa6d372c22246d9827880a9d6e804d8)

>[!NOTE]
>
>Legenden funktionieren nur dann als Auswahlen (d. h. sie wirken sich nicht auf andere Visualisierungen innerhalb des Arbeitsbereichs aus), wenn Sie eine Auswahl innerhalb des Callout treffen.

Sie können die Definitionen für die Berechnung von Hinweisen hinzufügen oder bearbeiten, indem Sie die im *Profilname*\Context\Callout-Ordner des [!DNL Server] Installationsordner. Siehe [Konfigurieren von Legenden](../../../home/c-get-started/c-intf-anlys-ftrs/c-config-callouts.md#concept-f6e91e172f5e4c009245c9c549beb76a).

## So fügen Sie einer Visualisierung einen Anmerkungsaufruf hinzu {#section-7b6742160b3f4aed872a09c8c023f90d}

1. Klicken Sie mit der rechten Maustaste auf das Element, für das Sie einen Callout erstellen möchten, und klicken Sie dann auf **[!UICONTROL Add Callout]** > **[!UICONTROL Annotation]** > **[!UICONTROL Image]** oder **[!UICONTROL Add Callout]** > **[!UICONTROL Annotation]** > **[!UICONTROL Text]**. Es wird ein leeres Fenster mit einer sichtbaren Verbindung zu diesem Element angezeigt.

   ![](assets/client-call.png)

   Um Graph-Visualisierungen Legenden hinzuzufügen, müssen Sie unten in der Visualisierung (der Basisachse) mit der rechten Maustaste klicken, um ein Menü zu öffnen.

   ![](assets/visualization_callout_linegraph.png)

1. Führen Sie je nach Auswahl den entsprechenden Schritt aus:

   * Geben Sie für eine Textannotation den gewünschten Text ein oder fügen Sie ihn in den Callout ein und formatieren Sie dann den Text entsprechend. Siehe [Arbeiten mit Textanmerkungen](../../../home/c-get-started/c-analysis-vis/c-annots/c-text-annots.md#concept-55b4aa3e0c58470b8e3c9d452e12a777).
   * Fügen Sie für eine Bildannotation das gewünschte Bild in den Callout ein, indem Sie das Bild kopieren und dann mit der rechten Maustaste in den Callout klicken. Klicken Sie auf **[!UICONTROL Paste image]**. Siehe [Arbeiten mit Bildanmerkungen](../../../home/c-get-started/c-analysis-vis/c-annots/c-image-annots.md#concept-02081ed7d91c4fdcb8fc863f2a51c962).

## So fügen Sie einer Visualisierung einen leeren Tabellen-, Liniendiagramm- oder Streudiagrammaufruf hinzu {#section-5dcc0504bdb64ed4976f880e2f7b277f}

1. Klicken Sie mit der rechten Maustaste auf das Element, für das Sie einen Callout erstellen möchten, und klicken Sie auf **[!UICONTROL Add Callout]** > *&lt;**[!UICONTROL callout type]**>*.

   Das folgende Beispiel zeigt einen leeren Tabellenbericht.

   ![](assets/vis_callout_blank_bar_graph.png)

1. Um eine Dimension auszuwählen, klicken Sie mit der rechten Maustaste auf **[!UICONTROL None]** und klicken Sie auf **[!UICONTROL Change Dimension]** > *&lt;**[!UICONTROL dimension name]**>*.

   >[!NOTE]
   >
   >Wenn Sie die Dimension in einer Visualisierung ändern, die über einen Callout verfügt, ändert sich der Callout von der Verknüpfung mit dem Element der ursprünglichen Dimension zur Verbindung mit der gesamten Visualisierung.

## So fügen Sie einem Visualisierungs-Legende-Callout hinzu {#section-386d1293ddc24a0c9cccb332e20db791}

1. Klicken Sie mit der rechten Maustaste auf das Element, für das Sie den Callout erstellen möchten, und klicken Sie auf **[!UICONTROL Add Callout]** > **[!UICONTROL Confidence Legend]**.

   ![](assets/vis_callout_confidenceLegend.png)

1. Ändern Sie bei Bedarf die [!DNL Metric or Formula] -Feld.

Informationen zu Syntax-Regeln für Ausdrücke finden Sie unter [Syntax der Abfragesprache](../../../home/c-get-started/c-qry-lang-syntx/c-qry-lang-syntx.md#concept-15d1d3f5164a47d49468c5acb7299d9f). Siehe [Konfidenzlegenden](../../../home/c-get-started/c-analysis-vis/c-legends/c-conf-leg.md#concept-73db81c2c218427786c04068aa778efd).

## So fügen Sie einer Visualisierung einen Legenden-Legenden-Legenden-Legenden hinzu {#section-daa6d372c22246d9827880a9d6e804d8}

1. Klicken Sie mit der rechten Maustaste auf das Element, für das Sie den Callout erstellen möchten, und klicken Sie auf **[!UICONTROL Add Callout]** > **[!UICONTROL Metric Legend]**.

   ![](assets/vis_callout_metricLegend.png)

1. Fügen Sie bei Bedarf Metriken zur Metriklegende hinzu oder entfernen Sie sie aus ihr.

Siehe [Metriklegenden](../../../home/c-get-started/c-analysis-vis/c-legends/c-metric-leg.md#concept-e7195bc8f7844ae295bda3a88b028d5b).
