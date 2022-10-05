---
description: Die Datensatzeinschlussdatei für ein geerbtes Profil enthält Parameter, die mit der Protokollverarbeitungsphase der Datensatzerstellung verknüpft sind.
title: Datensatzaufnahme-Dateien zur Protokollverarbeitung
uuid: 8bf99c9a-f674-4a07-bb3e-de0d9efc9716
exl-id: 06d8046d-6bac-4ccd-bcef-06f7c9ec7619
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '660'
ht-degree: 3%

---

# Datensatzaufnahme-Dateien zur Protokollverarbeitung{#log-processing-dataset-include-files}

{{eol}}

Die Datensatzeinschlussdatei für ein geerbtes Profil enthält Parameter, die mit der Protokollverarbeitungsphase der Datensatzerstellung verknüpft sind.

Die erste Zeile eines [!DNL Log Processing Dataset Include] -Datei definiert einen Typ [!DNL LogProcessingInclude] unterstützt die Parameter &quot;Decoder-Gruppen&quot;, &quot;Felder&quot;, &quot;Log Entry Condition&quot;, &quot;Parameter&quot;, &quot;Reprocess&quot;, &quot;Staging&quot;und &quot;Transformations&quot;. Alle anderen Parameter für die Protokollverarbeitung müssen im [!DNL Log Processing.cfg] -Datei im Datensatzverzeichnis des Datensatzprofils. Sie können einen [!DNL Log Processing Dataset Include] Datei beliebig erstellen, die Dateierweiterung muss jedoch [!DNL .cfg]. Die Datei muss im *geerbter Profilname*\Ordner für die Datensatzverarbeitung\Protokollverarbeitung. Da die Dateien während der Protokollverarbeitungsphase der Datensatzerstellung rekursiv geladen werden, können Sie die [!DNL Log Processing Dataset Include] Dateien auf allen Ebenen innerhalb des Ordners (z. B. *geerbter Profilname*\Datensatz\Protokollverarbeitung\*Ordnername*\*Include-Dateiname*.cfg).

>[!NOTE]
>
>Viele webspezifische Konfigurationsparameter für Site sind in definiert. [!DNL Log Processing Dataset Include] Dateien. Weitere Informationen zu diesen Parametern finden Sie unter [Konfigurationseinstellungen für Webdaten](../../../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519).

