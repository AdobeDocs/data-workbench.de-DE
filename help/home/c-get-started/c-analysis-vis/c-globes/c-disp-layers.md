---
description: Das Geografie-Profil speichert eine Sammlung von Bildebenen und Dateien.
title: Anzeigeebenen
uuid: ebc7025d-e619-43dd-88da-7452ada3226b
exl-id: 12ec913f-c7e5-49b5-8792-db0881cb5cfe
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '267'
ht-degree: 1%

---

# Anzeigeebenen{#display-layers}

{{eol}}

Das Geografie-Profil speichert eine Sammlung von Bildebenen und Dateien.

Wenn Sie einen Globus anzeigen, können Sie auswählen, welche der verfügbaren Ebenen für eine bestimmte Analyseaufgabe angezeigt werden sollen:

* **Blauer Marmor 2 km:** Auf dieser Ebene wird der Globus angezeigt. Wenn diese Ebene nicht ausgewählt ist, ist der Globus nicht sichtbar.
* **IP-Koordinaten:** Diese Elementpunktebene zeigt den Breiten- und Längengrad der Standorte in Ihrem Datensatz basierend auf den IP-Adressen der Besucher an.
* **Postleitzahlen:** Diese Ebene zeigt den Längen- und Breitengrad der Standorte in Ihrem Datensatz basierend auf einer von Adobe bereitgestellten Liste der US-Postleitzahlen an. Die [!DNL Zip Points.txt] Die Lookup-Datei enthält die ZIP-Code-, Breiten- und Längengrad-Daten, die angezeigt werden sollen, während die [!DNL Zip Points.layer] enthält die Konfigurationsparameter, die zur Anzeige dieser Daten auf der Welt erforderlich sind. Beide Dateien werden im Ordner Profile\Geografie\Maps des Installationsordners des Data Workbench-Servers gespeichert.

* ***Andere verfügbare Ebenennamen:*** Jeder Ebenenname stellt einen [!DNL .layer] im Ordner Profile\Geography\Maps , Ordner Profile\IP Geo-Location\Maps oder Ordner Profile\IP Geo-Intelligence\Maps im Installationsordner von Insight Server gespeichert.

>[!NOTE]
>
>Um über den IP-Geolocation oder das IP-Geo-Intelligence-Profil zu verfügen, müssen Sie entweder den IP-Geolocation- oder den IP-Geo-Intelligence-Datendienst abonnieren.

Um die Reihenfolge zu steuern, in der Ihre Ebenen angezeigt werden, können Sie eine [!DNL order.txt] -Datei. Siehe [Menüs mithilfe von &quot;order.txt&quot;-Dateien anpassen](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999).

**So umschalten Sie Ebenen in einem Globus**

* Klicken Sie mit der rechten Maustaste in die Visualisierung und klicken Sie auf den gewünschten Ebenennamen. Ein X links neben der Ebene zeigt an, dass die Ebene sichtbar ist.
