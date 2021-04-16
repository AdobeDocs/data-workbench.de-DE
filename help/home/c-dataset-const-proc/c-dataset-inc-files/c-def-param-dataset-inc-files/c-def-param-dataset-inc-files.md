---
description: Beim Konfigurieren des Datensatzes können Sie Variablen definieren, die als Parameter bezeichnet werden, um aussagekräftige Werte darzustellen.
title: Definieren von Parametern Datensatzaufnahme-Dateien
uuid: 1eb7d48c-a107-4b32-abca-55d30586813f
exl-id: 80bb77e1-a157-4e16-9519-6d0e2ce17fe1
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '493'
ht-degree: 3%

---

# Definieren von Parametern Datensatzaufnahme-Dateien{#defining-parameters-in-dataset-include-files}

Beim Konfigurieren des Datensatzes können Sie Variablen definieren, die als Parameter bezeichnet werden, um aussagekräftige Werte darzustellen.

Um einem Parameter einen Wert zuzuweisen (d. h. den Parameter zu definieren), fügen Sie den Namen und den Wert des Parameters in einer Protokollverarbeitung oder [!DNL Transformation Dataset Include]-Datei zum Parameter-Vektor hinzu. Nachdem Sie Parameter definiert haben, können Sie sie in den Konfigurationsdateien Ihres DataSet-Profils referenzieren. Das Definieren und Verweisen auf solche Parameter wird als Parameterersetzung bezeichnet. Durch die Verwendung der Parameterersetzung beim Konfigurieren des Datensatzes können Sie einen zentralen Speicherort für Ihre Parameterdefinitionen erstellen. Wenn Sie einen Parameter aktualisieren müssen, auf den mehrere Male oder in mehreren Dateien verwiesen wird, müssen Sie die Änderung nur einmal vornehmen.

>[!NOTE]
>
>In diesem Handbuch wurde der Begriff Parameter verwendet, um auf den Namen einer Einstellung in einer Konfigurationsdatei zu verweisen (z. B. &quot;Protokolleingabebedingung&quot;, &quot;Neu verarbeiten&quot;oder &quot;Konvertierungen&quot;). Wie in diesem Abschnitt verwendet, bezieht sich Parameter jedoch spezifisch auf ein Element des Parameters-Vektors in einer Datensatzeinschlussdatei und nicht auf den Namen einer Einstellung in einer Konfigurationsdatei.

Beim Definieren eines Parameters sollten Sie folgende Punkte berücksichtigen:

* Ein Parameter muss exakt einmal definiert werden. Daher können Sie nicht dieselbe Variable in mehreren Datensatzeinschlussdateien definieren.
* Jeder Parameter, den Sie definieren, ist lokal für die Protokollverarbeitung oder die Transformationsphase, aber er ist für diese Phase global über mehrere Datensatzkonfigurationsdateien hinweg. Wenn Sie beispielsweise einen Parameter in einer [!DNL Transformation Dataset Include]-Datei definieren, wird der Parameter für die gesamte Transformationsphase definiert und Sie können ihn in der [!DNL Transformation.cfg]-Datei und in allen anderen [!DNL Transformation Dataset Include]-Dateien für die geerbten Profil referenzieren. Der Parameter wird für die Protokollverarbeitung nicht definiert. Daher würden alle Verweise auf den Parameter in der Datei [!DNL Log Processing.cfg] oder einer Datei [!DNL Log Processing Dataset Include] einen Verarbeitungsfehler erzeugen.

**So definieren Sie einen Parameter**

Sie können Zeichenfolgen-, numerische und Vektorparameter in den Dateien [!DNL Log Processing] und [!DNL Transformation Include] definieren.

1. Klicken Sie im Data Workbench-Fenster für die Datei [!DNL Log Processing] oder [!DNL Transformation Dataset Include] mit der rechten Maustaste auf **[!UICONTROL Parameters]** und dann auf **[!UICONTROL Add new]** > **[!UICONTROL Parameter]**.

1. Wählen Sie **[!UICONTROL String Parameter]**, **[!UICONTROL Numeric Parameter]** oder **[!UICONTROL Vector Parameter]** und füllen Sie die Parameter &quot;Name&quot;und &quot;Wert&quot;wie in den folgenden Abschnitten beschrieben aus.

1. Klicken Sie zum Speichern der Datensatzeinschlussdatei, in der Sie den Parameter definiert haben, mit der rechten Maustaste auf **[!UICONTROL (modified)]** oben im Fenster und klicken Sie auf **[!UICONTROL Save]**.

1. Um die lokal vorgenommenen Änderungen zu übernehmen, klicken Sie in der Spalte [!DNL Profile Manager] mit der rechten Maustaste auf das Häkchen für die Datei in der Spalte [!DNL User] und klicken Sie dann auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]***, wobei Profil der Name des Datensatzes oder das geerbte Profil ist, zu dem die Datensatzdatei gehört.

>[!NOTE]
>
>Speichern Sie die geänderte Konfigurationsdatei nicht in einem der von der Adobe bereitgestellten internen Profil, da Ihre Änderungen bei der Installation von Updates auf diesen Profilen überschrieben werden.

**So referenzieren Sie einen Parameter**

* Wenn Sie einen definierten Parameter in einer anderen Datensatzkonfigurationsdatei referenzieren, müssen Sie dessen Namen als [!DNL $(parameter name)] eingeben.

Die folgenden Abschnitte beschreiben die Parametertypen, die Sie definieren können.

* [Zeichenfolgen- und numerische Parameter](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-string-num-param.md#concept-14f391ce107c4a3dad827ec7967f1080)
* [Vektorparameter](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-vector-param.md#concept-adb42a5474e245a9996d0aa8d5d522d0)