<table id="table_E2112652CCD443E889A529EEDC4ADF1C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Decoder-Gruppen </td> 
   <td colname="col2"> <p>Erforderlich, wenn Sie die Protokollquellen für die Protokolldatei oder die XML-Datei im <span class="filepath"> Log Processing.cfg</span> -Datei. Die Textdatei oder XML-Decoder, die Sie definieren, um Datenfelder aus der Protokolldatei und XML-Protokollquellen zu extrahieren. </p> <p> <b>Hinzufügen einer neuen Decoder-Gruppe</b> 
     <ul id="ul_54087499003C48C8B0AD9660A2F46EA9"> 
      <li id="li_E361861E61D246DDB3964C97CC5187E9"> Rechtsklick <span class="uicontrol"> Decoder-Gruppe</span> und klicken Sie auf <span class="uicontrol"> Neu hinzufügen</span> &gt; <span class="uicontrol"> TextFileDecoderGroup</span> oder <span class="uicontrol"> XMLDecoderGroup</span>. </li> 
      <li id="li_B2D61A0763AD4FEDB619BF9550EF4602"> Geben Sie im Parameter Name für die neue Gruppe den gewünschten Namen der Decoder-Gruppe ein. </li> 
     </ul> </p> <p> <p>Hinweis: Wenn Sie eine Decoder-Gruppe im <span class="filepath"> Log Processing.cfg</span> -Datei für das Datensatzprofil ein, muss der Name genau mit dem Namen übereinstimmen, den Sie hier eingeben. Weitere Informationen finden Sie unter <a href="../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e"> Protokolldateien</a>. </p> </p> <p> Informationen zu den Decodern, die Sie für jede Gruppe definieren können, finden Sie unter <a href="../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-text-file-dec-groups.md#concept-0db34988e17c41bfb1797f1d8e78aabd"> Textdatei-Decoder-Gruppen</a> oder <a href="../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-xml-dec-grps.md#concept-5eda5ab253724674832f6951e2a0d1c3"> XML Decoder-Gruppen</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Felder </td> 
   <td colname="col2"> <p>Listet Felder auf, die in definiert sind. <span class="wintitle"> Protokollquellen</span> oder <span class="wintitle"> Umwandlungen</span> in <span class="wintitle"> Datensatzkonfiguration für die Protokollverarbeitung</span> Datei, die jedoch in Transformationen, Bedingungen oder erweiterten Dimensionen in einer <span class="wintitle"> Konfiguration von Umwandlungsdatensätzen</span> -Datei muss hier aufgeführt sein. </p> <p> Jedes Feld unten muss in <span class="wintitle"> Datensatz für die Protokollverarbeitung einschließen</span> Datei: 
     <ul id="ul_D1BB18A80D874C0B9B54DA361698EB30"> 
      <li id="li_7E8B5B697BDA408DBE10D9A63AF295AC"> x-trackingid </li> 
      <li id="li_F5DEE90A596A4A1C86AF874653C4048C"> x-timestamp </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Protokolleintragsbedingung </td> 
   <td colname="col2"> <p>Optional. Definiert die Regeln, nach denen Protokolleinträge zur Aufnahme in den Datensatz berücksichtigt werden. Siehe <a href="../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-ecaff95cee4e40bc90f81e099c5fc934"> Protokolleintragsbedingung</a>. </p> <p> <p>Hinweis: Um in den Datensatz aufgenommen zu werden, muss ein Protokolleintrag die <span class="wintitle"> Protokolleintragsbedingung</span> im <span class="filepath"> Log Processing.cfg</span> und <span class="wintitle"> Datensatz für die Protokollverarbeitung einschließen</span> -Datei. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Parameter </td> 
   <td colname="col2"> Optional. Eine Variable, die Sie in anderen Konfigurationsparametern referenzieren können. Weitere Informationen finden Sie unter <a href="../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-def-param-dataset-inc-files.md#concept-5ad06acc8dc44bf2a99643fafdd56b50"> Definieren von Parametern in Datensatzaufnahme-Dateien</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Neuverarbeitung </td> 
   <td colname="col2"> <p>Optional. Hier können beliebige Zeichen oder Kombinationen von Zeichen eingegeben werden. Wenn Sie diesen Parameter ändern und die Datei auf dem Data Workbench-Server speichern, wird die erneute Datenverarbeitung initiiert. </p> <p> Informationen zur erneuten Verarbeitung Ihrer Daten finden Sie unter <a href="../../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md"> Wiederaufbereitung und erneute Umwandlung</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Staging </td> 
   <td colname="col2"> <p>Optional. Der Name der Verarbeitungsstufe, die für diese <span class="wintitle"> Datensatz für die Protokollverarbeitung einschließen</span> -Datei. Die Verarbeitungsphasen werden im Parameter "Stages"im <span class="filepath"> Log Processing.cfg</span> -Datei. </p> <p> <p>Hinweis: Wenn Sie eine Bühne angeben, muss der Name der Bühne genau mit dem Namen übereinstimmen, der im Parameter "Stages"im <span class="filepath"> Log Processing.cfg</span> -Datei für das Datensatzprofil. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Umwandlungen </td> 
   <td colname="col2"> Optional. Definiert die Datenumwandlungen, die während der Protokollverarbeitung angewendet werden müssen. Informationen zu den verfügbaren Transformationstypen finden Sie unter <a href="../../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md"> Datenumwandlungen</a>. </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Beschreibungen der Parameter im Abschnitt [!DNL Log Processing.cfg] -Datei, siehe [Konfigurationsdatei für die Protokollverarbeitung](../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md).

Beachten Sie bei der Arbeit mit [!DNL Log Processing Dataset Include] -Dateien:

* Das Ändern der Parameter in dieser Datei erfordert eine erneute Verarbeitung aller Daten.
* Sie können jeden der oben beschriebenen Parameter zum [!DNL Log Processing Dataset Include] Datei, indem Sie die Datei im Editor öffnen und bearbeiten. Alle Änderungen, die Sie vornehmen und speichern, werden beim erneuten Öffnen der Datei in Data Workbench angezeigt. Verwenden Sie beim Hinzufügen eines neuen Parameters die Leertaste (nicht die Tabulatortaste), um zwei (2) Leerzeichen rechts von der vorherigen Überschriftenebene einzufügen.
