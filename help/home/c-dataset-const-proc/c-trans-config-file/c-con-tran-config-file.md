---
description: Wichtige Informationen, die beim Bearbeiten der Datei "Transformation.cfg"zu beachten sind.
title: Konzepte zur Konfigurationsdatei für Umwandlungen
uuid: 1b64d023-966d-4f84-beb6-4f02b3504eea
exl-id: 7164ccb5-269c-4968-a3b4-1ff046a57f92
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 5%

---

# Konzepte zur Konfigurationsdatei für Umwandlungen{#considerations-for-the-transformation-configuration-file}

Wichtige Informationen, die beim Bearbeiten der Datei &quot;Transformation.cfg&quot;zu beachten sind.

* Das Ändern der Parameter in dieser Datei erfordert eine Neuumwandlung der Daten.
* Wenn Sie die Daten erneut verarbeiten, können Sie den Parameter [!DNL Transformation Progress] im Parameter [!DNL Processing Legend] von Data Workbench überprüfen.

   Weitere Informationen zur Neuverarbeitung Ihrer Daten oder zum [!DNL Processing Legend,] finden Sie unter [Wiederaufbereitung und erneute Umwandlung](../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).

* [!DNL CrossRows],  [!DNL ODBCLookup],  [!DNL Sessionize] und  [!DNL AppendURI] Transformationen funktionieren nur, wenn sie in einer  [!DNL Transformation Dataset Configuration] Datei definiert sind. Weitere Informationen zu diesen Umwandlungen finden Sie unter [Datenumwandlungen](../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md).

   >[!NOTE]
   >
   >Adobe empfiehlt, Transformationen für die Umwandlungsphase der Datensatzerstellung in einer oder mehreren [!DNL Transformation Dataset Include] -Dateien zu definieren. Weitere Informationen finden Sie unter [Datensatzaufnahme-Dateien für Umwandlungen](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace).

* Sie können jeden der oben beschriebenen Parameter zur Datei [!DNL Transformation.cfg] hinzufügen, indem Sie die Datei im Notepad öffnen und bearbeiten. Alle Änderungen, die Sie vornehmen und speichern, werden beim erneuten Öffnen der Datei in Data Workbench angezeigt. Verwenden Sie beim Hinzufügen eines neuen Parameters die Leertaste (nicht die Tabulatortaste), um zwei (2) Leerzeichen rechts von der vorherigen Überschriftenebene einzufügen.

   Fehler, die während der Umwandlungsphase des Datensatzerstellungsprozesses für ein Datensatzprofil auftreten, werden im Knoten [!DNL Profiles] der [!DNL Detailed Status]-Schnittstelle in Data Workbench angezeigt. Weitere Informationen zur [!DNL Detailed Status]-Benutzeroberfläche finden Sie im *Data Workbench-Benutzerhandbuch*.
