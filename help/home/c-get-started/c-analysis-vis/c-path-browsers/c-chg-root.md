---
description: Sie können den Stamm des Pfadbrowsers ändern, indem Sie entweder ein angezeigtes Element als Stamm angeben oder ein neues Element zur Visualisierung hinzufügen.
title: Ändern des Stamms des Pfad-Browsers
uuid: 0bb9b004-9736-411b-bd22-cac04f4733a6
exl-id: 09842b93-af26-42b9-9395-a02b86978b21
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '347'
ht-degree: 2%

---

# Ändern des Stamms des Pfad-Browsers{#change-the-path-browser-s-root}

Sie können den Stamm des Pfadbrowsers ändern, indem Sie entweder ein angezeigtes Element als Stamm angeben oder ein neues Element zur Visualisierung hinzufügen.

>[!NOTE]
>
>Sie können einen Beginn- oder Endknoten nicht als Stamm eines Pfadbrowsers festlegen.

**So legen Sie den Stamm eines Pfadbrowsers fest**

* Klicken Sie mit der rechten Maustaste auf das gewünschte Element und klicken Sie auf **[!UICONTROL Set as root]**.

**So fügen Sie dem Pfadbrowser ein neues Element hinzu**

1. Öffnen Sie ein Diagramm oder eine Tabelle mit der Dimension, deren Elemente im Pfadbrowser angezeigt werden sollen.

   Wenn Sie beispielsweise mit Website-Daten arbeiten, öffnen Sie ein Seitendiagramm oder eine Tabelle und identifizieren Sie die Seite, die Sie als Stamm festlegen möchten.

1. Drücken Sie Strg+Alt und ziehen Sie das gewünschte Element auf die Stamposition im Pfadbrowser.

   >[!NOTE]
   >
   >Sie können die mit einem Pfadbrowser verknüpfte Basisdimension ändern, indem Sie ein Element der gewünschten Dimension in den Pfadbrowser ziehen. Dieses Element wird zum neuen Stamm des Pfadbrowsers und die Beschriftung in der oberen linken Ecke des Pfadbrowsers ändert sich, um die Dimension für dieses Element anzuzeigen.

   Angenommen, Sie erstellen einen Seitenpfadbrowser, der die Sequenz der Seiten für jede Sitzung anzeigt. Wenn Sie ein Element der Dimension &quot;Suchbegriff&quot;in den Pfadbrowser ziehen, wird das Element &quot;Suchbegriff&quot;zum neuen Stammordner und die Bezeichnung zeigt nun die Sequenz der Suchbegriffe für jede Sitzung an.

   >[!NOTE]
   >
   >Wenn Sie ein Element in einen Pfadbrowser ziehen, wird möglicherweise die mit dem Pfadbrowser verknüpfte Basisdimension geändert, jedoch nicht die Dimension der Ebene, die Gruppendimension oder die Metrik. Daher müssen Sie bei der Auswahl einer Basisdimension vorsichtig sein, die sinnvoll ist, wenn sie mit der Ebenendimension, Gruppendimension und Metrik des Pfadbrowsers verwendet wird. Um die Dimension der Ebene, die Gruppendimension oder die Metrik zu ändern, müssen Sie die Datei [!DNL *.vw] des Pfadbrowsers in einem Texteditor wie Notepad bearbeiten. Siehe [Konfigurieren von Pfadbrowsern](../../../../home/c-get-started/c-intf-anlys-ftrs/t-config-path-brwsr.md#task-bbb3ddaa140a414f984b697c2b8202a3).
