---
description: Informationen zum Hinzufügen, Entfernen oder Kopieren einer Bedingung.
title: Arbeiten mit Bedingungen
uuid: b6f52b40-26aa-429b-9ff5-3f3b9c9d57a9
exl-id: 0792b308-aa0b-4741-be0c-4f7cc28f3e09
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 1%

---

# Arbeiten mit Bedingungen{#working-with-conditions}

Informationen zum Hinzufügen, Entfernen oder Kopieren einer Bedingung.

* [So fügen Sie einer Datensatzkonfigurationsdatei eine Bedingung hinzu](../../../home/c-dataset-const-proc/c-conditions/c-work-cond.md#section-3e2a34db047b462585502f69722f6511)
* [So entfernen Sie eine Bedingung aus einer Datensatzkonfigurationsdatei](../../../home/c-dataset-const-proc/c-conditions/c-work-cond.md#section-677270f93f1648c3a268ca2aea7d4540)
* [So kopieren Sie eine Bedingung](../../../home/c-dataset-const-proc/c-conditions/c-work-cond.md#section-00617bcf2c274f428686b2ec7f2d1db8)

## Hinzufügen einer Bedingung zu einer Datensatzkonfigurationsdatei {#section-3e2a34db047b462585502f69722f6511}

1. Verwenden Sie beim Arbeiten in Ihrem Datensatzprofil [!DNL Profile Manager], um die zu bearbeitende Datensatzkonfigurationsdatei zu öffnen.

   * Informationen zum Öffnen der Datei [!DNL Log Processing.cfg] finden Sie unter [Bearbeiten der Konfigurationsdatei für die Protokollverarbeitung](../../../home/c-dataset-const-proc/c-log-proc-config-file/t-edit-log-proc-config-file.md#task-6a2fa1b735cb4eefad730f0a3a7858e5).

   * Informationen zum Öffnen der Datei [!DNL Transformation.cfg] finden Sie unter [Bearbeiten der Konfigurationsdatei für Umwandlungen](../../../home/c-dataset-const-proc/c-trans-config-file/t-edit-trans-config-file.md#task-cfef4142c1bf4437a669d1fdc75cabbc).

   * Informationen zum Öffnen einer [!DNL Dataset Include]-Datei finden Sie unter [Datensatzaufnahme-Dateien](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md).

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
1. Um Ihre Änderungen zu speichern, klicken Sie mit der rechten Maustaste auf **[!UICONTROL (modified)]** oben im Fenster und klicken Sie auf **[!UICONTROL Save]**.

1. Damit die lokal vorgenommenen Änderungen wirksam werden, klicken Sie mit der rechten Maustaste auf das Häkchen für die Datei in der Spalte [!DNL User] und klicken Sie dann auf **[!UICONTROL Save to]** > &lt;* **[!UICONTROL profile name]***>, wobei der Profilname der Name des Datensatzprofils oder das geerbte Profil ist, zu dem die Datei gehört.[!DNL Profile Manager,]

   >[!NOTE]
   >
   >Speichern Sie die geänderte Konfigurationsdatei nicht in einem der von Adobe bereitgestellten internen Profile, da Ihre Änderungen bei der Installation von Updates für diese Profile überschrieben werden.

## So entfernen Sie eine Bedingung aus einer Datensatzkonfigurationsdatei {#section-677270f93f1648c3a268ca2aea7d4540}

1. Klicken Sie mit der rechten Maustaste auf den Namen der Bedingung oder die Nummer, die der zu entfernenden Bedingung entspricht.
1. Klicken Sie auf **[!UICONTROL Remove]** &lt;* **[!UICONTROL #number]***>, wobei number die Zahl ist, die der zu entfernenden Bedingung entspricht.

## So kopieren Sie eine Bedingung {#section-00617bcf2c274f428686b2ec7f2d1db8}

Sie können eine Bedingung von einem Speicherort an einen anderen Speicherort in derselben Datei kopieren oder eine Bedingung aus einer Datensatzkonfigurationsdatei in einen anderen kopieren.

1. Klicken Sie mit der rechten Maustaste auf den Namen der Bedingung oder die Nummer, die der zu kopierenden Bedingung entspricht, und klicken Sie auf **[!UICONTROL Copy]**.
1. Klicken Sie mit der rechten Maustaste auf den Namen oder die Nummer der Bedingung, unter der Sie die kopierte Bedingung platzieren möchten, und klicken Sie auf **[!UICONTROL Paste]**.
