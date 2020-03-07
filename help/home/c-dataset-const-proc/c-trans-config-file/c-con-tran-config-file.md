---
description: Wichtige Informationen, die beim Bearbeiten der Datei "Transformation.cfg"zu beachten sind.
solution: Analytics
title: Überlegungen zur Konfigurationsdatei für Transformationen
topic: Data workbench
uuid: 1b64d023-966d-4f84-beb6-4f02b3504eea
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Überlegungen zur Konfigurationsdatei für Transformationen{#considerations-for-the-transformation-configuration-file}

Wichtige Informationen, die beim Bearbeiten der Datei &quot;Transformation.cfg&quot;zu beachten sind.

* Um einen der Parameter in dieser Datei zu ändern, müssen die Daten erneut transformiert werden.
* Wenn Sie die Daten erneut verarbeiten, können Sie den [!DNL Transformation Progress] Parameter in Data Workbench überprüfen [!DNL Processing Legend].

   Weitere Informationen zur erneuten Verarbeitung Ihrer Daten bzw. [!DNL Processing Legend,] finden Sie unter [Verarbeitung und Umformung](../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).

* [!DNL CrossRows], [!DNL ODBCLookup], [!DNL Sessionize]und [!DNL AppendURI] Konvertierungen funktionieren nur, wenn sie in einer [!DNL Transformation Dataset Configuration] Datei definiert sind. Informationen zu diesen Transformationen finden Sie unter [Datentransformationen](../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md).

   >[!NOTE]
   >
   >Adobe empfiehlt, Konvertierungen für die Konvertierungsphase der Dataset-Erstellung in einer oder mehreren [!DNL Transformation Dataset Include] Dateien zu definieren. Weitere Informationen finden Sie unter [Transformation DataSet Include Files](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace).

* Sie können der [!DNL Transformation.cfg] Datei einen der oben beschriebenen Parameter hinzufügen, indem Sie die Datei in Notepad öffnen und bearbeiten. Änderungen, die Sie vornehmen und speichern, werden angezeigt, wenn Sie die Datei in Data Workbench erneut öffnen. Verwenden Sie beim Hinzufügen eines neuen Parameters die Leertaste (nicht die Tabulatortaste), um zwei (2) Leerzeichen rechts neben der vorherigen Überschriftenebene einzurücken.

   Sämtliche Fehler, die während der Transformationsphase des Datensatzerstellungsprozesses für ein Datensatzprofil auftreten, werden im Knoten der [!DNL Profiles] Schnittstelle in Data Workbench angezeigt [!DNL Detailed Status] . Informationen zur [!DNL Detailed Status] Oberfläche finden Sie im *Data Workbench-Benutzerhandbuch*.

