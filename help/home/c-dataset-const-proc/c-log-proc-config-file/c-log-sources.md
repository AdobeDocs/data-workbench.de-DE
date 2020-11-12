---
description: Protokollquellen sind Dateien mit den Daten, die zum Erstellen eines Datensatzes verwendet werden sollen.
solution: Analytics
title: Quellen für die Protokollierung
topic: Data workbench
uuid: ea21c3d7-9188-4ba8-bacd-052d678bd799
translation-type: tm+mt
source-git-commit: 0727e5b18c89a22b6ee775b1293d3b68e5cee81c
workflow-type: tm+mt
source-wordcount: '3664'
ht-degree: 1%

---


# Quellen für die Protokollierung{#log-sources}

Protokollquellen sind Dateien mit den Daten, die zum Erstellen eines Datensatzes verwendet werden sollen.

Die in den Protokollquellen verfügbaren Daten werden als Ereignis-Daten bezeichnet, da jeder Datensatz einen Transaktionssatz oder eine Instanz eines Ereignisses darstellt. Der Data Workbench-Server kann Protokollquellen verarbeiten, die aus Daten stammen, die von anderen Datenquellen erfasst [!DNL Sensors] oder aus diesen extrahiert wurden.

* **Daten erfasst von [!DNL Sensors]: ** Daten, die von [!DNL Sensors] HTTP- und Anwendungsservern erfasst werden, werden an Data Workbench-Server übertragen, die die Daten in stark komprimierte Protokolldateien ( [!DNL .vsl]) konvertieren. Siehe [Sensordateien](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-b25f11c477b54032a15b6117b3bf9009).

