---
description: Bei der Konfiguration Ihres Datensatzes können Sie Variablen definieren, die als Parameter bezeichnet werden und aussagekräftige Werte darstellen.
title: Definieren von Parametern Datensatzaufnahme-Dateien
uuid: 1eb7d48c-a107-4b32-abca-55d30586813f
exl-id: 80bb77e1-a157-4e16-9519-6d0e2ce17fe1
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '493'
ht-degree: 3%

---

# Definieren von Parametern Datensatzaufnahme-Dateien{#defining-parameters-in-dataset-include-files}

Bei der Konfiguration Ihres Datensatzes können Sie Variablen definieren, die als Parameter bezeichnet werden und aussagekräftige Werte darstellen.

Um einem Parameter einen Wert zuzuweisen (d. h. den Parameter zu definieren), fügen Sie den Namen und Wert des Parameters in einer Protokollverarbeitung oder [!DNL Transformation Dataset Include]-Datei zum Parameter-Vektor hinzu. Nachdem Sie Parameter definiert haben, können Sie diese in den Konfigurationsdateien Ihres Datensatzprofils referenzieren. Die Definition und Referenzierung solcher Parameter wird als Parameterersetzung bezeichnet. Durch die Verwendung der Parameterersetzung bei der Konfiguration Ihres Datensatzes können Sie einen zentralen Speicherort für Ihre Parameterdefinitionen erstellen. Wenn Sie einen Parameter aktualisieren müssen, der mehrmals oder in mehreren Dateien referenziert wird, müssen Sie die Änderung nur einmal vornehmen.

>[!NOTE]
>
>In diesem Handbuch wurde der Begriffsparameter verwendet, um auf den Namen einer Einstellung in einer Konfigurationsdatei zu verweisen (z. B. Protokolleintragsbedingung, Neuverarbeitung oder Umwandlungen). Wie in diesem Abschnitt verwendet, bezieht sich der Parameter jedoch spezifisch auf ein Mitglied des Parameter-Vektors in einer Datensatzaufnahme-Datei und nicht auf den Namen einer Einstellung in einer Konfigurationsdatei.

Beachten Sie beim Definieren eines Parameters die folgenden Punkte:

* Ein Parameter muss genau einmal definiert werden. Daher können Sie nicht dieselbe Variable in mehreren Datensatzaufnahme-Dateien definieren.
* Jeder Parameter, den Sie definieren, ist lokal für die Protokollverarbeitungs- oder Transformationsphase, aber global für mehrere Datensatzkonfigurationsdateien für diese Phase. Wenn Sie beispielsweise einen Parameter in einer [!DNL Transformation Dataset Include]-Datei definieren, wird der Parameter für die gesamte Transformationsphase definiert und Sie können ihn in der [!DNL Transformation.cfg]-Datei und in allen anderen [!DNL Transformation Dataset Include]-Dateien für die geerbten Profile referenzieren. Der Parameter wurde nicht für die Protokollverarbeitung definiert. Daher würde jeder Verweis auf den Parameter in der Datei [!DNL Log Processing.cfg] oder einer Datei [!DNL Log Processing Dataset Include] einen Verarbeitungsfehler verursachen.

**So definieren Sie einen Parameter**

Sie können Zeichenfolgen-, numerische und Vektorparameter in den Dateien [!DNL Log Processing] und [!DNL Transformation Include] definieren.

1. Klicken Sie im Data Workbench-Fenster für die Datei [!DNL Log Processing] oder [!DNL Transformation Dataset Include] mit der rechten Maustaste auf **[!UICONTROL Parameters]** und klicken Sie dann auf **[!UICONTROL Add new]** > **[!UICONTROL Parameter]**.

1. Wählen Sie **[!UICONTROL String Parameter]**, **[!UICONTROL Numeric Parameter]** oder **[!UICONTROL Vector Parameter]** aus und füllen Sie die Parameter Name und Wert wie in den folgenden Abschnitten beschrieben aus.

1. Um die Datensatzaufnahme-Datei zu speichern, in der Sie den Parameter definiert haben, klicken Sie mit der rechten Maustaste auf **[!UICONTROL (modified)]** oben im Fenster und klicken Sie auf **[!UICONTROL Save]**.

1. Damit die lokal vorgenommenen Änderungen wirksam werden, klicken Sie in der Spalte [!DNL Profile Manager] mit der rechten Maustaste auf das Häkchen für die Datei in der Spalte [!DNL User] und klicken Sie dann auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]***, wobei der Profilname der Name des Datensatzprofils oder das geerbte Profil ist, zu dem die Datensatzaufnahme gehört.

>[!NOTE]
>
>Speichern Sie die geänderte Konfigurationsdatei nicht in einem der von Adobe bereitgestellten internen Profile, da Ihre Änderungen bei der Installation von Updates für diese Profile überschrieben werden.

**So verweisen Sie auf einen Parameter**

* Wenn Sie einen definierten Parameter in einer anderen Datensatzkonfigurationsdatei referenzieren, müssen Sie dessen Namen als [!DNL $(parameter name)] eingeben.

In den folgenden Abschnitten werden die Parametertypen beschrieben, die Sie definieren können.

* [Zeichenfolgen- und numerische Parameter](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-string-num-param.md#concept-14f391ce107c4a3dad827ec7967f1080)
* [Vektorparameter](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-vector-param.md#concept-adb42a5474e245a9996d0aa8d5d522d0)
