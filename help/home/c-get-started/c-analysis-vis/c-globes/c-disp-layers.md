---
description: Das Geografie-Profil speichert eine Sammlung von Bildebenen und Dateien.
solution: Analytics
title: Ebenen anzeigen
topic: Data workbench
uuid: ebc7025d-e619-43dd-88da-7452ada3226b
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Ebenen anzeigen{#display-layers}

Das Geografie-Profil speichert eine Sammlung von Bildebenen und Dateien.

Wenn Sie einen Globus anzeigen, können Sie auswählen, welche der verfügbaren Ebenen für eine bestimmte Analyseaufgabe angezeigt werden sollen:

* **Blaue Marmor 2 km:** Diese Ebene zeigt den Globus an. Wenn diese Ebene nicht ausgewählt ist, ist der Globus nicht sichtbar.
* **IP-Koordinaten:** Diese Elementpunkteebene zeigt den Breiten- und Längengrad der Positionen in Ihrem Datensatz basierend auf den IP-Adressen der Besucher an.
* **Zip-Punkte:** Diese Ebene zeigt den Breiten- und Längengrad der Speicherorte in Ihrem Datensatz basierend auf einer von Adobe bereitgestellten Liste der US-Postleitzahlen an. Die [!DNL Zip Points.txt] Lookup-Datei enthält die anzuzeigenden ZIP-Code-, Breiten- und Längengraddaten, während die [!DNL Zip Points.layer] Datei die Konfigurationsparameter enthält, die zum Anzeigen dieser Daten auf der Welt erforderlich sind. Beide Dateien werden im Ordner &quot;Profiles\Geography\Maps folder within the Data Workbench server installation directory&quot;gespeichert.

* ***Andere verfügbare Ebenennamen:*** Jeder Ebenenname stellt eine [!DNL .layer] Datei dar, die im Ordner &quot;Profiles\Geography\Maps folder&quot;, &quot;Profiles\IP Geo-location\Maps&quot;oder &quot;Profiles\IP Geo-Intelligence\Maps&quot;im Installationsordner von Insight Server gespeichert ist.

>[!NOTE]
>
>Um das IP-Geo-Standort- oder IP-Geo-Intelligence-Profil zu haben, müssen Sie entweder den Geo-Standort-IP oder den IP-Geo-Intelligence-Datendienst abonnieren.

Um die Reihenfolge zu steuern, in der die Ebenen angezeigt werden, können Sie eine [!DNL order.txt] Datei verwenden. Siehe [Anpassen von Menüs mithilfe von &quot;order.txt&quot;-Dateien](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999).

**So umschalten Sie Ebenen in einem Globus**

* Klicken Sie mit der rechten Maustaste in die Visualisierung und klicken Sie auf den gewünschten Ebenennamen. Ein X links neben der Ebene gibt an, dass die Ebene sichtbar ist.

