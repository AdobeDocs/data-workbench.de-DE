---
description: Das Profil Geografie speichert eine Sammlung von Bildebenen und -dateien.
title: Anzeigeebenen
uuid: ebc7025d-e619-43dd-88da-7452ada3226b
exl-id: 12ec913f-c7e5-49b5-8792-db0881cb5cfe
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '267'
ht-degree: 1%

---

# Anzeigeebenen{#display-layers}

Das Profil Geografie speichert eine Sammlung von Bildebenen und -dateien.

Wenn Sie einen Globus anzeigen, können Sie auswählen, welche der verfügbaren Ebenen für eine bestimmte Aufgabe der Analyse angezeigt werden sollen:

* **Blaue Marmor 2km:** Diese Ebene zeigt die Welt. Wenn diese Ebene nicht ausgewählt ist, ist der Globus nicht sichtbar.
* **IP-Koordinaten:** Diese Elementpunktebene zeigt die Breiten- und Längengrade der Positionen in Ihrem Datensatz basierend auf den IP-Adressen der Besucher an.
* **Zip-Punkte:** Diese Ebene zeigt den Breiten- und Längengrad der Positionen in Ihrem Datensatz basierend auf einer Liste der US-Postleitzahlen an, die von der Adobe bereitgestellt werden. Die [!DNL Zip Points.txt]-Lookup-Datei enthält die anzuzeigenden ZIP-Code-, Breiten- und Längengraddaten, während die [!DNL Zip Points.layer]-Datei die Konfigurationsparameter enthält, die zum Anzeigen dieser Daten auf der Welt erforderlich sind. Beide Dateien werden im Ordner &quot;Profiles\Geography\Maps folder within the Data Workbench server installation directory&quot;gespeichert.

* ***Andere verfügbare Ebenennamen:*** Jeder Ebenenname stellt eine  [!DNL .layer] Datei dar, die im Installationsordner von Insight Server im Ordner Profiles\Geography\Maps folder, Profils\IP Geo-location\Maps oder Profils\IP Geo-Intelligence\Maps gespeichert ist.

>[!NOTE]
>
>Um das IP-Geo-Location- oder IP-Geo-Intelligence-Profil nutzen zu können, müssen Sie entweder den Geo-Standort-IP oder den IP-Geo-Intelligence-Datendienst abonnieren.

Um die Reihenfolge zu steuern, in der die Ebenen angezeigt werden, können Sie eine [!DNL order.txt]-Datei verwenden. Siehe [Anpassen von Menüs mit order.txt-Dateien](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999).

**So umschalten Sie Ebenen in einem Globus**

* Klicken Sie mit der rechten Maustaste in die Visualisierung und klicken Sie auf den gewünschten Ebenennamen. Ein X links neben der Ebene gibt an, dass die Ebene sichtbar ist.
