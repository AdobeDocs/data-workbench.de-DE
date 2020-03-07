---
description: Sie können Datentransformationen definieren, die entweder während der Protokollverarbeitung oder während der Konvertierungsphase der Datensatzkonstruktion angewendet werden sollen.
solution: Analytics
title: Definieren einer Transformation
topic: Data workbench
uuid: 69dd667b-e465-4c1a-a20e-4384e8988cd0
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Definieren einer Transformation{#defining-a-transformation}

Sie können Datentransformationen definieren, die entweder während der Protokollverarbeitung oder während der Konvertierungsphase der Datensatzkonstruktion angewendet werden sollen.

>[!NOTE]
>
>Adobe empfiehlt, Konvertierungen in einer [!DNL Log Processing] oder [!DNL Transformation Dataset Include] Dateien anstatt in [!DNL Log Processing.cfg] oder [!DNL Transformation.cfg]zu definieren.

Die folgenden Konvertierungen funktionieren nur, wenn sie in der [!DNL Transformation.cfg] Datei oder in einer [!DNL Transformation Dataset Include] Datei definiert sind:

* [](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-uri-transf/c-appenduri.md#concept-a0df05dd958645bf8219fc7b0b675ee4)AppendURII
* [CrossRows](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-crossrows.md#concept-fcace08804f54db397ed631cc13ff4f2)
* [LookupRows](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-lookuprows.md#concept-4bd9a1f13ee243e592a6a0008053134f)
* [ODBC-Datenquellen](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-odbc-data-sources.md#concept-5f2cf635081d44beab826ef5ec8cf4e3)
* [Sessionieren](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-sessionize.md#concept-b1af95c8cba34b248f86de883d914bc0)

**So definieren Sie eine Transformation**

1. Verwenden Sie die [!DNL Profile Manager] zum Öffnen der Datensatzkonfigurationsdatei, in der Sie die Transformation definieren möchten.

   * (Empfohlen) Informationen zum Öffnen einer Datensatzeinschlussdatei finden Sie unter [Datenbestand einschließlich Dateien](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md).
   * Informationen zum Öffnen der [!DNL Log Processing.cfg] Datei finden Sie unter [Bearbeiten der Konfigurationsdatei](../../../home/c-dataset-const-proc/c-log-proc-config-file/t-edit-log-proc-config-file.md#task-6a2fa1b735cb4eefad730f0a3a7858e5)für die Protokollverarbeitung.

   * Informationen zum Öffnen der [!DNL Transformation.cfg] Datei finden Sie unter [Bearbeiten der Transformationskonfigurationsdatei](../../../home/c-dataset-const-proc/c-trans-config-file/t-edit-trans-config-file.md#task-cfef4142c1bf4437a669d1fdc75cabbc).

1. Klicken Sie mit der rechten Maustaste **[!UICONTROL Transformations]** und dann auf **[!UICONTROL Add new]** > *&lt;**[!UICONTROL Transformation type]**>*.
1. Geben Sie die entsprechenden Informationen für die Transformation ein. Beschreibungen der Transformationstypen und Informationen zu ihren Parametern finden Sie in den folgenden Abschnitten:

   * [Standardtransformationen](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-standard-transf.md#concept-25f4bdbf8fe74c4aaeb2fcd226243886)
   * [URI-Konvertierungen](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-uri-transf/c-uri-transf.md#concept-2dfa0ffcd83d4fb69c1f42ad50dea125)
   * [Integration von Suchdaten](../../../home/c-dataset-const-proc/c-data-trans/c-int-lookup-data/c-int-lookup-data.md#concept-08ff70769a464f50ab14299a344f05c7)

1. Nachdem Sie die Transformation(en) in der Konfigurationsdatei definiert haben, speichern Sie die Datei lokal und speichern Sie sie im DataSet-Profil auf dem Data Workbench-Server.

       Tipps zum Definieren und Bearbeiten von Transformationen:
   
   * Beim Bearbeiten der Konfiguration einer Transformation in einem Data Workbench-Fenster können Sie Tastenkombinationen für grundlegende Bearbeitungsfunktionen verwenden, z. B. Ausschneiden (Strg+x), Kopieren (Strg+c), Einfügen (Strg+v), Rückgängigmachen (Strg+Z), Wiederholen (Strg+Umschalt+Z), Abschnitt (Klicken+Ziehen) und Alles auswählen (Strg+a). Darüber hinaus können Sie mit den Tastaturbefehlen Text oder komplette Konvertierungsdefinitionen von einer Konfigurationsdatei ( [!DNL .cfg]) in eine andere kopieren und einfügen.
   * Bei jeder von Ihnen definierten Transformation können Sie dem Parameter &quot;Kommentare&quot;eine oder mehrere Kommentarzeilen hinzufügen, um die Transformation weiter zu beschreiben oder Anmerkungen zur Verwendung hinzuzufügen. Um einen Kommentar mithilfe von Data Workbench hinzuzufügen, klicken Sie mit der rechten Maustaste auf die **[!UICONTROL Comments]** Beschriftung und dann auf **[!UICONTROL Add new]** > **[!UICONTROL Comment Line]**.

   * Sie können die Konfiguration jeder Transformation von einem [!DNL Transformation Dependency Map]. Nachdem Sie die Konfiguration geöffnet haben, können Sie sie bearbeiten und Ihre Änderungen speichern. Weitere Informationen [!DNL Transformation Dependency Maps]finden Sie unter [DataSet-Konfigurationstools](../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md#concept-6e058b7691834cf79dcfd1573f78d4f5).

   * Eine leere Zeichenfolgenausgabe aus einer Transformation kann eine nicht leere Zeichenfolge im Ausgabefeld überschreiben.
