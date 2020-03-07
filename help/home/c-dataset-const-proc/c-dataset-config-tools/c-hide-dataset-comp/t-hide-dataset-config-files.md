---
description: Wenn Sie keine Konfigurationsdatei von einem internen oder anderen geerbten Profil übernehmen möchten (d. h., Sie möchten, dass die Anweisungen in der Datei während der Datensatzerstellung ignoriert werden), Sie die Datei jedoch nicht ändern möchten, können Sie eine leere (Null-Byte-)Datei mit demselben Namen erstellen und die Datei in einem anderen Profil speichern.
solution: Analytics
title: Ausblenden von Datenbestand-Konfigurationsdateien
topic: Data workbench
uuid: eb33cf54-e067-4af2-a10e-7ffe43910e4f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Ausblenden von Datenbestand-Konfigurationsdateien{#hiding-dataset-configuration-files}

Wenn Sie keine Konfigurationsdatei von einem internen oder anderen geerbten Profil übernehmen möchten (d. h., Sie möchten, dass die Anweisungen in der Datei während der Datensatzerstellung ignoriert werden), Sie die Datei jedoch nicht ändern möchten, können Sie eine leere (Null-Byte-)Datei mit demselben Namen erstellen und die Datei in einem anderen Profil speichern.

**So erstellen Sie eine Datensatzkonfigurationsdatei mit einem Nullbyte-Wert**

1. Öffnen Sie im [!DNL Profile Manager]Ordner die erforderlichen Ordner und Unterordner, um die Datei zu suchen, die Sie als 0-Byte-Datei verwenden möchten.
1. Klicken Sie mit der rechten Maustaste auf das Häkchen neben dem Namen der Datei und klicken Sie auf **[!UICONTROL Make Local]**.
1. Öffnen Sie die lokale Datei in einem Texteditor wie Notepad und löschen Sie deren Inhalt.
1. Speichern und schließen Sie die Datei.
1. Speichern Sie im [!DNL Profile Manager]Dialogfeld die Datei mit dem 0-Byte-Format in einem Profil rechts neben dem Profil, in dem sich die Originaldatei befindet. (Die Nullbyte-Datei hat Vorrang vor der Originaldatei.)

   Im [!DNL Profile Manager]Beispiel unten wird die 0-Byte-Datei durch einen Bindestrich (-) anstelle eines Häkchens in einer Spalte identifiziert.

   ![](assets/vis_ProfileManager_ZeroByteFile.png)

Wenn Sie den Datensatz neu verarbeiten, enthält der Datensatz nicht die Datensatzkomponenten, die die Originaldatei definiert.

>[!NOTE]
>
>Wenn Sie eine Konfigurationsdatei mit einem Nullbyte-Wert erstellen, die eine erweiterte Dimension definiert, die in einer Visualisierung oder Metrikdefinition verwendet wird, erzeugt Data Workbench einen Fehler für diese Visualisierung bzw. Metrik.

Sie können auch Nullbyte-Dateien verwenden, um eine Metrik, Dimension oder einen Filter an eine andere Position im Profil zu verschieben oder Menüelemente auszublenden. For information, see the *Data Workbench User Guide*.
