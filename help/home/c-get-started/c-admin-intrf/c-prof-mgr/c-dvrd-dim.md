---
description: Die neuen Dimensionen, die Sie mit Data Workbench erstellen (als abgeleitete Dimensionen bezeichnet), sind clientseitige Dimensionen.
title: Arbeiten mit abgeleiteten Dimensionen
uuid: 3a955fdc-6666-40ab-aee0-bd23c260c009
exl-id: 5b7e3a2a-ac61-4186-ad6c-234edf68af3e
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '562'
ht-degree: 1%

---

# Arbeiten mit abgeleiteten Dimensionen{#work-with-derived-dimensions}

Die neuen Dimensionen, die Sie mit Data Workbench erstellen (als abgeleitete Dimensionen bezeichnet), sind clientseitige Dimensionen.

Anstatt diese Dimensionen während der Erstellung und Aktualisierung von Datensätzen (in der Datei [!DNL Transformation.cfg] ) auf Ihren Data Workbench-Servercomputern zu definieren, werden abgeleitete Dimensionen einzeln als [!DNL .dim]- in einem Profil erstellt und gespeichert. Daher können Sie vorhandene ändern und neue abgeleitete Dimensionen erstellen, ohne den Datensatz erneut zu verarbeiten.

>[!NOTE]
>
>Weitere Informationen zu Dimensionen als in diesem Abschnitt bereitgestellt werden, finden Sie im entsprechenden Handbuch zur Data Workbench App.

Weitere Informationen zur Datensatzkonfiguration und zum Aktualisierungsprozess finden Sie im *Handbuch zur Datensatzkonfiguration*.

## Erstellen abgeleiteter Dimensionen {#section-fd9b6ca13a8f4aa9bbc2fff3ef15cb76}

Um eine abgeleitete Dimension zu erstellen, können Sie entweder eine vorhandene Dimension kopieren und ändern oder eine Dimension aus einer Visualisierung speichern.

## Abgeleitete Dimensionen aus einer vorhandenen Dimension erstellen {#section-f46c2d3ab0a5416c98d6e79d18d99fa1}

Die meisten Benutzer möchten aus vorhandenen Zeitdimensionen neue Zeitdimensionen erstellen. Sie können beispielsweise aus der vorhandenen Dimension &quot;Letzte 7 Tage&quot;eine neue Dimension &quot;Letzte 5 Tage&quot;erstellen.

1. Klicken Sie in der Spalte [!DNL Profile Manager] in der Spalte *Profilname* mit der rechten Maustaste auf das Häkchen für eine Dimension, die der zu erstellenden Dimension ähnelt, und klicken Sie auf **[!UICONTROL Copy]**.

   Um beispielsweise [!DNL Last 7 Days.dim] aus dem Ordner &quot;Reporting&quot;des Profils [!DNL Traffic] zu kopieren, klicken Sie mit der rechten Maustaste auf das Häkchen für den Dateinamen in der Spalte [!DNL Traffic] und klicken Sie auf **[!UICONTROL Copy]**.

   ![](assets/vis_ProfMgr_CopyDimension.png)

1. Klicken Sie mit der rechten Maustaste in die Spalte [!DNL User] des Ordners, in dem Sie die kopierte Dimension speichern möchten, und klicken Sie auf **[!UICONTROL Paste]**.

   Die Dimension wird im Ordner der ausgewählten Dimensionen mit einem Häkchen in der Spalte [!DNL User] angezeigt.

1. Um die neue Dimension umzubenennen, klicken Sie mit der rechten Maustaste auf das entsprechende Häkchen in der Spalte [!DNL User] und geben Sie den neuen Namen in das Feld [!DNL File] ein.
1. Klicken Sie im Kontextmenü auf **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Die für die Dimension definierten Parameter werden angezeigt.
1. Ändern Sie die Parameter nach Bedarf, um die neue Dimension zu definieren.

   Für Zeitdimensionen müssen Sie höchstwahrscheinlich nur die Parameter Zählung und Bereich ändern.

1. Klicken Sie zum Speichern der Datei mit der rechten Maustaste auf **[!UICONTROL (modified)]** oben im Fenster und klicken Sie auf **[!UICONTROL Save]**.

   Wenn Sie möchten, dass alle Benutzer eines Profils die von Ihnen erstellte Dimension verwenden, müssen Sie sie mit [!DNL Profile Manager] in das Profil hochladen. Weitere Informationen finden Sie unter [Veröffentlichen von Dateien in Ihrem Arbeitsprofil](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task-a0106e010c834d16bd60eef4721b6af9).

Jetzt können Sie die neue Dimension im gesamten aktuellen Profil verwenden, indem Sie sie wie jede integrierte Dimension auswählen.

## Speichern einer Dimension aus einer Visualisierung {#section-84cfe5e9ccb640afa2ee4e2da2682757}

Sie können erweiterte Dimensionen aus Prozesskarten und Segmenten speichern. Anweisungen zum Speichern einer Dimension aus einer Prozesskarte finden Sie unter [Speichern von Dimensionen aus Prozesskarten](../../../../home/c-get-started/c-analysis-vis/c-proc-maps/t-dim-proc-maps.md#task-44d9e555d4a944e6aa81993eef703051). Anweisungen zum Speichern einer Segmentdimension finden Sie unter [Erstellen von Segmentdimensionen](../../../../home/c-get-started/c-analysis-vis/c-seg/c-create-seg-dim.md#concept-70b363edcad14185ba8051646ad3d44e) auf Seite 82.

## Speichern eines Segments als Dimension {#section-7c443cf1ac5a44659623cabb9e0c1ab8}

Sie können auch definierte Segmente als Dimension speichern. Anweisungen finden Sie unter [Wiederverwenden einer Segmentvisualisierung](../../../../home/c-get-started/c-analysis-vis/c-seg/c-reuse-seg-vis.md#concept-a8a607bd415d404a83c32a26b804cbdc).

## Vorhandene abgeleitete Dimension bearbeiten {#section-3a82c604bf1c4d369770556d268808b2}

1. I

   Klicken Sie in der Spalte [!DNL Profile Manager] in der Spalte *Profilname* mit der rechten Maustaste auf das Häkchen für die Dimensionsdatei, die Sie bearbeiten möchten, und klicken Sie auf **[!UICONTROL Make Local]**.
1. Klicken Sie mit der rechten Maustaste auf das Häkchen für die Dimensionsdatei in der Spalte [!DNL User] und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**.
1. Füllen Sie die Parameter nach Bedarf aus. Weitere Informationen erhalten Sie von Adobe Consulting Services.
1. Klicken Sie zum Speichern der Datei mit der rechten Maustaste auf **[!UICONTROL (modified)]** oben im Fenster und klicken Sie auf **[!UICONTROL Save]**.

   Wenn Sie möchten, dass alle Benutzer eines Profils die geänderte Dimension verwenden, müssen Sie sie mit [!DNL Profile Manager] in das Profil hochladen. Weitere Informationen finden Sie unter [Veröffentlichen von Dateien in Ihrem Arbeitsprofil](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task-a0106e010c834d16bd60eef4721b6af9).
