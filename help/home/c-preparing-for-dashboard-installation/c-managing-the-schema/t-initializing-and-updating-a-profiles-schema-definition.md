---
description: Initialisieren und Aktualisieren der Schemadefinition eines Profils
title: Initialisieren und Aktualisieren der Schemadefinition eines Profils
uuid: 38e47ded-340e-4f65-b06c-f2e2254f0863
exl-id: e8190909-4416-4d4a-8901-130d01906773
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '269'
ht-degree: 7%

---

# Initialisieren und Aktualisieren der Schemadefinition eines Profils{#initializing-and-updating-a-profile-s-schema-definition}

1. Öffnen Sie **[!UICONTROL Schema Builder]** für das Profil, das Sie einrichten möchten.
1. Eine **[!UICONTROL Loading]**-Meldung wird angezeigt, während das Schema aus dem Insight-Profil abgerufen wird. Die Dauer des Ladens des Schemas hängt von der Komplexität des geladenen Profils ab.
1. Wenn Sie fertig sind, sehen Sie eine Zusammenfassung der Unterschiede zwischen **[!UICONTROL Insight Schema]** im linken Bereich und **[!UICONTROL Dashboard Schema]** im rechten Bereich. Diese Zusammenfassung wird im unteren linken Bereich des Fensters **[!UICONTROL Schema Builder]** angezeigt.

   >[!NOTE]
   >
   >Beim erstmaligen Einrichten des Schemas werden jede Metrik, Dimension und jeder Filter anders als das Schema des Dashboards aufgeführt. Dies liegt daran, dass die Dashboard-Schemaobjekte derzeit nicht vorhanden sind.

   ![](assets/schema_builder2.png)

1. Klicken Sie auf die Schaltfläche **[!UICONTROL Synchronize with Schema]** , um alle Metriken, Dimensionen und Filter aus der Ansicht &quot;Insight-Schema&quot;mit der Dashboard-Schema-Ansicht zu synchronisieren.
1. Nach Abschluss des Vorgangs sollte eine Meldung angezeigt werden, die angibt, dass keine Unterschiede gefunden wurden:

   ![](assets/diff_found.png)

1. Wenn Fehler im Dashboard-Schema auftreten, z. B. doppelte Metriken und Dimensionen, müssen Sie diese manuell korrigieren, bevor Sie speichern können.

   >[!NOTE]
   >
   >Sie können beliebige Metriken, Dimensionen oder Filter selektiv aus dem **[!UICONTROL Dashboard Schema]** entfernen, die Endbenutzern des Dashboards nicht angezeigt werden sollen. Sie erhalten eine Warnung, dass die Elemente nicht im Dashboard-Schema vorhanden sind. Sie werden jedoch nicht daran gehindert, sie zu speichern.

1. Wenn Sie bereit sind, klicken Sie auf **[!UICONTROL Save]** , um Ihre Änderungen im Schema des Dashboards zu speichern.
1. Das Dashboard-System verwendet diese Schemadefinition zum Ausfüllen der Dimensionen, Metriken und Filter, die Endbenutzern der Dashboard-Oberfläche zur Verfügung stehen.
