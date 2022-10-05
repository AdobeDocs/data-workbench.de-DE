---
description: Schritte zum Bereitstellen einer beliebigen Vektorebene für die Anzeige auf der globalen Visualisierung.
title: Verfügbar machen von neuen Vektorebenen
uuid: 7bfbae0d-e5db-4aa2-8a8b-15b4980aadb5
exl-id: 6c084bac-1a6d-452a-bf07-e502d0f2145a
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '171'
ht-degree: 7%

---

# Verfügbar machen von neuen Vektorebenen{#make-a-new-vector-layer-available}

{{eol}}

Schritte zum Bereitstellen einer beliebigen Vektorebene für die Anzeige auf der globalen Visualisierung.

1. Platzieren Sie im Ordner Profile\*profile name*\Maps im Installationsordner des Data Workbench-Servers die Ebenendatei und die [!DNL .vec] oder [!DNL .tsv] Dateien.
1. Bearbeiten Sie die [!DNL order.txt] im Ordner Profile\*Profilname*\Maps , um die Reihenfolge anzuzeigen, in der die Ebenen angezeigt werden sollen. Standardmäßig werden Ebenen anhand ihres Namens in Wörterbuchreihenfolge angezeigt.

   >[!NOTE]
   >
   >Beim Bearbeiten der [!DNL order.txt] -Datei, achten Sie darauf, keine Kartenschichten zu verdecken, die Sie anzeigen möchten.

   Weitere Informationen zur Verwendung von [!DNL order.txt] -Dateien, siehe [Menüs mithilfe von &quot;order.txt&quot;-Dateien anpassen](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999).

1. Wählen Sie in Insight das gewünschte Profil aus, indem Sie mit der rechten Maustaste auf die Titelleiste des Arbeitsbereichs klicken und auf **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]**>*.
1. Klicken Sie mit der rechten Maustaste auf die Titelleiste des Arbeitsbereichs und klicken Sie auf **[!UICONTROL Work Online]**. Neben Work Online wird ein X angezeigt.
1. Öffnen Sie einen Arbeitsbereich, klicken Sie mit der rechten Maustaste auf eine globale Visualisierung und wählen Sie die neue Ebene aus. Neben dem Ebenennamen wird ein X angezeigt.
