---
description: Die Datensatzaufnahme-Umwandlungsdatei für ein geerbtes Profil enthält Parameter, die mit der Umwandlungsphase der Datensatzerstellung verknüpft sind.
title: Datensatzaufnahme-Dateien zur Umwandlung
uuid: 46756f68-843c-4b0d-a79e-f107ef85db6c
exl-id: 58793f82-162a-4d43-aea9-163716c82db6
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '529'
ht-degree: 3%

---

# Datensatzaufnahme-Dateien zur Umwandlung{#transformation-dataset-include-files}

Die Datensatzaufnahme-Umwandlungsdatei für ein geerbtes Profil enthält Parameter, die mit der Umwandlungsphase der Datensatzerstellung verknüpft sind.

Die erste Zeile der Datei definiert den Typ [!DNL TransformationInclude] , der die Parameter &quot;Erweiterte Dimensionen&quot;, &quot;Parameter&quot;, &quot;Neu verarbeiten&quot;, &quot;Staging&quot;und &quot;Umwandlungen&quot;unterstützt. Alle anderen Parameter müssen in der Datei [!DNL Transformation.cfg] im Datensatzverzeichnis des Datensatzprofils definiert werden.

Das Einschließen von anderen Parametern als &quot;Erweiterte Dimensionen&quot;, &quot;Parameter&quot;, &quot;Neu verarbeiten&quot;, &quot;Staging&quot;und &quot;Umwandlungen&quot;in eine [!DNL Transformation Dataset Include]-Datei erzeugt Fehler.

Sie können eine [!DNL Transformation Dataset Include]-Datei beliebig benennen, die Dateierweiterung muss jedoch [!DNL .cfg] lauten. Die Datei muss im Ordner *geerbter Profilname*\Dataset\Transformation directory gespeichert werden. Da die Dateien während der Umwandlungsphase der Datensatzerstellung rekursiv geladen werden, können Sie die [!DNL Transformation Dataset Include]-Dateien auf jeder Ebene im Verzeichnis speichern (z. B. *geerbter Profilname*\Dataset\Transformation\*Ordnername*\*Include-Dateiname*.cfg).

>[!NOTE]
>
>Viele webspezifische Konfigurationsparameter für Site sind in [!DNL Transformation Dataset Include] -Dateien definiert. Weitere Informationen zu diesen Parametern finden Sie unter [Konfigurationseinstellungen für Webdaten](../../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519).

In der folgenden Tabelle werden die Parameter beschrieben, die in einer [!DNL Transformation Dataset Include]-Datei verfügbar sind:

<table id="table_7BD343888D9145BCBA889B531A4D18F8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Erweiterte Dimensionen </td> 
   <td colname="col2"> Optional. Definiert die erweiterten Dimensionen. Siehe <a href="../../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md"> Erweiterte Dimensionen</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Parameter </td> 
   <td colname="col2"> Optional. Eine Variable, die Sie in anderen Konfigurationsparametern referenzieren können. Weitere Informationen finden Sie unter <a href="../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-def-param-dataset-inc-files.md#concept-5ad06acc8dc44bf2a99643fafdd56b50"> Definieren von Parametern in Datensatzaufnahme-Dateien</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Neuverarbeitung </td> 
   <td colname="col2"> <p>Optional. Hier können beliebige Zeichen oder Kombinationen von Zeichen eingegeben werden. Wenn Sie diesen Parameter ändern und die Datei speichern, wird die Datenumwandlung initiiert. </p> <p> Weitere Informationen zur erneuten Verarbeitung Ihrer Daten finden Sie unter <a href="../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md"> Wiederaufbereitung und erneute Umwandlung</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Staging </td> 
   <td colname="col2"> <p>Optional. Der Name der Verarbeitungsphase, die für diese <span class="wintitle"> Transformation DataSet Include</span>-Datei gilt. Die Verarbeitungsphasen werden im Parameter "Stages"in der Datei <span class="filepath"> Transformation.cfg</span> definiert. </p> <p> <p>Hinweis: Wenn Sie eine Phase angeben, muss der Name der Bühne genau mit dem Namen übereinstimmen, der im Parameter "Stages"in der Datei <span class="filepath"> Transformation.cfg</span> für das Datensatzprofil aufgeführt ist. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Umwandlungen </td> 
   <td colname="col2"> Optional. Definiert die Datenumwandlungen, die während der Transformation angewendet werden müssen. Informationen zu den verfügbaren Transformationstypen finden Sie unter <a href="../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md"> Datenumwandlungen</a>. </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Beschreibungen der Parameter in der Datei [!DNL Transformation.cfg] finden Sie unter [Konfigurationsdatei für Umwandlungen](../../../../home/c-dataset-const-proc/c-trans-config-file/c-abt-trans-config-file.md).

Beachten Sie bei der Arbeit mit [!DNL Transformation Dataset Include]-Dateien die folgenden Punkte:

* Das Ändern der Parameter in dieser Datei erfordert eine Neuumwandlung der Daten.
* [!DNL CrossRows],  [!DNL ODBCLookup],  [!DNL Sessionize] und  [!DNL AppendURI] Transformationen funktionieren nur, wenn sie in einer  [!DNL Transformation Dataset Configuration] Datei definiert sind. Weitere Informationen zu diesen Umwandlungen finden Sie unter [Datenumwandlungen](../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md).

* Sie können jeden der oben beschriebenen Parameter zur Datei [!DNL Transformation Dataset Include] hinzufügen, indem Sie die Datei im Notepad öffnen und bearbeiten. Alle Änderungen, die Sie vornehmen und speichern, werden beim erneuten Öffnen der Datei in Data Workbench angezeigt. Verwenden Sie beim Hinzufügen eines neuen Parameters die Leertaste (nicht die Tabulatortaste), um zwei (2) Leerzeichen rechts von der vorherigen Überschriftenebene einzufügen.

Wenn Sie den Datendienst der Adobe [!DNL IP Geo-location] oder [!DNL IP Geo-intelligence] abonnieren, erhalten Sie von Adobe ein internes Profil, das aus einer Reihe von Datenumwandlungen und erweiterten Dimensionen besteht, die speziell für den Datendienst erstellt werden. Die Umwandlungen und Dimensionen werden in [!DNL Transformation Dataset Include]-Dateien definiert, die im Datensatzverzeichnis des internen Profils enthalten sind. Anweisungen zum Installieren des internen Profils für den Datendienst [!DNL IP Geo-location] oder [!DNL IP Geo-intelligence] finden Sie im *Data Workbench-Benutzerhandbuch*.
