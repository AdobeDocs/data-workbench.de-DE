---
description: Mit Prozesskarten können Sie den Fluss der Aktivität zwischen Elementen einer Dimension analysieren.
solution: Analytics
title: Prozesskarte
topic: Data workbench
uuid: f1db41a9-400e-467a-ba59-39831fb166af
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Prozesskarte{#process-map}

Mit Prozesskarten können Sie den Fluss der Aktivität zwischen Elementen einer Dimension analysieren.

Sie erstellen Prozesszuordnungen, indem Sie die Elemente einer Dimension per Drag &amp; Drop auf eine leere zweidimensionale (2D) oder dreidimensionale (3D) Zuordnung ziehen. Die Elemente werden zu Knoten auf der Karte. Knoten sind Kreise in 2D-Prozesszuordnungen und -leisten in 3D-Prozesszuordnungen.

![](assets/vis_2DProcessMap.png)

![](assets/vis_3DProcessMap.png)

>[!NOTE]
>
>Eine Prozesszuordnung erhält ihren Namen aus ihrer Verwendung bei der Analyse des Aktivitätsflusses zwischen den Schritten in einem Prozess. Bei dieser Art von Analyse stellt jedes Element auf der Map einen Schritt im Prozess dar.

Im Gegensatz zu Pfadbrowsern können Prozesszuordnungen so wenige oder so viele Elemente wie für Ihre Analyse erforderlich anzeigen. Sie wählen die gewünschten Elemente aus und ziehen sie per Drag &amp; Drop auf die Karte. Im Gegensatz zu Pfadbrowsern zeigen Prozesskarten den Aktivitätsfluss in beide Richtungen zwischen einem Element und einem oder mehreren anderen Elementen an.

>[!NOTE]
>
>Damit diese Maps am effektivsten funktionieren, sollten Sie eine Farblegende im Arbeitsbereich öffnen. Weitere Informationen zur Verwendung von Farblegenden mit Prozesskarten finden Sie unter [Aktivieren von Farblinks](../../../../home/c-get-started/c-analysis-vis/c-proc-maps/c-act-color-lnks.md#concept-2c9b9f67f2bd4cd7a5431fa21c094edc). Weitere Informationen zu Farblegenden finden Sie unter [Farblegende](../../../../home/c-get-started/c-analysis-vis/c-legends/c-color-leg.md#concept-f84d51dc0d6547f981d0642fc2d01358).

Jede Prozesszuordnung verfügt über eine zugeordnete Basisdimension, Gruppendimension, Ebenendimension und Metrik, die Schlüssel zur Interpretation der in der Prozesszuordnung angezeigten Daten bereitstellt.

Die Standardeinstellungen für die Dimensionen und Metriken einer Prozesszuordnung hängen von der von Ihnen verwendeten Data Workbench-Anwendung ab. Informationen zu den Dimensionen und Metriken, die für Ihre Prozesszuordnungen verfügbar sind, finden Sie im Anwendungshandbuch für Ihre Data Workbench-Anwendung.

* **Basisdimension:** Wenn Sie ein Element per Drag &amp; Drop auf eine Prozesszuordnung ziehen, ziehen Sie ein Element der Basisdimension und legen Sie es ab.
* **Ebene:** Jede Dimension in Ihrem Datensatz hat eine zugehörige Dimension der Ebene (auch als übergeordnetes Element bezeichnet). Die Dimension &quot;level&quot;für Ihre Prozesszuordnung sollte mit der Dimension &quot;level&quot;(oder der Dimension &quot;parent&quot;) für die Basisdimension der Prozesszuordnung identisch sein. Wenn Sie z. B. eine Seite (ein Element der Seitendimension) auf die Map ziehen, wäre die entsprechende Dimension der Ebene &quot;Seitenansicht&quot;.
* **Gruppendimension:** Die Gruppendimension legt fest, wie die Elemente der Dimension &quot;Ebene&quot;gruppiert werden, um die Verbindungen zwischen Knoten zu bilden. Bei Prozesskarten ist die Gruppendimension aus drei Hauptgründen wichtig:

   * Eine Verbindung zwischen zwei Knoten kann nicht mehr als ein Element einer Gruppendimension umfassen. Um dies zu verstehen, sollten Sie sich ein Beispiel für die Verwendung von Webdaten vorstellen. Angenommen, die Basis-, Ebenen- und Gruppendimensionen für Ihre Prozesszuordnung sind Seite, Seitenansicht bzw. Sitzung. Eine Verbindung von Seite A zu Seite B zeigt an, dass während einer einzelnen Sitzung vor einer Seitenansicht von Seite B eine Seitenansicht von Seite A stattgefunden hat, ohne dass dazwischenliegende Seitenansichten anderer Seiten (Knoten) auf der Karte angezeigt wurden. Beachten Sie, dass Seitenansichten anderer Seiten der Site möglicherweise während der gleichen Sitzung zwischen Seitenansichten der Seiten A und B erfolgten, aber diese Seiten werden auf dieser Zuordnung nicht angezeigt.
   * Eine Verbindung zwischen zwei Knoten kann mehrere Elemente der Gruppendimension darstellen. Es kann beispielsweise mehrere Sitzungen geben, in denen eine Seitenansicht von Seite A vor einer Seitenansicht von Seite B stattgefunden hat. Daher stellt die Verbindung zwischen Seite A und Seite B alle einzelnen Sitzungen dar, in denen ein Seitenaufruf von Seite A vor einem Seitenaufruf von Seite B stattfand, ohne dass dazwischen Seitenansichten anderer Seiten (Knoten) auf der Karte angezeigt wurden.
   * Wenn Sie eine Auswahl basierend auf einer Node in einer Prozesszuordnung treffen, wählen Sie alle Elemente der Gruppendimension aus, an der diese Node beteiligt war. Siehe [Treffen von Auswahlen in Visualisierungen](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-vis.md#concept-012870ec22c7476e9afbf3b8b2515746). Weitere Informationen zu Auswahlen finden Sie unter [Vornehmen von Auswahlen in Visualisierungen](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-vis.md#concept-012870ec22c7476e9afbf3b8b2515746).

* **Metrik:** Die Größe der Node für ein bestimmtes Element ist proportional zum Wert der Metrik für dieses Element. Größere Knoten geben größere Metrikwerte an als kleinere.

Wenn Sie beispielsweise die [!DNL Site] oder HBX-Anwendung verwenden, können Sie Elemente der Dimension &quot;Seite&quot;standardmäßig auf die Prozesskarte ziehen. Die Größe der einzelnen Knoten hängt von der Anzahl der Sitzungen ab (definiert durch die Metrik &quot;Sitzungen&quot;), in denen diese Seite angezeigt wurde.

>[!NOTE]
>
>Sie können die Standarddimensionen oder Metriken für eine Prozesszuordnung ändern. Anweisungen zum Konfigurieren einer Prozesszuordnung finden Sie unter [Konfigurieren von Prozesszuordnungen](../../../../home/c-get-started/c-intf-anlys-ftrs/t-config-proc-maps.md#task-4a95730b18a14bc790a77c013832b2d6).

