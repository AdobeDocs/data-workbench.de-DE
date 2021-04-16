---
description: Sie können einen Pfadbrowser aus einem Diagramm, einer Tabelle oder einer Prozesszuordnung erstellen.
title: Erstellen von Pfad-Browsern
uuid: 84a5e587-fb02-461b-aec8-1b6ad473ebc3
exl-id: 9fa11b84-da73-447a-8b10-7eab381e3f66
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '380'
ht-degree: 2%

---

# Erstellen von Pfad-Browsern{#creating-path-browsers}

Sie können einen Pfadbrowser aus einem Diagramm, einer Tabelle oder einer Prozesszuordnung erstellen.

**So erstellen Sie einen Pfadbrowser aus einem Diagramm oder einer Tabelle**

1. hinzufügen Sie einen Pfadbrowser zu Ihrem Arbeitsbereich. Die Visualisierung ist leer, mit Ausnahme der Beschriftung (Sequenz von...) in der oberen linken Ecke.
1. Öffnen Sie ein Diagramm oder eine Tabelle mit der Dimension, deren Elemente im Pfadbrowser angezeigt werden sollen. Wenn Sie beispielsweise mit Website-Daten arbeiten, öffnen Sie ein Seitendiagramm oder eine Tabelle und identifizieren Sie die Seite, die Sie als Stamm festlegen möchten.
1. Drücken Sie Strg+Alt und ziehen Sie das gewünschte Element in den Pfadbrowser. Die Beschriftung in der oberen linken Ecke des Pfadbrowsers ändert sich, um die grundlegende Dimension wiederzugeben, deren Element Sie in den Pfadbrowser ziehen.

>[!NOTE]
>
>Wenn Sie ein Element in einen Pfadbrowser ziehen, wird möglicherweise die mit dem Pfadbrowser verknüpfte Basisdimension geändert, jedoch nicht die Dimension der Ebene, die Gruppendimension oder die Metrik. Daher müssen Sie bei der Auswahl einer Basisdimension vorsichtig sein, die sinnvoll ist, wenn sie mit der Ebenendimension, Gruppendimension und Metrik des Pfadbrowsers verwendet wird. Um die Dimension der Ebene, die Gruppendimension oder die Metrik zu ändern, müssen Sie die Datei [!DNL *.vw] des Pfadbrowsers in einem Texteditor wie Notepad bearbeiten. Siehe [Konfigurieren von Pfadbrowsern](../../../../home/c-get-started/c-intf-anlys-ftrs/t-config-path-brwsr.md#task-bbb3ddaa140a414f984b697c2b8202a3).

**So erstellen Sie einen Pfadbrowser aus einer Prozesszuordnung**

>[!NOTE]
>
>Ein aus einer Prozesszuordnung erstellter Pfadbrowser zeigt nur die in der Prozesszuordnung angezeigten Elemente an. Andere Elemente der Basisdimension werden nicht angezeigt.

1. Erstellen von Prozesskarten. Siehe [Erstellen von Prozesszuordnungen](../../../../home/c-get-started/c-analysis-vis/c-proc-maps/c-create-proc-maps.md#concept-daf5b14dae7a442191611b1b9c1122bf).
1. Ziehen Sie das gewünschte Element aus der Zuordnung zum Pfadbrowser. Das Element wird zum Stamm des Pfadbrowsers.

>[!NOTE]
>
>Wenn Sie einen Pfadbrowser aus einer Prozesszuordnung erstellen, ignoriert der Pfadbrowser die Elemente der Dimension &quot;level&quot;ohne zugehörige grundlegende Dimensionselemente. Wenn Sie einen Knoten aus einer Prozesszuordnung in einen Pfadbrowser ziehen, wird die Basisdimension des Pfadbrowsers (mit der Bezeichnung &quot;Map&quot;) durch die Prozesszuordnung definiert und die Elemente sind auf die Elemente in der Prozesszuordnung beschränkt. Aus diesem Grund verfügen einige Elemente der Ebenendimension des Pfadbrowsers nicht über zugehörige grundlegende Dimensionselemente und werden nicht im Pfadbrowser dargestellt.
