---
description: Sie können einen field-Viewer als Callout aus einer Abhängigkeitszuordnung oder als Standalone-Visualisierung aus dem Admin-Menü öffnen.
title: Erstellen eines Feld-Viewers
uuid: df48e728-96f9-4432-82c8-f8047840ffb9
exl-id: a2563dbb-1d1f-4ed8-b73b-6ac7a2687405
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '346'
ht-degree: 2%

---

# Erstellen eines Feld-Viewers{#create-a-field-viewer}

Sie können einen field-Viewer als Callout aus einer Abhängigkeitszuordnung oder als Standalone-Visualisierung aus dem Admin-Menü öffnen.

## Erstellen eines field Viewers aus einer Abhängigkeitszuordnung {#section-040cb83c902b49c48b841d35abc127e5}

Wenn Sie einen field Viewer aus einer Abhängigkeitszuordnung öffnen (wie in [Öffnen von Feld-Viewern](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-opn-field-vwrs.md#concept-0f0738ac50804a33818487222c337c27) gezeigt), wird der Viewer automatisch basierend auf der Protokollquelle, Transformation oder Dimension gefüllt, auf die Sie mit der rechten Maustaste klicken. Bei einer Protokollquelle oder einer Transformation sind die Felder im Viewer Eingaben oder Ausgaben der Protokollquelle oder Transformation. Bei einer Dimension sind die Felder Eingaben der Dimension. Sie können Felder nach Bedarf hinzufügen und entfernen.

## Erstellen von Feldern-Viewern als eigenständige Visualisierung {#section-11d10e46631d4fdca45d7534336e1e80}

Wenn Sie einen field-Viewer als Standalone-Visualisierung öffnen, können Sie ein [!DNL Log Processing Field Viewer] oder ein [!DNL Transformation Field Viewer] erstellen. Der Viewer ist leer und Sie müssen die gewünschten Felder zum Viewer hinzufügen. Bei einem [!DNL Log Processing Field Viewer] können Sie Felder aus der [!DNL Log Processing.cfg]-Datei oder einer [!DNL Log Processing dataset include]-Datei hinzufügen. Bei einem [!DNL Transformation Field Viewer] können Sie Felder aus der [!DNL Transformation.cfg]-Datei oder einer [!DNL Transformation dataset include]-Datei hinzufügen.

Weitere Informationen zu Konfigurations- und Include-Dateien finden Sie im Handbuch *Konfiguration von Datensätzen*.

## hinzufügen und entfernen Sie ein Feld {#section-9c0d4f5735a044a8b21dc7a99c63a59a}

**So fügen Sie einem Feld-Viewer ein Feld hinzu**

* Klicken Sie mit der rechten Maustaste in den Feld-Viewer und klicken Sie auf **[!UICONTROL Fields]** > *&lt;**[!UICONTROL field name]**>* > *&lt;**[!UICONTROL instance]**>*.

   -oder-

* Klicken Sie mit der rechten Maustaste in eine vorhandene Spalte im Feld-Viewer und klicken Sie auf **[!UICONTROL Fields]** > *&lt;**[!UICONTROL field name]*** > *&lt;**[!UICONTROL instance]**>*.

Der Feldname bezieht sich auf den Namen des Felds. Die Instanz bezieht sich auf die Stelle, an der das Feld in der Datensatzkonfiguration verwendet wird, z. B. eine Datenverarbeitungsphase oder eine Transformation. Einige Felder werden an mehreren Stellen in der Datensatzkonfiguration verwendet (z. B. kann ein Feld durch mehrere Konvertierungen geändert werden). Daher müssen Sie auswählen, welche Instanz des Felds dem Feld-Viewer hinzugefügt werden soll.

In der Liste der verfügbaren Felder wird links neben jedem bereits im Viewer angezeigten Feld ein X angezeigt.

**So entfernen Sie ein Feld aus einem Feld-Viewer**

* Klicken Sie mit der rechten Maustaste in die Spalte für das Feld, das Sie entfernen möchten, und klicken Sie auf **[!UICONTROL Remove Field]**.
