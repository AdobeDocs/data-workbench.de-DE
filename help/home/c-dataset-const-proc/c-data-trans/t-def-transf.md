---
description: Sie können Datenumwandlungen definieren, die entweder während der Protokollverarbeitungs- oder Transformationsphase der Datensatzerstellung angewendet werden sollen.
title: Definieren von Umwandlungen
uuid: 69dd667b-e465-4c1a-a20e-4384e8988cd0
exl-id: 61ce8093-9e64-419a-bddc-dc2225c0eaab
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '351'
ht-degree: 5%

---

# Definieren von Umwandlungen{#defining-a-transformation}

Sie können Datenumwandlungen definieren, die entweder während der Protokollverarbeitungs- oder Transformationsphase der Datensatzerstellung angewendet werden sollen.

>[!NOTE]
>
>Adobe empfiehlt, Transformationen in [!DNL Log Processing] - oder [!DNL Transformation Dataset Include] -Dateien anstatt in [!DNL Log Processing.cfg] - oder [!DNL Transformation.cfg] -Dateien zu definieren.

Die folgenden Umwandlungen funktionieren nur, wenn sie in der Datei [!DNL Transformation.cfg] oder in der Datei [!DNL Transformation Dataset Include] definiert sind:

* [](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-uri-transf/c-appenduri.md#concept-a0df05dd958645bf8219fc7b0b675ee4)AppendURII
* [CrossRows](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-crossrows.md#concept-fcace08804f54db397ed631cc13ff4f2)
* [LookupRows](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-lookuprows.md#concept-4bd9a1f13ee243e592a6a0008053134f)
* [ODBC-Datenquellen](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-odbc-data-sources.md#concept-5f2cf635081d44beab826ef5ec8cf4e3)
* [Sessionize](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-sessionize.md#concept-b1af95c8cba34b248f86de883d914bc0)

**So definieren Sie eine Umwandlung**

1. Verwenden Sie [!DNL Profile Manager], um die Datensatzkonfigurationsdatei zu öffnen, in der Sie die Umwandlung definieren möchten.

   * (Empfohlen) Informationen zum Öffnen einer Datensatzaufnahme-Datei finden Sie unter [Datensatzaufnahme-Dateien](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md).
   * Informationen zum Öffnen der Datei [!DNL Log Processing.cfg] finden Sie unter [Bearbeiten der Konfigurationsdatei für die Protokollverarbeitung](../../../home/c-dataset-const-proc/c-log-proc-config-file/t-edit-log-proc-config-file.md#task-6a2fa1b735cb4eefad730f0a3a7858e5).

   * Informationen zum Öffnen der Datei [!DNL Transformation.cfg] finden Sie unter [Bearbeiten der Konfigurationsdatei für Umwandlungen](../../../home/c-dataset-const-proc/c-trans-config-file/t-edit-trans-config-file.md#task-cfef4142c1bf4437a669d1fdc75cabbc).

1. Klicken Sie mit der rechten Maustaste auf **[!UICONTROL Transformations]** und klicken Sie dann auf **[!UICONTROL Add new]** > *&lt;**[!UICONTROL Transformation type]***.
1. Geben Sie die entsprechenden Informationen für die Umwandlung ein. Beschreibungen der Umwandlungstypen und Informationen zu ihren Parametern finden Sie in den folgenden Abschnitten:

   * [Standardumwandlungen](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-standard-transf.md#concept-25f4bdbf8fe74c4aaeb2fcd226243886)
   * [URI-Umwandlungen](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-uri-transf/c-uri-transf.md#concept-2dfa0ffcd83d4fb69c1f42ad50dea125)
   * [Integration von Lookup-Daten](../../../home/c-dataset-const-proc/c-data-trans/c-int-lookup-data/c-int-lookup-data.md#concept-08ff70769a464f50ab14299a344f05c7)

1. Nachdem Sie Ihre Transformationen in der Konfigurationsdatei definiert haben, speichern Sie die Datei lokal und speichern Sie sie in Ihrem Datensatzprofil auf dem Data Workbench-Server.

       Tipps zum Definieren und Bearbeiten von Umwandlungen:
   
   * Beim Bearbeiten der Konfiguration einer Transformation in einem Data Workbench-Fenster können Sie Tastaturbefehle für grundlegende Bearbeitungsfunktionen verwenden, z. B. Ausschneiden (Strg+x ), Kopieren (Strg+C), Einfügen (Strg+V ), Rückgängigmachen (Strg+Z ), Wiederholen (Strg+Umschalt+Z ), Auswahl des Bereichs (Klicken+Ziehen) und Auswahl aller Elemente (Strg+A ). Darüber hinaus können Sie die Verknüpfungen verwenden, um Text oder komplette Transformationsdefinitionen von einer Konfigurationsdatei ( [!DNL .cfg]) in eine andere einzufügen.
   * Für jede von Ihnen definierte Umwandlung können Sie dem Kommentar-Parameter eine oder mehrere Kommentarzeilen hinzufügen, um die Umwandlung weiter zu beschreiben oder Hinweise zur Verwendung hinzuzufügen. Um einen Kommentar mithilfe von Data Workbench hinzuzufügen, klicken Sie mit der rechten Maustaste auf die **[!UICONTROL Comments]**-Bezeichnung und klicken Sie dann auf **[!UICONTROL Add new]** > **[!UICONTROL Comment Line]**.

   * Sie können die Konfiguration jeder Umwandlung von einem [!DNL Transformation Dependency Map] aus öffnen. Nachdem Sie die Konfiguration geöffnet haben, können Sie sie bearbeiten und Ihre Änderungen speichern. Weitere Informationen zu [!DNL Transformation Dependency Maps] finden Sie unter [Tools zur Datensatzkonfiguration](../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md#concept-6e058b7691834cf79dcfd1573f78d4f5).

   * Eine leere Zeichenfolgenausgabe aus einer Transformation kann eine nicht leere Zeichenfolge im Ausgabefeld überschreiben.
