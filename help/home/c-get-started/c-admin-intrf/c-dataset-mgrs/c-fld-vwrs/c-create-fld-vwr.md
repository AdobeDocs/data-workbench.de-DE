---
description: Sie können einen Feld-Viewer über eine Abhängigkeitskarte oder eine eigenständige Visualisierung im Admin-Menü als Callout öffnen.
title: Erstellen eines Feld-Viewers
uuid: df48e728-96f9-4432-82c8-f8047840ffb9
exl-id: a2563dbb-1d1f-4ed8-b73b-6ac7a2687405
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '346'
ht-degree: 2%

---

# Erstellen eines Feld-Viewers{#create-a-field-viewer}

{{eol}}

Sie können einen Feld-Viewer über eine Abhängigkeitskarte oder eine eigenständige Visualisierung im Admin-Menü als Callout öffnen.

## Erstellen eines Feld-Viewers aus einer Abhängigkeitskarte {#section-040cb83c902b49c48b841d35abc127e5}

Wenn Sie einen Feld-Viewer über eine Abhängigkeitszuordnung öffnen (wie in [Öffnen von Feld-Viewern](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-opn-field-vwrs.md#concept-0f0738ac50804a33818487222c337c27)), wird der Viewer automatisch basierend auf der Protokollquelle, Transformation oder Dimension, auf die Sie mit der rechten Maustaste klicken, aufgefüllt. Bei einer Protokollquelle oder einer Umwandlung sind die Felder im Viewer Eingabe- oder Ausgabeformate der Protokollquelle oder Transformation. Für eine Dimension sind die Felder Eingaben der Dimension. Sie können Felder nach Bedarf hinzufügen und entfernen.

## Erstellen von Feld-Viewern als eigenständige Visualisierung {#section-11d10e46631d4fdca45d7534336e1e80}

Wenn Sie einen Feld-Viewer als eigenständige Visualisierung öffnen, können Sie eine [!DNL Log Processing Field Viewer] oder [!DNL Transformation Field Viewer]. Der Viewer ist leer und Sie müssen die gewünschten Felder zum Viewer hinzufügen. Für [!DNL Log Processing Field Viewer]können Sie Felder aus dem [!DNL Log Processing.cfg] Datei oder [!DNL Log Processing dataset include] -Datei. Für [!DNL Transformation Field Viewer]können Sie Felder aus dem [!DNL Transformation.cfg] Datei oder [!DNL Transformation dataset include] -Datei.

Weitere Informationen zur Konfiguration und zum Einschließen von Dateien finden Sie unter *Anleitung zur Datensatzkonfiguration*.

## Feld hinzufügen und entfernen {#section-9c0d4f5735a044a8b21dc7a99c63a59a}

**So fügen Sie einem Feld-Viewer ein Feld hinzu**

* Klicken Sie mit der rechten Maustaste in den Feld-Viewer und klicken Sie auf **[!UICONTROL Fields]** > *&lt;**[!UICONTROL field name]**>* > *&lt;**[!UICONTROL instance]**>*.

   -oder-

* Klicken Sie mit der rechten Maustaste in eine vorhandene Spalte im Feld-Viewer und klicken Sie auf **[!UICONTROL Fields]** > *&lt;**[!UICONTROL field name]**>* > *&lt;**[!UICONTROL instance]**>*.

Der Feldname bezieht sich auf den Namen des Felds und die Instanz bezieht sich auf die Stelle, an der in der Datensatzkonfiguration das Feld verwendet wird, z. B. eine Datensatzverarbeitungsphase oder eine Umwandlung. Einige Felder werden an mehreren Stellen innerhalb der Datensatzkonfiguration verwendet (z. B. kann ein Feld durch mehrere Umwandlungen geändert werden). Daher müssen Sie auswählen, welche Instanz des Felds zu Ihrem Feld-Viewer hinzugefügt werden soll.

In der Liste der verfügbaren Felder wird links neben jedem Feld, das bereits im Viewer angezeigt wird, ein X angezeigt.

**So entfernen Sie ein Feld aus einem Feld-Viewer**

* Klicken Sie mit der rechten Maustaste in die Spalte für das Feld, das Sie entfernen möchten, und klicken Sie auf **[!UICONTROL Remove Field]**.
