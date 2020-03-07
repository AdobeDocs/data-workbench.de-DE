---
description: 'null'
solution: Analytics
title: Initialisieren und Aktualisieren der Schemadefinition eines Profils
topic: Data workbench
uuid: 38e47ded-340e-4f65-b06c-f2e2254f0863
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Initialisieren und Aktualisieren der Schemadefinition eines Profils{#initializing-and-updating-a-profile-s-schema-definition}

1. Öffnen Sie das **[!UICONTROL Schema Builder]** Profil, das Sie einrichten möchten.
1. Eine **[!UICONTROL Loading]** Meldung wird angezeigt, während das Schema aus dem Insight-Profil abgerufen wird. Die Dauer des Ladens des Schemas hängt von der Komplexität des zu ladenden Profils ab.
1. Nach Abschluss des Vorgangs wird eine Zusammenfassung der Unterschiede zwischen dem **[!UICONTROL Insight Schema]** im linken Bereich und dem **[!UICONTROL Dashboard Schema]** im rechten Bereich angezeigt. Diese Zusammenfassung wird im unteren linken Teil des **[!UICONTROL Schema Builder]** Fensters angezeigt.

   >[!NOTE]
   >
   >Beim erstmaligen Einrichten des Schemas wird jede Metrik, Dimension und jeder Filter anders als das Schema des Dashboards aufgeführt. Dies liegt daran, dass die Dashboard-Schemaobjekte derzeit nicht vorhanden sind.

   ![](assets/schema_builder2.png)

1. Klicken Sie auf die **[!UICONTROL Synchronize with Schema]** Schaltfläche, um alle Metriken, Dimensionen und Filter aus der Insight-Schemaansicht mit der Dashboard-Schemaansicht zu synchronisieren.
1. Nach Abschluss des Vorgangs sollte eine Meldung angezeigt werden, dass keine Unterschiede gefunden wurden:

   ![](assets/diff_found.png)

1. Wenn beim Dashboard-Schema Fehler auftreten, z. B. doppelte Metriken und Dimensionen, müssen Sie diese manuell korrigieren, bevor Sie speichern können.

   >[!NOTE]
   >
   >Sie können beliebige Metriken, Dimensionen oder Filter selektiv aus dem Bereich entfernen, **[!UICONTROL Dashboard Schema]** der den Endbenutzern des Dashboards nicht angezeigt werden soll. Sie erhalten eine Warnung, dass Elemente im Dashboard-Schema nicht vorhanden sind, aber das Speichern wird nicht verhindert.

1. Wenn Sie bereit sind, klicken Sie auf , **[!UICONTROL Save]** um Ihre Änderungen im Dashboard-Schema zu speichern.
1. Das Dashboard-System verwendet diese Schemadefinition, um die Dimensionen, Metriken und Filter zu füllen, die Endbenutzern der Dashboard-Oberfläche zur Verfügung stehen.
