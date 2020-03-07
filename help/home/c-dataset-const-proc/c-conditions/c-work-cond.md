---
description: Informationen zum Hinzufügen, Entfernen oder Kopieren einer Bedingung.
solution: Analytics
title: Arbeiten mit Bedingungen
topic: Data workbench
uuid: b6f52b40-26aa-429b-9ff5-3f3b9c9d57a9
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Arbeiten mit Bedingungen{#working-with-conditions}

Informationen zum Hinzufügen, Entfernen oder Kopieren einer Bedingung.

* [So fügen Sie einer Datensatzkonfigurationsdatei eine Bedingung hinzu](../../../home/c-dataset-const-proc/c-conditions/c-work-cond.md#section-3e2a34db047b462585502f69722f6511)
* [So entfernen Sie eine Bedingung aus einer DataSet-Konfigurationsdatei](../../../home/c-dataset-const-proc/c-conditions/c-work-cond.md#section-677270f93f1648c3a268ca2aea7d4540)
* [So kopieren Sie eine Bedingung](../../../home/c-dataset-const-proc/c-conditions/c-work-cond.md#section-00617bcf2c274f428686b2ec7f2d1db8)

## So fügen Sie einer Datensatzkonfigurationsdatei eine Bedingung hinzu {#section-3e2a34db047b462585502f69722f6511}

1. Verwenden Sie beim Arbeiten im DataSet-Profil den [!DNL Profile Manager] , um die zu bearbeitende Datensatzkonfigurationsdatei zu öffnen.

   * Informationen zum Öffnen der [!DNL Log Processing.cfg] Datei finden Sie unter [Bearbeiten der Konfigurationsdatei](../../../home/c-dataset-const-proc/c-log-proc-config-file/t-edit-log-proc-config-file.md#task-6a2fa1b735cb4eefad730f0a3a7858e5)für die Protokollverarbeitung.

   * Informationen zum Öffnen der [!DNL Transformation.cfg] Datei finden Sie unter [Bearbeiten der Transformationskonfigurationsdatei](../../../home/c-dataset-const-proc/c-trans-config-file/t-edit-trans-config-file.md#task-cfef4142c1bf4437a669d1fdc75cabbc).

   * Informationen zum Öffnen einer [!DNL Dataset Include] Datei finden Sie unter [DataSet Include Files](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md).

1. Suchen Sie in der Datensatzkonfigurationsdatei den Parameter &quot;Protokolleingabebedingung&quot;oder &quot;Bedingung&quot;, den Sie definieren möchten.
1. Klicken Sie mit der rechten Maustaste auf den Parameter und klicken Sie auf **[!UICONTROL Add new]**. Wählen Sie einen der folgenden Bedingungstypen:

   * [!DNL Not Empty]
   * [!DNL String Match]
   * [!DNL Regular Expression]
   * [!DNL Range]
   * [!DNL And]
   * [!DNL Or]
   * [!DNL Neither]
   * [!DNL Compare]

1. Bearbeiten Sie die Parameter der Bedingung nach Bedarf. Beschreibungen der Parameter der einzelnen Bedingungen finden Sie im entsprechenden Abschnitt dieser Anlage.
1. Um Ihre Änderungen zu speichern, klicken Sie mit der rechten Maustaste **[!UICONTROL (modified)]** oben im Fenster und klicken Sie auf **[!UICONTROL Save]**.

1. Damit die lokal vorgenommenen Änderungen wirksam werden, klicken Sie mit der [!DNL Profile Manager,] rechten Maustaste auf das Häkchen für die Datei in der [!DNL User] Spalte und klicken Sie dann auf **[!UICONTROL Save to]** > &lt;* **[!UICONTROL profile name]***>, wobei der Profilname der Name des Datensatzprofils oder das geerbte Profil ist, zu dem die Datei gehört.

   >[!NOTE]
   >
   >Speichern Sie die geänderte Konfigurationsdatei nicht in einem der von Adobe bereitgestellten internen Profile, da Ihre Änderungen bei der Installation von Updates für diese Profile überschrieben werden.

## So entfernen Sie eine Bedingung aus einer DataSet-Konfigurationsdatei {#section-677270f93f1648c3a268ca2aea7d4540}

1. Klicken Sie mit der rechten Maustaste auf den Namen der Bedingung oder die Zahl, die der zu entfernenden Bedingung entspricht.
1. Klicken Sie auf **[!UICONTROL Remove]** &lt;* **[!UICONTROL #number]***>, wobei number die Zahl ist, die der Bedingung entspricht, die Sie entfernen möchten.

## So kopieren Sie eine Bedingung {#section-00617bcf2c274f428686b2ec7f2d1db8}

Sie können eine Bedingung von einem Speicherort an einen anderen Speicherort in derselben Datei kopieren oder eine Bedingung aus einer Datensatzkonfigurationsdatei in einen anderen kopieren.

1. Klicken Sie mit der rechten Maustaste auf den Namen der Bedingung oder die Nummer, die der Bedingung entspricht, die Sie kopieren möchten, und klicken Sie dann auf **[!UICONTROL Copy]**.
1. Klicken Sie mit der rechten Maustaste auf den Namen oder die Nummer der Bedingung, unter der Sie die kopierte Bedingung platzieren möchten, und klicken Sie auf **[!UICONTROL Paste]**.

