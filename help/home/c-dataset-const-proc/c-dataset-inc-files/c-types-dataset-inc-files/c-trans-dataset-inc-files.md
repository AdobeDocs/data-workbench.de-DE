---
description: Die Datensatzaufnahme-Umwandlungsdatei für ein geerbtes Profil enthält Parameter, die mit der Umwandlungsphase der Datensatzerstellung verknüpft sind.
title: Datensatzaufnahme-Dateien zur Umwandlung
uuid: 46756f68-843c-4b0d-a79e-f107ef85db6c
exl-id: 58793f82-162a-4d43-aea9-163716c82db6
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '529'
ht-degree: 3%

---

# Datensatzaufnahme-Dateien zur Umwandlung{#transformation-dataset-include-files}

{{eol}}

Die Datensatzaufnahme-Umwandlungsdatei für ein geerbtes Profil enthält Parameter, die mit der Umwandlungsphase der Datensatzerstellung verknüpft sind.

Die erste Zeile der Datei definiert einen Typ [!DNL TransformationInclude] unterstützt die erweiterten Parameter &quot;Dimensionen&quot;, &quot;Parameter&quot;, &quot;Neu verarbeiten&quot;, &quot;Staging&quot;und &quot;Umwandlungen&quot;. Alle anderen Parameter müssen im Abschnitt [!DNL Transformation.cfg] -Datei im Datensatzverzeichnis des Datensatzprofils.

Einschließen anderer Parameter als erweiterter Dimensionen, Parameter, Neuverarbeitung, Phase und Umwandlungen in einer [!DNL Transformation Dataset Include] -Datei erzeugt Fehler.

Sie können einen [!DNL Transformation Dataset Include] Datei beliebig erstellen, die Dateierweiterung muss jedoch [!DNL .cfg]. Die Datei muss im *geerbter Profilname*\Datensatz\Umwandlungsordner. Da die Dateien während der Umwandlungsphase der Datensatzerstellung rekursiv geladen werden, können Sie die [!DNL Transformation Dataset Include] Dateien auf allen Ebenen innerhalb des Ordners (z. B. *geerbter Profilname*\Dataset\Transformation\*Ordnername*\*Include-Dateiname*.cfg).

>[!NOTE]
>
>Viele webspezifische Konfigurationsparameter für Site sind in definiert. [!DNL Transformation Dataset Include] Dateien. Weitere Informationen zu diesen Parametern finden Sie unter [Konfigurationseinstellungen für Webdaten](../../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519).

In der folgenden Tabelle werden die Parameter beschrieben, die in einer [!DNL Transformation Dataset Include] Datei:

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
   <td colname="col2"> <p>Optional. Hier können beliebige Zeichen oder Kombinationen von Zeichen eingegeben werden. Wenn Sie diesen Parameter ändern und die Datei speichern, wird die Datenumwandlung initiiert. </p> <p> Informationen zur erneuten Verarbeitung Ihrer Daten finden Sie unter <a href="../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md"> Wiederaufbereitung und erneute Umwandlung</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Staging </td> 
   <td colname="col2"> <p>Optional. Der Name der Verarbeitungsstufe, die für diese <span class="wintitle"> Einschließen von Umwandlungsdatensätzen</span> -Datei. Die Verarbeitungsphasen werden im Parameter "Stages"im <span class="filepath"> Transformation.cfg</span> -Datei. </p> <p> <p>Hinweis: Wenn Sie eine Bühne angeben, muss der Name der Bühne genau mit dem Namen übereinstimmen, der im Parameter "Stages"im <span class="filepath"> Transformation.cfg</span> -Datei für das Datensatzprofil. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Umwandlungen </td> 
   <td colname="col2"> Optional. Definiert die Datenumwandlungen, die während der Transformation angewendet werden müssen. Informationen zu den verfügbaren Transformationstypen finden Sie unter <a href="../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md"> Datenumwandlungen</a>. </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Beschreibungen der Parameter im Abschnitt [!DNL Transformation.cfg] -Datei, siehe [Konfigurationsdatei für Umwandlungen](../../../../home/c-dataset-const-proc/c-trans-config-file/c-abt-trans-config-file.md).

Beachten Sie bei der Arbeit mit [!DNL Transformation Dataset Include] -Dateien:

* Das Ändern der Parameter in dieser Datei erfordert eine Neuumwandlung der Daten.
* [!DNL CrossRows], [!DNL ODBCLookup], [!DNL Sessionize]und [!DNL AppendURI] Transformationen funktionieren nur, wenn sie in einer [!DNL Transformation Dataset Configuration] -Datei. Weitere Informationen zu diesen Umwandlungen finden Sie unter [Datenumwandlungen](../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md).

* Sie können jeden der oben beschriebenen Parameter zum [!DNL Transformation Dataset Include] Datei, indem Sie die Datei im Editor öffnen und bearbeiten. Alle Änderungen, die Sie vornehmen und speichern, werden beim erneuten Öffnen der Datei in Data Workbench angezeigt. Verwenden Sie beim Hinzufügen eines neuen Parameters die Leertaste (nicht die Tabulatortaste), um zwei (2) Leerzeichen rechts von der vorherigen Überschriftenebene einzufügen.

Wenn Sie ein Abonnement für die Adobe [!DNL IP Geo-location] oder [!DNL IP Geo-intelligence] Adobe stellt Ihnen ein internes Profil bereit, das aus einer Reihe von Datenumwandlungen und erweiterten Dimensionen besteht, die speziell für den Datendienst erstellt werden. Die Umwandlungen und Dimensionen werden in [!DNL Transformation Dataset Include] -Dateien, die im Datensatzverzeichnis des internen Profils enthalten sind. Anweisungen zur Installation des internen Profils für die [!DNL IP Geo-location] oder [!DNL IP Geo-intelligence] Datendienst, siehe *Data Workbench-Benutzerhandbuch*.
