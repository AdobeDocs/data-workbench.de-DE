---
description: Schritte, die sicherstellen, dass die Wiederaufbereitung oder Umwandlung reibungslos verläuft und rechtzeitig abgeschlossen wird, damit Data Workbench-Benutzer wieder arbeiten können
title: Vorbereiten der Wiederaufbereitung oder erneuten Umwandlung
uuid: 69a5878e-707a-4100-89ba-bae0b8a16c84
exl-id: f3746edf-416e-45c2-896c-48a3c875318c
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '218'
ht-degree: 4%

---

# Vorbereiten der Wiederaufbereitung oder erneuten Umwandlung{#preparing-for-reprocessing-or-retransformation}

{{eol}}

Schritte, die sicherstellen, dass die Wiederaufbereitung oder Umwandlung reibungslos verläuft und rechtzeitig abgeschlossen wird, damit Data Workbench-Benutzer wieder arbeiten können

1. Bestimmen Sie die verstrichene Zeit der vorherigen Verarbeitung oder Transformation, indem Sie die [!DNL Processing Mode History] im [!DNL Detailed Status] -Schnittstelle.

   1. Wenn Sie in Ihrem Datensatzprofil arbeiten, öffnen Sie die [!DNL Detailed Status] -Schnittstelle.
   1. Klicken **[!UICONTROL Processing Status]** > *&lt;**[!UICONTROL dataset profile name]**>* > **[!UICONTROL Processing Mode History]** , um die verstrichenen Zeiten der vorherigen Verarbeitung oder Transformation anzuzeigen.

      * &quot;Schnelle Eingabe&quot;ist die Gesamtdauer, die für die Protokollverarbeitung erforderlich ist.
      * Die schnelle Zusammenführung ist die für die Umwandlung benötigte Gesamtdauer.
      * Die Summe der beiden Male (Schnelle Eingabe + Schnelle Zusammenführung) ist die Gesamtdauer, die für die Verarbeitung des Datensatzes erforderlich ist.

      Das folgende Beispiel zeigt, dass die Protokollverarbeitung ca. 43 Sekunden dauerte, während die Umwandlung weniger als 2 Minuten dauerte.

      ![](assets/vis_DetailedStatus_ProcessingModeHistory.png)

      Weitere Informationen zum [!DNL Detailed Status] -Benutzeroberfläche, siehe *Data Workbench-Benutzerhandbuch*.


1. Planen und planen Sie die Wiederaufbereitung. Da Benutzer von Data Workbench während der Protokollverarbeitungsphase keinen Zugriff auf die Daten haben, müssen Sie sicherstellen, dass Sie eine Neuverarbeitung planen, die zu einem geeigneten Zeitpunkt erfolgt, z. B. über das Wochenende.
1. Überwachen Sie den Fortschritt der Neuverarbeitung und Neuumwandlung mithilfe der Felder im [!DNL Processing Legend.] Weitere Informationen zum [!DNL Processing Legend], siehe *Data Workbench-Benutzerhandbuch*.
