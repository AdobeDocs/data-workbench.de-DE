---
description: Sie können einen field-Viewer als Callout aus einer Abhängigkeitszuordnung oder als Standalone-Visualisierung aus dem Admin-Menü öffnen.
solution: Analytics
title: Erstellen eines field-Viewers
topic: Data workbench
uuid: df48e728-96f9-4432-82c8-f8047840ffb9
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Erstellen eines field-Viewers{#create-a-field-viewer}

Sie können einen field-Viewer als Callout aus einer Abhängigkeitszuordnung oder als Standalone-Visualisierung aus dem Admin-Menü öffnen.

## Erstellen eines field Viewers aus einer Abhängigkeitszuordnung {#section-040cb83c902b49c48b841d35abc127e5}

Wenn Sie einen field Viewer über eine Abhängigkeitszuordnung öffnen (wie in [Öffnen von Feldern-Viewern](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-opn-field-vwrs.md#concept-0f0738ac50804a33818487222c337c27)gezeigt), wird der Viewer automatisch basierend auf der Protokollquelle, Transformation oder Dimension gefüllt, auf die Sie mit der rechten Maustaste klicken. Bei einer Protokollquelle oder einer Transformation sind die Felder im Viewer Eingaben oder Ausgaben der Protokollquelle oder Transformation. Bei einer Dimension sind die Felder Eingaben der Dimension. Sie können Felder nach Bedarf hinzufügen und entfernen.

## Erstellen von Feldern-Viewern als eigenständige Visualisierung {#section-11d10e46631d4fdca45d7534336e1e80}

Wenn Sie einen Feld-Viewer als eigenständige Visualisierung öffnen, können Sie eine [!DNL Log Processing Field Viewer] oder eine [!DNL Transformation Field Viewer]erstellen. Der Viewer ist leer und Sie müssen die gewünschten Felder zum Viewer hinzufügen. Für einen [!DNL Log Processing Field Viewer]Vorgang können Sie Felder aus der [!DNL Log Processing.cfg] Datei oder einer beliebigen [!DNL Log Processing dataset include] Datei hinzufügen. Für einen [!DNL Transformation Field Viewer]Vorgang können Sie Felder aus der [!DNL Transformation.cfg] Datei oder einer beliebigen [!DNL Transformation dataset include] Datei hinzufügen.

Weitere Informationen zur Konfiguration und zum Einschließen von Dateien finden Sie im Handbuch zur Konfiguration von *Datasets*.

## Feld hinzufügen und entfernen {#section-9c0d4f5735a044a8b21dc7a99c63a59a}

**So fügen Sie einem Feld-Viewer ein Feld hinzu**

* Klicken Sie mit der rechten Maustaste in den field Viewer und klicken Sie auf **[!UICONTROL Fields]** > *&lt;**[!UICONTROL field name]**>* > *&lt;**[!UICONTROL instance]**>*.

   -oder-

* Klicken Sie mit der rechten Maustaste in eine vorhandene Spalte im Feld-Viewer und klicken Sie auf **[!UICONTROL Fields]** > *&lt;**[!UICONTROL field name]**>* > *&lt;**[!UICONTROL instance]**>*.

Der Feldname bezieht sich auf den Namen des Felds. Die Instanz bezieht sich auf die Stelle, an der das Feld in der Datensatzkonfiguration verwendet wird, z. B. eine Datenverarbeitungsphase oder eine Transformation. Einige Felder werden an mehreren Stellen in der Datensatzkonfiguration verwendet (z. B. kann ein Feld durch mehrere Konvertierungen geändert werden). Daher müssen Sie auswählen, welche Instanz des Felds dem Feld-Viewer hinzugefügt werden soll.

In der Liste der verfügbaren Felder wird links neben jedem Feld, das bereits im Viewer angezeigt wird, ein X angezeigt.

**So entfernen Sie ein Feld aus einem Feld-Viewer**

* Klicken Sie mit der rechten Maustaste in die Spalte für das Feld, das Sie entfernen möchten, und klicken Sie auf **[!UICONTROL Remove Field]**.
