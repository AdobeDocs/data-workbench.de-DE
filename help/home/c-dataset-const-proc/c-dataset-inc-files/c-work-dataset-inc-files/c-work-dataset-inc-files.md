---
description: Datensatzaufnahme-Dateien bieten eine flexible Möglichkeit, Ihren Datensatz zu konfigurieren.
title: Arbeiten mit Datensatzaufnahme-Dateien
uuid: 258226c4-22e5-4d9d-9044-8312709e0460
exl-id: 94044c85-030c-4912-9546-d4a34b4115e0
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 4%

---

# Arbeiten mit Datensatzaufnahme-Dateien{#working-with-dataset-include-files}

{{eol}}

Datensatzaufnahme-Dateien bieten eine flexible Möglichkeit, Ihren Datensatz zu konfigurieren.

In jeder Datei können Sie beliebig viele Felder, Umwandlungen oder Dimensionen definieren und die Include-Dateien basierend auf dem geerbten Profil, zu dem sie gehören, organisieren. Beim Konfigurieren Ihres Datensatzes haben Sie die Möglichkeit, den Datensatz mit Einschlussdateien zu bearbeiten, die mit den internen Profilen für Ihre Adobe App bereitgestellt werden, oder neue Datensatzeinschlussdateien für von Ihnen erstellte geerbte Profile zu erstellen.

Wenn Sie die Parameter einer Datensatzeinschlussdatei für ein internes Profil bearbeiten und die aktualisierte Datei in Ihrem Datensatzprofil oder in einem von Ihnen erstellten geerbten Profil speichern, überschreiben Sie in der Tat die ursprünglichen Einstellungen der Datei. Adobe empfiehlt, eine Datensatzaufnahme-Datei für ein internes Profil zu bearbeiten, wenn Sie kleinere Änderungen am Inhalt des Datensatzes vornehmen müssen, z. B. eine Bedingungsparameter- oder die Standardeinstellung eines Parameters. Siehe [Bearbeiten vorhandener Datensatzaufnahme-Dateien](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077). Wenn Sie jedoch ein neues Feld angeben möchten, das von der Protokollverarbeitung an die Transformation übergeben, mithilfe von Transformationen neue Felder aktualisieren oder erstellen oder erweiterte Dimensionen definieren soll, ist es am besten, eine neue Datensatzaufnahme-Datei zu erstellen. Siehe [Erstellen neuer Datensatzaufnahme-Dateien](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-create-new-dataset-inc-files.md#task-b29f30605c374a6ca747ac843337b06e). Sie können die Datei bearbeiten, die Sie erstellen, wann immer Sie es für richtig halten.
