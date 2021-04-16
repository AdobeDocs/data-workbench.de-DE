---
description: Grundlegende Informationen, die beim Bearbeiten der Datei "Log Processing.cfg"zu beachten sind.
title: Konzepte zur Konfigurationsdatei für die Protokollverarbeitung
uuid: 2ccedf63-12d9-40e9-912a-aee030191b1e
exl-id: 278a4a10-d382-4d9f-b3f4-bcc4783eb50c
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 4%

---

# Konzepte zur Konfigurationsdatei für die Protokollverarbeitung{#considerations-for-the-log-processing-configuration-file}

Grundlegende Informationen, die beim Bearbeiten der Datei &quot;Log Processing.cfg&quot;zu beachten sind.

* Datendateien sollten nicht zwischen Ordnern verschoben werden, nachdem die Quellen für einen Datensatz definiert wurden. Die einzigen zusätzlichen Dateien, die ein Ordner erhalten sollte, sind neu erstellte Dateien, die vom Data Workbench-Server stammen, der Daten von Sensor(en) empfängt.
* Um einen der Parameter in dieser Datei zu ändern, müssen alle Daten erneut verarbeitet werden. Der Parameter &quot;Pause&quot;in der Datei [!DNL Log Processing Mode.cfg] muss auf &quot;false&quot;gesetzt werden, damit eine erneute Verarbeitung erfolgt. (Beachten Sie, dass der Standardwert dieses Parameters &quot;false&quot;ist, sodass eine Änderung des Parameters möglicherweise nicht erforderlich ist.) Weitere Informationen zur Datei [!DNL Log Processing Mode.cfg] finden Sie unter [Zusätzliche Konfigurationsdateien](../../../home/c-dataset-const-proc/c-add-config-files/c-add-config-files.md#concept-1afef4f88f1e467ab4326875fd1d3004).

* Wenn Sie die Daten erneut verarbeiten, können Sie den Parameter &quot;Fortschritt bei der Protokollverarbeitung&quot;in der Data Workbench [!DNL Processing Legend] überprüfen.

   Weitere Informationen zur erneuten Verarbeitung Ihrer Daten finden Sie unter [Wiederaufbereitung und Verarbeitung](../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md). Siehe [Verarbeitende Legende](../../../home/c-get-started/c-admin-intrf/c-pro-lgd.md#concept-233e27c9c84c426f8c178a27cc7ff828).

* Die [!DNL Log Processing.cfg]-Datei kann von mehreren DataSet-Profilen gemeinsam verwendet werden. In der Datei [!DNL Log Processing.cfg] definierte Konvertierungen werden auf alle DataSet-Profil angewendet, die diese Konfigurationsdatei gemeinsam verwenden.

   >[!NOTE]
   >
   >Adobe empfiehlt das Definieren von Konvertierungen für die Protokollverarbeitung in einer oder mehreren Protokollverarbeitungsdateien [!DNL dataset include]. Weitere Informationen finden Sie unter [Datensatz zur Protokollverarbeitung: Dateien einschließen](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab).

* Sie können einen der oben beschriebenen Parameter zur Datei [!DNL Log Processing.cfg] hinzufügen, indem Sie die Datei in Notepad öffnen und bearbeiten. Änderungen, die Sie vornehmen und speichern, werden angezeigt, wenn Sie die Datei in Data Workbench erneut öffnen. Verwenden Sie beim Hinzufügen eines neuen Parameters die Leertaste (nicht die Tabulatortaste), um zwei (2) Leerzeichen rechts neben der vorherigen Überschriftenebene einzurücken.

   Fehler, die während der Protokollverarbeitungsphase des Datensatzerstellungsprozesses für ein Dataset-Profil auftreten, werden im Knoten [!DNL Profiles] der [!DNL Detailed Status]-Schnittstelle in Data Workbench angezeigt. Informationen zur [!DNL Detailed Status]-Schnittstelle finden Sie im *Data Workbench-Benutzerhandbuch*.
