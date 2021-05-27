---
description: Mit Prozesskarten können Sie den Aktivitätsfluss zwischen Elementen einer Dimension analysieren.
title: Prozesskarte
uuid: f1db41a9-400e-467a-ba59-39831fb166af
exl-id: 019cee7b-a704-4b47-84c6-d3ddc277c43e
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '737'
ht-degree: 0%

---

# Prozesskarte{#process-map}

Mit Prozesskarten können Sie den Aktivitätsfluss zwischen Elementen einer Dimension analysieren.

Sie erstellen Prozesskarten, indem Sie die Elemente einer Dimension auf eine leere zweidimensionale (2D) oder dreidimensionale (3D) Karte ziehen und ablegen. Die Elemente werden zu Knoten auf der Karte. Knoten sind Kreise in 2D-Prozesskarten und Balken in 3D-Prozesskarten.

![](assets/vis_2DProcessMap.png)

![](assets/vis_3DProcessMap.png)

>[!NOTE]
>
>Eine Prozesszuordnung erhält ihren Namen durch ihre Verwendung bei der Analyse des Aktivitätsflusses zwischen den Schritten in einem Prozess. Bei dieser Art von Analyse stellt jedes Element auf der Zuordnung einen Schritt im Prozess dar.

Im Gegensatz zu Pfadbrowsern können Prozesskarten so wenige oder so viele Elemente anzeigen, wie für Ihre Analyse erforderlich sind. Sie wählen die gewünschten Elemente aus und ziehen sie per Drag-and-Drop auf die Karte. Im Gegensatz zu Pfadbrowsern zeigen Prozesskarten den Aktivitätsfluss in beide Richtungen zwischen einem Element und einem oder mehreren anderen Elementen an.

>[!NOTE]
>
>Damit diese Maps am effektivsten funktionieren, sollten Sie eine Farblegende im Arbeitsbereich öffnen. Informationen zur Verwendung von Farblegenden mit Prozesskarten finden Sie unter [Aktivieren von Farblinks](../../../../home/c-get-started/c-analysis-vis/c-proc-maps/c-act-color-lnks.md#concept-2c9b9f67f2bd4cd7a5431fa21c094edc). Weitere Informationen zu Farblegenden finden Sie unter [Farblegenden](../../../../home/c-get-started/c-analysis-vis/c-legends/c-color-leg.md#concept-f84d51dc0d6547f981d0642fc2d01358).

Jede Prozesszuordnung verfügt über eine zugeordnete Basisdimension, Gruppendimension, Ebenendimension und Metrik, die Schlüssel zur Interpretation der in der Prozesszuordnung angezeigten Daten bereitstellen.

Die Standardeinstellungen für die Dimensionen und Metriken einer Prozesszuordnung hängen von der verwendeten Data Workbench App ab. Informationen zu den Dimensionen und Metriken, die Ihnen für Ihre Prozesskarten zur Verfügung stehen, finden Sie im Anwendungshandbuch für Ihre Data Workbench App.

* **Basisdimension:** Wenn Sie ein Element auf eine Prozesskarte ziehen und dort ablegen, ziehen Sie ein Element der Basisdimension.
* **Ebenendimension:** Jede Dimension in Ihrem Datensatz hat eine zugeordnete Ebenendimension (auch als übergeordnetes Element bezeichnet). Die Ebenendimension für Ihre Prozesszuordnung sollte mit der Ebenendimension (oder der übergeordneten Dimension) für die Basisdimension Ihrer Prozesszuordnung übereinstimmen. Wenn Sie beispielsweise eine Seite (ein Element der Dimension Seite ) auf die Zuordnung ziehen, wäre die entsprechende Ebenendimension &quot;Seitenansicht&quot;.
* **Gruppendimension:** Die Gruppendimension bestimmt, wie die Elemente der Ebenendimension gruppiert werden, um die Verbindungen zwischen Knoten zu bilden. Bei Prozesskarten ist die Gruppendimension aus drei Hauptgründen wichtig:

   * Eine Verbindung zwischen zwei Knoten kann nicht mehr als ein Element einer Gruppendimension umfassen. Um dies zu verstehen, sehen Sie sich ein Beispiel für die Verwendung von Webdaten an. Angenommen, die Basis-, Ebene- und Gruppendimensionen für Ihre Prozesszuordnung sind &quot;Seite&quot;, &quot;Seitenansicht&quot;und &quot;Sitzung&quot;. Eine Verbindung von Seite A zu Seite B teilt Ihnen mit, dass während einer einzelnen Sitzung vor einer Seitenansicht von Seite B eine Seitenansicht von Seite A stattgefunden hat, ohne dass andere Seiten (Knoten) auf der Karte dazwischenangezeigt werden. Beachten Sie, dass Seitenansichten anderer Seiten der Site möglicherweise zwischen Seitenansichten für die Seiten A und B während derselben Sitzung aufgetreten sind, diese Seiten jedoch nicht auf dieser Zuordnung angezeigt werden.
   * Eine Verbindung zwischen zwei Knoten kann mehrere Elemente der Gruppendimension darstellen. Beispielsweise kann es mehrere Sitzungen geben, in denen vor einem Seitenaufruf von Seite B ein Seitenaufruf von Seite A stattgefunden hat. Daher stellt die Verbindung zwischen Seite A und Seite B alle einzelnen Sitzungen dar, in denen ein Seitenaufruf von Seite A vor einem Seitenaufruf von Seite B stattgefunden hat, ohne dass dazwischenliegende Seitenansichten anderer Seiten (Knoten) auf der Karte vorhanden sind.
   * Wenn Sie eine Auswahl basierend auf einem Knoten in einer Prozesszuordnung treffen, wählen Sie alle Elemente der Gruppendimension aus, die diesen Knoten betrifft. Siehe [Auswahlen in Visualisierungen](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-vis.md#concept-012870ec22c7476e9afbf3b8b2515746). Weitere Informationen zu Auswahlen finden Sie unter [Auswahlen in Visualisierungen](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-vis.md#concept-012870ec22c7476e9afbf3b8b2515746).

* **Metrik:** Die Größe des Knotens für ein bestimmtes Element ist proportional zum Wert der Metrik für dieses Element. Größere Knoten geben größere Metrikwerte als kleinere Knoten an.

Wenn Sie beispielsweise die Anwendung [!DNL Site] oder HBX verwenden, können Sie Elemente der Dimension &quot;Seite&quot;standardmäßig auf die Prozesskarte ziehen. Die Größe der einzelnen Knoten hängt von der Anzahl der Sitzungen ab (definiert durch die Sitzungsmetrik), in denen die Seite angezeigt wurde.

>[!NOTE]
>
>Sie können die Standarddimensionen oder Metriken für eine Prozesszuordnung ändern. Anweisungen zum Konfigurieren einer Prozesszuordnung finden Sie unter [Konfigurieren von Prozesskarten](../../../../home/c-get-started/c-intf-anlys-ftrs/t-config-proc-maps.md#task-4a95730b18a14bc790a77c013832b2d6).
