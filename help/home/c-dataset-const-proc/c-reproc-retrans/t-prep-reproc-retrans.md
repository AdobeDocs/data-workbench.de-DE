---
description: Schritte, um sicherzustellen, dass die Wiederaufarbeitung oder Umwandlung reibungslos verläuft und rechtzeitig abgeschlossen wird, damit Benutzer von Data Workbench wieder arbeiten können
solution: Analytics
title: Vorbereiten der Wiederaufbereitung oder Umformung
topic: Data workbench
uuid: 69a5878e-707a-4100-89ba-bae0b8a16c84
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Vorbereiten der Wiederaufbereitung oder Umformung{#preparing-for-reprocessing-or-retransformation}

Schritte, um sicherzustellen, dass die Wiederaufarbeitung oder Umwandlung reibungslos verläuft und rechtzeitig abgeschlossen wird, damit Benutzer von Data Workbench wieder arbeiten können

1. Stellen Sie die verstrichene Zeit der vorherigen Verarbeitung oder Transformation fest, indem Sie die Daten des Datensatzprofils [!DNL Processing Mode History] in der [!DNL Detailed Status] Oberfläche überprüfen.

   1. Öffnen Sie bei der Arbeit mit Ihrem DataSet-Profil die [!DNL Detailed Status] Oberfläche.
   1. Klicken Sie auf **[!UICONTROL Processing Status]** > *&lt;**[!UICONTROL dataset profile name]**>* > **[!UICONTROL Processing Mode History]** , um die abgelaufenen Zeiten der vorherigen Verarbeitung oder Transformation anzuzeigen.

      * Die schnelle Eingabe ist die für die Protokollverarbeitung benötigte Gesamtzeit.
      * &quot;Schnelle Zusammenführung&quot;ist die gesamte für die Transformation benötigte Zeit.
      * Die Summe der beiden Male (Schnelle Eingabe + Schnelle Zusammenführung) ist die Gesamtdauer, die für die Verarbeitung des Datensatzes benötigt wird.
      Das folgende Beispiel zeigt, dass die Protokollverarbeitung etwa 43 Sekunden dauerte, während die Konvertierung weniger als 2 Minuten dauerte.

      ![](assets/vis_DetailedStatus_ProcessingModeHistory.png)

      Weitere Informationen zur [!DNL Detailed Status] Oberfläche finden Sie im *Data Workbench-Benutzerhandbuch*.


1. Planen und planen Sie die Wiederaufbereitung. Da Data Workbench-Benutzer während der Protokollverarbeitungszeit keinen Zugriff auf die Daten haben, stellen Sie sicher, dass Sie die Wiederaufbereitung für eine angemessene Zeit planen, z. B. über das Wochenende.
1. Überwachen Sie den Fortschritt der Wiederaufarbeitung und Umgestaltung mithilfe der Felder im [!DNL Processing Legend.] Weitere Informationen zum [!DNL Processing Legend]Thema finden Sie im *Data Workbench-Benutzerhandbuch*.
