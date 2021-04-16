---
description: Die Seitenleiste bietet Zugriff auf regelmäßig verwendete Funktionen und behält Visualisierungen beim Wechsel zwischen Arbeitsbereichen bei.
title: Konfigurieren der Seitenleiste
uuid: 0d2f0b9a-56a9-4f27-aaa6-1f9bf7fcab2d
exl-id: 75ccc869-8ced-4beb-b3d7-ed7febe347f9
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '745'
ht-degree: 2%

---

# Konfigurieren der Seitenleiste{#configure-the-sidebar}

Die Seitenleiste bietet Zugriff auf regelmäßig verwendete Funktionen und behält Visualisierungen beim Wechsel zwischen Arbeitsbereichen bei.

Administratoren können eine Seitenleiste so anpassen, dass sie für verschiedene Benutzergruppen geeignet ist, und dann die Seitenleiste mit einem Profil bereitstellen.

Die Seitenleiste ist ideal, um Filter und lokale Überschreibungen zu verfolgen. Wenn Sie die Seitenleiste nicht verwenden möchten, können Sie sie ausblenden.

## hinzufügen Visualisierungen für die Seitenleiste {#section-666f70a405db4f8d8eaffa567ffcac06}

1. Data Workbench starten.
1. Klicken Sie in der Seitenleiste auf **[!UICONTROL Add]** > *&lt;**[!UICONTROL item]***. Beispiele: [!DNL Selections Panel], [!DNL Filters Panel] oder [!DNL Table].

   Die folgenden Randleistenbedienfelder stehen bei der Standardinstallation der Data Workbench zur Verfügung. Möglicherweise stehen in Ihrem spezifischen Profil weitere Elemente zur Verfügung:

   * **Auswahlfenster:** Hier können Sie erkennen, welche Auswahlen im aktuellen Arbeitsbereich aktiv sind. Das [!DNL Selections Panel] wird immer dann aktualisiert, wenn Sie eine neue Auswahl treffen. Sie können die Auswahl löschen, indem Sie auf **[!UICONTROL x]** klicken. Informationen zur Auswahl der Daten finden Sie unter [Vornehmen von Auswahlen in Visualisierungen](../../home/c-get-started/c-vis/c-sel-vis/c-sel-vis.md#concept-012870ec22c7476e9afbf3b8b2515746).
   * **Bedienfeld &quot;Filter&quot;:** Ermöglicht das Laden und Anwenden gespeicherter Filter. Sie können mehrere Filter laden und diese einzeln aktivieren oder deaktivieren, indem Sie auf das Kontrollkästchen neben diesen  klicken. Siehe [Filter-Editoren](../../home/c-get-started/c-analysis-vis/c-filter-editors/c-filter-editors.md#concept-2f343ecbed8240f18b0c1f1eccef11e3).
   * **Lokaler Bereich zum Überschreiben:** Dieser Bereich zeigt an, welche Metriken, Dimensionen und Filter im Profil in Ihrer persönlichen Kopie des Profils geändert wurden. Dadurch können Sie auf mögliche Unterschiede zwischen der Art und Weise aufmerksam machen, wie Daten in Ihrem Client angezeigt werden, und der anderer Benutzer. Wenn Sie Änderungen in einer Metrik, Dimension oder einem Filter auf dem Server speichern, wird die Außerkraftsetzung aus dem [!DNL Local Overrides panel] entfernt. Wenn Sie auf eine Überschreibung klicken und dann auf **[!UICONTROL Revert to Server]** klicken, wird die lokale Überschreibung entfernt und das Element wird zur freigegebenen Version zurückgesetzt.
   * **Metriklegende:** Fügt eine Metriklegende hinzu. [!DNL Metric legends] ermöglichen Ihnen die Anzeige von Basismetriken in Bezug auf Ihr Profil und Statistiken zum Datensatz (oder zur aktuellen Auswahl, falls vorhanden). Siehe [Metrische Legenden](../../home/c-get-started/c-analysis-vis/c-legends/c-metric-leg.md#concept-e7195bc8f7844ae295bda3a88b028d5b).
   * **Farblegende:** Fügt eine Farblegende hinzu. Sie können Visualisierungen nach Metriken wie Konversion und Treue farbkodieren und sie in fast allen [!DNL Workspace] verwenden. Durch die Verknüpfung von Geschäftsmetriken mit Farben lassen sich Anomalien, Ausnahmen und Trends leicht erkennen. Siehe [Farbige Legenden](../../home/c-get-started/c-analysis-vis/c-legends/c-color-leg.md#concept-f84d51dc0d6547f981d0642fc2d01358).
   * **Textkommentar:** Fügt einen Notizenbedienfeld hinzu. [!DNL Text annotations] sind Fenster, in die Sie beliebigen Text eingeben können, um beschreibende Informationen oder Kommentare zu einem  [!DNL Workspace]. Siehe [Arbeiten mit Textanmerkungen](../../home/c-get-started/c-analysis-vis/c-annots/c-text-annots.md#concept-55b4aa3e0c58470b8e3c9d452e12a777).
   * **Tabelle:** Fügt eine Tabelle hinzu. Eine Tabelle kann eine oder mehrere Metriken über eine oder mehrere Datendimensionen hinweg anzeigen. Siehe [Tabellen](../../home/c-get-started/c-analysis-vis/c-tables/c-tables.md#concept-c632cb8ad9724f90ac5c294d52ae667f).
   * **Öffnen:** Öffnet eine gespeicherte Datei.

## Öffnen Sie ein Seitenleistenbedienfeld {#section-cbc8e57491854274a577d47a48c306b8}

Sie können eine Visualisierungsdatei für die Seitenleiste an einem gespeicherten Speicherort oder in der Zwischenablage öffnen.

1. Klicken Sie in der Seitenleiste auf **[!UICONTROL Add]** > **[!UICONTROL Open]**.
1. Klicken Sie auf **[!UICONTROL File]**, um die [!DNL .vw]-Datei des hinzuzufügenden Bereichs zu suchen, oder klicken Sie auf **[!UICONTROL Last Closed Window]**, um die Visualisierung aus der Zwischenablage abzurufen.

   Außerdem können Sie auf **[!UICONTROL From Clipboard]** klicken, um eine Visualisierung einzufügen, die in die Zwischenablage kopiert wurde. Siehe [Kopieren eines Seitenleistenbedienfelds](../../home/c-get-started/c-config-sidebar.md#section-720ae057632a4b8dbb94412e06a370b1).

## Kopieren eines Seitenleistenbedienfelds {#section-720ae057632a4b8dbb94412e06a370b1}

1. Klicken Sie mit der rechten Maustaste auf den oberen Rand des Bedienfelds und klicken Sie dann auf **[!UICONTROL Copy]** > **[!UICONTROL Window]**.
1. Um das Bedienfeld einzufügen, klicken Sie auf **[!UICONTROL Add]** > **[!UICONTROL Open]** > **[!UICONTROL From Clipboard]**.

## Speichern eines Seitenleistenbedienfelds {#section-fb19936b12704fb0a4c592abb579db1d}

Klicken Sie in einem Seitenleistenbedienfeld mit der rechten Maustaste in die Titelleiste und klicken Sie auf **[!UICONTROL Save]**.

Ebenso können Sie eine gespeicherte Seitenleistenvisualisierung öffnen. Data Workbench speichert die Visualisierung als [!DNL .vw]-Datei am angegebenen Speicherort.

## Zurück zur Standardseitenleiste {#section-4d14b8771ad747bba799876267f24831}

Klicken Sie in der Seitenleiste auf **[!UICONTROL Options]** > **[!UICONTROL Revert]**.

Wenn Sie die Data Workbench schließen, speichert das System die aktuelle Seitenleistenkonfiguration in der Datei [!DNL sidebar.vw] im Profil user. Wenn Sie die Data Workbench öffnen, lädt das System die Datei [!DNL sidebar.vw] statt eines übergeordneten Profils vom Profil des Benutzers.

Sie können zu einer standardmäßigen oder zuvor gespeicherten Seitenleiste zurückkehren, wodurch die Seitenleiste aus dem Profil gelöscht und die Seitenleiste erneut aus dem übergeordneten Profil geladen wird. Administratoren können die Standardseitenleiste (übergeordnete Seitenleiste) durch eine lokale Seitenleiste ersetzen, indem sie sie aus dem [!DNL Profile Manager] hochladen.

## Anpassen der Mehr-Status-Bedienfelddatei {#section-8d502f3b59cc4331966edec05e896ce1}

Systemadministratoren können Formeln im [!DNL More Status Panel.vw] erstellen. Dadurch werden kontextbezogene Wörter um Metrik- und Dimensionswerte platziert und die Ergebnisse in der Seitenleiste im Format [!DNL More Status panel] angezeigt.

Um das [!DNL More Status panel] in der Seitenleiste anzuzeigen, klicken Sie auf die Pfeile, die im folgenden Beispiel gezeigt werden.

![](assets/more_status_panel_arrows.png)

Das folgende Verfahren zeigt ein einfaches Beispiel, wie Sie einen benutzerspezifischen Status erstellen, der angibt, wie viele Tage sich in einem Datensatz befinden:

1. Klicken Sie in [!DNL Profile Manager] auf **[!UICONTROL Sidebar\]**.

1. Erstellen Sie in der Spalte [!DNL Base_5_3*] eine lokale Kopie der Datei [!DNL More Status Panel.vw].

   Klicken Sie dazu mit der rechten Maustaste auf das Dateiprüfzeichen und dann auf **[!UICONTROL Make Local]**.

1. Öffnen Sie die Datei [!DNL More Status Panel.vw] im [!DNL .vw] [!DNL Editor] oder im Notepad.

   ![](assets/more_status_panel_file.png)

1. Füllen Sie die Felder [!DNL Context] und [!DNL Items] in [!DNL Editor] aus. Richtlinien zur Syntax finden Sie unter [Abfrage Language Syntax](../../home/c-get-started/c-qry-lang-syntx/c-qry-lang-syntx.md#concept-15d1d3f5164a47d49468c5acb7299d9f).

1. Speichern Sie die Datei.

   Die Werte im obigen Beispiel führen zu einer Statusformel, die wie folgt angezeigt wird:

   ![](assets/more_status_panel.png)
