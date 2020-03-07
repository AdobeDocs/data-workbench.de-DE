---
description: Viele der internen Profile, die Sie mit Ihrer Adobe-Anwendung erhalten haben, verfügen über eigene Datensatzkonfigurationsdateien.
solution: Analytics
title: Info zu Datenaset einschließlich Dateien
topic: Data workbench
uuid: e04d412e-7d73-4a7d-b0b6-0c2347c6201b
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Info zu Datenaset einschließlich Dateien{#about-dataset-include-files}

Viele der internen Profile, die Sie mit Ihrer Adobe-Anwendung erhalten haben, verfügen über eigene Datensatzkonfigurationsdateien.

Da die internen Profile Unterprofile des Datensatzprofils sind, enthalten ihre Datensatzkonfigurationsdateien Regeln, die zusätzliche Parameter für die Protokollverarbeitungs- oder Transformationsphasen der Datensatzkonstruktion bereitstellen. Die Konfigurationsdateien des Datensatzes für interne Profile und für alle von Ihnen erstellten geerbten Profile werden als &quot;Datensatz enthält Dateien&quot; bezeichnet.

Eine Datensatzeinschluss-Datei enthält eine Untergruppe der Parameter, die in den Hauptdatenaset-Konfigurationsdateien ( [!DNL Log Processing.cfg] oder [!DNL Transformation.cfg]) für das Datensatzprofil enthalten sind. Im Datensatz sind Dateien enthalten, die Parameter enthalten, die mit der Protokollverarbeitung verknüpft sind, so genannte [!DNL Log Processing Dataset Include] Dateien (siehe [Protokollverarbeitungsdataset einschließlich Dateien](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab)), während im Datensatz Dateien enthalten sind, die mit der Transformation verknüpft sind, als [!DNL Transformation Dataset Include] Dateien bezeichnet werden. Siehe [Transformation DataSet Include-Dateien](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace). Sie können mehrere Datenaset-Include-Dateien erstellen, die bei der Datensatzerstellung verwendet werden sollen. Der vollständige Datensatz enthält alle Felder, Transformationen und erweiterten Dimensionen, die in allen Datensatzkonfigurationsdateien für das Datenaset-Profil und alle geerbten Profile definiert sind.
