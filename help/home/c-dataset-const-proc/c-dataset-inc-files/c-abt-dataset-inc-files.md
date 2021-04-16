---
description: Viele der internen Profile, die Sie mit Ihrer Adobe erhalten haben, sind mit eigenen Datenset-Konfigurationsdateien ausgestattet.
title: Über Datensatzaufnahme-Dateien
uuid: e04d412e-7d73-4a7d-b0b6-0c2347c6201b
exl-id: a23d3f83-4e92-4787-9f77-ee9914cb8893
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '193'
ht-degree: 4%

---

# Über Datensatzaufnahme-Dateien{#about-dataset-include-files}

Viele der internen Profile, die Sie mit Ihrer Adobe erhalten haben, sind mit eigenen Datenset-Konfigurationsdateien ausgestattet.

Da es sich bei den internen Profilen um Unterelemente des DataSet-Profils handelt, enthalten ihre Datensatzkonfigurationsdateien Profile, die zusätzliche Parameter für die Protokollverarbeitungs- oder Umwandlungsphasen der Datensatzkonstruktion enthalten. Die Datensatzkonfigurationsdateien für interne Profil und für alle von Ihnen erstellten geerbten Profil werden als &quot;Datensatzeinschließungsdateien&quot;bezeichnet.

Eine Datensatzeinschlussdatei enthält eine Untergruppe der Parameter, die in den Hauptdatenaset-Konfigurationsdateien ( [!DNL Log Processing.cfg] oder [!DNL Transformation.cfg]) für das DataSet-Profil enthalten sind. Im Datensatz sind auch Dateien enthalten, die Parameter enthalten, die mit der Protokollverarbeitung verknüpft sind. Die Dateien werden als [!DNL Log Processing Dataset Include] bezeichnet (siehe [Datensatz zur Protokollverarbeitung: Dateien einschließen](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab)), während die mit der Datenverarbeitung verknüpften Dateien [!DNL Transformation Dataset Include]-Dateien genannt werden. Siehe [Transformation DataSet Include Files](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace). Sie können mehrere Datenaset-Include-Dateien erstellen, die bei der Datensatzerstellung verwendet werden sollen. Der vollständige Datensatz umfasst alle Felder, Transformationen und erweiterten Dimensionen, die in allen Datensatzkonfigurationsdateien für das DataSet-Profil und alle geerbten Profil definiert sind.
