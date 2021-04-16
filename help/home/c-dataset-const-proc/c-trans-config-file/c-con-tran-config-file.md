---
description: Wichtige Informationen, die beim Bearbeiten der Datei "Transformation.cfg"zu beachten sind.
title: Konzepte zur Konfigurationsdatei für Umwandlungen
uuid: 1b64d023-966d-4f84-beb6-4f02b3504eea
exl-id: 7164ccb5-269c-4968-a3b4-1ff046a57f92
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 5%

---

# Konzepte zur Konfigurationsdatei für Umwandlungen{#considerations-for-the-transformation-configuration-file}

Wichtige Informationen, die beim Bearbeiten der Datei &quot;Transformation.cfg&quot;zu beachten sind.

* Um einen der Parameter in dieser Datei zu ändern, müssen die Daten erneut transformiert werden.
* Wenn Sie die Daten erneut verarbeiten, können Sie den Parameter [!DNL Transformation Progress] in der Datenbasis [!DNL Processing Legend] überprüfen.

   Weitere Informationen zur Neuverarbeitung Ihrer Daten bzw. des [!DNL Processing Legend,] finden Sie unter [Neuverarbeitung und Umgestaltung](../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).

* [!DNL CrossRows],  [!DNL ODBCLookup],  [!DNL Sessionize]und  [!DNL AppendURI] Konvertierungen funktionieren nur, wenn sie in einer  [!DNL Transformation Dataset Configuration] Datei definiert sind. Informationen zu diesen Transformationen finden Sie unter [Datentransformationen](../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md).

   >[!NOTE]
   >
   >Adobe empfiehlt die Definition von Transformationen für die Konvertierungsphase der Datensatzkonstruktion in einer oder mehreren [!DNL Transformation Dataset Include]-Dateien. Weitere Informationen finden Sie unter [Transformationsdataset Dateien einschließen](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace).

* Sie können einen der oben beschriebenen Parameter zur Datei [!DNL Transformation.cfg] hinzufügen, indem Sie die Datei in Notepad öffnen und bearbeiten. Änderungen, die Sie vornehmen und speichern, werden angezeigt, wenn Sie die Datei in Data Workbench erneut öffnen. Verwenden Sie beim Hinzufügen eines neuen Parameters die Leertaste (nicht die Tabulatortaste), um zwei (2) Leerzeichen rechts neben der vorherigen Überschriftenebene einzurücken.

   Sämtliche Fehler, die während der Transformationsphase des Datensatzerstellungsprozesses für ein Dataset-Profil auftreten, werden im [!DNL Profiles]-Knoten der [!DNL Detailed Status]-Schnittstelle in Data Workbench angezeigt. Informationen zur [!DNL Detailed Status]-Schnittstelle finden Sie im *Data Workbench-Benutzerhandbuch*.
