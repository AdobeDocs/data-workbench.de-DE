---
description: Die Transformation DataSet-Include-Datei für ein geerbtes Profil enthält Parameter, die mit der Transformationsphase der Datensatzkonstruktion verknüpft sind.
title: Datensatzaufnahme-Dateien zur Umwandlung
uuid: 46756f68-843c-4b0d-a79e-f107ef85db6c
exl-id: 58793f82-162a-4d43-aea9-163716c82db6
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '529'
ht-degree: 3%

---

# Datensatzaufnahme-Dateien zur Umwandlung{#transformation-dataset-include-files}

Die Transformation DataSet-Include-Datei für ein geerbtes Profil enthält Parameter, die mit der Transformationsphase der Datensatzkonstruktion verknüpft sind.

Die erste Zeile der Datei definiert den Typ [!DNL TransformationInclude], der die Parameter &quot;Erweiterte Dimensionen&quot;, &quot;Parameter&quot;, &quot;Neu verarbeiten&quot;, &quot;Phase&quot;und &quot;Transformationen&quot;unterstützt. Alle anderen Parameter müssen in der Datei [!DNL Transformation.cfg] im DataSet-Profil definiert werden.

Das Einbeziehen von Parametern, die keine erweiterten Dimensionen, Parameter, Neuverarbeitung, Phase und Konvertierungen sind, in eine [!DNL Transformation Dataset Include]-Datei erzeugt Fehler.

Sie können einer [!DNL Transformation Dataset Include]-Datei beliebig einen Namen geben. Die Dateierweiterung muss jedoch [!DNL .cfg] lauten. Die Datei muss im Ordner *inherited Profil name*\Dataset\Transformation directory gespeichert werden. Da die Dateien während der Konvertierungsphase der Datensatzerstellung rekursiv geladen werden, können Sie die [!DNL Transformation Dataset Include]-Dateien auf jeder Ebene im Ordner speichern (z. B. *geerbter Profil-Name*\Dataset\Transformation\*Ordnername*\*Include-Dateiname*.cfg).

>[!NOTE]
>
>Viele webspezifische Konfigurationsparameter für Site werden in [!DNL Transformation Dataset Include]-Dateien definiert. Weitere Informationen zu diesen Parametern finden Sie unter [Konfigurationseinstellungen für Webdaten](../../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519).

Die folgende Tabelle beschreibt die Parameter, die in einer [!DNL Transformation Dataset Include]-Datei verfügbar sind:

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
   <td colname="col2"> Optional. Eine Variable, die Sie in anderen Konfigurationsparametern referenzieren können. Weitere Informationen finden Sie unter <a href="../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-def-param-dataset-inc-files.md#concept-5ad06acc8dc44bf2a99643fafdd56b50"> Definieren von Parametern in DataSet Include Files</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Neu verarbeiten </td> 
   <td colname="col2"> <p>Optional. Alle Zeichen oder Kombinationen von Zeichen können hier eingegeben werden. Wenn Sie diesen Parameter ändern und die Datei speichern, wird eine Datenumwandlung initiiert. </p> <p> Weitere Informationen zur erneuten Verarbeitung Ihrer Daten finden Sie unter <a href="../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md"> Wiederaufbereitung und Umrechnung</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Staging </td> 
   <td colname="col2"> <p>Optional. Der Name der Verarbeitungsstufe, die für diese Datei <span class="wintitle"> "Transformationsdatenaset einschließlich</span> gilt. Die Verarbeitungsschritte werden im Parameter "Stages"in der Datei <span class="filepath"> Transformation.cfg</span> definiert. </p> <p> <p>Hinweis: Wenn Sie eine Phase angeben, muss der Name der Bühne exakt mit dem Namen übereinstimmen, der im Parameter "Stages"in der Datei <span class="filepath"> Transformation.cfg</span> für das DataSet-Profil aufgeführt ist. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Transformationen </td> 
   <td colname="col2"> Optional. Definiert die Datentransformationen, die während der Transformation angewendet werden müssen. Informationen zu den verfügbaren Transformationstypen finden Sie unter <a href="../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md"> Datentransformationen</a>. </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Beschreibungen der Parameter in der Datei [!DNL Transformation.cfg] finden Sie unter [Transformationskonfigurationsdatei](../../../../home/c-dataset-const-proc/c-trans-config-file/c-abt-trans-config-file.md).

Beachten Sie bei der Arbeit mit [!DNL Transformation Dataset Include]-Dateien die folgenden Punkte:

* Um einen der Parameter in dieser Datei zu ändern, müssen die Daten erneut transformiert werden.
* [!DNL CrossRows],  [!DNL ODBCLookup],  [!DNL Sessionize]und  [!DNL AppendURI] Konvertierungen funktionieren nur, wenn sie in einer  [!DNL Transformation Dataset Configuration] Datei definiert sind. Informationen zu diesen Transformationen finden Sie unter [Datentransformationen](../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md).

* Sie können einen der oben beschriebenen Parameter zur Datei [!DNL Transformation Dataset Include] hinzufügen, indem Sie die Datei in Notepad öffnen und bearbeiten. Änderungen, die Sie vornehmen und speichern, werden angezeigt, wenn Sie die Datei in Data Workbench erneut öffnen. Verwenden Sie beim Hinzufügen eines neuen Parameters die Leertaste (nicht die Tabulatortaste), um zwei (2) Leerzeichen rechts neben der vorherigen Überschriftenebene einzurücken.

Wenn Sie den Datendienst [!DNL IP Geo-location] oder [!DNL IP Geo-intelligence] der Adobe abonnieren, stellt Ihnen Adobe ein internes Profil bereit, das aus einer Reihe von Datentransformationen und erweiterten Dimensionen besteht, die speziell für den Datendienst erstellt wurden. Die Transformationen und Dimensionen werden in [!DNL Transformation Dataset Include]-Dateien definiert, die im Datenaset-Ordner des internen Profils enthalten sind. Anweisungen zum Installieren des internen Profils für den Datendienst [!DNL IP Geo-location] oder [!DNL IP Geo-intelligence] finden Sie im *Data Workbench-Benutzerhandbuch*.
