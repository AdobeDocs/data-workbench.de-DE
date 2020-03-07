---
description: Grundlegende Informationen, die beim Bearbeiten der Datei "Log Processing.cfg"zu beachten sind.
solution: Analytics
title: Überlegungen zur Konfigurationsdatei für die Protokollverarbeitung
topic: Data workbench
uuid: 2ccedf63-12d9-40e9-912a-aee030191b1e
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Überlegungen zur Konfigurationsdatei für die Protokollverarbeitung{#considerations-for-the-log-processing-configuration-file}

Grundlegende Informationen, die beim Bearbeiten der Datei &quot;Log Processing.cfg&quot;zu beachten sind.

* Datendateien sollten nicht zwischen Ordnern verschoben werden, nachdem die Quellen für einen Datensatz definiert wurden. Die einzigen zusätzlichen Dateien, die ein Ordner erhalten sollte, sind neu erstellte Dateien, die vom Data Workbench-Server stammen, der Daten von Sensor(en) empfängt.
* Um einen der Parameter in dieser Datei zu ändern, müssen alle Daten erneut verarbeitet werden. Der Parameter &quot;Pause&quot;in der [!DNL Log Processing Mode.cfg] Datei muss auf &quot;false&quot;gesetzt werden, damit eine erneute Verarbeitung erfolgt. (Beachten Sie, dass der Standardwert dieses Parameters &quot;false&quot;ist, sodass eine Änderung des Parameters möglicherweise nicht erforderlich ist.) Weitere Informationen zur [!DNL Log Processing Mode.cfg] Datei finden Sie unter [Zusätzliche Konfigurationsdateien](../../../home/c-dataset-const-proc/c-add-config-files/c-add-config-files.md#concept-1afef4f88f1e467ab4326875fd1d3004).

* Wenn Sie die Daten erneut verarbeiten, können Sie den Parameter &quot;Fortschritt bei der Protokollverarbeitung&quot;in Data Workbench überprüfen [!DNL Processing Legend].

   Weitere Informationen zur erneuten Verarbeitung Ihrer Daten finden Sie unter [Verarbeitung und Verarbeitung](../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md). Siehe [Legende](../../../home/c-get-started/c-admin-intrf/c-pro-lgd.md#concept-233e27c9c84c426f8c178a27cc7ff828)für die Verarbeitung.

* Die [!DNL Log Processing.cfg] Datei kann von mehreren Datensatzprofilen gemeinsam verwendet werden. Die in der [!DNL Log Processing.cfg] Datei definierten Konvertierungen werden auf alle Datensatzprofile angewendet, die diese Konfigurationsdatei gemeinsam verwenden.

   >[!NOTE]
   >
   >Adobe empfiehlt, Konvertierungen für die Protokollverarbeitung in einer oder mehreren [!DNL dataset include] Protokollverarbeitungsdateien zu definieren. Weitere Informationen finden Sie unter [Protokollverarbeitungsdataset Dateien](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab)einschließen.

* Sie können der [!DNL Log Processing.cfg] Datei einen der oben beschriebenen Parameter hinzufügen, indem Sie die Datei in Notepad öffnen und bearbeiten. Änderungen, die Sie vornehmen und speichern, werden angezeigt, wenn Sie die Datei in Data Workbench erneut öffnen. Wenn Sie einen neuen Parameter hinzufügen, verwenden Sie die Leertaste (nicht die Tabulatortaste), um zwei (2) Leerzeichen rechts neben der vorherigen Überschriftenebene einzurücken.

   Sämtliche Fehler, die während der Phase der Protokollverarbeitung des Datensatzerstellungsprozesses für ein Datensatzprofil auftreten, werden im Knoten der [!DNL Profiles] Schnittstelle in Data Workbench angezeigt [!DNL Detailed Status] . Informationen zur [!DNL Detailed Status] Oberfläche finden Sie im *Data Workbench-Benutzerhandbuch*.

