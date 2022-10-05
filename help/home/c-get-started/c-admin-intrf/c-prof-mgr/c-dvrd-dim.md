---
description: Die neuen Dimensionen, die Sie mit Data Workbench erstellen (als abgeleitete Dimensionen bezeichnet), sind clientseitige Dimensionen.
title: Arbeiten mit abgeleiteten Dimensionen
uuid: 3a955fdc-6666-40ab-aee0-bd23c260c009
exl-id: 5b7e3a2a-ac61-4186-ad6c-234edf68af3e
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '562'
ht-degree: 1%

---

# Arbeiten mit abgeleiteten Dimensionen{#work-with-derived-dimensions}

{{eol}}

Die neuen Dimensionen, die Sie mit Data Workbench erstellen (als abgeleitete Dimensionen bezeichnet), sind clientseitige Dimensionen.

Anstatt diese Dimensionen während der Erstellung und Aktualisierung des Datensatzes zu definieren (im [!DNL Transformation.cfg] -Datei) auf Ihren Data Workbench-Server-Computern erstellt und gespeichert werden, werden abgeleitete Dimensionen einzeln als [!DNL .dim] -Dateien in einem Profil. Daher können Sie vorhandene ändern und neue abgeleitete Dimensionen erstellen, ohne den Datensatz erneut zu verarbeiten.

>[!NOTE]
>
>Weitere Informationen zu Dimensionen als in diesem Abschnitt bereitgestellt werden, finden Sie im entsprechenden Handbuch zur Data Workbench App.

Weitere Informationen zur Datensatzkonfiguration und zum Aktualisierungsprozess finden Sie unter *Anleitung zur Datensatzkonfiguration*.

## Erstellen abgeleiteter Dimensionen {#section-fd9b6ca13a8f4aa9bbc2fff3ef15cb76}

Um eine abgeleitete Dimension zu erstellen, können Sie entweder eine vorhandene Dimension kopieren und ändern oder eine Dimension aus einer Visualisierung speichern.

## Erstellen abgeleiteter Dimensionen aus einer vorhandenen Dimension {#section-f46c2d3ab0a5416c98d6e79d18d99fa1}

Die meisten Benutzer möchten aus vorhandenen Zeitdimensionen neue Zeitdimensionen erstellen. Sie können beispielsweise aus der vorhandenen Dimension &quot;Letzte 7 Tage&quot;eine neue Dimension &quot;Letzte 5 Tage&quot;erstellen.

1. Im [!DNL Profile Manager]in der *Profilname* klicken Sie mit der rechten Maustaste auf das Häkchen für eine Dimension, die der zu erstellenden Dimension ähnlich ist, und klicken Sie auf **[!UICONTROL Copy]**.

   Um beispielsweise die [!DNL Last 7 Days.dim] aus dem Ordner Berichterstellung des [!DNL Traffic] Profil, klicken Sie mit der rechten Maustaste auf das Häkchen für den Dateinamen im [!DNL Traffic] Spalte und klicken Sie auf **[!UICONTROL Copy]**.

   ![](assets/vis_ProfMgr_CopyDimension.png)

1. Klicken Sie mit der rechten Maustaste auf die [!DNL User] Spalte für den Ordner, in dem Sie die kopierte Dimension speichern möchten, und klicken Sie auf **[!UICONTROL Paste]**.

   Die Dimension wird im Ordner &quot;Dimensionen&quot;mit einem Häkchen im [!DNL User] Spalte.

1. Um die neue Dimension umzubenennen, klicken Sie mit der rechten Maustaste auf ihr Häkchen im [!DNL User] und geben Sie den neuen Namen in die [!DNL File] -Feld.
1. Klicken Sie im Kontextmenü auf **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Die für die Dimension definierten Parameter werden angezeigt.
1. Ändern Sie die Parameter nach Bedarf, um die neue Dimension zu definieren.

   Für Zeitdimensionen müssen Sie höchstwahrscheinlich nur die Parameter Zählung und Bereich ändern.

1. Um die Datei zu speichern, klicken Sie mit der rechten Maustaste auf **[!UICONTROL (modified)]** Klicken Sie oben im Fenster auf **[!UICONTROL Save]**.

   Wenn Sie möchten, dass alle Benutzer eines Profils die von Ihnen erstellte Dimension verwenden, müssen Sie sie mithilfe der [!DNL Profile Manager]. Weitere Informationen finden Sie unter [Veröffentlichen von Dateien in Ihrem Arbeitsprofil](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task-a0106e010c834d16bd60eef4721b6af9).

Jetzt können Sie die neue Dimension im gesamten aktuellen Profil verwenden, indem Sie sie wie jede integrierte Dimension auswählen.

## Speichern einer Dimension aus einer Visualisierung {#section-84cfe5e9ccb640afa2ee4e2da2682757}

Sie können erweiterte Dimensionen aus Prozesskarten und Segmenten speichern. Anweisungen zum Speichern einer Dimension aus einer Prozesszuordnung finden Sie unter [Speichern von Dimensionen aus Prozesskarten](../../../../home/c-get-started/c-analysis-vis/c-proc-maps/t-dim-proc-maps.md#task-44d9e555d4a944e6aa81993eef703051). Anweisungen zum Speichern einer Segmentdimension finden Sie unter [Erstellen von Dimensionen](../../../../home/c-get-started/c-analysis-vis/c-seg/c-create-seg-dim.md#concept-70b363edcad14185ba8051646ad3d44e) auf Seite 82.

## Speichern eines Segments als Dimension {#section-7c443cf1ac5a44659623cabb9e0c1ab8}

Sie können auch definierte Segmente als Dimension speichern. Anweisungen finden Sie unter [Wiederverwenden einer Segmentvisualisierung](../../../../home/c-get-started/c-analysis-vis/c-seg/c-reuse-seg-vis.md#concept-a8a607bd415d404a83c32a26b804cbdc).

## Vorhandene abgeleitete Dimension bearbeiten {#section-3a82c604bf1c4d369770556d268808b2}

1. I

   n [!DNL Profile Manager]in der *Profilname* klicken Sie mit der rechten Maustaste auf das Häkchen für die Dimensionsdatei, die Sie bearbeiten möchten, und klicken Sie auf **[!UICONTROL Make Local]**.
1. Klicken Sie mit der rechten Maustaste auf das Häkchen für die Dimensionsdatei im [!DNL User] Spalte und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**.
1. Füllen Sie die Parameter nach Bedarf aus. Weitere Informationen erhalten Sie von Adobe Consulting Services.
1. Um die Datei zu speichern, klicken Sie mit der rechten Maustaste auf **[!UICONTROL (modified)]** Klicken Sie oben im Fenster auf **[!UICONTROL Save]**.

   Wenn Sie möchten, dass alle Benutzer eines Profils die geänderte Dimension verwenden, müssen Sie sie mithilfe der [!DNL Profile Manager]. Weitere Informationen finden Sie unter [Veröffentlichen von Dateien in Ihrem Arbeitsprofil](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task-a0106e010c834d16bd60eef4721b6af9).
