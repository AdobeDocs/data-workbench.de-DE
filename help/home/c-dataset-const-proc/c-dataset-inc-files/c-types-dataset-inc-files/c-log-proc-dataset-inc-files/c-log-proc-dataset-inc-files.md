---
description: Die Protokollverarbeitungsdatenaset-Include-Datei für ein geerbtes Profil enthält Parameter, die mit der Protokollverarbeitungsphase der Datensatzkonstruktion verknüpft sind.
solution: Analytics
title: 'Datensatz zur Protokollverarbeitung: Dateien einschließen'
topic: Data workbench
uuid: 8bf99c9a-f674-4a07-bb3e-de0d9efc9716
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Datensatz zur Protokollverarbeitung: Dateien einschließen{#log-processing-dataset-include-files}

Die Protokollverarbeitungsdatenaset-Include-Datei für ein geerbtes Profil enthält Parameter, die mit der Protokollverarbeitungsphase der Datensatzkonstruktion verknüpft sind.

Die erste Zeile einer [!DNL Log Processing Dataset Include] Datei definiert einen Typ, [!DNL LogProcessingInclude] der die Parameter Decoder Groups, Fields, Log Entry Condition, Parameters, Reprocess, Stage und Transformations unterstützt. Alle anderen Parameter für die Protokollverarbeitung müssen in der [!DNL Log Processing.cfg] Datei im DataSet-Verzeichnis des Datensatzprofils definiert werden. Sie können einer [!DNL Log Processing Dataset Include] Datei beliebig einen Namen geben, die Dateierweiterung muss jedoch gleich sein [!DNL .cfg]. Die Datei muss im *geerbten Profilnamen*\Dataset\Log Processing directory gespeichert werden. Da die Dateien während der Protokollbearbeitung der Datensatzerstellung rekursiv geladen werden, können Sie die [!DNL Log Processing Dataset Include] Dateien auf jeder beliebigen Ebene im Ordner speichern (z. B. *geerbter Profilname*\Dataset\Log Processing\*Ordnername*\*Include Dateiname*.cfg).

>[!NOTE]
>
>Viele webspezifische Konfigurationsparameter für Site werden in [!DNL Log Processing Dataset Include] Dateien definiert. Weitere Informationen zu diesen Parametern finden Sie unter [Konfigurationseinstellungen für Webdaten](../../../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519).

<table id="table_E2112652CCD443E889A529EEDC4ADF1C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Decoder von Gruppen </td> 
   <td colname="col2"> <p>Erforderlich, wenn Sie in der Datei "Log Processing.cfg"Protokollquellen für die <span class="filepath"> Protokolldatei oder die XML-Datei definiert haben</span> . Die Textdatei oder XML-Dekodierer, die Sie definieren, um Datenfelder aus der Protokolldatei und den XML-Protokollquellen zu extrahieren. </p> <p> <b>So fügen Sie eine neue Decoder-Gruppe hinzu</b> 
     <ul id="ul_54087499003C48C8B0AD9660A2F46EA9"> 
      <li id="li_E361861E61D246DDB3964C97CC5187E9"> Klicken Sie mit der rechten Maustaste auf <span class="uicontrol"> Decoder-Gruppe</span> und klicken Sie auf <span class="uicontrol"> Neue</span> hinzufügen &gt; <span class="uicontrol"> TextFileDecoderGroup</span> oder <span class="uicontrol"> XMLDecoderGroup</span>. </li> 
      <li id="li_B2D61A0763AD4FEDB619BF9550EF4602"> Geben Sie im Parameter Name für die neue Gruppe den gewünschten Namen der Decoder-Gruppe ein. </li> 
     </ul> </p> <p> <p>Hinweis:  Wenn Sie eine Decoder-Gruppe in der Datei " <span class="filepath"> Log Processing.cfg</span> "für das Datensatzprofil angeben, muss der Name exakt mit dem Namen übereinstimmen, den Sie hier eingeben. Weitere Informationen finden Sie unter <a href="../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e"> Protokolldateien</a>. </p> </p> <p> Informationen zu den Decoder, die Sie für jede Gruppe definieren können, finden Sie unter <a href="../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-text-file-dec-groups.md#concept-0db34988e17c41bfb1797f1d8e78aabd"> Textdatei-Decoder-Gruppen</a> oder <a href="../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-xml-dec-grps.md#concept-5eda5ab253724674832f6951e2a0d1c3"> XML-Decoder-Gruppen</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Felder </td> 
   <td colname="col2"> <p>Listet Felder auf, die in <span class="wintitle"> Protokollquellen</span> oder <span class="wintitle"> Transformationen</span> in einer <span class="wintitle"> Protokollverarbeitungsdatenaset-Konfigurationsdatei</span> definiert, aber in Transformationen, Bedingungen oder erweiterten Dimensionen in einer <span class="wintitle"> Transformation DataSet-Konfigurationsdatei</span> verwendet werden, müssen hier aufgeführt werden. </p> <p> Jedes Feld unten muss in einer <span class="wintitle"> Protokollverarbeitungsdatenaset-Include-Datei aufgeführt</span> werden: 
     <ul id="ul_D1BB18A80D874C0B9B54DA361698EB30"> 
      <li id="li_7E8B5B697BDA408DBE10D9A63AF295AC"> x-trackingid </li> 
      <li id="li_F5DEE90A596A4A1C86AF874653C4048C"> x-timestamp </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Protokolleinstiegsbedingung </td> 
   <td colname="col2"> <p>Optional. Definiert die Regeln, nach denen Protokolleinträge in den Datensatz aufgenommen werden sollen. Siehe <a href="../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-ecaff95cee4e40bc90f81e099c5fc934"> Protokolleingabebedingung</a>. </p> <p> <p>Hinweis:  Um in den Datensatz aufgenommen zu werden, muss ein Protokolleintrag die <span class="wintitle"> Protokolleintragungsbedingung</span> in der Datei " <span class="filepath"> Log Processing.cfg</span> "und in jeder Datei mit <span class="wintitle"> "Log Processing DataSet Include"erfüllen</span> . </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Parameter </td> 
   <td colname="col2"> Optional. Eine Variable, die Sie in anderen Konfigurationsparametern referenzieren können. Weitere Informationen finden Sie unter <a href="../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-def-param-dataset-inc-files.md#concept-5ad06acc8dc44bf2a99643fafdd56b50"> Definieren von Parametern in DataSet Include-Dateien</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Neu verarbeiten </td> 
   <td colname="col2"> <p>Optional. Alle Zeichen oder Kombinationen von Zeichen können hier eingegeben werden. Durch Ändern dieses Parameters und Speichern der Datei auf dem Data Workbench-Server wird die Datenverarbeitung initiiert. </p> <p> Informationen zur erneuten Verarbeitung Ihrer Daten finden Sie unter <a href="../../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md"> Neuverarbeitung und</a>Verarbeitung. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Phase </td> 
   <td colname="col2"> <p>Optional. Der Name der Verarbeitungsstufe, die für diese <span class="wintitle"> Protokollverarbeitungsdatendatei gilt</span> . Die Verarbeitungsschritte werden im Parameter "Stages"in der Datei " <span class="filepath"> Log Processing.cfg</span> "definiert. </p> <p> <p>Hinweis:  Wenn Sie eine Phase angeben, muss der Name der Bühne exakt mit dem Namen übereinstimmen, der im Parameter "Stages"in der Datei " <span class="filepath"> Log Processing.cfg</span> "für das Datensatzprofil aufgeführt ist. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Transformationen </td> 
   <td colname="col2"> Optional. Definiert die Datentransformationen, die während der Protokollverarbeitung angewendet werden müssen. Informationen zu den verfügbaren Transformationstypen finden Sie unter <a href="../../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md"> Datentransformationen</a>. </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Beschreibungen der Parameter in der [!DNL Log Processing.cfg] Datei finden Sie unter Konfigurationsdatei für die [Protokollverarbeitung](../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md).

Beachten Sie bei der Arbeit mit [!DNL Log Processing Dataset Include] Dateien die folgenden Punkte:

* Um einen der Parameter in dieser Datei zu ändern, müssen alle Daten erneut verarbeitet werden.
* Sie können der [!DNL Log Processing Dataset Include] Datei einen der oben beschriebenen Parameter hinzufügen, indem Sie die Datei in Notepad öffnen und bearbeiten. Änderungen, die Sie vornehmen und speichern, werden angezeigt, wenn Sie die Datei in Data Workbench erneut öffnen. Wenn Sie einen neuen Parameter hinzufügen, verwenden Sie die Leertaste (nicht die Tabulatortaste), um zwei (2) Leerzeichen rechts neben der vorherigen Überschriftenebene einzurücken.

