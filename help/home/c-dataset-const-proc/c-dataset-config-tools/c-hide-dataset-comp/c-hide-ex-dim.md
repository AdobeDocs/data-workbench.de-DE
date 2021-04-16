---
description: Sie können entweder den Parameter "Ausgeblendet"oder den Parameter "Anzeigen"verwenden, um erweiterte Dimensionen auszublenden, damit sie nicht im Dimensionsmenü in Data Workbench angezeigt werden.
title: Ausblenden erweiterter Dimensionen
uuid: c32f47ad-0246-4611-b54c-0c9f0eb396bd
exl-id: 5baccf39-6f3b-40a1-b1c0-a8e5d6a61211
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '535'
ht-degree: 1%

---

# Ausblenden erweiterter Dimensionen{#hiding-extended-dimensions}

Sie können entweder den Parameter &quot;Ausgeblendet&quot;oder den Parameter &quot;Anzeigen&quot;verwenden, um erweiterte Dimensionen auszublenden, damit sie nicht im Dimensionsmenü in Data Workbench angezeigt werden.

Wenn Sie die entsprechende Einstellung für einen der beiden Parameter eingeben, wird der Dimensionsname nicht im Menü der Data Workbench aufgeführt, sondern befindet sich weiterhin im Profil und kann verwendet werden. Jeder Data Workbench-Benutzer kann die ausgeblendeten Dimensionen vorübergehend wieder einblenden, indem er den Parameter &quot;Alle ausblenden&quot;in der Datei [!DNL Insight.cfg] auf &quot;true&quot;setzt.

Weitere Informationen zum Parameter &quot;Rückgängig: Alle&quot;finden Sie im Anhang zu den Konfigurationsparametern der Data Workbench im *Data Workbench Benutzerhandbuch*.

In den folgenden Abschnitten wird beschrieben, wie Sie mit den Parametern &quot;Ausgeblendet&quot;und &quot;Anzeigen&quot;erweiterte Dimensionen ausblenden.

* [Ausblenden erweiterter Dimensionen mit dem Parameter &quot;Ausgeblendet&quot;](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-hide-dataset-comp/c-hide-ex-dim.md#section-7167a6f6241a4bc78f2f322e048d65cf)
* [Ausblenden erweiterter Dimensionen mit dem Parameter &quot;Anzeigen&quot;](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-hide-dataset-comp/c-hide-ex-dim.md#section-4dceb1079c7f40d2bffc686d1f73f8ad)

## Ausblenden erweiterter Dimensionen mit dem ausgeblendeten Parameter {#section-7167a6f6241a4bc78f2f322e048d65cf}

Der Parameter &quot;Ausgeblendet&quot;ist ein optionaler Parameter, den Sie beim Definieren erweiterter Dimensionen in [!DNL Transformation Dataset Configuration]-Dateien verwenden können.

1. Öffnen Sie [!DNL Transformation Dataset Configuration]-Dateien, in denen die erweiterte Dimension definiert ist, die Sie ausblenden möchten. Siehe [Bearbeiten des vorhandenen Datensatzes Include-Dateien](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077).

1. Suchen Sie den Parameter Ausgeblendet für die gewünschte Dimension im Konfigurationsfenster und geben Sie *true* ein.
1. Speichern Sie die Datei lokal und speichern Sie sie dann im entsprechenden Profil auf dem Server. Siehe [Bearbeiten des vorhandenen Datensatzes Include-Dateien](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077).

Der Datensatz wird neu transformiert, danach wird die erweiterte Dimension nicht im Dimensionsmenü in Data Workbench angezeigt. Weitere Informationen zum Parameter &quot;Ausgeblendet&quot;finden Sie unter [Erweiterte Dimensionen](../../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md).

Wenn Sie die Einstellung des Parameters &quot;Ausgeblendet&quot;ändern, müssen Sie den Datensatz erneut transformieren, damit die Änderung wirksam wird.

## Ausblenden erweiterter Dimensionen mithilfe des Parameters Anzeigen {#section-4dceb1079c7f40d2bffc686d1f73f8ad}

Der Parameter Anzeigen ist nicht einer der Parameter, der zum Definieren erweiterter Dimensionen in [!DNL Transformation Dataset Configuration]-Dateien verfügbar ist. Stattdessen wird der Parameter in den [!DNL .dim]-Dateien für alle abgeleiteten Dimensionen definiert, die Sie erstellen. Um mit dem Parameter &quot;Anzeigen&quot;eine erweiterte Dimension auszublenden, müssen Sie daher zunächst eine abgeleitete Dimension erstellen, die auf der erweiterten Dimension basiert, wie im folgenden Verfahren beschrieben:

1. Verwenden Sie einen Texteditor wie Notepad, um eine leere Datei mit dem Namen &lt;*Dimensionsname*.dim zu erstellen. Der Dateiname sollte mit dem Namen der Dimension übereinstimmen, die Sie ausblenden möchten. Wenn Sie beispielsweise die Dimension &quot;Nächste Seite&quot;ausblenden möchten, erstellen Sie eine Datei [!DNL Next Page.dim].

1. hinzufügen Sie folgenden Text in die Datei ein:

   * entity = ref: wdata/model/dim/parent/+name
   * show = bool: false

1. Speichern Sie die Datei im Ordner &quot;Dimensionen&quot;des Profils. Sie können die Datei auf Wunsch in einem Unterverzeichnis speichern.

Wenn Sie den Parameter &quot;Anzeigen&quot;verwenden, um eine erweiterte Dimension auszublenden, müssen Sie den Datensatz nicht erneut transformieren, damit die Änderung wirksam wird. Sie können die Dimension in Ihrer lokalen Version des Profils ein- oder ausblenden (d. h. die [!DNL .dim]-Datei im Benutzerordner speichern) oder die [!DNL .dim]-Datei für andere Benutzer des Profils auf dem Server speichern.

Mit dem Parameter &quot;Anzeigen&quot;können Sie auch Metriken und Filter ausblenden. Weitere Informationen finden Sie im Kapitel &quot;Configuring Interface and Analyse Features&quot;im *Data Workbench-Benutzerhandbuch*.
