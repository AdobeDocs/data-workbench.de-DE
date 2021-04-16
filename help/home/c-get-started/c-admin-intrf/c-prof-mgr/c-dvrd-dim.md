---
description: Die neuen Dimensionen, die Sie mit Data Workbench erstellen (abgeleitete Dimensionen genannt), sind clientseitige Dimensionen.
title: Arbeiten mit abgeleiteten Dimensionen
uuid: 3a955fdc-6666-40ab-aee0-bd23c260c009
exl-id: 5b7e3a2a-ac61-4186-ad6c-234edf68af3e
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '562'
ht-degree: 1%

---

# Arbeiten mit abgeleiteten Dimensionen{#work-with-derived-dimensions}

Die neuen Dimensionen, die Sie mit Data Workbench erstellen (abgeleitete Dimensionen genannt), sind clientseitige Dimensionen.

Anstatt diese Dimensionen während der Datensatzerstellung und des Aktualisierungsprozesses (in der Datei [!DNL Transformation.cfg]) auf Ihren Data Workbenchs-Servercomputern zu definieren, werden abgeleitete Dimensionen einzeln als [!DNL .dim]-Dateien in einem Profil erstellt und gespeichert. Daher können Sie vorhandene Dimensionen ändern und neue abgeleitete Dimensionen erstellen, ohne den Datensatz erneut zu verarbeiten.

>[!NOTE]
>
>Weitere Informationen zu Dimensionen, die in diesem Abschnitt angegeben sind, finden Sie im entsprechenden Anwendungshandbuch zur Data Workbench.

Weitere Informationen zur Konfiguration und zum Aktualisierungsprozess des Datensatzes finden Sie im Handbuch *Konfiguration des Datensatzes*.

## abgeleitete Dimensionen {#section-fd9b6ca13a8f4aa9bbc2fff3ef15cb76} erstellen

Um eine abgeleitete Dimension zu erstellen, können Sie entweder eine vorhandene Dimension kopieren und ändern oder eine Dimension aus einer Visualisierung speichern.

## Erstellen Sie abgeleitete Dimensionen aus einer vorhandenen Dimension {#section-f46c2d3ab0a5416c98d6e79d18d99fa1}

Die Benutzer möchten am häufigsten neue Zeitdimensionen aus vorhandenen erstellen. Sie können beispielsweise eine neue Dimension &quot;Letzte 5 Tage&quot;aus der vorhandenen Dimension &quot;Letzte 7 Tage&quot;erstellen.

1. Klicken Sie in der Spalte [!DNL Profile Manager] in der Spalte *Profil-Name* mit der rechten Maustaste auf das Häkchen für eine Dimension, die der zu erstellenden Dimension ähnlich ist, und klicken Sie auf **[!UICONTROL Copy]**.

   Wenn Sie beispielsweise [!DNL Last 7 Days.dim] aus dem Berichte-Ordner des Profils [!DNL Traffic] kopieren möchten, klicken Sie mit der rechten Maustaste auf das Häkchen für den Dateinamen in der Spalte [!DNL Traffic] und klicken Sie auf **[!UICONTROL Copy]**.

   ![](assets/vis_ProfMgr_CopyDimension.png)

1. Klicken Sie mit der rechten Maustaste in die Spalte [!DNL User] für den Ordner, in dem Sie die kopierte Dimension speichern möchten, und klicken Sie auf **[!UICONTROL Paste]**.

   Die Dimension wird im Ordner &quot;Dimensionen&quot;mit einem Häkchen in der Spalte [!DNL User] angezeigt.

1. Um die neue Dimension umzubenennen, klicken Sie mit der rechten Maustaste auf das Häkchen in der Spalte [!DNL User] und geben Sie den neuen Namen in das Feld [!DNL File] ein.
1. Klicken Sie im Kontextmenü auf **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Die definierten Parameter für die Dimension werden angezeigt.
1. Ändern Sie die Parameter nach Bedarf, um die neue Dimension zu definieren.

   Bei Zeitdimensionen müssen Sie höchstwahrscheinlich nur die Parameter &quot;Anzahl&quot;und &quot;Bereich&quot;ändern.

1. Klicken Sie zum Speichern der Datei mit der rechten Maustaste auf **[!UICONTROL (modified)]** oben im Fenster und klicken Sie auf **[!UICONTROL Save]**.

   Wenn Sie möchten, dass alle Benutzer eines Profils die von Ihnen erstellte Dimension verwenden, müssen Sie sie mit dem [!DNL Profile Manager] in das Profil hochladen. Weitere Informationen finden Sie unter [Veröffentlichen von Dateien in Ihrem Profil](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task-a0106e010c834d16bd60eef4721b6af9).

Sie können die neue Dimension jetzt im gesamten aktuellen Profil verwenden, indem Sie sie wie jede integrierte Dimension auswählen.

## Speichern einer Dimension aus einer Visualisierung {#section-84cfe5e9ccb640afa2ee4e2da2682757}

Sie können erweiterte Dimensionen aus Prozesszuordnungen und Segmenten speichern. Anweisungen zum Speichern einer Dimension aus einer Prozesszuordnung finden Sie unter [Speichern von Dimensionen aus Prozesszuordnungen](../../../../home/c-get-started/c-analysis-vis/c-proc-maps/t-dim-proc-maps.md#task-44d9e555d4a944e6aa81993eef703051). Eine Anleitung zum Speichern einer Segmentdimension finden Sie unter [Erstellen von Dimensionen](../../../../home/c-get-started/c-analysis-vis/c-seg/c-create-seg-dim.md#concept-70b363edcad14185ba8051646ad3d44e) auf Seite 82.

## Speichern eines Segments als Dimension {#section-7c443cf1ac5a44659623cabb9e0c1ab8}

Sie können auch definierte Segmente als Dimension speichern. Anweisungen hierzu finden Sie unter [Wiederverwenden einer Segmentvisualisierung](../../../../home/c-get-started/c-analysis-vis/c-seg/c-reuse-seg-vis.md#concept-a8a607bd415d404a83c32a26b804cbdc).

## Bearbeiten einer vorhandenen abgeleiteten Dimension {#section-3a82c604bf1c4d369770556d268808b2}

1. I

   Klicken Sie in der Spalte [!DNL Profile Manager] in der Spalte *Profil-Name* mit der rechten Maustaste auf das Häkchen der zu bearbeitenden Dimensionsdatei und klicken Sie auf **[!UICONTROL Make Local]**.
1. Klicken Sie mit der rechten Maustaste auf das Häkchen für die Dimensionsdatei in der Spalte [!DNL User] und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**.
1. Füllen Sie die Parameter nach Bedarf aus. Weitere Informationen erhalten Sie bei Adobe Consulting Services.
1. Klicken Sie zum Speichern der Datei mit der rechten Maustaste auf **[!UICONTROL (modified)]** oben im Fenster und klicken Sie auf **[!UICONTROL Save]**.

   Wenn Sie möchten, dass alle Benutzer eines Profils die geänderte Dimension verwenden, müssen Sie sie mit dem [!DNL Profile Manager] in das Profil hochladen. Weitere Informationen finden Sie unter [Veröffentlichen von Dateien in Ihrem Profil](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task-a0106e010c834d16bd60eef4721b6af9).
