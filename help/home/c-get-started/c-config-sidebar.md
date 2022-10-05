---
description: Die Seitenleiste bietet Zugriff auf regelmäßig verwendete Funktionen und behält Visualisierungen beim Wechsel zwischen Arbeitsbereichen bei.
title: Konfigurieren der Seitenleiste
uuid: 0d2f0b9a-56a9-4f27-aaa6-1f9bf7fcab2d
exl-id: 75ccc869-8ced-4beb-b3d7-ed7febe347f9
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '745'
ht-degree: 2%

---

# Konfigurieren der Seitenleiste{#configure-the-sidebar}

{{eol}}

Die Seitenleiste bietet Zugriff auf regelmäßig verwendete Funktionen und behält Visualisierungen beim Wechsel zwischen Arbeitsbereichen bei.

Administratoren können eine Seitenleiste so anpassen, dass sie für verschiedene Benutzergruppen geeignet ist. Anschließend können sie die Seitenleiste mit einem Profil bereitstellen.

Die Seitenleiste ist ideal, um Filter und lokale Überschreibungen zu verfolgen. Wenn Sie es vorziehen, die Seitenleiste nicht zu verwenden, können Sie sie verbergen.

## Hinzufügen von Visualisierungen zur Seitenleiste {#section-666f70a405db4f8d8eaffa567ffcac06}

