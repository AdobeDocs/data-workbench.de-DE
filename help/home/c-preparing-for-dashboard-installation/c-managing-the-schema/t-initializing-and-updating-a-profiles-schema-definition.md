---
description: Initialisieren und Aktualisieren der Schemadefinition eines Profils
title: Initialisieren und Aktualisieren der Schemadefinition eines Profils
uuid: 38e47ded-340e-4f65-b06c-f2e2254f0863
exl-id: e8190909-4416-4d4a-8901-130d01906773
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '269'
ht-degree: 7%

---

# Initialisieren und Aktualisieren der Schemadefinition eines Profils{#initializing-and-updating-a-profile-s-schema-definition}

1. Öffnen Sie das **[!UICONTROL Schema Builder]** für das Profil, das Sie einrichten möchten.
1. Eine **[!UICONTROL Loading]**-Meldung wird angezeigt, während das Schema aus dem Insight-Profil abgerufen wird. Die Ladezeit des Schemas hängt von der Komplexität des geladenen Profils ab.
1. Nach Abschluss des Vorgangs wird eine Zusammenfassung der Unterschiede zwischen dem **[!UICONTROL Insight Schema]** im linken Bereich und dem **[!UICONTROL Dashboard Schema]** im rechten Bereich angezeigt. Diese Zusammenfassung wird im linken unteren Teil des Fensters **[!UICONTROL Schema Builder]** angezeigt.

   >[!NOTE]
   >
   >Beim erstmaligen Einrichten des Schemas werden die einzelnen Metriken, Dimensionen und Filter anders aufgelistet als das Schema des Dashboards. Das liegt daran, dass die Dashboard-Schema-Objekte derzeit nicht vorhanden sind.

   ![](assets/schema_builder2.png)

1. Klicken Sie auf die Schaltfläche **[!UICONTROL Synchronize with Schema]**, um alle Metriken, Dimensionen und Filter aus der Insight Schema-Ansicht mit der Dashboard-Schema-Ansicht zu synchronisieren.
1. Nach Abschluss des Vorgangs sollte eine Meldung angezeigt werden, dass keine Unterschiede gefunden wurden:

   ![](assets/diff_found.png)

1. Wenn beim Dashboard-Schema Fehler auftreten, z. B. Duplikat-Metriken und -Dimensionen, müssen Sie diese vor dem Speichern manuell korrigieren.

   >[!NOTE]
   >
   >Sie können alle Metriken, Dimensionen oder Filter selektiv aus dem **[!UICONTROL Dashboard Schema]** entfernen, das bzw. die nicht für Endbenutzer des Dashboards angezeigt werden sollen. Sie erhalten eine Warnung, dass keine Elemente im Dashboard-Schema vorhanden sind. Das Speichern wird jedoch nicht verhindert.

1. Wenn Sie bereit sind, klicken Sie auf **[!UICONTROL Save]**, um die Änderungen im Schema des Dashboards zu speichern.
1. Das Dashboard-System verwendet diese Schema-Definition, um die Dimensionen, Metriken und Filter zu füllen, die Endbenutzern der Dashboard-Oberfläche zur Verfügung stehen.
