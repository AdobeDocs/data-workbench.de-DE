---
description: Sie können den Stamm eines Pfad-Browsers ändern, indem Sie entweder ein angezeigtes Element als Stamm angeben oder ein neues Element zur Visualisierung hinzufügen.
title: Ändern des Stamms des Pfad-Browsers
uuid: 0bb9b004-9736-411b-bd22-cac04f4733a6
exl-id: 09842b93-af26-42b9-9395-a02b86978b21
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '347'
ht-degree: 2%

---

# Ändern des Stamms des Pfad-Browsers{#change-the-path-browser-s-root}

{{eol}}

Sie können den Stamm eines Pfad-Browsers ändern, indem Sie entweder ein angezeigtes Element als Stamm angeben oder ein neues Element zur Visualisierung hinzufügen.

>[!NOTE]
>
>Sie können einen Start- oder Endknoten nicht als Stamm eines Pfad-Browsers festlegen.

**So legen Sie den Stamm eines Pfad-Browsers fest**

* Klicken Sie mit der rechten Maustaste auf das gewünschte Element und klicken Sie auf **[!UICONTROL Set as root]**.

**So fügen Sie dem Pfad-Browser ein neues Element hinzu**

1. Öffnen Sie ein Diagramm oder eine Tabelle mit der Dimension, deren Elemente im Pfadbrowser angezeigt werden sollen.

   Wenn Sie beispielsweise mit Website-Daten arbeiten, öffnen Sie ein Seitendiagramm oder eine Tabelle und identifizieren Sie die Seite, die Sie als Stammverzeichnis festlegen möchten.

1. Drücken Sie Strg+Alt und ziehen Sie das gewünschte Element auf die Stammposition im Pfad-Browser.

   >[!NOTE]
   >
   >Sie können die mit einem Pfad-Browser verknüpfte Basisdimension ändern, indem Sie ein Element der gewünschten Dimension in den Pfad-Browser ziehen. Dieses Element wird zum neuen Stamm des Pfad-Browsers und die Bezeichnung in der oberen linken Ecke des Pfad-Browsers ändert sich, um die Dimension für dieses Element widerzuspiegeln.

   Angenommen, Sie erstellen einen Seitenpfadbrowser, der die Seitensequenz für jede Sitzung anzeigt. Wenn Sie ein Element der Dimension &quot;Suchbegriff&quot;in den Pfadbrowser ziehen würden, würde das Suchbegriffelement zum neuen Stammverzeichnis und die Bezeichnung würde nun die Sequenz der Suchbegriffe für jede Sitzung anzeigen.

   >[!NOTE]
   >
   >Das Ziehen eines Elements in einen Pfad-Browser kann die mit dem Pfad-Browser verknüpfte Basisdimension ändern, die Ebenendimension, Gruppendimension oder Metrik wird jedoch nicht geändert. Daher müssen Sie bei der Auswahl einer Basisdimension vorsichtig sein, die bei Verwendung mit der Ebenendimension, Gruppendimension und Metrik des Pfadbrowsers sinnvoll ist. Um die Ebenendimension, Gruppendimension oder Metrik zu ändern, müssen Sie die [!DNL *.vw] in einem Texteditor wie Notepad. Siehe [Konfigurieren von Pfad-Browsern](../../../../home/c-get-started/c-intf-anlys-ftrs/t-config-path-brwsr.md#task-bbb3ddaa140a414f984b697c2b8202a3).
