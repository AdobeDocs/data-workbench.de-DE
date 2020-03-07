---
description: Exportieren Sie Data Workbench-Daten mit TargetBulkUpload.exe aus der Detailtabelle.
title: Nach Adobe Target exportieren
uuid: 0eb99e6f-f0b5-495e-a3b6-df30f61378a7
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Nach Adobe Target exportieren{#export-to-adobe-target}

Exportieren Sie Data Workbench-Daten mit TargetBulkUpload.exe aus der Detailtabelle.

Mit Data Workbench können Sie Dateien exportieren, um sie als Teil einer integrierten Adobe Experience Cloud in Adobe Target zu integrieren.

Die **[!DNL TargetBulkUpload]** Datei befindet sich im Ordner &quot; *Server\Scripts* &quot;in den Serverinstallationsdateien. Die ausführbare Datei verfügt über eine Logik zum erneuten Versuch sowie zusätzliche Logik zur Leistungsoptimierung.

Sie können die `TargetBulkUpload.cfg` Datei ändern und in den Ordner *Server/Admin/Export* verschieben, bevor Sie das Upload-Skript ausführen. Sie können beispielsweise ein Max. Timeout-Intervall auf 720 Minuten festlegen (Standard), um den Upload nach dem angegebenen Zeitraum abzubrechen.

**Das funktioniert so**

Nachdem die Daten erfolgreich an Target gesendet wurden, wird der Status des Uploads kontinuierlich überwacht. Bei erfolgreichem Hochladen wird eine Erfolgsmeldung protokolliert. Wenn der Upload fehlschlägt oder noch aussteht, wird die Überwachung fortgesetzt. Sie können das Zeitüberschreitungsintervall in der `TargetBulkUpload.cfg` Datei konfigurieren. Wenn der Upload in Target blockiert wird, wird eine Meldung protokolliert und der Status kann weiterhin überwacht werden.

Es gibt zwei Protokolldateien, die in der Ablaufverfolgung für den ausgelösten Export generiert werden unter [!DNL /server/Trace/]:

* `targetbulkuploadexportname.log`
* `targetbulkuploadexportname.log.completed`

Die `targetbulkuploadexportname.log` Datei hat den detaillierten Status für alle Datensätze aus mehreren Stapeln, den Edge-Server, den sie verwenden, und den Status (erfolgreich, fehlgeschlagen, Profil nicht gefunden, Status unbekannt und blockiert). Wird festgestellt, dass ein Stapel feststeckt, wird der Stapel nicht weiter verarbeitet. Zur Statusverfolgung steht eine hängende Stapel-URL zur Verfügung. Siehe die folgenden Beispieldaten aus der `targetbulkuploadexportname.log.completed` Datei:

```
1205057 total rows 
568740 successful 
62 failed 
28964 profile not found 
112169 unknown status 
492339 stuck status
```

Der Wert für den blockierten Status wird mit der Gesamtgröße des angehaltenen Stapels inkrementiert, unabhängig davon, wie viele Uploads erfolgreich oder fehlgeschlagen sind. Der Wert der Zeilen insgesamt wird auch um dieselbe Anzahl festsitzender Stapelgrößen erhöht.

>[!NOTE]
>
>Zuvor wurden DWB-Daten mit dem [!DNL ExportIntegration.exe]exportiert. Derzeit werden nur die Exporte MMP, CRS und S/FTP mit dieser ausführbaren Datei verwendet. Die Adobe Target-Integration verwendet jetzt die [!DNL TargetBulkUpload.exe] in Data Workbench.

