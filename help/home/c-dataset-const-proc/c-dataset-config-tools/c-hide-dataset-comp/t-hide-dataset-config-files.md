---
description: Wenn Sie eine Konfigurationsdatei nicht von einem internen oder von einem anderen geerbten Profil übernehmen möchten (d. h., Sie möchten, dass die Anweisungen in der Datei bei der Erstellung des Datensatzes ignoriert werden), Sie die Datei jedoch nicht ändern möchten, können Sie eine leere (0-Byte-)Datei mit demselben Namen erstellen und die Datei in einem anderen Profil speichern.
title: Ausblenden von Datensatzkonfigurationsdateien
uuid: eb33cf54-e067-4af2-a10e-7ffe43910e4f
exl-id: 327847d1-421a-4ed1-9a5f-2491765a34bd
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '319'
ht-degree: 2%

---

# Ausblenden von Datensatzkonfigurationsdateien{#hiding-dataset-configuration-files}

{{eol}}

Wenn Sie eine Konfigurationsdatei nicht von einem internen oder von einem anderen geerbten Profil übernehmen möchten (d. h., Sie möchten, dass die Anweisungen in der Datei bei der Erstellung des Datensatzes ignoriert werden), Sie die Datei jedoch nicht ändern möchten, können Sie eine leere (0-Byte-)Datei mit demselben Namen erstellen und die Datei in einem anderen Profil speichern.

**So erstellen Sie eine Datensatzkonfigurationsdatei für Null-Byte**

1. Im [!DNL Profile Manager], öffnen Sie die erforderlichen Ordner und Unterordner, um die Datei zu finden, die Sie als Nullbyte-Datei verwenden möchten.
1. Klicken Sie mit der rechten Maustaste auf das Häkchen neben dem Dateinamen und klicken Sie auf **[!UICONTROL Make Local]**.
1. Öffnen Sie die lokale Datei in einem Texteditor wie Notepad und löschen Sie den Inhalt.
1. Speichern und schließen Sie die Datei.
1. Im [!DNL Profile Manager]speichern Sie die Zero-Byte-Datei in einem Profil rechts neben dem Profil, in dem sich die Originaldatei befindet. (Sie möchten, dass die Zero-Byte-Datei Vorrang vor der Originaldatei hat.)

   Im [!DNL Profile Manager], ein Bindestrich (-) anstelle eines Kontrollkästchens, gibt in einer Spalte die Nullbytedatei an, wie im Beispiel unten dargestellt.

   ![](assets/vis_ProfileManager_ZeroByteFile.png)

Wenn Sie Ihren Datensatz erneut verarbeiten, enthält der Datensatz nicht die Datensatzkomponenten, die die Originaldatei definiert.

>[!NOTE]
>
>Wenn Sie eine Nullbyte-Konfigurationsdatei verwenden, die eine erweiterte Dimension definiert, die in einer Visualisierung oder Metrikdefinition verwendet wird, erzeugt Data Workbench einen Fehler für diese Visualisierung bzw. Metrik.

Sie können auch Nullbyte-Dateien verwenden, um eine Metrik, Dimension oder Filter an eine andere Position im Profil zu verschieben oder Menüelemente auszublenden. Weitere Informationen finden Sie unter *Data Workbench-Benutzerhandbuch*.
