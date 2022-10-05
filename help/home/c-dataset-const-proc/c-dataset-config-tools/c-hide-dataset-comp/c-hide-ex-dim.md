---
description: Sie können den Parameter Ausgeblendet oder den Parameter Anzeigen verwenden, um erweiterte Dimensionen auszublenden, damit sie nicht im Dimensionsmenü in Data Workbench angezeigt werden.
title: Ausblenden erweiterter Dimensionen
uuid: c32f47ad-0246-4611-b54c-0c9f0eb396bd
exl-id: 5baccf39-6f3b-40a1-b1c0-a8e5d6a61211
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '535'
ht-degree: 1%

---

# Ausblenden erweiterter Dimensionen{#hiding-extended-dimensions}

{{eol}}

Sie können den Parameter Ausgeblendet oder den Parameter Anzeigen verwenden, um erweiterte Dimensionen auszublenden, damit sie nicht im Dimensionsmenü in Data Workbench angezeigt werden.

Wenn Sie die entsprechende Einstellung für einen der Parameter eingeben, wird der Dimensionsname nicht im Menü in Data Workbench aufgeführt, sondern befindet sich noch im Profil und kann verwendet werden. Jeder Benutzer von Data Workbench kann ausgeblendete Dimensionen vorübergehend wieder einblenden, indem er den Parameter Alle einblenden in der [!DNL Insight.cfg] auf &quot;true&quot;gesetzt.

Weitere Informationen zum Parameter &quot;Alle einblenden&quot;finden Sie im Anhang zu den Konfigurationsparametern für Data Workbench im *Data Workbench-Benutzerhandbuch*.

In den folgenden Abschnitten wird beschrieben, wie Sie mit den Parametern Ausgeblendet und Anzeigen erweiterte Dimensionen ausblenden.

* [Ausblenden erweiterter Dimensionen mithilfe des ausgeblendeten Parameters](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-hide-dataset-comp/c-hide-ex-dim.md#section-7167a6f6241a4bc78f2f322e048d65cf)
* [Ausblenden erweiterter Dimensionen mit dem Parameter &quot;Anzeigen&quot;](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-hide-dataset-comp/c-hide-ex-dim.md#section-4dceb1079c7f40d2bffc686d1f73f8ad)

## Ausblenden erweiterter Dimensionen mithilfe des ausgeblendeten Parameters {#section-7167a6f6241a4bc78f2f322e048d65cf}

Der Parameter Ausgeblendet ist ein optionaler Parameter, den Sie beim Definieren erweiterter Dimensionen in [!DNL Transformation Dataset Configuration] Dateien.

1. Öffnen [!DNL Transformation Dataset Configuration] -Dateien, in denen die erweiterte Dimension, die Sie ausblenden möchten, definiert ist. Siehe [Bearbeiten vorhandener Datensatzaufnahme-Dateien](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077).

1. Suchen Sie den Parameter Ausgeblendet für die gewünschte Dimension im Konfigurationsfenster und geben Sie *true*.
1. Speichern Sie die Datei lokal und speichern Sie sie dann im entsprechenden Profil auf dem Server. Siehe [Bearbeiten vorhandener Datensatzaufnahme-Dateien](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077).

Der Datensatz wird neu umgewandelt, danach wird die erweiterte Dimension nicht im Dimensionsmenü in Data Workbench angezeigt. Weitere Informationen zum Parameter &quot;Ausgeblendet&quot;finden Sie unter [Erweiterte Dimensionen](../../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md).

Wenn Sie die Einstellung des Parameters Ausgeblendet ändern, müssen Sie den Datensatz neu transformieren, damit die Änderung wirksam wird.

## Ausblenden erweiterter Dimensionen mit dem Parameter &quot;Anzeigen&quot; {#section-4dceb1079c7f40d2bffc686d1f73f8ad}

Der Parameter Anzeigen ist nicht einer der Parameter, die zum Definieren erweiterter Dimensionen in [!DNL Transformation Dataset Configuration] Dateien. Stattdessen wird der Parameter im [!DNL .dim] -Dateien für alle abgeleiteten Dimensionen, die Sie erstellen. Um den Parameter Anzeigen zum Ausblenden einer erweiterten Dimension zu verwenden, müssen Sie daher zunächst eine abgeleitete Dimension erstellen, die auf der erweiterten Dimension basiert, wie im folgenden Verfahren beschrieben:

1. Verwenden Sie einen Texteditor wie Notepad, um eine leere Datei mit dem Namen &lt; zu erstellen.*Dimensionsname*>.dim Der Dateiname sollte mit dem Namen der Dimension übereinstimmen, die Sie ausblenden möchten. Um beispielsweise die Dimension &quot;Nächste Seite&quot;auszublenden, erstellen Sie eine [!DNL Next Page.dim] -Datei.

1. Fügen Sie der Datei den folgenden Text hinzu:

   * entity = ref: wdata/model/dim/Parent/+name
   * show = bool: false

1. Speichern Sie die Datei im Verzeichnis Dimensionen des Profils. Sie können die Datei bei Bedarf in einem Unterverzeichnis speichern.

Wenn Sie den Parameter Anzeigen verwenden, um eine erweiterte Dimension auszublenden, müssen Sie Ihren Datensatz nicht erneut transformieren, damit die Änderung wirksam wird. Sie können die Dimension in Ihrer lokalen Version des Profils ein- oder ausblenden (d. h. Sie können die [!DNL .dim] Datei in den Ordner &quot;User&quot;) oder Sie können die [!DNL .dim] -Datei auf den Server zu laden, damit sie von anderen Benutzern des Profils verwendet werden kann.

Sie können auch den Parameter Anzeigen verwenden, um Metriken und Filter auszublenden. Weitere Informationen finden Sie im Kapitel Configuring Interface and Analysis Features im Abschnitt *Data Workbench-Benutzerhandbuch*.