1. Launch-Data Workbench.
1. Klicken Sie in der Seitenleiste auf **[!UICONTROL Add]** > *&lt;**[!UICONTROL item]**>*. Beispiele: [!DNL Selections Panel], [!DNL Filters Panel] oder [!DNL Table].

   Die folgenden Seitenleisten-Bedienfelder sind in der Standardinstallation von Data Workbench verfügbar. In Ihrem spezifischen Profil können weitere Elemente verfügbar sein:

   * **Auswahlbereich:** Ermöglicht Ihnen, zu verstehen, welche Auswahlen im aktuellen Arbeitsbereich aktiv sind. Die [!DNL Selections Panel] aktualisiert, sobald Sie eine neue Auswahl treffen. Sie können die Auswahl löschen, indem Sie auf **[!UICONTROL x]**. Siehe [Auswahlen in Visualisierungen](../../home/c-get-started/c-vis/c-sel-vis/c-sel-vis.md#concept-012870ec22c7476e9afbf3b8b2515746) für Informationen zur Auswahl von Daten.
   * **Filterbereich:** Erleichtert das Laden und Anwenden gespeicherter Filter. Sie können mehrere Filter laden und jede einzelne einzeln aktivieren oder deaktivieren, indem Sie auf das Kontrollkästchen daneben klicken. Siehe [Filter-Editoren](../../home/c-get-started/c-analysis-vis/c-filter-editors/c-filter-editors.md#concept-2f343ecbed8240f18b0c1f1eccef11e3).
   * **Lokales Override-Bedienfeld:** In diesem Bereich wird angezeigt, welche Metriken, Dimensionen und Filter, die im Profil vorhanden sind, in Ihrer persönlichen Kopie des Profils geändert wurden. Auf diese Weise können Sie auf mögliche Unterschiede zwischen der Darstellung von Daten in Ihrem Client und der anderer Benutzer aufmerksam machen. Wenn Sie Änderungen in einer Metrik, Dimension oder Filter auf dem Server speichern, wird die Überschreibung aus dem [!DNL Local Overrides panel]. Wenn Sie auf eine Überschreibung klicken und dann auf **[!UICONTROL Revert to Server]**, wird die lokale Überschreibung entfernt und das Element wird auf die freigegebene Version zurückgesetzt.
   * **Metriklegende:** Fügt eine Metriklegende hinzu. [!DNL Metric legends] aktivieren, können Sie Grundlinien-Metriken sehen, die sich auf Ihr Profil beziehen, sowie Statistiken, die sich auf den Datensatz beziehen (oder auf die aktuelle Auswahl, falls eine vorgenommen wurde). Siehe [Metriklegenden](../../home/c-get-started/c-analysis-vis/c-legends/c-metric-leg.md#concept-e7195bc8f7844ae295bda3a88b028d5b).
   * **Farblegende:** Fügt eine Farblegende hinzu. Sie können Visualisierungen nach Metriken wie Konversion und Treue farbkodieren und in fast allen [!DNL Workspace]. Wenn Sie Geschäftsmetriken mit Farben verknüpfen, können Sie einfach Anomalien, Ausnahmen und Trends erkennen. Siehe [Farblegende](../../home/c-get-started/c-analysis-vis/c-legends/c-color-leg.md#concept-f84d51dc0d6547f981d0642fc2d01358).
   * **Textanmerkung:** Fügt einen Bereich für Notizen hinzu. [!DNL Text annotations] sind Fenster, in die Sie beliebigen Text eingeben können, um beschreibende Informationen oder Kommentare zu einer [!DNL Workspace]. Siehe [Arbeiten mit Textanmerkungen](../../home/c-get-started/c-analysis-vis/c-annots/c-text-annots.md#concept-55b4aa3e0c58470b8e3c9d452e12a777).
   * **Tabelle:** Fügt eine Tabelle hinzu. Eine Tabelle kann eine oder mehrere Metriken über eine oder mehrere Datendimensionen hinweg anzeigen. Siehe [Tabellen](../../home/c-get-started/c-analysis-vis/c-tables/c-tables.md#concept-c632cb8ad9724f90ac5c294d52ae667f).
   * **Öffnen Sie:** Öffnet eine gespeicherte Datei.

## Öffnen eines Seitenleisten-Bedienfelds {#section-cbc8e57491854274a577d47a48c306b8}

Sie können eine Visualisierungsdatei für die Seitenleiste von einem gespeicherten Speicherort oder aus der Zwischenablage aus öffnen.

1. Klicken Sie in der Seitenleiste auf **[!UICONTROL Add]** > **[!UICONTROL Open]**.
1. Klicken **[!UICONTROL File]** , um [!DNL .vw] Datei des Bereichs, den Sie hinzufügen möchten, oder klicken Sie auf **[!UICONTROL Last Closed Window]**, wodurch die Visualisierung aus der Zwischenablage abgerufen wird.

   Außerdem können Sie auf **[!UICONTROL From Clipboard]** , um eine in die Zwischenablage kopierte Visualisierung einzufügen. Siehe [Kopieren eines Seitenleisten-Bedienfelds](../../home/c-get-started/c-config-sidebar.md#section-720ae057632a4b8dbb94412e06a370b1).

## Kopieren eines Seitenleisten-Bedienfelds {#section-720ae057632a4b8dbb94412e06a370b1}

1. Klicken Sie mit der rechten Maustaste auf den oberen Rand des Bedienfelds und klicken Sie dann auf **[!UICONTROL Copy]** > **[!UICONTROL Window]**.
1. Um das Bedienfeld einzufügen, klicken Sie auf **[!UICONTROL Add]** > **[!UICONTROL Open]** > **[!UICONTROL From Clipboard]**.

## Speichern eines Seitenleisten-Bedienfelds {#section-fb19936b12704fb0a4c592abb579db1d}

Klicken Sie in einem Seitenleistenbedienfeld mit der rechten Maustaste in die Titelleiste und klicken Sie auf **[!UICONTROL Save]**.

Auf ähnliche Weise können Sie eine gespeicherte Visualisierung der Seitenleiste öffnen. Data Workbench speichert die Visualisierung als [!DNL .vw] -Datei an dem von Ihnen angegebenen Speicherort.

## Wiederherstellen der Standardseitenleiste {#section-4d14b8771ad747bba799876267f24831}

Klicken Sie in der Seitenleiste auf **[!UICONTROL Options]** > **[!UICONTROL Revert]**.

Wenn Sie die Data Workbench schließen, speichert das System die aktuelle Seitenleistenkonfiguration im [!DNL sidebar.vw] -Datei im Benutzerprofil. Wenn Sie die Data Workbench öffnen, lädt das System die [!DNL sidebar.vw] -Datei aus dem Benutzerprofil anstatt aus einem übergeordneten Profil.

Sie können zu einer standardmäßigen oder zuvor gespeicherten Seitenleiste zurückkehren, die die Seitenleiste aus dem Benutzerprofil löscht und die Seitenleiste erneut aus dem übergeordneten Profil lädt. Administratoren können die standardmäßige (übergeordnete) Seitenleiste durch eine lokale Seitenleiste ersetzen, indem sie sie aus dem [!DNL Profile Manager].

## Anpassen der Datei &quot;More Status Panel&quot; {#section-8d502f3b59cc4331966edec05e896ce1}

Systemadministratoren können Formeln im [!DNL More Status Panel.vw]. Dadurch werden kontextbezogene Wörter um Metrik- und Dimensionswerte herum platziert und die Ergebnisse in der [!DNL More Status panel] in der Seitenleiste.

So zeigen Sie die [!DNL More Status panel] Klicken Sie in der Seitenleiste auf die Pfeile im folgenden Beispiel.

![](assets/more_status_panel_arrows.png)

Die folgende Prozedur zeigt ein einfaches Beispiel, wie Sie einen benutzerdefinierten Status erstellen, der angibt, wie viele Tage sich in einem Datensatz befinden:

1. Klicken Sie in [!DNL Profile Manager] auf **[!UICONTROL Sidebar\]**.

1. Im [!DNL Base_5_3*] eine lokale Kopie der [!DNL More Status Panel.vw] -Datei.

   Klicken Sie dazu mit der rechten Maustaste auf das Dateikontrollzeichen und klicken Sie auf **[!UICONTROL Make Local]**.

1. Öffnen Sie die [!DNL More Status Panel.vw] in der Datei [!DNL .vw] [!DNL Editor] oder im Editor.

   ![](assets/more_status_panel_file.png)

1. Führen Sie die [!DNL Context] und [!DNL Items] -Felder in [!DNL Editor]. Siehe [Syntax der Abfragesprache](../../home/c-get-started/c-qry-lang-syntx/c-qry-lang-syntx.md#concept-15d1d3f5164a47d49468c5acb7299d9f) für Richtlinien zur Syntax.

1. Speichern Sie die Datei.

   Die Werte im obigen Beispiel führen zu einer Statusformel, die wie folgt dargestellt wird:

   ![](assets/more_status_panel.png)
