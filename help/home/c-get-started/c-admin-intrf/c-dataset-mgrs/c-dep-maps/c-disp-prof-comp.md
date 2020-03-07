---
description: Sie können festlegen, dass die Dataset-Komponenten Ihres Profils, Abfragemodellkomponenten oder Arbeitsbereiche, Berichte, Menüoptionen und globale Ebenen in der Abhängigkeitszuordnung angezeigt werden.
solution: Analytics
title: Profilkomponenten anzeigen
topic: Data workbench
uuid: c904dcb7-6bb9-445c-be55-0573f88928ad
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Profilkomponenten anzeigen{#display-profile-components}

Sie können festlegen, dass die Dataset-Komponenten Ihres Profils, Abfragemodellkomponenten oder Arbeitsbereiche, Berichte, Menüoptionen und globale Ebenen in der Abhängigkeitszuordnung angezeigt werden.

**So wählen Sie die anzuzeigenden Komponenten aus**

1. Klicken Sie mit der rechten Maustaste in die Abhängigkeitskarte und klicken Sie auf **[!UICONTROL Display]**.
1. Wählen Sie eine oder mehrere der folgenden Optionen aus, die auf der Karte angezeigt werden sollen. Links neben jeder von Ihnen aktivierten Anzeigeoption wird ein X angezeigt.

   * **Datensatz** zur Anzeige der Datensatzkomponenten. Siehe [Datensatzkomponenten](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-dataset-comp.md#concept-4afe28ad29d14eca8a5000847254c293). Wenn Sie sich dafür entscheiden, die DataSet-Komponenten anzuzeigen, haben Sie die Möglichkeit, diese auf der Map [!DNL Include File Blocks] anzuzeigen. Siehe [Arbeiten mit Dateiblöcken](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-wkg-file-blocks.md#concept-3652bbabfbd34449a5f842d8aa598efc).

   * **Abfragemodell** zum Anzeigen von Abfragemodellkomponenten. Siehe Komponenten [des Abfragemodells](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-qry-mod-comp.md#concept-32c6dadd32f74179b026c7e96d47710f).

   * **Arbeitsbereiche und Visualisierungen** zum Anzeigen von Arbeitsbereichen, Berichten, Menüoptionen und globalen Ebenen. Siehe [Arbeitsbereiche und Visualisierungen](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-wksps-vis.md#concept-abbd4fb115ff47f49f879466ce274921). Diese Option funktioniert nur, wenn die [!DNL Query Model] Anzeigeoption aktiviert ist.

>[!NOTE]
>
>Wenn die [!DNL Query Model] Anzeigeoption bei Auswahl der [!DNL Workspaces and Visualizations] Anzeigeoption nicht aktiviert ist, wird eine Fehlermeldung angezeigt.

Wenn Sie nicht alle Knoten auf der Karte sehen können, können Sie die Karte verschieben, vergrößern oder verkleinern, um die gesamte Karte anzuzeigen oder sich auf einen bestimmten Abschnitt zu konzentrieren. Weitere Informationen zum Zoomen finden Sie unter [Vergrößern von Visualisierungen](../../../../../home/c-get-started/c-vis/c-zoom-vis.md#concept-7e33670bb5344f78a316f1a84cc20530).

Wenn Sie auf eine Node klicken, werden alle Nodes, die von dieser Node abhängen, sowie alle Nodes, von denen diese Node abhängig ist, hervorgehoben und ihre Namen werden angezeigt.

![](assets/vis_DependencyMap_HighlightedPath.png)

>[!NOTE]
>
>Ein hervorgehobener Pfad in einer Abhängigkeitszuordnung stellt keine Auswahl dar.

Wenn Sie mit der rechten Maustaste auf eine Node klicken, können Sie Informationen zu den einzelnen Komponenten auf der Map anzeigen und Menüoptionen auswählen, mit denen Sie weitere Details zur Komponente anzeigen oder die Komponente bearbeiten können. Darüber hinaus können Sie Textsuchen durchführen und Leistungsinformationen für Transformationen und erweiterte Dimensionen anzeigen.
