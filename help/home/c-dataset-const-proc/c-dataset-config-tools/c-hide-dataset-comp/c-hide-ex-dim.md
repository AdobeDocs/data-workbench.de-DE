---
description: Sie können entweder den Parameter "Ausgeblendet"oder den Parameter "Anzeigen"verwenden, um erweiterte Dimensionen auszublenden, damit sie nicht im Dimensionsmenü in Data Workbench angezeigt werden.
solution: Analytics
title: Ausblenden erweiterter Dimensionen
topic: Data workbench
uuid: c32f47ad-0246-4611-b54c-0c9f0eb396bd
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Ausblenden erweiterter Dimensionen{#hiding-extended-dimensions}

Sie können entweder den Parameter &quot;Ausgeblendet&quot;oder den Parameter &quot;Anzeigen&quot;verwenden, um erweiterte Dimensionen auszublenden, damit sie nicht im Dimensionsmenü in Data Workbench angezeigt werden.

Wenn Sie die entsprechende Einstellung für einen der Parameter eingeben, wird der Dimensionsname nicht im Menü in der Data Workbench aufgeführt, aber er befindet sich weiterhin im Profil und kann verwendet werden. Jeder Data Workbench-Benutzer kann die ausgeblendeten Dimensionen vorübergehend wieder einblenden, indem er den Parameter &quot;Alle einblenden&quot;in der [!DNL Insight.cfg] Datei auf &quot;true&quot;setzt.

Weitere Informationen zum Parameter &quot;Rückgängig: Alle&quot;finden Sie im Anhang zu den Konfigurationsparametern für Data Workbench im *Data Workbench-Benutzerhandbuch*.

In den folgenden Abschnitten wird beschrieben, wie Sie mit den Parametern &quot;Ausgeblendet&quot;und &quot;Anzeigen&quot;erweiterte Dimensionen ausblenden.

* [Ausblenden erweiterter Dimensionen mit dem Parameter &quot;Ausgeblendet&quot;](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-hide-dataset-comp/c-hide-ex-dim.md#section-7167a6f6241a4bc78f2f322e048d65cf)
* [Ausblenden erweiterter Dimensionen mit dem Parameter &quot;Anzeigen&quot;](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-hide-dataset-comp/c-hide-ex-dim.md#section-4dceb1079c7f40d2bffc686d1f73f8ad)

## Ausblenden erweiterter Dimensionen mit dem Parameter &quot;Ausgeblendet&quot; {#section-7167a6f6241a4bc78f2f322e048d65cf}

Der Parameter &quot;Ausgeblendet&quot;ist ein optionaler Parameter, den Sie beim Definieren erweiterter Dimensionen in [!DNL Transformation Dataset Configuration] Dateien verwenden können.

1. Öffnen Sie [!DNL Transformation Dataset Configuration] Dateien, in denen die erweiterte Dimension, die Sie ausblenden möchten, definiert ist. Siehe [Bearbeiten vorhandener Datenbestände](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077).

1. Suchen Sie den Parameter Ausgeblendet für die gewünschte Dimension im Konfigurationsfenster und geben Sie *true* ein.
1. Speichern Sie die Datei lokal und speichern Sie sie dann im entsprechenden Profil auf dem Server. Siehe [Bearbeiten vorhandener Datenbestände](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077).

Der Datensatz wird neu transformiert, danach wird die erweiterte Dimension nicht im Dimensionsmenü in Data Workbench angezeigt. Weitere Informationen zum Parameter &quot;Ausgeblendet&quot;finden Sie unter [Erweiterte Dimensionen](../../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md).

Wenn Sie die Einstellung des Parameters &quot;Ausgeblendet&quot;ändern, müssen Sie den Datensatz erneut transformieren, damit die Änderung wirksam wird.

## Ausblenden erweiterter Dimensionen mit dem Parameter &quot;Anzeigen&quot; {#section-4dceb1079c7f40d2bffc686d1f73f8ad}

Der Parameter &quot;Anzeigen&quot;ist nicht einer der Parameter zum Definieren erweiterter Dimensionen in [!DNL Transformation Dataset Configuration] Dateien. Stattdessen wird der Parameter in den [!DNL .dim] Dateien für alle abgeleiteten Dimensionen definiert, die Sie erstellen. Um mit dem Parameter &quot;Anzeigen&quot;eine erweiterte Dimension auszublenden, müssen Sie daher zunächst eine abgeleitete Dimension erstellen, die auf der erweiterten Dimension basiert, wie im folgenden Verfahren beschrieben:

1. Verwenden Sie einen Texteditor wie Notepad, um eine leere Datei mit dem Namen &lt;*Dimensionsname*>.dim zu erstellen. Der Dateiname sollte mit dem Namen der Dimension übereinstimmen, die Sie ausblenden möchten. Wenn Sie beispielsweise die Dimension &quot;Nächste Seite&quot;ausblenden möchten, erstellen Sie eine [!DNL Next Page.dim] Datei.

1. Fügen Sie der Datei den folgenden Text hinzu:

   * entity = ref: wdata/model/dim/parent/+name
   * show = bool: false

1. Speichern Sie die Datei im Ordner Dimensionen des Profils. Sie können die Datei auf Wunsch in einem Unterverzeichnis speichern.

Wenn Sie den Parameter &quot;Anzeigen&quot;verwenden, um eine erweiterte Dimension auszublenden, müssen Sie den Datensatz nicht erneut transformieren, damit die Änderung wirksam wird. Sie können die Dimension in Ihrer lokalen Version des Profils ein- oder ausblenden (d. h. Sie können die [!DNL .dim] Datei im Ordner &quot;Benutzer&quot;speichern) oder die [!DNL .dim] Datei auf dem Server speichern, um sie von anderen Profilbenutzern zu verwenden.

Mit dem Parameter &quot;Anzeigen&quot;können Sie auch Metriken und Filter ausblenden. Weitere Informationen finden Sie im Kapitel &quot;Configuring Interface and Analysis Features&quot;im *Data Workbench-Benutzerhandbuch*.
