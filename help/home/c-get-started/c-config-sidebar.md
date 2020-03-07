---
description: Die Seitenleiste bietet Zugriff auf regelmäßig verwendete Funktionen und behält Visualisierungen beim Wechsel zwischen Arbeitsbereichen bei.
solution: Analytics
title: Konfigurieren der Seitenleiste
topic: Data workbench
uuid: 0d2f0b9a-56a9-4f27-aaa6-1f9bf7fcab2d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Konfigurieren der Seitenleiste{#configure-the-sidebar}

Die Seitenleiste bietet Zugriff auf regelmäßig verwendete Funktionen und behält Visualisierungen beim Wechsel zwischen Arbeitsbereichen bei.

Administratoren können eine Seitenleiste so anpassen, dass sie für verschiedene Benutzergruppen geeignet ist, und dann die Seitenleiste mit einem Profil bereitstellen.

Die Seitenleiste ist ideal, um Filter und lokale Überschreibungen zu verfolgen. Wenn Sie die Seitenleiste nicht verwenden möchten, können Sie sie ausblenden.

## Hinzufügen von Visualisierungen zur Seitenleiste {#section-666f70a405db4f8d8eaffa567ffcac06}

1. Starten Sie Data Workbench.
1. Klicken Sie in der Seitenleiste auf **[!UICONTROL Add]** > *&lt;**[!UICONTROL item]**>*. For example, [!DNL Selections Panel], [!DNL Filters Panel], or [!DNL Table].

   Die folgenden Randleistenbedienfelder sind in der Standardinstallation von Data Workbench verfügbar. Möglicherweise stehen in Ihrem Profil weitere Elemente zur Verfügung:

   * **Auswahlfeld:** Ermöglicht Ihnen, zu verstehen, welche Auswahlen im aktuellen Arbeitsbereich aktiv sind. Die [!DNL Selections Panel] Aktualisierung erfolgt, sobald Sie eine neue Auswahl treffen. Sie können die Auswahl löschen, indem Sie auf **[!UICONTROL x]**. Informationen zur Auswahl der Daten finden Sie unter [Vornehmen von Auswahlen in Visualisierungen](../../home/c-get-started/c-vis/c-sel-vis/c-sel-vis.md#concept-012870ec22c7476e9afbf3b8b2515746) .
   * **Filter-Bedienfeld:** Erleichtert das Laden und Anwenden gespeicherter Filter. Sie können mehrere Filter laden und diese einzeln aktivieren oder deaktivieren, indem Sie auf das Kontrollkästchen neben diesen Filtern klicken. Siehe [Filter-Editoren](../../home/c-get-started/c-analysis-vis/c-filter-editors/c-filter-editors.md#concept-2f343ecbed8240f18b0c1f1eccef11e3).
   * **Lokales Override-Bedienfeld:** In diesem Fenster wird angezeigt, welche Metriken, Dimensionen und Filter, die im Profil vorhanden sind, in Ihrer persönlichen Kopie des Profils geändert wurden. Dadurch können Sie auf mögliche Unterschiede zwischen der Art und Weise aufmerksam machen, wie Daten in Ihrem Client angezeigt werden, und der anderer Benutzer. Wenn Sie Änderungen in einer Metrik, Dimension oder einem Filter auf dem Server speichern, wird die Außerkraftsetzung aus dem [!DNL Local Overrides panel]Filter entfernt. Wenn Sie auf eine Überschreibung klicken und dann darauf klicken, **[!UICONTROL Revert to Server]** wird die lokale Überschreibung entfernt und das Element wird zur freigegebenen Version zurückgesetzt.
   * **Metriklegende:** Fügt eine Metriklegende hinzu. [!DNL Metric legends] ermöglichen Ihnen die Anzeige von Basismetriken in Bezug auf Ihr Profil und Statistiken im Zusammenhang mit dem Datensatz (oder, falls vorhanden, zur aktuellen Auswahl). Siehe [MetrikLegenden](../../home/c-get-started/c-analysis-vis/c-legends/c-metric-leg.md#concept-e7195bc8f7844ae295bda3a88b028d5b).
   * **Farblegende:** Fügt eine Farblegende hinzu. Sie können Visualisierungen nach Metriken wie Konversion und Treue farbkodieren und sie in fast allen [!DNL Workspace]Bereichen verwenden. Durch die Verknüpfung von Geschäftsmetriken mit Farben lassen sich Anomalien, Ausnahmen und Trends leicht erkennen. Siehe [Farblegende](../../home/c-get-started/c-analysis-vis/c-legends/c-color-leg.md#concept-f84d51dc0d6547f981d0642fc2d01358).
   * **Textkommentar:** Fügt ein Notizbedienfeld hinzu. [!DNL Text annotations] sind Fenster, in die Sie beliebigen Text eingeben können, um beschreibende Informationen oder Kommentare zu einem [!DNL Workspace]. Siehe [Arbeiten mit Textanmerkungen](../../home/c-get-started/c-analysis-vis/c-annots/c-text-annots.md#concept-55b4aa3e0c58470b8e3c9d452e12a777).
   * **Tabelle:** Fügt eine Tabelle hinzu. Eine Tabelle kann eine oder mehrere Metriken über eine oder mehrere Datendimensionen hinweg anzeigen. Siehe [Tabellen](../../home/c-get-started/c-analysis-vis/c-tables/c-tables.md#concept-c632cb8ad9724f90ac5c294d52ae667f).
   * **Öffnen:** Öffnet eine gespeicherte Datei.

## Öffnen eines Seitenleistenbedienfelds {#section-cbc8e57491854274a577d47a48c306b8}

Sie können eine Visualisierungsdatei für die Seitenleiste an einem gespeicherten Speicherort oder in der Zwischenablage öffnen.

1. Klicken Sie in der Seitenleiste auf **[!UICONTROL Add]** > **[!UICONTROL Open]**.
1. Klicken Sie auf **[!UICONTROL File]** , um die [!DNL .vw] Datei des hinzuzufügenden Bereichs zu suchen, oder klicken Sie auf **[!UICONTROL Last Closed Window]**, um die Visualisierung aus der Zwischenablage zu ziehen.

   Außerdem können Sie auf klicken, **[!UICONTROL From Clipboard]** um eine Visualisierung einzufügen, die in die Zwischenablage kopiert wurde. Siehe [Kopieren eines Seitenleistenbedienfelds](../../home/c-get-started/c-config-sidebar.md#section-720ae057632a4b8dbb94412e06a370b1).

## Kopieren eines Seitenleistenbedienfelds {#section-720ae057632a4b8dbb94412e06a370b1}

1. Klicken Sie mit der rechten Maustaste auf den oberen Rand des Bedienfelds und klicken Sie dann auf **[!UICONTROL Copy]** > **[!UICONTROL Window]**.
1. Klicken Sie zum Einfügen des Bedienfelds auf **[!UICONTROL Add]** > **[!UICONTROL Open]** > **[!UICONTROL From Clipboard]**.

## Speichern eines Seitenleistenbedienfelds {#section-fb19936b12704fb0a4c592abb579db1d}

Klicken Sie in einem Seitenleistenbedienfeld mit der rechten Maustaste in die Titelleiste und klicken Sie auf **[!UICONTROL Save]**.

Ebenso können Sie eine gespeicherte Seitenleistenvisualisierung öffnen. Data Workbench speichert die Visualisierung als [!DNL .vw] Datei am angegebenen Speicherort.

## Zurück zur Standardseitenleiste {#section-4d14b8771ad747bba799876267f24831}

Klicken Sie in der Seitenleiste auf **[!UICONTROL Options]** > **[!UICONTROL Revert]**.

Wenn Sie Data Workbench schließen, speichert das System die aktuelle sidebar-Konfiguration in der [!DNL sidebar.vw] Datei im Benutzerprofil. Wenn Sie Data Workbench öffnen, lädt das System die [!DNL sidebar.vw] Datei aus dem Benutzerprofil und nicht aus einem übergeordneten Profil.

Sie können zu einer standardmäßigen oder zuvor gespeicherten Seitenleiste zurückkehren, wodurch die Seitenleiste aus dem Benutzerprofil gelöscht und die Seitenleiste erneut aus dem übergeordneten Profil geladen wird. Administratoren können die Standardseitenleiste (übergeordnete Seitenleiste) durch eine lokale Seitenleiste ersetzen, indem sie sie aus dem [!DNL Profile Manager].

## Anpassen der Datei mit dem Statusbedienfeld {#section-8d502f3b59cc4331966edec05e896ce1}

Systemadministratoren können Formeln in der [!DNL More Status Panel.vw]erstellen. Dadurch werden kontextbezogene Wörter um Metrik- und Dimensionswerte verschoben und die Ergebnisse in der Seitenleiste [!DNL More Status panel] angezeigt.

Klicken Sie auf die Pfeile, die im folgenden Beispiel gezeigt werden, um den [!DNL More Status panel] in der Seitenleiste anzuzeigen.

![](assets/more_status_panel_arrows.png)

Das folgende Verfahren zeigt ein einfaches Beispiel, wie Sie einen benutzerspezifischen Status erstellen, der angibt, wie viele Tage sich in einem Datensatz befinden:

1. Klicken Sie in der [!DNL Profile Manager]Symbolleiste auf **[!UICONTROL-Seitenleiste\]**.

1. Erstellen Sie in der [!DNL Base_5_3*] Spalte eine lokale Kopie der [!DNL More Status Panel.vw] Datei.

   Klicken Sie dazu mit der rechten Maustaste auf das Dateiprüfzeichen und dann auf **[!UICONTROL Make Local]**.

1. Öffnen Sie die [!DNL More Status Panel.vw] Datei im [!DNL .vw] Editor [!DNL Editor] oder im Editor.

   ![](assets/more_status_panel_file.png)

1. Füllen Sie die Felder [!DNL Context] und [!DNL Items] im [!DNL Editor]aus. Richtlinien zur Syntax finden Sie unter [Abfragesprachsyntax](../../home/c-get-started/c-qry-lang-syntx/c-qry-lang-syntx.md#concept-15d1d3f5164a47d49468c5acb7299d9f) .

1. Speichern Sie die Datei.

   Die Werte im obigen Beispiel führen zu einer Statusformel, die wie folgt angezeigt wird:

   ![](assets/more_status_panel.png)

