---
description: Wenn Sie keine Konfigurationsdatei von einem internen oder anderen geerbten Profil übernehmen möchten (d. h., Sie möchten, dass die Dateianweisungen während der Datensatzerstellung ignoriert werden), Sie die Datei jedoch nicht ändern möchten, können Sie eine leere (Null-Byte-)Datei mit demselben Namen erstellen und die Datei in einem anderen Profil speichern.
title: Ausblenden von Datensatzkonfigurationsdateien
uuid: eb33cf54-e067-4af2-a10e-7ffe43910e4f
exl-id: 327847d1-421a-4ed1-9a5f-2491765a34bd
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '319'
ht-degree: 2%

---

# Ausblenden von Datensatzkonfigurationsdateien{#hiding-dataset-configuration-files}

Wenn Sie keine Konfigurationsdatei von einem internen oder anderen geerbten Profil übernehmen möchten (d. h., Sie möchten, dass die Dateianweisungen während der Datensatzerstellung ignoriert werden), Sie die Datei jedoch nicht ändern möchten, können Sie eine leere (Null-Byte-)Datei mit demselben Namen erstellen und die Datei in einem anderen Profil speichern.

**So erstellen Sie eine Datensatzkonfigurationsdatei mit einem Nullbyte-Wert**

1. Öffnen Sie unter [!DNL Profile Manager] die erforderlichen Ordner und Unterordner, um die Datei zu suchen, die Sie als 0-Byte-Datei verwenden möchten.
1. Klicken Sie mit der rechten Maustaste auf das Häkchen neben dem Namen der Datei und klicken Sie auf **[!UICONTROL Make Local]**.
1. Öffnen Sie die lokale Datei in einem Texteditor wie Notepad und löschen Sie deren Inhalt.
1. Speichern und schließen Sie die Datei.
1. Speichern Sie die Nullbyte-Datei im Ordner [!DNL Profile Manager] in einem Profil rechts neben dem Profil, in dem sich die Originaldatei befindet. (Die Nullbyte-Datei hat Vorrang vor der Originaldatei.)

   In der Spalte [!DNL Profile Manager] gibt ein Bindestrich (-) anstelle eines Häkchens die Null-Byte-Datei an, wie im Beispiel unten dargestellt.

   ![](assets/vis_ProfileManager_ZeroByteFile.png)

Wenn Sie den Datensatz neu verarbeiten, enthält der Datensatz nicht die Datensatzkomponenten, die die Originaldatei definiert.

>[!NOTE]
>
>Wenn Sie eine Konfigurationsdatei mit einem Nullbyte-Wert erstellen, die eine erweiterte Dimension definiert, die in einer Visualisierung oder Metrikdefinition verwendet wird, erzeugt Data Workbench einen Fehler für diese Visualisierung bzw. Metrik.

Sie können auch Nullbyte-Dateien verwenden, um eine Metrik, Dimension oder einen Filter an eine andere Position im Profil zu verschieben oder Menüelemente auszublenden. Weitere Informationen finden Sie im *Data Workbench Benutzerhandbuch*.
