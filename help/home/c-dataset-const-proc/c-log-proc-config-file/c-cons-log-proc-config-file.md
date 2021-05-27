---
description: Grundlegende Informationen, die bei der Bearbeitung der Datei "Log Processing.cfg"zu beachten sind.
title: Konzepte zur Konfigurationsdatei für die Protokollverarbeitung
uuid: 2ccedf63-12d9-40e9-912a-aee030191b1e
exl-id: 278a4a10-d382-4d9f-b3f4-bcc4783eb50c
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 4%

---

# Konzepte zur Konfigurationsdatei für die Protokollverarbeitung{#considerations-for-the-log-processing-configuration-file}

Grundlegende Informationen, die bei der Bearbeitung der Datei &quot;Log Processing.cfg&quot;zu beachten sind.

* Datendateien sollten nicht zwischen Ordnern verschoben werden, nachdem die Quellen für einen Datensatz definiert wurden. Die einzigen zusätzlichen Dateien, die ein Ordner empfangen sollte, sind neu erstellte Dateien, die vom Data Workbench-Server stammen, der Daten von Sensor(en) erhält.
* Um einen der Parameter in dieser Datei zu ändern, müssen alle Daten erneut verarbeitet werden. Der Parameter Pause in der Datei [!DNL Log Processing Mode.cfg] muss auf false gesetzt werden, damit eine erneute Verarbeitung erfolgt. (Beachten Sie, dass der Standardwert dieses Parameters &quot;false&quot;ist, sodass eine Änderung des Parameters möglicherweise nicht erforderlich ist.) Weitere Informationen zur Datei [!DNL Log Processing Mode.cfg] finden Sie unter [Zusätzliche Konfigurationsdateien](../../../home/c-dataset-const-proc/c-add-config-files/c-add-config-files.md#concept-1afef4f88f1e467ab4326875fd1d3004).

* Wenn Sie die Daten erneut verarbeiten, können Sie den Parameter &quot;Log Processing Progress&quot;im Parameter [!DNL Processing Legend] von Data Workbench überprüfen.

   Weitere Informationen zur erneuten Verarbeitung Ihrer Daten finden Sie unter [Wiederaufbereitung und erneute Umwandlung](../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md). Siehe [Verarbeitungslegende](../../../home/c-get-started/c-admin-intrf/c-pro-lgd.md#concept-233e27c9c84c426f8c178a27cc7ff828).

* Die Datei [!DNL Log Processing.cfg] kann von mehreren Datensatzprofilen gemeinsam genutzt werden. In der Datei [!DNL Log Processing.cfg] definierte Umwandlungen werden auf alle Datensatzprofile angewendet, die diese Konfigurationsdatei gemeinsam nutzen.

   >[!NOTE]
   >
   >Adobe empfiehlt, Transformationen für die Protokollverarbeitung in einer oder mehreren Protokollverarbeitungsdateien ([!DNL dataset include]) zu definieren. Weitere Informationen finden Sie unter [Datensatzaufnahme-Dateien für die Protokollverarbeitung](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab).

* Sie können jeden der oben beschriebenen Parameter zur Datei [!DNL Log Processing.cfg] hinzufügen, indem Sie die Datei im Notepad öffnen und bearbeiten. Alle Änderungen, die Sie vornehmen und speichern, werden beim erneuten Öffnen der Datei in Data Workbench angezeigt. Verwenden Sie beim Hinzufügen eines neuen Parameters die Leertaste (nicht die Tabulatortaste), um zwei (2) Leerzeichen rechts von der vorherigen Überschriftenebene einzufügen.

   Fehler, die während der Protokollverarbeitungsphase des Datensatzerstellungsprozesses für ein Datensatzprofil auftreten, werden im Knoten [!DNL Profiles] der [!DNL Detailed Status]-Schnittstelle in Data Workbench angezeigt. Weitere Informationen zur [!DNL Detailed Status]-Benutzeroberfläche finden Sie im *Data Workbench-Benutzerhandbuch*.
