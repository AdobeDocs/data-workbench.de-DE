---
description: Viele der internen Profile, die Sie mit Ihrer Adobe App erhalten haben, verfügen über eigene Datensatzkonfigurationsdateien.
title: Über Datensatzaufnahme-Dateien
uuid: e04d412e-7d73-4a7d-b0b6-0c2347c6201b
exl-id: a23d3f83-4e92-4787-9f77-ee9914cb8893
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '193'
ht-degree: 4%

---

# Über Datensatzaufnahme-Dateien{#about-dataset-include-files}

Viele der internen Profile, die Sie mit Ihrer Adobe App erhalten haben, verfügen über eigene Datensatzkonfigurationsdateien.

Da die internen Profile Unterprofile des Datensatzprofils sind, enthalten ihre Datensatzkonfigurationsdateien Regeln, die zusätzliche Parameter für die Protokollverarbeitungs- oder Transformationsphasen der Datensatzerstellung bereitstellen. Die Datensatzkonfigurationsdateien für interne Profile und für von Ihnen erstellte geerbte Profile werden als Datensatzaufnahme-Dateien bezeichnet.

Eine Datensatzaufnahme-Datei enthält eine Untergruppe der Parameter, die in den Hauptkonfigurationsdateien des Datensatzes ( [!DNL Log Processing.cfg] oder [!DNL Transformation.cfg]) für das Datensatzprofil enthalten sind. Datensatzaufnahme-Dateien mit Parametern, die mit der Protokollverarbeitung verknüpft sind, werden als [!DNL Log Processing Dataset Include]-Dateien bezeichnet (siehe [Datensatzaufnahme-Dateien für die Protokollverarbeitung](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab)), während Datensatzaufnahme-Dateien, die mit der Transformation verknüpft sind, als [!DNL Transformation Dataset Include]-Dateien bezeichnet werden. Siehe [Datensatzaufnahme-Dateien für Umwandlungen](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace). Sie können mehrere Datensatzaufnahme-Dateien erstellen, die im Prozess der Datensatzerstellung verwendet werden können. Der vollständige Datensatz enthält alle Felder, Umwandlungen und erweiterten Dimensionen, die in allen Datensatzkonfigurationsdateien für das Datensatzprofil und alle übernommenen Profile definiert sind.
