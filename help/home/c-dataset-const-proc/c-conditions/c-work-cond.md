---
description: Informationen zum Hinzufügen, Entfernen oder Kopieren einer Bedingung.
title: Arbeiten mit Bedingungen
uuid: b6f52b40-26aa-429b-9ff5-3f3b9c9d57a9
exl-id: 0792b308-aa0b-4741-be0c-4f7cc28f3e09
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 1%

---

# Arbeiten mit Bedingungen{#working-with-conditions}

{{eol}}

Informationen zum Hinzufügen, Entfernen oder Kopieren einer Bedingung.

* [So fügen Sie einer Datensatzkonfigurationsdatei eine Bedingung hinzu](../../../home/c-dataset-const-proc/c-conditions/c-work-cond.md#section-3e2a34db047b462585502f69722f6511)
* [So entfernen Sie eine Bedingung aus einer Datensatzkonfigurationsdatei](../../../home/c-dataset-const-proc/c-conditions/c-work-cond.md#section-677270f93f1648c3a268ca2aea7d4540)
* [So kopieren Sie eine Bedingung](../../../home/c-dataset-const-proc/c-conditions/c-work-cond.md#section-00617bcf2c274f428686b2ec7f2d1db8)

## So fügen Sie einer Datensatzkonfigurationsdatei eine Bedingung hinzu {#section-3e2a34db047b462585502f69722f6511}

1. Verwenden Sie bei der Arbeit mit Ihrem Datensatzprofil den [!DNL Profile Manager] , um die Datensatzkonfigurationsdatei zu öffnen, die Sie bearbeiten möchten.

   * So öffnen Sie die [!DNL Log Processing.cfg] -Datei, siehe [Bearbeiten der Konfigurationsdatei für die Protokollverarbeitung](../../../home/c-dataset-const-proc/c-log-proc-config-file/t-edit-log-proc-config-file.md#task-6a2fa1b735cb4eefad730f0a3a7858e5).

   * So öffnen Sie die [!DNL Transformation.cfg] -Datei, siehe [Bearbeiten der Konfigurationsdatei für Umwandlungen](../../../home/c-dataset-const-proc/c-trans-config-file/t-edit-trans-config-file.md#task-cfef4142c1bf4437a669d1fdc75cabbc).

   * So öffnen Sie eine [!DNL Dataset Include] -Datei, siehe [Datensatzaufnahme-Dateien](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md).

1. Suchen Sie in der Datensatzkonfigurationsdatei den Parameter Protokolleintragsbedingung oder -bedingung , den Sie definieren möchten.
1. Klicken Sie mit der rechten Maustaste auf den Parameter und klicken Sie auf **[!UICONTROL Add new]**. Wählen Sie einen der folgenden Bedingungstypen aus:

   * [!DNL Not Empty]
   * [!DNL String Match]
   * [!DNL Regular Expression]
   * [!DNL Range]
   * [!DNL And]
   * [!DNL Or]
   * [!DNL Neither]
   * [!DNL Compare]

1. Bearbeiten Sie die Parameter der Bedingung nach Bedarf. Beschreibungen der Parameter jeder Bedingung finden Sie im entsprechenden Abschnitt dieses Anhangs.
1. Um Ihre Änderungen zu speichern, klicken Sie mit der rechten Maustaste auf **[!UICONTROL (modified)]** Klicken Sie oben im Fenster auf **[!UICONTROL Save]**.

1. Damit die lokal vorgenommenen Änderungen wirksam werden, finden Sie im [!DNL Profile Manager,] Klicken Sie mit der rechten Maustaste auf das Häkchen für die Datei im [!DNL User] und klicken Sie auf **[!UICONTROL Save to]** > &lt;* **[!UICONTROL profile name]***>, wobei der Profilname der Name des Datensatzprofils oder des geerbten Profils ist, zu dem die Datei gehört.

   >[!NOTE]
   >
   >Speichern Sie die geänderte Konfigurationsdatei nicht in einem der von Adobe bereitgestellten internen Profile, da Ihre Änderungen bei der Installation von Updates für diese Profile überschrieben werden.

## So entfernen Sie eine Bedingung aus einer Datensatzkonfigurationsdatei {#section-677270f93f1648c3a268ca2aea7d4540}

1. Klicken Sie mit der rechten Maustaste auf den Namen der Bedingung oder die Nummer, die der zu entfernenden Bedingung entspricht.
1. Klicken **[!UICONTROL Remove]** &lt;* **[!UICONTROL #number]***>, wobei number die Zahl ist, die der Bedingung entspricht, die Sie entfernen möchten.

## So kopieren Sie eine Bedingung {#section-00617bcf2c274f428686b2ec7f2d1db8}

Sie können eine Bedingung von einem Speicherort an einen anderen Speicherort in derselben Datei kopieren oder eine Bedingung aus einer Datensatzkonfigurationsdatei in einen anderen kopieren.

1. Klicken Sie mit der rechten Maustaste auf den Namen der Bedingung oder die Nummer, die der zu kopierenden Bedingung entspricht, und klicken Sie auf **[!UICONTROL Copy]**.
1. Klicken Sie mit der rechten Maustaste auf den Namen oder die Nummer der Bedingung, unter der Sie die kopierte Bedingung platzieren möchten, und klicken Sie auf **[!UICONTROL Paste]**.
