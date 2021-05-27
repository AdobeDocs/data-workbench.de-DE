---
description: Das Geografie-Profil speichert eine Sammlung von Bildebenen und Dateien.
title: Anzeigeebenen
uuid: ebc7025d-e619-43dd-88da-7452ada3226b
exl-id: 12ec913f-c7e5-49b5-8792-db0881cb5cfe
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '267'
ht-degree: 1%

---

# Anzeigeebenen{#display-layers}

Das Geografie-Profil speichert eine Sammlung von Bildebenen und Dateien.

Wenn Sie einen Globus anzeigen, können Sie auswählen, welche der verfügbaren Ebenen für eine bestimmte Analyseaufgabe angezeigt werden sollen:

* **Blue Marble 2km:** Diese Schicht zeigt den Globus an. Wenn diese Ebene nicht ausgewählt ist, ist der Globus nicht sichtbar.
* **IP-Koordinaten:**  Diese Elementpunktebene zeigt den Längen- und Breitengrad der Positionen in Ihrem Datensatz basierend auf den IP-Adressen der Besucher an.
* **Postleitzahlen:** Diese Ebene zeigt den Längen- und Breitengrad der Standorte in Ihrem Datensatz basierend auf einer von Adobe bereitgestellten Liste der US-Postleitzahlen an. Die Lookup-Datei [!DNL Zip Points.txt] enthält die anzuzeigenden ZIP-Code-, Breiten- und Längengrad-Daten, während die Datei [!DNL Zip Points.layer] die Konfigurationsparameter enthält, die zum Anzeigen dieser Daten auf der Welt erforderlich sind. Beide Dateien werden im Ordner &quot;Profiles\Geography\Maps folder within the Data Workbench server installation directory&quot;gespeichert.

* ***Andere verfügbare Ebenennamen:***  Jeder Ebenenname stellt eine  [!DNL .layer] Datei dar, die im Ordner Profiles\Geography\Maps folder, Profiles\IP Geo-Location\Maps oder im Ordner Profiles\IP Geo-Intelligence\Maps im Installationsordner von Insight Server gespeichert ist.

>[!NOTE]
>
>Um über den IP-Geolocation oder das IP-Geo-Intelligence-Profil zu verfügen, müssen Sie entweder den IP-Geolocation- oder den IP-Geo-Intelligence-Datendienst abonnieren.

Um die Reihenfolge zu steuern, in der Ihre Ebenen angezeigt werden, können Sie eine [!DNL order.txt]-Datei verwenden. Siehe [Anpassen von Menüs mithilfe von &quot;Order.txt&quot;-Dateien](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999).

**So umschalten Sie Ebenen in einem Globus**

* Klicken Sie mit der rechten Maustaste in die Visualisierung und klicken Sie auf den gewünschten Ebenennamen. Ein X links neben der Ebene zeigt an, dass die Ebene sichtbar ist.
