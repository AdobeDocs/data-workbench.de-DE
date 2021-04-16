---
description: Mit Prozesskarten können Sie den Fluss der Aktivität zwischen Elementen einer Dimension analysieren.
title: Prozesskarte
uuid: f1db41a9-400e-467a-ba59-39831fb166af
exl-id: 019cee7b-a704-4b47-84c6-d3ddc277c43e
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '737'
ht-degree: 0%

---

# Prozesskarte{#process-map}

Mit Prozesskarten können Sie den Fluss der Aktivität zwischen Elementen einer Dimension analysieren.

Sie erstellen Prozesszuordnungen, indem Sie die Elemente einer Dimension per Drag &amp; Drop auf eine leere zweidimensionale (2D) oder dreidimensionale (3D) Zuordnung ziehen. Die Elemente werden zu Knoten auf der Karte. Knoten sind Kreise in 2D-Prozesszuordnungen und -leisten in 3D-Prozesszuordnungen.

![](assets/vis_2DProcessMap.png)

![](assets/vis_3DProcessMap.png)

>[!NOTE]
>
>Eine Prozesszuordnung erhält ihren Namen bei der Analyse der Aktivität zwischen den Prozessschritten. Bei dieser Analyse stellt jedes Element auf der Map einen Prozessschritt dar.

Im Gegensatz zu Pfadbrowsern können Prozesskarten so wenige oder so viele Elemente anzeigen, wie für Ihre Analyse erforderlich sind. Sie wählen die gewünschten Elemente aus und ziehen sie per Drag &amp; Drop auf die Karte. Im Gegensatz zu Pfadbrowsern zeigen Prozesskarten den Fluss der Aktivität in beide Richtungen zwischen einem Element und einem oder mehreren anderen Elementen an.

>[!NOTE]
>
>Damit diese Maps am effektivsten funktionieren, sollten Sie eine Farblegende im Arbeitsbereich öffnen. Informationen zur Verwendung von Farblegenden mit Prozesszuordnungen finden Sie unter [Aktivieren von Farblinks](../../../../home/c-get-started/c-analysis-vis/c-proc-maps/c-act-color-lnks.md#concept-2c9b9f67f2bd4cd7a5431fa21c094edc). Weitere Informationen zu Farblegenden finden Sie unter [Farblegende](../../../../home/c-get-started/c-analysis-vis/c-legends/c-color-leg.md#concept-f84d51dc0d6547f981d0642fc2d01358).

Jede Prozesszuordnung verfügt über eine zugeordnete Basisdimension, Gruppendimension, Ebenendimension und Metrik, die Schlüssel zur Interpretation der in der Prozesszuordnung angezeigten Daten bereitstellt.

Die Standardeinstellungen für die Dimensionen und Metriken einer Prozesszuordnung hängen von der verwendeten Data Workbench ab. Informationen zu den Dimensionen und Metriken, die für Ihre Prozesszuordnungen zur Verfügung stehen, finden Sie im Anwendungshandbuch für Ihre Data Workbench.

* **Basisdimension:** Wenn Sie ein Element per Drag &amp; Drop auf eine Prozesszuordnung ziehen, ziehen Sie ein Element der Basisdimension und legen Sie es ab.
* **Ebenendimension:** Jede Dimension in Ihrem Datensatz hat eine zugehörige Dimension der Ebene (auch als übergeordnetes Element bezeichnet). Die Dimension &quot;level&quot;für Ihre Prozesszuordnung sollte mit der Dimension &quot;level&quot;(oder der Dimension &quot;parent&quot;) für die Basisdimension der Prozesszuordnung identisch sein. Wenn Sie beispielsweise eine Seite (ein Element der Seitendimension) in die Map ziehen, wäre die Dimension &quot;Ansicht&quot;die entsprechende Ebene.
* **Gruppendimension:** Die Gruppendimension legt fest, wie die Elemente der Dimension &quot;Ebene&quot;gruppiert werden, um Verbindungen zwischen Knoten zu bilden. Bei Prozesskarten ist die Gruppendimension aus drei Hauptgründen wichtig:

   * Eine Verbindung zwischen zwei Knoten kann nicht mehr als ein Element einer Gruppendimension umfassen. Um dies zu verstehen, sollten Sie sich ein Beispiel für die Verwendung von Webdaten vorstellen. Angenommen, die Basis-, Ebenen- und Gruppendimensionen für Ihre Prozesszuordnung sind Seiten-, Seiten- bzw. Sitzungselemente. Eine Verbindung von Seite A zu Seite B zeigt an, dass während einer einzelnen Sitzung vor der Ansicht von Seite B eine Ansicht von Seite A stattgefunden hat, ohne dass dazwischenliegende Ansichten anderer Seiten (Nodes) auf der Karte vorhanden sind. Beachten Sie, dass die Ansichten anderer Seiten der Site möglicherweise zwischen den Ansichten der Seiten A und B während der gleichen Sitzung aufgetreten sind. Diese Seiten werden jedoch nicht auf dieser Zuordnung angezeigt.
   * Eine Verbindung zwischen zwei Knoten kann mehrere Elemente der Gruppendimension darstellen. Es kann beispielsweise mehrere Sitzungen geben, in denen eine Ansicht der Seite A vor einer Ansicht der Seite B stattgefunden hat. Daher stellt die Verbindung zwischen Seite A und Seite B alle einzelnen Sitzungen dar, in denen eine Ansicht von Seite A vor einer Ansicht von Seite B stattgefunden hat, ohne dass dazwischenliegende Ansichten anderer Seiten (Nodes) auf der Karte vorhanden sind.
   * Wenn Sie eine Auswahl basierend auf einer Node in einer Prozesszuordnung treffen, wählen Sie alle Elemente der Gruppendimension aus, an der diese Node beteiligt war. Siehe [Vornehmen von Auswahlen in Visualisierungen](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-vis.md#concept-012870ec22c7476e9afbf3b8b2515746). Weitere Informationen zu Auswahlen finden Sie unter [Vornehmen von Auswahlen in Visualisierungen](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-vis.md#concept-012870ec22c7476e9afbf3b8b2515746).

* **Metrik:** Die Größe der Node für ein bestimmtes Element ist proportional zum Wert der Metrik für dieses Element. Größere Knoten geben größere Metrikwerte an als kleinere.

Wenn Sie beispielsweise die Anwendung [!DNL Site] oder HBX verwenden, können Sie Elemente der Dimension &quot;Seite&quot;standardmäßig auf die Prozesszuordnung ziehen. Die Größe der einzelnen Knoten hängt von der Anzahl der Sitzungen ab (definiert durch die Metrik &quot;Sitzungen&quot;), in denen diese Seite angezeigt wurde.

>[!NOTE]
>
>Sie können die Standarddimensionen oder Metriken für eine Prozesszuordnung ändern. Anweisungen zum Konfigurieren einer Prozesszuordnung finden Sie unter [Prozesszuordnungen konfigurieren](../../../../home/c-get-started/c-intf-anlys-ftrs/t-config-proc-maps.md#task-4a95730b18a14bc790a77c013832b2d6).
