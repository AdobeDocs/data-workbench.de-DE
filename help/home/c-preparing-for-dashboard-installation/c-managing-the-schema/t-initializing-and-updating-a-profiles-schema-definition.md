---
description: Initialisieren und Aktualisieren der Schemadefinition eines Profils
title: Initialisieren und Aktualisieren der Schemadefinition eines Profils
uuid: 38e47ded-340e-4f65-b06c-f2e2254f0863
exl-id: e8190909-4416-4d4a-8901-130d01906773
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '269'
ht-degree: 7%

---

# Initialisieren und Aktualisieren der Schemadefinition eines Profils{#initializing-and-updating-a-profile-s-schema-definition}

{{eol}}

1. Öffnen Sie die **[!UICONTROL Schema Builder]** für das Profil, das Sie einrichten möchten.
1. A **[!UICONTROL Loading]** wird angezeigt, während das Schema aus dem Insight-Profil abgerufen wird. Die Dauer des Ladens des Schemas hängt von der Komplexität des geladenen Profils ab.
1. Wenn Sie fertig sind, sehen Sie eine Zusammenfassung der Unterschiede zwischen den **[!UICONTROL Insight Schema]** im linken Bereich und dem **[!UICONTROL Dashboard Schema]** im rechten Bereich. Diese Zusammenfassung wird im unteren linken Bereich der **[!UICONTROL Schema Builder]** Fenster.

   >[!NOTE]
   >
   >Beim erstmaligen Einrichten des Schemas werden jede Metrik, Dimension und jeder Filter anders als das Schema des Dashboards aufgeführt. Dies liegt daran, dass die Dashboard-Schemaobjekte derzeit nicht vorhanden sind.

   ![](assets/schema_builder2.png)

1. Klicken Sie auf **[!UICONTROL Synchronize with Schema]** Schaltfläche zum Synchronisieren aller Metriken, Dimensionen und Filter aus der Ansicht &quot;Insight-Schema&quot;mit der Dashboard-Schema-Ansicht.
1. Nach Abschluss des Vorgangs sollte eine Meldung angezeigt werden, die angibt, dass keine Unterschiede gefunden wurden:

   ![](assets/diff_found.png)

1. Wenn Fehler im Dashboard-Schema auftreten, z. B. doppelte Metriken und Dimensionen, müssen Sie diese manuell korrigieren, bevor Sie speichern können.

   >[!NOTE]
   >
   >Sie können beliebige Metriken, Dimensionen oder Filter selektiv aus der **[!UICONTROL Dashboard Schema]** dass Sie nicht für Endbenutzer des Dashboards angezeigt werden möchten. Sie erhalten eine Warnung, dass die Elemente nicht im Dashboard-Schema vorhanden sind. Sie werden jedoch nicht daran gehindert, sie zu speichern.

1. Wenn Sie bereit sind, klicken Sie auf **[!UICONTROL Save]** , um Ihre Änderungen im Schema des Dashboards zu speichern.
1. Das Dashboard-System verwendet diese Schemadefinition zum Ausfüllen der Dimensionen, Metriken und Filter, die Endbenutzern der Dashboard-Oberfläche zur Verfügung stehen.
