---
description: Die neuen Dimensionen, die Sie mit Data Workbench erstellen (als abgeleitete Dimensionen bezeichnet), sind clientseitige Dimensionen.
solution: Analytics
title: Arbeiten mit abgeleiteten Dimensionen
topic: Data workbench
uuid: 3a955fdc-6666-40ab-aee0-bd23c260c009
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Arbeiten mit abgeleiteten Dimensionen{#work-with-derived-dimensions}

Die neuen Dimensionen, die Sie mit Data Workbench erstellen (als abgeleitete Dimensionen bezeichnet), sind clientseitige Dimensionen.

Anstatt diese Dimensionen während der Dataset-Erstellung und des Aktualisierungsprozesses (in der [!DNL Transformation.cfg] Datei) auf Ihren Data Workbench-Servercomputern zu definieren, werden abgeleitete Dimensionen einzeln als [!DNL .dim] Dateien in einem Profil erstellt und gespeichert. Daher können Sie vorhandene Dimensionen ändern und neue abgeleitete Dimensionen erstellen, ohne den Datensatz erneut zu verarbeiten.

>[!NOTE]
>
>Weitere Informationen zu Dimensionen, die in diesem Abschnitt angegeben sind, finden Sie im entsprechenden Data Workbench-Anwendungshandbuch.

Weitere Informationen zur Konfiguration und zum Aktualisierungsprozess des Datensatzes finden Sie im Handbuch zur Konfiguration von *Datasets*.

## abgeleitete Dimensionen erstellen {#section-fd9b6ca13a8f4aa9bbc2fff3ef15cb76}

Um eine abgeleitete Dimension zu erstellen, können Sie entweder eine vorhandene Dimension kopieren und ändern oder eine Dimension aus einer Visualisierung speichern.

## Abgeleitete Dimensionen aus einer vorhandenen Dimension erstellen {#section-f46c2d3ab0a5416c98d6e79d18d99fa1}

Die Benutzer möchten am häufigsten neue Zeitdimensionen aus vorhandenen erstellen. Sie können beispielsweise eine neue Dimension &quot;Letzte 5 Tage&quot;aus der vorhandenen Dimension &quot;Letzte 7 Tage&quot;erstellen.

1. Klicken Sie in der Spalte [!DNL Profile Manager]des *Profilnamens* mit der rechten Maustaste auf das Häkchen für eine Dimension, die der zu erstellenden Dimension ähnlich ist, und klicken Sie auf **[!UICONTROL Copy]**.

   Wenn Sie beispielsweise die Datei [!DNL Last 7 Days.dim] aus dem Berichtsordner des [!DNL Traffic] Profils kopieren möchten, klicken Sie mit der rechten Maustaste auf das Häkchen für den Dateinamen in der [!DNL Traffic] Spalte und dann auf **[!UICONTROL Copy]**.

   ![](assets/vis_ProfMgr_CopyDimension.png)

1. Klicken Sie mit der rechten Maustaste in die [!DNL User] Spalte für den Ordner, in dem Sie die kopierte Dimension speichern möchten, und klicken Sie auf **[!UICONTROL Paste]**.

   Die Dimension wird im ausgewählten Dimensionsordner mit einem Häkchen in der [!DNL User] Spalte angezeigt.

1. Um die neue Dimension umzubenennen, klicken Sie mit der rechten Maustaste auf das entsprechende Häkchen in der [!DNL User] Spalte und geben Sie den neuen Namen in das [!DNL File] Feld ein.
1. Klicken Sie im Kontextmenü auf **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Die definierten Parameter für die Dimension werden angezeigt.
1. Ändern Sie die Parameter nach Bedarf, um die neue Dimension zu definieren.

   Bei Zeitdimensionen müssen Sie höchstwahrscheinlich nur die Parameter &quot;Anzahl&quot;und &quot;Bereich&quot;ändern.

1. Um die Datei zu speichern, klicken Sie mit der rechten Maustaste **[!UICONTROL (modified)]** am oberen Rand des Fensters und klicken Sie auf **[!UICONTROL Save]**.

   Wenn Sie möchten, dass alle Benutzer eines Profils die von Ihnen erstellte Dimension verwenden, müssen Sie sie mit der [!DNL Profile Manager]Option in das Profil hochladen. Weitere Informationen finden Sie unter [Veröffentlichen von Dateien in Ihrem Arbeitsprofil](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task-a0106e010c834d16bd60eef4721b6af9).

Sie können die neue Dimension jetzt im gesamten aktuellen Profil verwenden, indem Sie sie wie jede integrierte Dimension auswählen.

## Speichern einer Dimension aus einer Visualisierung {#section-84cfe5e9ccb640afa2ee4e2da2682757}

Sie können erweiterte Dimensionen aus Prozesszuordnungen und Segmenten speichern. Anweisungen zum Speichern einer Dimension aus einer Prozesszuordnung finden Sie unter [Speichern von Dimensionen aus Prozesszuordnungen](../../../../home/c-get-started/c-analysis-vis/c-proc-maps/t-dim-proc-maps.md#task-44d9e555d4a944e6aa81993eef703051). Anweisungen zum Speichern einer Segmentdimension finden Sie unter [Erstellen von Segmentdimensionen](../../../../home/c-get-started/c-analysis-vis/c-seg/c-create-seg-dim.md#concept-70b363edcad14185ba8051646ad3d44e) auf Seite 82.

## Speichern eines Segments als Dimension {#section-7c443cf1ac5a44659623cabb9e0c1ab8}

Sie können auch definierte Segmente als Dimension speichern. Anweisungen hierzu finden Sie unter [Wiederverwenden einer Segmentvisualisierung](../../../../home/c-get-started/c-analysis-vis/c-seg/c-reuse-seg-vis.md#concept-a8a607bd415d404a83c32a26b804cbdc).

## Eine vorhandene abgeleitete Dimension bearbeiten {#section-3a82c604bf1c4d369770556d268808b2}

1. I

   Klicken Sie in der Spalte [!DNL Profile Manager]des *Profilnamens* mit der rechten Maustaste auf das Häkchen der Dimensionsdatei, die Sie bearbeiten möchten, und klicken Sie auf **[!UICONTROL Make Local]**.
1. Klicken Sie mit der rechten Maustaste auf das Häkchen für die Dimensionsdatei in der [!DNL User] Spalte und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**.
1. Füllen Sie die Parameter nach Bedarf aus. Weitere Informationen erhalten Sie bei Adobe Consulting Services.
1. Um die Datei zu speichern, klicken Sie mit der rechten Maustaste **[!UICONTROL (modified)]** am oberen Rand des Fensters und klicken Sie auf **[!UICONTROL Save]**.

   Wenn Sie möchten, dass alle Benutzer eines Profils die geänderte Dimension verwenden, müssen Sie sie mithilfe der [!DNL Profile Manager]Funktion in das Profil hochladen. Weitere Informationen finden Sie unter [Veröffentlichen von Dateien in Ihrem Arbeitsprofil](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task-a0106e010c834d16bd60eef4721b6af9).

