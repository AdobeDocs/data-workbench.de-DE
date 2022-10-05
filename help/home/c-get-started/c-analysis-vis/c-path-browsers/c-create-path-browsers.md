---
description: Sie können einen Pfadbrowser aus einem Diagramm, einer Tabelle oder einer Prozesskarte erstellen.
title: Erstellen von Pfad-Browsern
uuid: 84a5e587-fb02-461b-aec8-1b6ad473ebc3
exl-id: 9fa11b84-da73-447a-8b10-7eab381e3f66
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '380'
ht-degree: 2%

---

# Erstellen von Pfad-Browsern{#creating-path-browsers}

{{eol}}

Sie können einen Pfadbrowser aus einem Diagramm, einer Tabelle oder einer Prozesskarte erstellen.

**So erstellen Sie einen Pfad-Browser aus einem Diagramm oder einer Tabelle**

1. Fügen Sie Ihrem Arbeitsbereich einen Pfad-Browser hinzu. Die Visualisierung ist leer, mit Ausnahme der Beschriftung (Sequenz von ...) in der oberen linken Ecke.
1. Öffnen Sie ein Diagramm oder eine Tabelle mit der Dimension, deren Elemente im Pfadbrowser angezeigt werden sollen. Wenn Sie beispielsweise mit Website-Daten arbeiten, öffnen Sie ein Seitendiagramm oder eine Tabelle und identifizieren Sie die Seite, die Sie als Stammverzeichnis festlegen möchten.
1. Drücken Sie Strg+Alt und ziehen Sie das gewünschte Element in den Pfad-Browser. Die Beschriftung in der oberen linken Ecke des Pfad-Browsers ändert sich entsprechend der Basisdimension, deren Element Sie in den Pfad-Browser ziehen.

>[!NOTE]
>
>Das Ziehen eines Elements in einen Pfad-Browser kann die mit dem Pfad-Browser verknüpfte Basisdimension ändern, die Ebenendimension, Gruppendimension oder Metrik wird jedoch nicht geändert. Daher müssen Sie bei der Auswahl einer Basisdimension vorsichtig sein, die bei Verwendung mit der Ebenendimension, Gruppendimension und Metrik des Pfadbrowsers sinnvoll ist. Um die Ebenendimension, Gruppendimension oder Metrik zu ändern, müssen Sie die [!DNL *.vw] in einem Texteditor wie Notepad. Siehe [Konfigurieren von Pfad-Browsern](../../../../home/c-get-started/c-intf-anlys-ftrs/t-config-path-brwsr.md#task-bbb3ddaa140a414f984b697c2b8202a3).

**So erstellen Sie einen Pfad-Browser aus einer Prozesszuordnung**

>[!NOTE]
>
>Ein aus einer Prozesszuordnung erstellter Pfadbrowser zeigt nur die Elemente an, die auf der Prozesszuordnung angezeigt werden. Andere Elemente der Basisdimension werden nicht angezeigt.

1. Erstellen von Prozesskarten. Siehe [Erstellen von Prozesskarten](../../../../home/c-get-started/c-analysis-vis/c-proc-maps/c-create-proc-maps.md#concept-daf5b14dae7a442191611b1b9c1122bf).
1. Ziehen Sie das gewünschte Element aus der Prozesszuordnung in den Pfad-Browser. Das Element wird zum Stamm des Pfad-Browsers.

>[!NOTE]
>
>Wenn Sie einen Pfad-Browser aus einer Prozesszuordnung erstellen, ignoriert der Pfad-Browser die Elemente der Ebenendimension ohne zugehörige grundlegende Dimensionselemente. Wenn Sie einen Knoten aus einer Prozesszuordnung in einen Pfadbrowser ziehen, wird die Basisdimension des Pfadbrowsers (namens &quot;Map&quot;) durch die Prozesszuordnung definiert und die zugehörigen Elemente sind auf die Elemente in der Prozesszuordnung beschränkt. Daher verfügen einige Elemente der Ebenendimension des Pfad-Browsers nicht über zugeordnete grundlegende Dimensionselemente und werden nicht im Pfad-Browser dargestellt.