* **Von Insight Server extrahierte Daten:** Der Data Workbench-Server liest Ereignis-Daten, die in Flachdateien, XML-Dateien oder ODBC-kompatiblen Datenbanken enthalten sind, und verwendet seine Dekodierer, um die gewünschten Datenelemente zu extrahieren. Diese Ereignis-Daten müssen nicht speicherresidenz sein, aber die Datensätze, die die Daten enthalten, müssen eine Tracking-ID enthalten. Siehe [Protokolldateien](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e), [XML-Protokollquellen](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-c7b154e93748447b986e97f6ef688887)und [ODBC-Datenquellen](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-odbc-data-sources.md#concept-5f2cf635081d44beab826ef5ec8cf4e3).

**So fügen Sie eine Protokollquelle hinzu**

1. Öffnen Sie [!DNL Log Processing.cfg] in Data Workbench.
1. Klicken Sie mit der rechten Maustaste **[!UICONTROL Log Sources]** und dann auf **[!UICONTROL Add New]**.

1. Wählen Sie eine der folgenden Optionen aus:

   * **[!UICONTROL Sensor]**
   * **[!UICONTROL Log File]**
   * **[!UICONTROL XML Log Source]**
   * **[!UICONTROL ODBC Data Source]**

1. Die zur Definition eines Datensatzes verwendeten spezifischen Parameter variieren je nach dem Typ der Protokollquelle, die im Konfigurationsprozess des Datensatzes verwendet wird. Geben Sie die Parameter wie im Abschnitt für die entsprechende Protokollquelle angegeben an:

   * [Sensordateien](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-b25f11c477b54032a15b6117b3bf9009)
   * [Protokolldateien](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e)
   * [XML-Protokollquellen](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-c7b154e93748447b986e97f6ef688887)
   * [ODBC-Datenquellen](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-odbc-data-sources.md#concept-5f2cf635081d44beab826ef5ec8cf4e3)

1. Nachdem Sie die Protokollquelle (und Änderungen an anderen Parametern) in der [!DNL Log Processing.cfg] Datei definiert haben, speichern Sie die Datei lokal und speichern Sie sie im DataSet-Profil auf dem Data Workbench-Server.

   >[!NOTE]
   >
   >Ein Data Workbench-Server [!DNL File Server Unit] kann [!DNL Sensor] Dateien, Protokolldateien und XML-Dateien empfangen und speichern und sie an die Datenbasis-Server weiterleiten, [!DNL Data Processing Units] die den Datensatz erstellen. Siehe [Konfigurieren einer Insight Server-Dateiservereinheit](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d).

   Sie können die Konfiguration einer beliebigen Protokollquelle von einem [!DNL Transformation Dependency Map]aus öffnen. Weitere Informationen [!DNL Transformation Dependency Map]finden Sie unter [DataSet-Konfigurationstools](../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md#concept-6e058b7691834cf79dcfd1573f78d4f5).

<!--
c_sensor_files.xml
-->

## Voraussetzungen {#section-d5901a4872774ad5bd01a18db114f1f2}

Von [!DNL Sensors] HTTP- und Anwendungsservern erfasste Ereignis-Daten werden an Data Workbench-Server übertragen, die die Daten in stark komprimierte Protokolldateien ( [!DNL .vsl]) konvertieren. Das [!DNL .vsl] Dateiformat wird vom Data Workbench-Server verwaltet und jede Datei hat einen Namen im folgenden Format:

JJJMMTT-*SENSORID*.VSL

wobei YJJMMTT das Datum der Datei ist und *SENSORID* der Name (von Ihrem Unternehmen zugewiesen), der angibt, welche Daten gesammelt und an den Data Workbench-Server übermittelt [!DNL Sensor] wurden.

## Parameter {#section-5c3f1e341c284486aeba3452057da7f3}

Für [!DNL Sensor] Dateien stehen die folgenden Parameter zur Verfügung:

<table id="table_F583B475600041AFA3B9399AE0592146"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Protokollpfade </td> 
   <td colname="col2"> <p>Die Ordner, in denen die <span class="filepath"> .vsl</span> -Dateien gespeichert werden. Der Standardspeicherort ist der Protokollordner. Ein relativer Pfad bezieht sich auf den Installationsordner des Data Workbench-Servers. </p> <p>Mithilfe von Platzhalterzeichen können Sie angeben, welche <span class="filepath"> .vsl</span> -Dateien verarbeitet werden sollen: 
     <ul id="ul_AE144ED0FAB94FE8B32599A058659DE1"> 
      <li id="li_1E4E4CFD72C34B5EB71A3C59877950A9"> * entspricht einer beliebigen Anzahl von Zeichen </li> 
      <li id="li_4664400FC12E44B39B28438B85D20ED8"> ? entspricht einem einzelnen Zeichen </li> 
     </ul> </p> <p> Beispielsweise stimmt der Protokollpfad <span class="filepath"> Logs\*.vsl</span> mit allen Dateien im Verzeichnis Protokolle, die in <span class="filepath"> .vsl</span>enden, überein. Der Protokollpfad <span class="filepath"> Logs\*-SENSOR?.vsl</span> stimmt mit Dateien im Protokollverzeichnis mit jedem Datum (JJJMMTT) und einem einzelnen Zeichen nach SENSOR überein, wie in SENSOR1. </p> <p> Wenn Sie alle Unterordner des angegebenen Pfads durchsuchen möchten, müssen Sie den Parameter "Umkehren"auf "true"setzen. </p> <p> <p>Hinweis: Wenn die Dateien von der <span class="wintitle"> File Server Unit</span>eines Data Workbench-Servers gelesen werden sollen, müssen Sie die entsprechenden URI(s) im Parameter Log Paths eingeben. Beispielsweise stimmt der <span class="filepath"> URI /Logs/*-*.vsl</span> mit jeder <span class="filepath"> .vsl</span> -Datei im Protokollordner überein. Siehe <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d"> Konfigurieren einer Insight Server-Dateiservereinheit</a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Protokollserver </td> 
   <td colname="col2">Informationen (Adresse, Name, Anschluss usw.), die zum Herstellen einer Verbindung mit einem Dateiserver erforderlich sind. Wenn der Parameter "Log Server"einen Eintrag enthält, werden die <span class="wintitle"> Protokollpfade</span> als URIs interpretiert. Andernfalls werden sie als lokale Pfade interpretiert. Siehe <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d"> Konfigurieren einer Insight Server-Dateiservereinheit</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Protokollquelle-ID </td> 
   <td colname="col2"> <p>Der Wert dieses Parameters kann eine beliebige Zeichenfolge sein. Wenn ein Wert angegeben wird, können Sie mit diesem Parameter Protokolleinträge von verschiedenen Protokollquellen zur Quellidentifizierung oder gezielten Verarbeitung unterscheiden. Das Feld x-log-source-id wird mit einem Wert gefüllt, der die Protokollquelle für jeden Protokolleintrag identifiziert. Wenn Sie z. B. Protokolleinträge eines <span class="wintitle"> Sensors</span> mit dem Namen VSensor01 identifizieren möchten, können Sie <span class="filepath"> von VSensor01</span>eingeben. Diese Zeichenfolge wird für jeden Protokolleintrag aus dieser Quelle an das Feld x-log-source-id übergeben. </p> <p> Informationen zum Feld x-log-source-id finden Sie unter <a href="../../../home/c-dataset-const-proc/c-ev-data-rec-fields.md#concept-06bda4be1a4649a2905a4422e9e6c42f"> Ereignis Data Record Fields</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Rekursiv </td> 
   <td colname="col2"> Wahr oder falsch. Bei der Einstellung "true"werden alle Unterordner jedes in " <span class="wintitle"> Protokollpfade</span> "angegebenen Pfads nach Dateien durchsucht, die dem angegebenen Dateinamen oder Platzhaltermuster entsprechen. Der Standardwert ist „false“. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Beginns-/Endzeit verwenden </td> 
   <td colname="col2"> <p>Wahr oder falsch. Wenn "true"festgelegt und "Beginn Time"oder "End Time"angegeben ist, müssen alle Dateien für diese Protokollquelle Dateinamen haben, die mit Datumsangaben im ISO-Format (JJJMMTT) beginnen. Es wird davon ausgegangen, dass jede Datei Daten für einen GMT-Tag enthält (z. B. der Zeitraum, der an einem Tag bei 0000 GMT beginnt und am folgenden Tag bei 0000 GMT endet). Wenn die Protokollquellen-Dateien Daten enthalten, die keinem GMT-Tag entsprechen, muss dieser Parameter auf "false"gesetzt werden, um falsche Ergebnisse zu vermeiden. </p> <p> <p>Hinweis: Standardmäßig entsprechen <span class="filepath"> .vsl- </span>Dateien, die von <span class="wintitle"> Sensor</span> erfasste Daten enthalten, automatisch den oben beschriebenen Benennungs- und Zeitbereichsanforderungen. Wenn Sie diesen Parameter auf "true"setzen, verarbeitet der Data Workbench-Server immer Daten aus Dateien, deren Namen ISO-Daten enthalten, die zwischen der angegebenen Beginn- und Endzeit liegen. Wenn Sie diesen Parameter auf "false"setzen, liest der Data Workbench-Server während der Protokollverarbeitung alle <span class="filepath"> .vsl</span> -Dateien, um zu ermitteln, welche Dateien Daten im Zeitbereich des Beginns und der Endzeit enthalten. </p> </p> <p> Informationen zu den Parametern für die Beginn- und Endzeit finden Sie unter <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d"> Data Filters</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Verwenden Sie nicht die Konfigurationsparameter für [!DNL Sensor] Datenquellen, um zu bestimmen, welche Protokolleinträge in einer Protokolldatei in einen Datensatz aufgenommen werden sollen. Richten Sie stattdessen die Datenquelle so ein, dass sie auf alle Protokolldateien in einem Ordner verweist. Verwenden Sie dann die Parameter &quot;Beginn-Zeit&quot;und &quot;Endzeit&quot;, [!DNL Log Processing.cfg] um zu bestimmen, welche Protokolleinträge bei der Erstellung des Datensatzes verwendet werden sollen. Siehe [Data-Filter](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d).

<!--
c_log_files.xml
-->

Die Datei mit den Ereignis-Daten muss die folgenden Anforderungen erfüllen:

* Jeder Ereignis-Datensatz in der Datei muss durch eine Zeile dargestellt werden.
* Die Felder in einem Datensatz müssen durch ein ASCII-Trennzeichen getrennt werden, unabhängig davon, ob sie leer sind oder nicht. Für den Data Workbench-Server müssen Sie kein bestimmtes Trennzeichen verwenden. Sie können jedes Zeichen verwenden, das kein Zeilenendezeichen ist und nicht an einer beliebigen Stelle in den Ereignis-Daten angezeigt wird.
* Jeder Datensatz in der Datei muss Folgendes enthalten:

   * Eine Tracking-ID
   * Ein Zeitstempel

* Um Beginns- und Endzeiten für die Datenverarbeitung anzugeben, muss jeder Dateiname im folgenden Format stehen:

   * [!DNL YYYYMMDD-SOURCE.log]

   wobei *JJJMMTT* der GMT-Tag aller Daten in der Datei ist und *SOURCE* eine Variable ist, die die Quelle der in der Datei enthaltenen Daten identifiziert.

   >[!NOTE]
   >
   >Wenden Sie sich an Adobe Consulting Services, um eine Übersicht der Protokolldateien zu erhalten, die Sie in den Datensatz aufnehmen möchten.

## Parameter {#section-83a861ac24954d54bbb9530e4d8bf23c}

Für Protokolldateien stehen die Parameter in der folgenden Tabelle zur Verfügung.

>[!NOTE]
>
>Die Verarbeitung von Protokollquellen für Protokolldateien erfordert zusätzliche Parameter, die in einer [!DNL Log Processing Dataset Include] [!DNL Log Processing.cfg] Datei definiert sind, die eine Untergruppe der in einer Datei enthaltenen Parameter sowie spezielle Parameter zum Definieren von Decodern zum Extrahieren von Daten aus der Protokolldatei enthält. Informationen zum Definieren von Decodern für Protokollquellen für Protokolldateien finden Sie unter [Textdatei-Decoder-Gruppen](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-text-file-dec-groups.md#concept-0db34988e17c41bfb1797f1d8e78aabd).

<table id="table_F33735B5B90A48B0B21FA02D9198CCA9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Name </td> 
   <td colname="col2"> Der Bezeichner für die Protokolldateiquelle. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Protokollpfade </td> 
   <td colname="col2"> <p>Die Ordner, in denen die Protokolldateien gespeichert werden. Der Standardspeicherort ist der Protokollordner. Ein relativer Pfad bezieht sich auf den Installationsordner des Data Workbench-Servers. </p> <p> Mithilfe von Platzhalterzeichen können Sie angeben, welche Protokolldateien verarbeitet werden sollen: 
     <ul id="ul_1F02D26A08D846E2A3114E5C33F60ECF"> 
      <li id="li_ECAE1C03A1C448A1B86AE00B3A955708"> * entspricht einer beliebigen Anzahl von Zeichen. </li> 
      <li id="li_24FDB500C5934CAAA4124C435DF4B290"> ? entspricht einem einzelnen Zeichen. </li> 
     </ul> </p> <p> Beispielsweise stimmt der Protokollpfad <span class="filepath"> Logs\*.log</span> mit allen Dateien im Protokollordner überein, die in <span class="filepath"> .log</span>enden. </p> <p> Wenn Sie alle Unterordner des angegebenen Pfads durchsuchen möchten, müssen Sie den Parameter "Umkehren"auf "true"setzen. </p> <p> Wenn die Dateien von der <span class="wintitle"> File Server Unit</span>eines Data Workbench-Servers gelesen werden sollen, müssen Sie die entsprechenden URI(s) im Parameter Log Paths eingeben. Beispielsweise stimmt der <span class="filepath"> URI/Protokolle/*.log</span> mit jeder beliebigen <span class="filepath"> .log</span> -Datei im Protokollordner überein. Siehe <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d"> Konfigurieren einer Insight Server-Dateiservereinheit</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Protokollserver </td> 
   <td colname="col2"> Informationen (Adresse, Name, Anschluss usw.), die zum Herstellen einer Verbindung mit einem Dateiserver erforderlich sind. Wenn der Parameter "Log Server"einen Eintrag enthält, werden die <span class="wintitle"> Protokollpfade</span> als URIs interpretiert. Andernfalls werden sie als lokale Pfade interpretiert. Siehe <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d"> Konfigurieren einer Insight Server-Dateiservereinheit</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> komprimiert </td> 
   <td colname="col2"> Wahr oder falsch. Dieser Wert sollte auf "true"gesetzt werden, wenn die vom Data Workbench-Server zu lesenden Protokolldateien komprimierte GZIP-Dateien sind. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Decoder-Gruppe </td> 
   <td colname="col2"> Der Name der Textdatei-Decoder-Gruppe, die auf die Protokollquelle der Protokolldatei angewendet werden soll. Dieser Name muss exakt mit dem Namen der entsprechenden Textdatei-Decoder-Gruppe übereinstimmen, die in der Datei " <span class="wintitle"> Log Processing DataSet Include"angegeben ist</span> . See <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-text-file-dec-groups.md#concept-0db34988e17c41bfb1797f1d8e78aabd"> Text File Decoder Groups</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Protokollquelle-ID </td> 
   <td colname="col2"> <p>Der Wert dieses Parameters kann eine beliebige Zeichenfolge sein. Wenn ein Wert angegeben wird, können Sie mit diesem Parameter Protokolleinträge von verschiedenen Protokollquellen zur Quellidentifizierung oder gezielten Verarbeitung unterscheiden. Das Feld x-log-source-id wird mit einem Wert gefüllt, der die Protokollquelle für jeden Protokolleintrag identifiziert. Wenn Sie beispielsweise Protokolleinträge aus einer Protokolldatei-Quelle mit dem Namen LogFile01 identifizieren möchten, können Sie <span class="filepath"> aus LogFile01</span>eingeben. Diese Zeichenfolge wird für jeden Protokolleintrag aus dieser Quelle an das Feld x-log-source-id übergeben. </p> <p> Informationen zum Feld x-log-source-id finden Sie unter <a href="../../../home/c-dataset-const-proc/c-ev-data-rec-fields.md#concept-06bda4be1a4649a2905a4422e9e6c42f"> Ereignis Data Record Fields</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Maskenmuster </td> 
   <td colname="col2"> <p>Ein regulärer Ausdruck mit einem einzigen erfassten Submuster, der einen konsistenten Namen extrahiert, der zur Identifizierung der Quelle einer Reihe von Protokolldateien verwendet wird. Nur der Dateiname wird berücksichtigt. Der Pfad und die Erweiterung werden bei der Regelübereinstimmung mit dem Ausdruck nicht berücksichtigt. Wenn Sie kein <span class="wintitle"> Maskenmuster</span>angeben, wird automatisch eine Maske generiert. </p> <p> Bei den Dateien <span class="filepath"> Logs\010105server1.log</span> und <span class="filepath"> Logs\010105server2.log</span>ist das <span class="wintitle"> Maskenmuster</span> <code>[0-9]{6}(.*)</code>. Dieses Muster extrahiert die Zeichenfolge "server1"oder "server2"aus den Dateinamen oben. </p> <p> Siehe <a href="../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c"> Reguläre Ausdrücke</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Rekursiv </td> 
   <td colname="col2"> Wahr oder falsch. Wenn dieser Parameter auf "true"gesetzt ist, werden alle Unterordner jedes in " <span class="wintitle"> Protokollpfade</span> "angegebenen Pfads nach Dateien durchsucht, die dem angegebenen Dateinamen oder dem Platzhaltermuster entsprechen. Der Standardwert ist „false“. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Datei ablehnen </td> 
   <td colname="col2"> Der Pfad und der Dateiname der Datei mit den Protokolleinträgen, die die Bedingungen des Decoders nicht erfüllen. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Beginns-/Endzeit verwenden </td> 
   <td colname="col2"> <p>Wahr oder falsch. Wenn dieser Parameter auf "true"gesetzt ist und "Beginn Time"oder "End Time"angegeben ist, müssen alle Dateien für diese Protokollquelle Dateinamen haben, die mit Datumsangaben im ISO-Format (JJJJMMTT) beginnen. Es wird davon ausgegangen, dass jede Datei Daten für einen GMT-Tag enthält (z. B. der Zeitraum, der an einem Tag bei 0000 GMT beginnt und am folgenden Tag bei 0000 GMT endet). Wenn die Dateinamen der Protokollquellen nicht mit ISO-Daten beginnen oder wenn die Dateien Daten enthalten, die keinem GMT-Tag entsprechen, muss dieser Parameter auf "false"gesetzt werden, um falsche Ergebnisse zu vermeiden. </p> <p> <p>Hinweis:  Wenn die oben beschriebenen Benennungs- und Zeitbereichsanforderungen für die Protokolldateien erfüllt sind und Sie diesen Parameter auf "true"setzen, beschränkt die angegebene Textdatei-Dekodierergruppe die gelesenen Dateien auf diejenigen Dateien, deren Namen ISO-Daten haben, die zwischen der angegebenen Beginn- und Endzeit liegen. Wenn Sie diesen Parameter auf "false"setzen, liest der Data Workbench-Server alle Protokolldateien während der Protokollverarbeitung, um zu ermitteln, welche Beginn Daten im Zeitraum "Time"und "End Time"enthalten. </p> </p> <p> Informationen zu den Parametern für die Beginn- und Endzeit finden Sie unter <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d"> Data Filters</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

In diesem Beispiel wird der Datensatz aus zwei Arten von Protokollquellen erstellt.

Protokollquelle 0 gibt Protokolldateien an, die aus den von [!DNL Sensor]dem Ereignis erfassten Daten generiert wurden. Diese Datenquelle verweist auf einen Ordner namens &quot;Logs&quot;und auf alle Dateien in diesem Ordner mit einer [!DNL .vsl] Dateinamenerweiterung.

Protokollquelle 1 verweist auf alle Dateien im Ordner &quot;Protokolle&quot;mit [!DNL .txt] Dateinamenerweiterung. Die Decoder-Gruppe für diese Protokollquelle heißt &quot;Textprotokolle&quot;.

![](assets/cfg_LogProcessing_LogSources.png)

Sie sollten keine Protokolldateien löschen oder verschieben, nachdem die Datenquellen für einen Datensatz definiert wurden. Dem Verzeichnis der Datenquellen sollten nur neu erstellte Protokolldateien hinzugefügt werden.

<!--
c_xml_log_sources.xml
-->

Die Datei mit den Ereignis-Daten muss die folgenden Anforderungen erfüllen:

* Ereignis-Daten müssen in eine ordnungsgemäß formatierte XML-Datei mit entsprechenden Beziehungen zwischen über- und untergeordnet aufgenommen werden.
* Für jedes XML-Dateiformat muss eine eindeutige Decoder-Gruppe vorhanden sein. Informationen zum Erstellen einer Decoder-Gruppe finden Sie unter [XML Decoder-Gruppen](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-xml-dec-grps.md#concept-5eda5ab253724674832f6951e2a0d1c3).
* Jeder Besucher-Datensatz in der Datei muss Folgendes enthalten:

   * Eine Tracking-ID
   * Ein Zeitstempel

* Um Beginns- und Endzeiten für die Datenverarbeitung anzugeben, muss jeder Dateiname im Formular angegeben werden.

[!DNL YYYYMMDD-SOURCE.log]

wobei *JJJMMTT* der GMT-Tag aller Daten in der Datei ist und *SOURCE* eine Variable ist, die die Quelle der in der Datei enthaltenen Daten identifiziert.

Ein Beispiel für eine XML-Datei, die diese Anforderungen erfüllt, finden Sie unter [XML Decoder-Gruppen](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-xml-dec-grps.md#concept-5eda5ab253724674832f6951e2a0d1c3).

>[!NOTE]
>
>Wenden Sie sich an Adobe Consulting Services, um die XML-Protokolldateien zu überprüfen, die Sie in den Datensatz aufnehmen möchten.

## Parameter {#section-d07b96d7f6ad4affb9cc0a0bc1b88c4d}

Für XML-Protokollquellen sind die Parameter in der folgenden Tabelle verfügbar.

>[!NOTE]
>
>Für die Verarbeitung von XML-Protokollquellen sind zusätzliche Parameter erforderlich, die in einer [!DNL Log Processing Dataset Include] Datei definiert sind, die eine Untergruppe der in einer [!DNL Log Processing.cfg] Datei enthaltenen Parameter sowie spezielle Parameter zum Definieren von Decodern zum Extrahieren von Daten aus der XML-Datei enthalten. Informationen zum Definieren von Decodern für XML-Protokollquellen finden Sie unter [XML Decoder-Gruppen](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-xml-dec-grps.md#concept-5eda5ab253724674832f6951e2a0d1c3).

<table id="table_86B849F379CF4FEBA9294ACEF8F55184"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Feld </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Name </td> 
   <td colname="col2"> Der Bezeichner für die XML-Protokollquelle. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Protokollpfade </td> 
   <td colname="col2"> <p>Die Ordner, in denen die XML-Protokollquellen gespeichert werden. Der Standardspeicherort ist der Protokollordner. Ein relativer Pfad bezieht sich auf den Installationsordner des Data Workbench-Servers. </p> <p> Mithilfe von Platzhalterzeichen können Sie angeben, welche XML-Protokollquellen verarbeitet werden sollen: 
     <ul id="ul_0AE5D0ADE0F64CFAA856492A49239F58"> 
      <li id="li_4CBC0D1733F04258B3A55CC6FA714538 "> * entspricht einer beliebigen Anzahl von Zeichen </li> 
      <li id="li_81B597436A1241FF94E73C18A0ABBFA1"> ? entspricht einem einzelnen Zeichen </li> 
     </ul> </p> <p>Beispielsweise stimmt der Protokollpfad <span class="filepath"> Logs\*.xml</span> mit allen Dateien im Verzeichnis Protokolle, die in <span class="filepath"> .xml</span>enden, überein. </p> <p> Wenn Sie alle Unterverzeichnisse des angegebenen Pfades durchsuchen möchten, müssen Sie das Feld " <span class="wintitle"> Rekursiv</span> "auf "true"setzen. </p> <p> <p>Hinweis: Wenn die Dateien von der <span class="wintitle"> Dateiservereinheit</span>eines Data Workbench-Servers gelesen werden sollen, müssen Sie die entsprechenden URI(s) in das Feld " <span class="wintitle"> Protokollpfade</span> "eingeben. Beispielsweise stimmt die Datei " <span class="filepath"> URI/Protokolle/*.xml</span> "mit jeder beliebigen <span class="filepath"> .xml</span> -Datei im Ordner "Protokolle"überein. Siehe <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d"> Konfigurieren einer Insight Server-Dateiservereinheit</a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Protokollserver </td> 
   <td colname="col2"> Informationen (Adresse, Name, Anschluss usw.), die zum Herstellen einer Verbindung mit einem Dateiserver erforderlich sind. Wenn sich im Feld <span class="wintitle"> Protokollserver</span> ein Eintrag befindet, werden die <span class="wintitle"> Protokollpfade</span> als URIs interpretiert. Andernfalls werden sie als lokale Pfade interpretiert. Siehe <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d"> Konfigurieren einer Insight Server-Dateiservereinheit</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> komprimiert </td> 
   <td colname="col2"> Wahr oder falsch. Dieser Wert sollte auf "true"gesetzt werden, wenn die XML-Protokollquellen, die vom Data Workbench-Server gelesen werden sollen, komprimierte GZIP-Dateien sind. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Decoder-Gruppe </td> 
   <td colname="col2"> Der Name der XML-Decoder-Gruppe, die auf die XML-Protokollquelle angewendet werden soll. Dieser Name muss exakt mit dem Namen der entsprechenden XML-Decoder-Gruppe übereinstimmen, die in der Datei " <span class="wintitle"> Log Processing DataSet Include"angegeben ist</span> . See <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-xml-dec-grps.md#concept-5eda5ab253724674832f6951e2a0d1c3"> XML Decoder Groups</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Protokollquelle-ID </td> 
   <td colname="col2"> <p>Der Wert dieses Felds kann eine beliebige Zeichenfolge sein. Wenn ein Wert angegeben ist, können Sie mit diesem Feld Protokolleinträge von verschiedenen Protokollquellen zur Quellidentifizierung oder gezielten Verarbeitung unterscheiden. Das Feld x-log-source-id wird mit einem Wert gefüllt, der die Protokollquelle für jeden Protokolleintrag identifiziert. Wenn Sie beispielsweise Protokolleinträge aus einer Protokolldatei-Quelle mit dem Namen XMLFile01 identifizieren möchten, können Sie XMLFile01 <span class="filepath"></span>eingeben und diese Zeichenfolge wird für jeden Protokolleintrag aus dieser Quelle an das Feld x-log-source-id übergeben. </p> <p> Informationen zum Feld x-log-source-id finden Sie unter <a href="../../../home/c-dataset-const-proc/c-ev-data-rec-fields.md#concept-06bda4be1a4649a2905a4422e9e6c42f"> Ereignis Data Record Fields</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Maskenmuster </td> 
   <td colname="col2"> <p>Ein regulärer Ausdruck mit einem einzigen erfassten Submuster, der einen konsistenten Namen extrahiert, der zur Identifizierung der Quelle einer Reihe von Protokolldateien verwendet wird. Nur der Dateiname wird berücksichtigt. Der Pfad und die Erweiterung werden bei der Regelübereinstimmung mit dem Ausdruck nicht berücksichtigt. Wenn Sie kein <span class="wintitle"> Maskenmuster</span>angeben, wird automatisch eine Maske generiert. </p> <p> Bei den Dateien <span class="filepath"> Logs\010105server1.xml</span> und <span class="filepath"> Logs\010105server2.xml</span>ist das Maskenmuster <code>[0-9]{6}(.*)</code>. Dieses Muster extrahiert die Zeichenfolge "server1"oder "server2"aus den Dateinamen oben. </p> <p> Siehe <a href="../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c"> Reguläre Ausdrücke</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Rekursiv </td> 
   <td colname="col2"> Wahr oder falsch. Wenn dieser Parameter auf "true"gesetzt ist, werden alle Unterordner jedes in " <span class="wintitle"> Protokollpfade</span> "angegebenen Pfads nach Dateien durchsucht, die dem angegebenen Dateinamen oder dem Platzhaltermuster entsprechen. Der Standardwert ist „false“. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Datei ablehnen </td> 
   <td colname="col2"> Der Pfad und der Dateiname der Datei mit den Protokolleinträgen, die die Bedingungen des Decoders nicht erfüllen. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Beginns-/Endzeit verwenden </td> 
   <td colname="col2"> <p>Wahr oder falsch. Wenn dieser Parameter auf "true"gesetzt ist und "Beginn Time"oder "End Time"angegeben ist, müssen alle Dateien für diese Protokollquelle Dateinamen haben, die mit Datumsangaben im ISO-Format (JJJJMMTT) beginnen. Es wird davon ausgegangen, dass jede Datei Daten für einen GMT-Tag enthält (z. B. der Zeitraum, der an einem Tag bei 0000 GMT beginnt und am folgenden Tag bei 0000 GMT endet). Wenn die Dateinamen der Protokollquellen nicht mit ISO-Daten beginnen oder wenn die Dateien Daten enthalten, die keinem GMT-Tag entsprechen, muss dieser Parameter auf "false"gesetzt werden, um falsche Ergebnisse zu vermeiden. </p> <p> <p>Hinweis:  Wenn die oben beschriebenen Benennungs- und Zeitbereichsanforderungen für die XML-Dateien erfüllt sind und Sie diesen Parameter auf true setzen, beschränkt die angegebene XML-Decoder-Gruppe die gelesenen Dateien auf die Dateien, deren Namen ISO-Daten haben, die zwischen der angegebenen Beginn-Zeit und der Endzeit liegen. Wenn Sie diesen Parameter auf "false"setzen, liest der Data Workbench-Server alle XML-Dateien während der Protokollverarbeitung, um zu ermitteln, welche Beginn Daten im Zeitraum "Time"und "End Time"enthalten. </p> </p> <p> Informationen zu den Parametern für die Beginn- und Endzeit finden Sie unter <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d"> Data Filters</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Sie sollten keine XML-Protokollquellen löschen oder verschieben, nachdem die Datenquellen für einen Datensatz definiert wurden. Dem Verzeichnis der Datenquellen sollten nur neu erstellte XML-Dateien hinzugefügt werden.

<!--
AVRO-log-file.xml
-->

Der Avro-Datenfeed bietet eine effizientere Möglichkeit, Daten in die Data Workbench zu integrieren:

<!-- <a id="section_45E3105B971C4220AE9CF573BEBF6080"></a> -->

* Avro bietet ein Einzelquellenformat für Traffic- und Commerce-Daten.
* Der Avro-Feed ist komprimierte Daten aus mehreren Quellchunken, die pro Tag bereitgestellt werden. Es bietet nur ausgefüllte Felder und Funktionen zur Überwachung und Benachrichtigung, Zugriff auf historische Daten und automatische Wiederherstellung.
* Das Schema, ein selbstdefiniertes Layout von Avro-Protokolldateien, ist am Anfang jeder Datei enthalten.
* Neue Felder werden mit unterstützenden Informationen hinzugefügt, um Daten aus der Data Workbench ohne erforderliche Änderungen am Decoder zu erfassen. Dazu gehören:

   * eVars: 1-250 (früher 1-75)
   * Benutzerspezifische Ereignis: 1-1000 (versus 1-100)
   * Zugriff auf Lösungsvariablen für mobile, soziale und Videodaten

>[!NOTE]
>
>Darüber hinaus ermöglicht die Verwendung des Avro-Feeds den sofortigen Zugriff auf alle neuen Felder im Feed ohne Herunterfahren, sodass die Felder ohne Dienststundenanforderungen aktualisiert werden können.

Der Avro-Datenfeed wird in separaten Dateien eingerichtet:

* Eine **Avro-Protokolldatei**: Dies ist das Avro-Protokollformat, das vom Decoder zur Formatierung von Traffic- und Commerce-Daten generiert wurde.
* Eine **Avro Decoder-Datei**: Mit dieser Datei können Sie Werte dem neuen Avro-Format zuordnen. Sie können den Decoder mit dem Assistenten Avro Decoder einrichten.

## Avro Decoder-Assistent {#section-9a824b4c3d5549e7952a7111232035b2}

Mit diesem Assistenten wird die Avro-Decoder-Protokolldatei eingerichtet.

Klicken Sie zum Öffnen mit der rechten Maustaste auf einen Arbeitsbereich und wählen Sie &quot; **Admin** &quot;> &quot; **Assistenten** &quot;> &quot; **Avro Decoder-Assistent**&quot;.

**Schritt 1:** **Wählen Sie eine Avro-Protokolldatei**.

In diesem Schritt können Sie eine Quelldatei für das Avro-Schema auswählen. Schema können über eine Protokolldatei (.log) oder eine vorhandene Decoder-Datei (.avro) aufgerufen werden. Schemas können aus beiden Dateien gezogen werden.

| **Avro-Protokolldatei ** | Klicken Sie auf , um eine Protokolldatei (.log) zu öffnen, um das Schema oben in der Protokolldatei Ansicht und eine Decoder-Datei zu generieren. |
|---|---|
| **Avro Decoder-Datei** | Klicken Sie auf , um das Schema einer vorhandenen Dekodiererdatei (.avro) zu öffnen und zu bearbeiten. |

**Schritt 2: Wählen Sie Eingabefelder**.

Wählen Sie die Eingabefelder aus, die im Datensatz verwendet werden sollen, um die Protokollverarbeitung zu durchlaufen. Alle Felder in der Datei werden angezeigt, sodass Sie Felder für den Feed auswählen können.

>[!NOTE]
>
>Ein [!DNL x-product(Generates row)] Feld wird bereitgestellt, wenn ein Array in den Daten gefunden wird. Dieses Feld generiert neue Zeilen für die verschachtelten Daten in einem Array als Eingabefelder. Wenn Sie beispielsweise eine Trefferzeile mit vielen Produktwerten in einem Array haben, werden Zeilen in der Eingabedatei für jedes Produkt generiert.

| **Standardeinstellungen auswählen** | Wählen Sie Felder aus, die als Standardsatz von Standardfeldern identifiziert werden sollen. |
|---|---|
| **Alle auswählen** | Wählen Sie alle Felder in der Datei aus. |
| **Auswahl aufheben** | Löschen Sie alle Felder in der Datei. |

**Schritt 3: Wählen Sie die Felder aus, die kopiert werden, um Zeilen zu generieren.**

Da neue Zeilen aus verschachtelten Werten in einem Array erstellt werden können, muss jede neu erstellte Zeile über eine Verfolgungs-ID und einen Zeitstempel verfügen. Mit diesem Schritt können Sie die Felder auswählen, die aus dem übergeordneten Datensatz in Zeilen kopiert werden sollen, z. B. eine Verfolgungs-ID und einen Zeitstempel. Sie können auch andere Werte auswählen, die jeder Zeile hinzugefügt werden sollen.

| **Standardeinstellungen auswählen** | Wählen Sie einen Standardsatz von Standardfeldern aus, für die jeder Zeile neue Spaltenwerte hinzugefügt werden müssen, z. B. eine Verfolgungs-ID und einen Zeitstempel. Ein [!DNL hit_source] Feld ist beispielsweise ein Standardwert, der jeder neuen Zeile hinzugefügt werden muss (er wird in der Liste als Standardwert definiert). Sie können jeder Zeile nach Bedarf weitere Spaltenwerte hinzufügen. |
|---|---|
| **Alle auswählen** | Wählen Sie alle Felder in der Datei aus. |
| **Auswahl aufheben** | Löschen Sie alle Felder in der Datei. |

Verwenden Sie das Feld **Suchen** , um Werte in der Liste zu suchen.

**Schritt 4: Festlegen des Decoder-Namens**

Weisen Sie der Gruppe der Felder einen Namen zu und speichern Sie sie als Decoder-Datei. Der Name sollte mit dem in Ihrer Protokollquelle angegebenen Decoder-Gruppennamen übereinstimmen.

**Schritt 5: Speichern Sie die Decoder-Datei.**

Das Dateimenü wird geöffnet, um die Decoder-Datei zu benennen und als [!DNL .cfg] Datei im Ordner **Protokolle** zu speichern.
