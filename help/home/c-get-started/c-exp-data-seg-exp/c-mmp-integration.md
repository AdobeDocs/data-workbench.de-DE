---
description: Mit Data Workbench können Sie Dateien exportieren, um sie im Rahmen eines integrierten Adobe Experience Cloud in den Export von Profilen und Zielgruppen zu integrieren.
title: Übergeordnetes Marketingprofil - Export
uuid: bae0f0c5-a452-4afd-9f2c-5f3ab69a12d2
exl-id: 9fc89815-d31d-41a7-a0c0-de1e84b24baa
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '644'
ht-degree: 3%

---

# Übergeordnetes Marketingprofil - Export{#master-marketing-profile-export}

{{eol}}

Mit Data Workbench können Sie Dateien exportieren, um sie im Rahmen einer integrierten Adobe Experience Cloud in Profile und Zielgruppen zu integrieren.

<!-- <a id="section_731922BC8628479198A41EF3EA72F2FF"></a> -->

Profile und Zielgruppen sind Teil der [Experience Cloud Identity-Dienst](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=de), einem Hauptdienst der [!DNL Adobe Experience Cloud]. Der Export von Profilen und Zielgruppen ermöglicht die Freigabe von Zielgruppen über das Experience Cloud mithilfe einer eindeutigen Experience Cloud-ID (ECID), die jedem Besucher zugewiesen und von [Audience Manager](https://experienceleague.adobe.com/docs/audience-manager/user-guide/aam-home.html?lang=de). Die [!DNL ExportIntegration.exe] application ( [!DNL E:\Server\Scripts]) wird verwendet, um sowohl MMP- als auch Adobe Target-Exporte zu generieren.

**FSU-Server für die Verwendung von Profilen und Zielgruppen konfigurieren**

1. Greifen Sie auf Ihren FSU-Server zu.
1. Öffnen Sie die Datei MMPExport.cfg . `Server/Admin/Export/MMPExport.cfg`.
1. Geben Sie die erforderlichen Werte in die Felder ein. Beispiel:

   >[!NOTE]
   >
   >Die Integration von MMP/AAM beruht bei der Datenübertragung auf dem Amazon-s3-Bucket.
   >
   >
   >Die für die Übertragung von MMP (s3) erforderlichen s3-Informationen erhalten Sie vom Audience Manager-Team.

   ```
   Sample MMPExport.cfg
   MMP Export Configuration = MMPExportConfiguration: 
   s3 Bucket = string: aws_bucket_for_mmp 
   s3 Object Directory = string: test/files/ 
   s3 Region = string: us-east-1 
   s3 Access Key = string: ZZKI62OO5YBA 
   s3 Secret Key = string: ioqwa3OpNE5 
   data Provider Name = string: 895 
   client ID = string: mcprofile2-test 
   client Secret = string: saea1287617212987q 
   username = string: mmptest 
   password = string: pass 
   numRecordsPerChunk = int:  
   numThreads = int:  
   maxRetriesOnSendFailure = unsigned int:
   ```

   >[!NOTE]
   >
   >Die [!DNL MMPExport.cfg]-Datei können Sie außerdem alle Datensätze aufnehmen, in Sets aufteilen und Datensätze erstellen. Die Datensätze werden dann nach Amazon S3 exportiert. Zur Erstellung von Datensatzblöcken sind drei Parameter erforderlich: [!DNL numRecordsPerChunk], [!DNL numThreads]und [!DNL maxRetriesOnSendFailure].

**Definition von Parametern**

<table id="table_DDEFBC45895A4663973F9C2EB9052FEF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Definition </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <i>s3 Bucket</i> </td> 
   <td colname="col2"> Der AWS S3-Bucket, in den der Export übertragen wird. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>s3-Objektverzeichnis</i> </td> 
   <td colname="col2"> Ein Pfad zum Speichern von s3-Dateien. Dies unterstützt Unterverzeichnisse. <p> <p>Wichtig: Leerzeichen und Multibyte-Zeichen sind im Pfad nicht zulässig und verursachen Fehler beim Export. (Der Bindestrich ist erlaubt). </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>s3-Region</i> </td> 
   <td colname="col2"> Die AWS s3-Region, an die der Export gesendet wird. Ex. us-east-1 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>s3-Zugriffsschlüssel</i> </td> 
   <td colname="col2"> AWS-Zugriffsschlüssel </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>s3 Secret Key</i> </td> 
   <td colname="col2"> Geheimer AWS s3-Schlüssel </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>Datenanbietername</i> </td> 
   <td colname="col2"> Dies ist der Ordnername, der zum Speichern von Segmenten und Eigenschaften in AAM verwendet wird. Dies sollte pro Kunde eindeutig sein. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>Client-ID</i> </td> 
   <td colname="col2"> Dies ist eine eindeutige Client-ID, die einem Kunden bereitgestellt wird, wenn sie für MMP bereitgestellt wird. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>Client Secret</i> </td> 
   <td colname="col2"> <p><i></i>Dies ist ein eindeutiges Client-Geheimnis, das einem Kunden bereitgestellt wird, wenn er für MMP bereitgestellt wird. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>username</i> </td> 
   <td colname="col2"> MMP-Benutzername </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>password</i> </td> 
   <td colname="col2"> MMP-Kennwort </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>numRecordsPerChunk</i> </td> 
   <td colname="col2"> <p>Bestimmt die Größe des Stapels in Bezug auf die Anzahl der Datensätze. </p> <p>Durch die Implementierung wird der vom Benutzer angegebene Wert auf min = 1000 Datensätze&amp;nbsp;(~50 KB Abschnitte)&amp;nbsp;und max = 50000 Datensätze (~2,5 MB Abschnitte) begrenzt.&amp;nbsp;Für den Fall, dass der Benutzer diese Konfigurationseigenschaft nicht angibt, wird der Standardwert 10000 verwendet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>numThreads</i> </td> 
   <td colname="col2"> <p>Bestimmt die Parallelität des Chunk-Sendeteils. Es akzeptiert einen Wert zwischen 1 und 24 Threads und der Standardwert ist 12 Threads. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>maxRetriesOnSendFailure</i> </td> 
   <td colname="col2"> <p>Ermittelt die Anzahl der Wiederholungsversuche im Fall von fehlgeschlagenen Chunk-Sendungen. Der Standardwert ist 0 und gibt keine weiteren Zustellversuche an. </p> <p>Zwischen Wiederholungen wird ein Schlafintervall von 2 Sekunden verwendet. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Erstellen eines MMP-Exports vom Client**

1. Öffnen Sie im Client einen Arbeitsbereich und klicken Sie mit der rechten Maustaste darauf **[!UICONTROL Tools]**> **[!UICONTROL Detail Table]**.
1. Hinzufügen **Ebene**.
1. Klicken Sie mit der rechten Maustaste auf die Kopfzeile und wählen Sie **Attribute hinzufügen**.
1. Klicken Sie mit der rechten Maustaste auf die Kopfzeile und wählen Sie **Neuer Übergeordneter Marketing-Profil-Export**. ![](assets/mmp_mmp_export.png)
1. Erweitern **Abfrage**.

   ![](assets/mmp_mmp_query.png)

1. Erweitern **MMP-Konfiguration**.
1. (erforderlich) Geben Sie die **MMP-Segmentname** und **Feld für MMP-Besucher-ID**. Diese Parameter können nicht leer gelassen werden.
1. Die **MMP-Segmentname** sollte mit der im MMP definierten Segment-ID übereinstimmen.
1. Die **MMP-Besucher-ID** ist die in Schritt 4 definierte Attributspalte, die der **Besucher-ID**.
1. Nach Eingabe dieser Felder können Sie den Export speichern, indem Sie mit der rechten Maustaste auf die Überschrift für den Export klicken und die Option auswählen **Speichern** als &quot;Benutzer\.export&quot;bezeichnet.
1. Öffnen **Admin** > **Profil-Manager** und speichern Sie den Export im Profil.

   Wenn alle Daten korrekt eingegeben werden, wird eine Exportdatei in der FSU ([!DNL Server/Exports]), und der Export wird mithilfe der Informationen unter [!DNL MMPExport.cfg]. Das Protokoll zu diesem Thema finden Sie unter [!DNL Server/Trace/]. z. B. [!DNL MMP-102014-133651- `<Segment Export Name>` .log]

```
Query = SegmentExportQuery: 
Command = string: ExportIntegration.exe 
Command Arguments = string: \"%file%.cfg\" \"%file%\" 
Filter = string: 
Level = string: Page View 
MMP Configuration = MMPConfiguration: 
MMP Segment Name = string: 12345 
MMP Visitor ID Field = string: Tracking ID 
Oneshot = bool: true 
Output Fields = vector: 3 items 
0 = ColumnDefinition: 
Column Name = string: 
Field Name = string: Tracking ID 
1 = ColumnDefinition: 
Column Name = string: 
Field Name = string: PID 
2 = ColumnDefinition: 
Column Name = string: 
Field Name = string: SID 
Output File = string: MMPTest.txt 
Output Format = string: %1%\t%2%\t%3%\r\n 
Schedule End Time = string: 
Schedule Every = string: 
Schedule Start Time = string: 
Time Limit (sec) = double: 1800 
```

| Konfigurationsdetails | Beschreibung |
|---|---|
| MMP-Segment-ID | Erforderlich. Dies ist eine Kennung, die Sie zuerst in Audience Manager definieren würden. |
| Feld für MMP-Besucher-ID | Ordnen Sie die ECID zu. |
