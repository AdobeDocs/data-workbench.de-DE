---
description: Wichtige Informationen, die beim Bearbeiten der Datei "Transformation.cfg"zu beachten sind.
title: Konzepte zur Konfigurationsdatei für Umwandlungen
uuid: 1b64d023-966d-4f84-beb6-4f02b3504eea
exl-id: 7164ccb5-269c-4968-a3b4-1ff046a57f92
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 5%

---

# Konzepte zur Konfigurationsdatei für Umwandlungen{#considerations-for-the-transformation-configuration-file}

{{eol}}

Wichtige Informationen, die beim Bearbeiten der Datei &quot;Transformation.cfg&quot;zu beachten sind.

* Das Ändern der Parameter in dieser Datei erfordert eine Neuumwandlung der Daten.
* Wenn Sie die Daten erneut verarbeiten, können Sie die [!DNL Transformation Progress] Parameter in der Data Workbench [!DNL Processing Legend].

   Informationen zur erneuten Verarbeitung Ihrer Daten oder [!DNL Processing Legend,] see [Wiederaufbereitung und erneute Umwandlung](../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).

* [!DNL CrossRows], [!DNL ODBCLookup], [!DNL Sessionize]und [!DNL AppendURI] Transformationen funktionieren nur, wenn sie in einer [!DNL Transformation Dataset Configuration] -Datei. Weitere Informationen zu diesen Umwandlungen finden Sie unter [Datenumwandlungen](../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md).

   >[!NOTE]
   >
   >Adobe empfiehlt die Definition von Transformationen für die Umwandlungsphase der Datensatzerstellung in einer oder mehreren [!DNL Transformation Dataset Include] Dateien. Weitere Informationen finden Sie unter [Datensatzaufnahme-Dateien zur Transformation](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace).

* Sie können jeden der oben beschriebenen Parameter zum [!DNL Transformation.cfg] Datei, indem Sie die Datei im Editor öffnen und bearbeiten. Alle Änderungen, die Sie vornehmen und speichern, werden beim erneuten Öffnen der Datei in Data Workbench angezeigt. Verwenden Sie beim Hinzufügen eines neuen Parameters die Leertaste (nicht die Tabulatortaste), um zwei (2) Leerzeichen rechts von der vorherigen Überschriftenebene einzufügen.

   Fehler, die während der Umwandlungsphase des Datensatzerstellungsprozesses für ein Datensatzprofil auftreten, werden im Abschnitt [!DNL Profiles] Knoten der [!DNL Detailed Status] -Schnittstelle in Data Workbench. Informationen zum [!DNL Detailed Status] -Benutzeroberfläche, siehe *Data Workbench-Benutzerhandbuch*.
