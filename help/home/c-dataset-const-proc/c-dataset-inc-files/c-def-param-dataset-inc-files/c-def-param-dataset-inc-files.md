---
description: Beim Konfigurieren des Datensatzes können Sie Variablen definieren, die als Parameter bezeichnet werden, um aussagekräftige Werte darzustellen.
solution: Analytics
title: Definieren von Parametern in DataSet Include-Dateien
topic: Data workbench
uuid: 1eb7d48c-a107-4b32-abca-55d30586813f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Definieren von Parametern in DataSet Include-Dateien{#defining-parameters-in-dataset-include-files}

Beim Konfigurieren des Datensatzes können Sie Variablen definieren, die als Parameter bezeichnet werden, um aussagekräftige Werte darzustellen.

Um einem Parameter einen Wert zuzuweisen (d. h. den Parameter zu definieren), fügen Sie dem Parameter-Vektor den Namen und den Wert des Parameters in einer Protokollverarbeitung oder [!DNL Transformation Dataset Include] -datei hinzu. Nachdem Sie Parameter definiert haben, können Sie sie in den Konfigurationsdateien Ihres Datensatzprofils referenzieren. Das Definieren und Verweisen auf solche Parameter wird als Parameterersetzung bezeichnet. Durch die Verwendung der Parameterersetzung beim Konfigurieren des Datensatzes können Sie einen zentralen Speicherort für Ihre Parameterdefinitionen erstellen. Wenn Sie einen Parameter aktualisieren müssen, auf den mehrere Male oder in mehreren Dateien verwiesen wird, müssen Sie die Änderung nur einmal vornehmen.

>[!NOTE]
>
>In diesem Handbuch wurde der Begriff Parameter verwendet, um auf den Namen einer Einstellung in einer Konfigurationsdatei zu verweisen (z. B. &quot;Protokolleingabebedingung&quot;, &quot;Neu verarbeiten&quot;oder &quot;Konvertierungen&quot;). Wie in diesem Abschnitt verwendet, bezieht sich Parameter jedoch spezifisch auf ein Element des Parameters-Vektors in einer Datensatzeinschlussdatei und nicht auf den Namen einer Einstellung in einer Konfigurationsdatei.

Beim Definieren eines Parameters sollten Sie folgende Punkte berücksichtigen:

* Ein Parameter muss exakt einmal definiert werden. Daher können Sie nicht dieselbe Variable in mehreren Datensatzeinschlussdateien definieren.
* Jeder Parameter, den Sie definieren, ist lokal für die Protokollverarbeitung oder die Transformationsphase, aber er ist für diese Phase global über mehrere Datensatzkonfigurationsdateien hinweg. Wenn Sie beispielsweise einen Parameter in einer [!DNL Transformation Dataset Include] Datei definieren, wird der Parameter für die gesamte Konvertierungsphase definiert und Sie können ihn in der [!DNL Transformation.cfg] Datei und in allen anderen [!DNL Transformation Dataset Include] Dateien für die geerbten Profile referenzieren. Der Parameter wird für die Protokollverarbeitung nicht definiert. Daher würde jeder Verweis auf den Parameter in der [!DNL Log Processing.cfg] Datei oder einer [!DNL Log Processing Dataset Include] Datei einen Verarbeitungsfehler erzeugen.

**So definieren Sie einen Parameter**

Sie können Zeichenfolgen-, numerische und Vektorparameter in [!DNL Log Processing] und [!DNL Transformation Include] Dateien definieren.

1. Klicken Sie im Data Workbench-Fenster für die [!DNL Log Processing] Datei oder [!DNL Transformation Dataset Include] -Datei mit der rechten Maustaste **[!UICONTROL Parameters]** und klicken Sie dann auf **[!UICONTROL Add new]** > **[!UICONTROL Parameter]**.

1. Wählen Sie **[!UICONTROL String Parameter]** die Parameter Name und Wert aus, **[!UICONTROL Numeric Parameter]** oder **[!UICONTROL Vector Parameter]** füllen Sie sie aus, wie in den folgenden Abschnitten beschrieben.

1. Um die Datensatzeinschlussdatei zu speichern, in der Sie den Parameter definiert haben, klicken Sie mit der rechten Maustaste **[!UICONTROL (modified)]** oben im Fenster und klicken Sie auf **[!UICONTROL Save]**.

1. Um die lokal vorgenommenen Änderungen in Kraft zu setzen, klicken Sie mit der [!DNL Profile Manager]rechten Maustaste auf das Häkchen für die Datei in der [!DNL User] Spalte und klicken Sie dann auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*, wobei der Profilname der Name des Datensatzprofils oder das geerbte Profil ist, zu dem die Datensatzdatei gehört.

>[!NOTE]
>
>Speichern Sie die geänderte Konfigurationsdatei nicht in einem der von Adobe bereitgestellten internen Profile, da Ihre Änderungen bei der Installation von Updates für diese Profile überschrieben werden.

**So referenzieren Sie einen Parameter**

* Wenn Sie auf einen definierten Parameter in einer anderen Datensatzkonfigurationsdatei verweisen, müssen Sie dessen Namen wie [!DNL $(parameter name)].

Die folgenden Abschnitte beschreiben die Parametertypen, die Sie definieren können.

* [String und numerische Parameter](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-string-num-param.md#concept-14f391ce107c4a3dad827ec7967f1080)
* [Vektorparameter](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-vector-param.md#concept-adb42a5474e245a9996d0aa8d5d522d0)

