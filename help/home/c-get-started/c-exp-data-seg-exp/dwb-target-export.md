---
description: Exportieren Sie Data Workbench-Daten mithilfe von TargetBulkUpload.exe aus der Detailtabelle in Adobe Target.
title: Exportieren in Adobe Target
uuid: 0eb99e6f-f0b5-495e-a3b6-df30f61378a7
exl-id: 41e885bb-182a-4983-98e8-65eec1da9fe9
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 3%

---

# Exportieren in Adobe Target{#export-to-adobe-target}

{{eol}}

Exportieren Sie Data Workbench-Daten mithilfe von TargetBulkUpload.exe aus der Detailtabelle in Adobe Target.

Mit Data Workbench können Sie Dateien exportieren, um sie im Rahmen einer integrierten Adobe Experience Cloud in Adobe Target zu integrieren.

Die **[!DNL TargetBulkUpload]** finden Sie im Abschnitt *Server\Scripts* in den Server-Installationsdateien. Die ausführbare Datei verfügt über eine Wiederholungslogik sowie zusätzliche Logik zur Leistungsoptimierung.

Sie können die `TargetBulkUpload.cfg` Datei und verschieben Sie sie in *Server/Admin/Export* Ordner vor dem Ausführen des Upload-Skripts. Sie können beispielsweise ein Max. Timeout-Intervall auf 720 Minuten festlegen (Standard), um den Upload nach dem angegebenen Zeitraum zu einem Timeout zu führen.

**Funktionsweise**

Nachdem die Daten erfolgreich an Target gesendet wurden, wird der Status des Uploads kontinuierlich überwacht. Wenn der Upload erfolgreich war, wird eine Erfolgsmeldung protokolliert. Wenn der Upload fehlschlägt oder aussteht, wird die Überwachung fortgesetzt. Sie können das Timeout-Intervall im `TargetBulkUpload.cfg` -Datei. Wenn der Upload in Target blockiert wird, wird eine Nachricht protokolliert und der Status kann weiterhin überwacht werden.

Es werden zwei Protokolldateien im Trace für den ausgelösten Export unter generiert [!DNL /server/Trace/]:

* `targetbulkuploadexportname.log`
* `targetbulkuploadexportname.log.completed`

Die `targetbulkuploadexportname.log` -Datei weist den detaillierten Status für alle Datensätze aus mehreren Batches, den Edge-Server, den sie verwenden werden, und den Status (erfolgreich, fehlgeschlagen, Profil nicht gefunden, Status unbekannt und hängengeblieben) auf. Wenn festgestellt wird, dass ein Batch hängengeblieben ist, wird der Batch nicht weiter verarbeitet. Eine hängende Batch-URL ist verfügbar, um den Status zu verfolgen. Siehe die folgenden Beispieldaten aus der `targetbulkuploadexportname.log.completed` Datei:

```
1205057 total rows 
568740 successful 
62 failed 
28964 profile not found 
112169 unknown status 
492339 stuck status
```

Der Wert für den hängenden Status wird mit der Gesamtgröße des angehaltenen Batches inkrementiert, unabhängig davon, wie viele Uploads erfolgreich sind oder fehlgeschlagen sind. Der Wert für die Zeilen insgesamt wird ebenfalls um dieselbe Anzahl festsitzender Batch-Größe erhöht.

>[!NOTE]
>
>Zuvor wurden DWB-Daten mit dem [!DNL ExportIntegration.exe]. Derzeit werden nur die MMP-, CRS- und S/FTP-Exporte mit dieser ausführbaren Datei verwendet. Die Adobe Target-Integration verwendet jetzt die [!DNL TargetBulkUpload.exe] in der Data Workbench.
