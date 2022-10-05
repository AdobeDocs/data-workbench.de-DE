---
description: Protokollquellen sind Dateien, die die Daten enthalten, die zum Erstellen eines Datensatzes verwendet werden sollen.
title: Quellen für die Protokollierung
uuid: ea21c3d7-9188-4ba8-bacd-052d678bd799
exl-id: 36e0799b-197d-4c59-84ae-7a4350584ab1
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '3664'
ht-degree: 1%

---

# Quellen für die Protokollierung{#log-sources}

{{eol}}

Protokollquellen sind Dateien, die die Daten enthalten, die zum Erstellen eines Datensatzes verwendet werden sollen.

Die in den Protokollquellen verfügbaren Daten werden als Ereignisdaten bezeichnet, da jeder Datensatz einen Transaktionsdatensatz oder eine einzelne Instanz eines Ereignisses darstellt. Der Data Workbench-Server kann Protokollquellen verarbeiten, die aus von [!DNL Sensors] oder aus anderen Datenquellen extrahiert werden.

* **Daten, die von [!DNL Sensors]: ** Daten, die von [!DNL Sensors] von HTTP- und Anwendungsservern an Data Workbench-Server übertragen werden, die die Daten in ein stark komprimiertes Protokoll ( [!DNL .vsl]). Siehe [Sensor-Dateien](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-b25f11c477b54032a15b6117b3bf9009).

* **Von Insight Server extrahierte Daten:** Der Data Workbench-Server liest Ereignisdaten aus reduzierten Dateien, XML-Dateien oder ODBC-kompatiblen Datenbanken und extrahiert mithilfe seiner Decoder die gewünschten Datenelemente. Diese Ereignisdaten müssen nicht speicherspeicherspeicherspeicherresidenz sein, aber die Datensätze, die die Daten enthalten, müssen eine Tracking-ID enthalten. Siehe [Protokolldateien](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e), [XML-Protokollquellen](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-c7b154e93748447b986e97f6ef688887)und [ODBC-Datenquellen](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-odbc-data-sources.md#concept-5f2cf635081d44beab826ef5ec8cf4e3).

**So fügen Sie eine Protokollquelle hinzu**

1. Öffnen [!DNL Log Processing.cfg] in Data Workbench.
1. Rechtsklick **[!UICONTROL Log Sources]** Klicken Sie auf **[!UICONTROL Add New]**.

1. Wählen Sie eine der folgenden Optionen aus:

   * **[!UICONTROL Sensor]**
   * **[!UICONTROL Log File]**
   * **[!UICONTROL XML Log Source]**
   * **[!UICONTROL ODBC Data Source]**

1. Die spezifischen Parameter, die zum Definieren eines Datensatzes verwendet werden, variieren je nach dem Typ der Protokollquelle, die im Konfigurationsprozess des Datensatzes verwendet werden soll. Geben Sie die Parameter wie im Abschnitt angegeben an, die der entsprechenden Protokollquelle entsprechen:

   * [Sensor-Dateien](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-b25f11c477b54032a15b6117b3bf9009)
   * [Protokolldateien](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e)
   * [XML-Protokollquellen](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-c7b154e93748447b986e97f6ef688887)
   * [ODBC-Datenquellen](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-odbc-data-sources.md#concept-5f2cf635081d44beab826ef5ec8cf4e3)

1. Nachdem Sie Ihre Protokollquelle (und Änderungen an anderen Parametern vorgenommen haben) im [!DNL Log Processing.cfg] speichern Sie die Datei lokal und speichern Sie sie in Ihrem Datensatzprofil auf dem Data Workbench-Server.

   >[!NOTE]
   >
   >Ein Data Workbench-Server [!DNL File Server Unit] empfangen und speichern können [!DNL Sensor] Dateien, Protokolldateien und XML-Dateien und deren Bereitstellung für den Data Workbench-Server [!DNL Data Processing Units] , die den Datensatz erstellen. Siehe [Konfigurieren einer Insight Server File Server Unit](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d).

   Sie können die Konfiguration einer beliebigen Protokollquelle über eine [!DNL Transformation Dependency Map]. Informationen zu [!DNL Transformation Dependency Map], siehe [Tools zur Datensatzkonfiguration](../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md#concept-6e058b7691834cf79dcfd1573f78d4f5).

<!--
c_sensor_files.xml
-->

## Voraussetzungen {#section-d5901a4872774ad5bd01a18db114f1f2}

Von [!DNL Sensors] von HTTP- und Anwendungsservern an Data Workbench-Server übertragen werden, die die Daten in ein stark komprimiertes Protokoll ( [!DNL .vsl]). Die [!DNL .vsl] Das Dateiformat wird vom Data Workbench-Server verwaltet und jede Datei hat einen Namen im folgenden Format:

JJJJMMTT -*SENSORID*.VSL

wobei JJJMMTT das Datum der Datei ist und *SENSORID* ist der (von Ihrer Organisation zugewiesene) Name, der angibt, [!DNL Sensor] die Daten erfasst und an den Data Workbench-Server übermittelt.

## Parameter {#section-5c3f1e341c284486aeba3452057da7f3}

Für [!DNL Sensor] -Dateien, sind die folgenden Parameter verfügbar:

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
   <td colname="col2"> <p>Die Ordner, in denen die <span class="filepath"> .vsl</span> -Dateien gespeichert werden. Der Standardspeicherort ist der Protokollordner. Ein relativer Pfad bezieht sich auf den Installationsordner des Data Workbench-Servers. </p> <p>Sie können Platzhalterzeichen verwenden, um anzugeben, welche <span class="filepath"> .vsl</span> zu verarbeitende Dateien: 
     <ul id="ul_AE144ED0FAB94FE8B32599A058659DE1"> 
      <li id="li_1E4E4CFD72C34B5EB71A3C59877950A9"> * entspricht einer beliebigen Anzahl von Zeichen </li> 
      <li id="li_4664400FC12E44B39B28438B85D20ED8"> ? entspricht einem einzelnen Zeichen </li> 
     </ul> </p> <p> Beispielsweise der Protokollpfad <span class="filepath"> Protokolle\*.vsl</span> entspricht allen Dateien im Protokollordner, die auf <span class="filepath"> .vsl</span>. Der Protokollpfad <span class="filepath"> Protokolle\*-SENSOR?.vsl</span> findet Dateien im Protokollverzeichnis mit einem beliebigen Datum (JJJMMTT) und einem einzelnen Zeichen nach SENSOR, wie in SENSOR1. </p> <p> Wenn Sie alle Unterverzeichnisse des angegebenen Pfads durchsuchen möchten, müssen Sie den Parameter "Rekursiv"auf "true"setzen. </p> <p> <p>Hinweis: Wenn die Dateien von einem Data Workbench-Server gelesen werden sollen <span class="wintitle"> File Server Unit</span>eingeben, müssen Sie die entsprechenden URI(s) im Parameter "Log Paths"eingeben. Beispiel: die <span class="filepath"> URI /Logs/*-*.vsl</span> entspricht <span class="filepath"> .vsl</span> -Datei im Verzeichnis "Logs". Siehe <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d"> Konfigurieren einer Insight Server File Server Unit</a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Protokollserver </td> 
   <td colname="col2">Informationen (Adresse, Name, Anschluss usw.), die für die Verbindung mit einem Dateiserver erforderlich sind. Wenn ein Eintrag im Parameter "Log Server"vorhanden ist, wird die <span class="wintitle"> Protokollpfade</span> werden als URIs interpretiert. Andernfalls werden sie als lokale Pfade interpretiert. Siehe <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d"> Konfigurieren einer Insight Server File Server Unit</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Protokollquellen-ID </td> 
   <td colname="col2"> <p>Der Wert dieses Parameters kann eine beliebige Zeichenfolge sein. Wenn ein Wert angegeben wird, können Sie mit diesem Parameter Protokolleinträge von verschiedenen Protokollquellen für die Quellidentifizierung oder die gezielte Verarbeitung unterscheiden. Das Feld x-log-source-id wird mit einem Wert gefüllt, der die Protokollquelle für jeden Protokolleintrag angibt. Wenn Sie beispielsweise Protokolleinträge aus einer <span class="wintitle"> Sensor</span> VSensor01 genannt, können Sie <span class="filepath"> von VSensor01</span>und diese Zeichenfolge an das Feld x-log-source-id für jeden Protokolleintrag aus dieser Quelle übergeben wird. </p> <p> Weitere Informationen zum Feld x-log-source-id finden Sie unter <a href="../../../home/c-dataset-const-proc/c-ev-data-rec-fields.md#concept-06bda4be1a4649a2905a4422e9e6c42f"> Felder für Ereignisdatensätze</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Rekursiv </td> 
   <td colname="col2"> True oder false. Wenn auf "true"gesetzt, werden alle Unterverzeichnisse aller in <span class="wintitle"> Protokollpfade</span> nach Dateien gesucht werden, die dem angegebenen Dateinamen oder dem Platzhaltermuster entsprechen. Der Standardwert ist „false“. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Start-/Endzeiten verwenden </td> 
   <td colname="col2"> <p>True oder false. Wenn auf "true"gesetzt und Startzeit oder Endzeit angegeben ist, müssen alle Dateien für diese Protokollquelle Dateinamen haben, die mit Datumsangaben im ISO-Format (JJJMMTT) beginnen. Es wird davon ausgegangen, dass jede Datei Daten für einen GMT-Tag enthält (z. B. der Zeitraum, der bei 0000 GMT an einem Tag beginnt und am folgenden Tag bei 0000 GMT endet). Wenn die Protokollquellendateien Daten enthalten, die keinem GMT-Tag entsprechen, muss dieser Parameter auf false gesetzt werden, um falsche Ergebnisse zu vermeiden. </p> <p> <p>Hinweis: Standardmäßig <span class="filepath"> .vsl </span>Dateien mit Daten, die von <span class="wintitle"> Sensor</span> automatisch die oben beschriebenen Benennungs- und Zeitbereichsanforderungen erfüllen. Wenn Sie diesen Parameter auf "true"setzen, verarbeitet der Data Workbench-Server immer Daten aus Dateien, deren Namen ISO-Daten enthalten, die zwischen der angegebenen Startzeit und Endzeit liegen. Wenn Sie diesen Parameter auf "false"setzen, liest der Data Workbench-Server alle <span class="filepath"> .vsl</span> -Dateien während der Protokollverarbeitung, um zu bestimmen, welche Dateien Daten innerhalb des Zeitraums für die Startzeit und das Ende enthalten. </p> </p> <p> Informationen zu den Parametern für Startzeit und Endzeit finden Sie unter <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d"> Datenfilter</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Verwenden Sie nicht die Konfigurationsparameter für [!DNL Sensor] Datenquellen, um zu bestimmen, welche Protokolleinträge in einer Protokolldatei in einen Datensatz aufgenommen werden sollen. Richten Sie stattdessen die Datenquelle so ein, dass sie auf alle Protokolldateien in einem Ordner verweist. Verwenden Sie dann die Parameter Startzeit und Endzeit von [!DNL Log Processing.cfg] , um zu bestimmen, welche Protokolleinträge beim Erstellen des Datensatzes verwendet werden sollen. Siehe [Datenfilter](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d).

<!--
c_log_files.xml
-->

Die Datei, die die Ereignisdaten enthält, muss die folgenden Anforderungen erfüllen:

* Jeder Ereignisdatensatz in der Datei muss durch eine Zeile dargestellt werden.
* Die Felder in einem Datensatz müssen durch ein ASCII-Trennzeichen getrennt werden (ob leer oder nicht). Für den Data Workbench-Server ist die Verwendung eines bestimmten Trennzeichens nicht erforderlich. Sie können beliebige Zeichen verwenden, die kein Zeilenendezeichen sind und an keiner Stelle in den Ereignisdaten selbst erscheinen.
* Jeder Datensatz in der Datei muss Folgendes enthalten:

   * Tracking-ID
   * Ein Zeitstempel

* Um Start- und Endzeiten für die Datenverarbeitung anzugeben, muss jeder Dateiname im folgenden Format stehen:

   * [!DNL YYYYMMDD-SOURCE.log]

   where *JJJJMMTT* ist der Greenwich Mean Time (GMT)-Tag aller Daten in der Datei und *QUELLE* ist eine Variable, die die Quelle der in der Datei enthaltenen Daten angibt.

   >[!NOTE]
   >
   >Wenden Sie sich an Adobe Consulting Services , um eine Übersicht über die Protokolldateien zu erhalten, die Sie in den Datensatz integrieren möchten.

## Parameter {#section-83a861ac24954d54bbb9530e4d8bf23c}

Für Protokolldateien sind die Parameter in der folgenden Tabelle verfügbar.

>[!NOTE]
>
>Für die Verarbeitung der Protokolldateiquellen sind zusätzliche Parameter erforderlich, die in einer [!DNL Log Processing Dataset Include] -Datei, die eine Teilmenge der in einer [!DNL Log Processing.cfg] sowie spezielle Parameter zum Definieren von Decodern zum Extrahieren von Daten aus der Protokolldatei. Informationen zum Definieren von Decodern für Protokollquellen für Protokolldateien finden Sie unter [Textdatei-Decoder-Gruppen](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-text-file-dec-groups.md#concept-0db34988e17c41bfb1797f1d8e78aabd).

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
   <td colname="col2"> Die Kennung für die Protokolldateiquelle. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Protokollpfade </td> 
   <td colname="col2"> <p>Die Ordner, in denen die Protokolldateien gespeichert werden. Der Standardspeicherort ist der Protokollordner. Ein relativer Pfad bezieht sich auf den Installationsordner des Data Workbench-Servers. </p> <p> Sie können Platzhalterzeichen verwenden, um anzugeben, welche Protokolldateien verarbeitet werden sollen: 
     <ul id="ul_1F02D26A08D846E2A3114E5C33F60ECF"> 
      <li id="li_ECAE1C03A1C448A1B86AE00B3A955708"> * entspricht einer beliebigen Anzahl von Zeichen. </li> 
      <li id="li_24FDB500C5934CAAA4124C435DF4B290"> ? entspricht einem einzelnen Zeichen. </li> 
     </ul> </p> <p> Beispielsweise der Protokollpfad <span class="filepath"> Protokolle\*.log</span> entspricht allen Dateien im Protokollordner, die auf <span class="filepath"> .log</span>. </p> <p> Wenn Sie alle Unterverzeichnisse des angegebenen Pfads durchsuchen möchten, müssen Sie den Parameter "Rekursiv"auf "true"setzen. </p> <p> Wenn die Dateien von einem Data Workbench-Server gelesen werden sollen <span class="wintitle"> File Server Unit</span>eingeben, müssen Sie die entsprechenden URI(s) im Parameter "Log Paths"eingeben. Beispiel: die <span class="filepath"> URI/Logs/*.log</span> entspricht <span class="filepath"> .log</span> -Datei im Verzeichnis "Logs". Siehe <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d"> Konfigurieren einer Insight Server File Server Unit</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Protokollserver </td> 
   <td colname="col2"> Informationen (Adresse, Name, Anschluss usw.), die für die Verbindung mit einem Dateiserver erforderlich sind. Wenn ein Eintrag im Parameter "Log Server"vorhanden ist, wird die <span class="wintitle"> Protokollpfade</span> werden als URIs interpretiert. Andernfalls werden sie als lokale Pfade interpretiert. Siehe <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d"> Konfigurieren einer Insight Server File Server Unit</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Komprimiert </td> 
   <td colname="col2"> True oder false. Dieser Wert sollte auf true gesetzt werden, wenn die vom Data Workbench-Server zu lesenden Protokolldateien komprimierte gzip-Dateien sind. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Decoder-Gruppe </td> 
   <td colname="col2"> Der Name der Textdatei-Decoder-Gruppe, die auf die Protokollquelle der Protokolldatei angewendet werden soll. Dieser Name muss genau mit dem Namen der entsprechenden Textdatei-Decoder-Gruppe übereinstimmen, der in der <span class="wintitle"> Datensatz für die Protokollverarbeitung einschließen</span> -Datei. Siehe <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-text-file-dec-groups.md#concept-0db34988e17c41bfb1797f1d8e78aabd"> Textdatei-Decoder-Gruppen</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Protokollquellen-ID </td> 
   <td colname="col2"> <p>Der Wert dieses Parameters kann eine beliebige Zeichenfolge sein. Wenn ein Wert angegeben wird, können Sie mit diesem Parameter Protokolleinträge von verschiedenen Protokollquellen für die Quellidentifizierung oder die gezielte Verarbeitung unterscheiden. Das Feld x-log-source-id wird mit einem Wert gefüllt, der die Protokollquelle für jeden Protokolleintrag angibt. Wenn Sie beispielsweise Protokolleinträge aus einer Protokolldateiquelle namens LogFile01 identifizieren möchten, können Sie <span class="filepath"> von LogFile01</span>und diese Zeichenfolge an das Feld x-log-source-id für jeden Protokolleintrag aus dieser Quelle übergeben wird. </p> <p> Weitere Informationen zum Feld x-log-source-id finden Sie unter <a href="../../../home/c-dataset-const-proc/c-ev-data-rec-fields.md#concept-06bda4be1a4649a2905a4422e9e6c42f"> Felder für Ereignisdatensätze</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Maskenmuster </td> 
   <td colname="col2"> <p>Ein regulärer Ausdruck mit einem einzelnen Erfassen-Untermuster, der einen konsistenten Namen extrahiert, der zur Identifizierung der Quelle einer Reihe von Protokolldateien verwendet wird. Nur der Dateiname wird berücksichtigt. Der Pfad und die Erweiterung werden bei der Zuordnung regulärer Ausdrücke nicht berücksichtigt. Wenn Sie keine <span class="wintitle"> Maskenmuster</span>, wird automatisch eine Maske erzeugt. </p> <p> Für die Dateien <span class="filepath"> Protokolle\010105server1.log</span> und <span class="filepath"> Protokolle\010105server2.log</span>, die <span class="wintitle"> Maskenmuster</span> würde <code>[0-9]{6}(.*)</code>. Dieses Muster extrahiert die Zeichenfolge "server1"oder "server2"aus den oben genannten Dateinamen. </p> <p> Siehe <a href="../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c"> Reguläre Ausdrücke</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Rekursiv </td> 
   <td colname="col2"> True oder false. Wenn dieser Parameter auf "true"gesetzt ist, werden alle Unterverzeichnisse aller in <span class="wintitle"> Protokollpfade</span> nach Dateien gesucht werden, die dem angegebenen Dateinamen oder dem Platzhaltermuster entsprechen. Der Standardwert ist „false“. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Datei zurückweisen </td> 
   <td colname="col2"> Der Pfad und der Dateiname der Datei, die die Protokolleinträge enthält, die die Bedingungen des Decoders nicht erfüllen. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Start-/Endzeiten verwenden </td> 
   <td colname="col2"> <p>True oder false. Wenn dieser Parameter auf "true"gesetzt ist und Startzeit oder Endzeit angegeben ist, müssen alle Dateien für diese Protokollquelle Dateinamen haben, die mit Datumsangaben im ISO-Format (JJJMMTT) beginnen. Es wird davon ausgegangen, dass jede Datei Daten für einen GMT-Tag enthält (z. B. der Zeitraum, der bei 0000 GMT an einem Tag beginnt und am folgenden Tag bei 0000 GMT endet). Wenn die Dateinamen der Protokollquellen nicht mit ISO-Daten beginnen oder die Dateien Daten enthalten, die keinem GMT-Tag entsprechen, muss dieser Parameter auf false gesetzt werden, um falsche Ergebnisse zu vermeiden. </p> <p> <p>Hinweis: Wenn die oben beschriebenen Anforderungen an die Benennung und den Zeitraum für die Protokolldateien erfüllt sind und Sie diesen Parameter auf "true"setzen, beschränkt die angegebene Textdatei-Decoder-Gruppe die zu lesenden Dateien auf diejenigen Dateien, deren Namen ISO-Daten aufweisen, die zwischen der angegebenen Start- und Endzeit liegen. Wenn Sie diesen Parameter auf "false"setzen, liest der Data Workbench-Server alle Protokolldateien während der Protokollverarbeitung, um zu bestimmen, welche Dateien Daten innerhalb des Zeitraums "Startzeit"und "Endzeit"enthalten. </p> </p> <p> Informationen zu den Parametern für Startzeit und Endzeit finden Sie unter <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d"> Datenfilter</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

In diesem Beispiel wird der Datensatz aus zwei Arten von Protokollquellen erstellt.

Protokollquelle 0 gibt Protokolldateien an, die aus Ereignisdaten generiert wurden, die von [!DNL Sensor]. Diese Datenquelle verweist auf ein Verzeichnis namens Protokolle und auf alle Dateien in diesem Verzeichnis mit einer [!DNL .vsl] Dateinamenerweiterung.

Protokollquelle 1 verweist auf alle Dateien im Protokollverzeichnis mit einer [!DNL .txt] Dateinamenerweiterung. Die Decoder-Gruppe für diese Protokollquelle heißt &quot;Textprotokolle&quot;.

![](assets/cfg_LogProcessing_LogSources.png)

Sie sollten Protokolldateien nicht löschen oder verschieben, nachdem die Datenquellen für einen Datensatz definiert wurden. Dem Ordner für die Datenquellen sollten nur neu erstellte Protokolldateien hinzugefügt werden.

<!--
c_xml_log_sources.xml
-->

Die Datei, die die Ereignisdaten enthält, muss die folgenden Anforderungen erfüllen:

* Ereignisdaten müssen in eine ordnungsgemäß formatierte XML-Datei mit entsprechenden übergeordneten/untergeordneten Beziehungen aufgenommen werden.
* Für jedes XML-Dateiformat muss eine eindeutige Decoder-Gruppe vorhanden sein. Informationen zum Erstellen einer Decoder-Gruppe finden Sie unter [XML Decoder-Gruppen](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-xml-dec-grps.md#concept-5eda5ab253724674832f6951e2a0d1c3).
* Jeder Besucherdatensatz in der Datei muss Folgendes enthalten:

   * Tracking-ID
   * Ein Zeitstempel

* Um Start- und Endzeiten für die Datenverarbeitung anzugeben, muss jeder Dateiname im Formular angegeben werden.

[!DNL YYYYMMDD-SOURCE.log]

where *JJJJMMTT* ist der Greenwich Mean Time (GMT)-Tag aller Daten in der Datei und *QUELLE* ist eine Variable, die die Quelle der in der Datei enthaltenen Daten angibt.

Ein Beispiel für eine XML-Datei, die diese Anforderungen erfüllt, finden Sie unter [XML Decoder-Gruppen](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-xml-dec-grps.md#concept-5eda5ab253724674832f6951e2a0d1c3).

>[!NOTE]
>
>Wenden Sie sich an Adobe Consulting Services , um eine Übersicht über die XML-Protokolldateien zu erhalten, die Sie in den Datensatz integrieren möchten.

## Parameter {#section-d07b96d7f6ad4affb9cc0a0bc1b88c4d}

Für XML-Protokollquellen sind die Parameter in der folgenden Tabelle verfügbar.

>[!NOTE]
>
>Die Verarbeitung von XML-Protokollquellen erfordert zusätzliche Parameter, die in einer [!DNL Log Processing Dataset Include] -Datei, die eine Teilmenge der in einer [!DNL Log Processing.cfg] sowie spezielle Parameter zum Definieren von Decodern zum Extrahieren von Daten aus der XML-Datei. Informationen zum Definieren von Decodern für XML-Protokollquellen finden Sie unter [XML Decoder-Gruppen](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-xml-dec-grps.md#concept-5eda5ab253724674832f6951e2a0d1c3).

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
   <td colname="col2"> Die Kennung für die XML-Protokollquelle. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Protokollpfade </td> 
   <td colname="col2"> <p>Die Ordner, in denen die XML-Protokollquellen gespeichert sind. Der Standardspeicherort ist der Protokollordner. Ein relativer Pfad bezieht sich auf den Installationsordner des Data Workbench-Servers. </p> <p> Sie können Platzhalterzeichen verwenden, um anzugeben, welche XML-Protokollquellen verarbeitet werden sollen: 
     <ul id="ul_0AE5D0ADE0F64CFAA856492A49239F58"> 
      <li id="li_4CBC0D1733F04258B3A55CC6FA714538 "> * entspricht einer beliebigen Anzahl von Zeichen </li> 
      <li id="li_81B597436A1241FF94E73C18A0ABBFA1"> ? entspricht einem einzelnen Zeichen </li> 
     </ul> </p> <p>Beispielsweise der Protokollpfad <span class="filepath"> Protokolle\*.xml</span> entspricht allen Dateien im Protokollordner, die auf <span class="filepath"> .xml</span>. </p> <p> Wenn Sie alle Unterverzeichnisse des angegebenen Pfads durchsuchen möchten, müssen Sie die <span class="wintitle"> Rekursiv</span> auf "true"gesetzt. </p> <p> <p>Hinweis: Wenn die Dateien von einem Data Workbench-Server gelesen werden sollen <span class="wintitle"> File Server Unit</span>müssen Sie die entsprechenden URIs in die <span class="wintitle"> Protokollpfade</span> -Feld. Beispiel: die <span class="filepath"> URI/Logs/*.xml</span> entspricht <span class="filepath"> .xml</span> -Datei im Verzeichnis "Logs". Siehe <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d"> Konfigurieren einer Insight Server File Server Unit</a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Protokollserver </td> 
   <td colname="col2"> Informationen (Adresse, Name, Anschluss usw.), die für die Verbindung mit einem Dateiserver erforderlich sind. Wenn ein Eintrag im <span class="wintitle"> Protokollserver</span> -Feld, die <span class="wintitle"> Protokollpfade</span> werden als URIs interpretiert. Andernfalls werden sie als lokale Pfade interpretiert. Siehe <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d"> Konfigurieren einer Insight Server File Server Unit</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Komprimiert </td> 
   <td colname="col2"> True oder false. Dieser Wert sollte auf true gesetzt werden, wenn die XML-Protokollquellen, die vom Data Workbench-Server gelesen werden sollen, komprimierte gzip-Dateien sind. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Decoder-Gruppe </td> 
   <td colname="col2"> Der Name der XML-Decoder-Gruppe, die auf die XML-Protokollquelle angewendet werden soll. Dieser Name muss genau mit dem Namen der entsprechenden XML-Decoder-Gruppe übereinstimmen, der in der Variablen <span class="wintitle"> Datensatz für die Protokollverarbeitung einschließen</span> -Datei. Siehe <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-xml-dec-grps.md#concept-5eda5ab253724674832f6951e2a0d1c3"> XML Decoder-Gruppen</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Protokollquellen-ID </td> 
   <td colname="col2"> <p>Der Wert dieses Felds kann eine beliebige Zeichenfolge sein. Wenn ein Wert angegeben ist, können Sie in diesem Feld Protokolleinträge von verschiedenen Protokollquellen unterscheiden, um die Quellerkennung oder die gezielte Verarbeitung zu ermitteln. Das Feld x-log-source-id wird mit einem Wert gefüllt, der die Protokollquelle für jeden Protokolleintrag angibt. Wenn Sie beispielsweise Protokolleinträge aus einer Protokolldateiquelle mit dem Namen XMLFile01 identifizieren möchten, können Sie <span class="filepath"> von XMLFile01</span>und diese Zeichenfolge an das Feld x-log-source-id für jeden Protokolleintrag aus dieser Quelle übergeben wird. </p> <p> Weitere Informationen zum Feld x-log-source-id finden Sie unter <a href="../../../home/c-dataset-const-proc/c-ev-data-rec-fields.md#concept-06bda4be1a4649a2905a4422e9e6c42f"> Felder für Ereignisdatensätze</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Maskenmuster </td> 
   <td colname="col2"> <p>Ein regulärer Ausdruck mit einem einzelnen Erfassen-Untermuster, der einen konsistenten Namen extrahiert, der zur Identifizierung der Quelle einer Reihe von Protokolldateien verwendet wird. Nur der Dateiname wird berücksichtigt. Der Pfad und die Erweiterung werden bei der Zuordnung regulärer Ausdrücke nicht berücksichtigt. Wenn Sie keine <span class="wintitle"> Maskenmuster</span>, wird automatisch eine Maske erzeugt. </p> <p> Für die Dateien <span class="filepath"> Protokolle\010105server1.xml</span> und <span class="filepath"> Protokolle\010105server2.xml</span>, würde das Maskenmuster <code>[0-9]{6}(.*)</code>. Dieses Muster extrahiert die Zeichenfolge "server1"oder "server2"aus den oben genannten Dateinamen. </p> <p> Siehe <a href="../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c"> Reguläre Ausdrücke</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Rekursiv </td> 
   <td colname="col2"> True oder false. Wenn dieser Parameter auf "true"gesetzt ist, werden alle Unterverzeichnisse aller in <span class="wintitle"> Protokollpfade</span> nach Dateien gesucht werden, die dem angegebenen Dateinamen oder dem Platzhaltermuster entsprechen. Der Standardwert ist „false“. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Datei zurückweisen </td> 
   <td colname="col2"> Der Pfad und der Dateiname der Datei, die die Protokolleinträge enthält, die die Bedingungen des Decoders nicht erfüllen. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Start-/Endzeiten verwenden </td> 
   <td colname="col2"> <p>True oder false. Wenn dieser Parameter auf "true"gesetzt ist und Startzeit oder Endzeit angegeben ist, müssen alle Dateien für diese Protokollquelle Dateinamen haben, die mit Datumsangaben im ISO-Format (JJJMMTT) beginnen. Es wird davon ausgegangen, dass jede Datei Daten für einen GMT-Tag enthält (z. B. der Zeitraum, der bei 0000 GMT an einem Tag beginnt und am folgenden Tag bei 0000 GMT endet). Wenn die Dateinamen der Protokollquellen nicht mit ISO-Daten beginnen oder die Dateien Daten enthalten, die keinem GMT-Tag entsprechen, muss dieser Parameter auf false gesetzt werden, um falsche Ergebnisse zu vermeiden. </p> <p> <p>Hinweis: Wenn die oben beschriebenen Anforderungen an die Benennung und den Zeitraum für die XML-Dateien erfüllt sind und Sie diesen Parameter auf "true"setzen, beschränkt die angegebene XML-Decoder-Gruppe die gelesenen Dateien auf die Dateien, deren Namen ISO-Daten aufweisen, die zwischen der angegebenen Start- und Endzeit liegen. Wenn Sie diesen Parameter auf "false"setzen, liest der Data Workbench-Server alle XML-Dateien während der Protokollverarbeitung, um zu bestimmen, welche Dateien Daten innerhalb des Zeitraums "Startzeit"und "Endzeit"enthalten. </p> </p> <p> Informationen zu den Parametern für Startzeit und Endzeit finden Sie unter <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d"> Datenfilter</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Sie sollten keine XML-Protokollquellen löschen oder verschieben, nachdem die Datenquellen für einen Datensatz definiert wurden. Dem Verzeichnis für die Datenquellen sollten nur neu erstellte XML-Dateien hinzugefügt werden.

<!--
AVRO-log-file.xml
-->

Der Avro-Daten-Feed bietet eine effizientere Möglichkeit, Daten in Data Workbench zu integrieren:

<!-- <a id="section_45E3105B971C4220AE9CF573BEBF6080"></a> -->

* Avro bietet ein einzelnes Quellformat für Traffic- und Commerce-Daten.
* Der Avro-Feed ist komprimierte Daten aus mehreren Quellblöcken, die pro Tag bereitgestellt werden. Es stellt nur ausgefüllte Felder bereit und bietet Überwachungs- und Benachrichtigungsfunktionen, Zugriff auf historische Daten und automatische Wiederherstellung.
* Das Schema, ein selbstdefiniertes Layout von Avro-Protokolldateien, ist am Anfang jeder Datei enthalten.
* Neue Felder werden mit unterstützenden Informationen hinzugefügt, um Daten der Data Workbench ohne erforderliche Änderungen am Decoder zu erfassen. Dazu gehören:

   * eVars: 1-250 (früher 1-75)
   * Benutzerspezifische Ereignisse: 1-1000 (gegenüber 1-100)
   * Zugriff auf Lösungsvariablen für mobile, soziale und Videodaten

>[!NOTE]
>
>Darüber hinaus ermöglicht die Verwendung des Avro-Feeds den sofortigen Zugriff auf alle neuen Felder im Feed, ohne dass ein Herunterfahren erforderlich ist. Dadurch können die Felder ohne Service-Stunde-Anforderungen aktualisiert werden.

Der Avro-Daten-Feed wird in separaten Dateien eingerichtet:

* Ein **Avro-Protokolldatei**: Dies ist das vom Decoder generierte Avro-Protokollformat zum Formatieren von Traffic- und Commerce-Daten.
* Ein **Avro Decoder-Datei**: Mit dieser Datei können Sie Werte dem neuen Avro-Format zuordnen. Sie können den Decoder mit dem Assistenten &quot;Avro Decoder&quot;einrichten.

## Avro Decoder-Assistent {#section-9a824b4c3d5549e7952a7111232035b2}

Mit diesem Assistenten wird die Protokolldatei des Avro-Decoders eingerichtet.

Klicken Sie zum Öffnen mit der rechten Maustaste auf einen Arbeitsbereich und wählen Sie **Admin** > **Assistenten** > **Avro Decoder-Assistent**.

**Schritt 1:** **Avro-Protokolldatei auswählen**.

In diesem Schritt können Sie eine Quelldatei für das Avro-Schema auswählen. Der Zugriff auf Schemas erfolgt über eine Protokolldatei (.log) oder eine vorhandene Decoder-Datei (.avro). Schemas können aus beiden Dateien abgerufen werden.

| **Avro-Protokolldatei ** | Klicken Sie auf , um eine Protokolldatei (.log) zu öffnen, um das Schema oben in der Protokolldatei anzuzeigen und eine Decoder-Datei zu generieren. |
|---|---|
| **Avro Decoder-Datei** | Klicken Sie auf , um das Schema einer vorhandenen Decoder-Datei (.avro) zu öffnen und zu bearbeiten. |

**Schritt 2: Eingabefelder auswählen**.

Wählen Sie die Eingabefelder aus, die im Datensatz verwendet werden sollen, um die Protokollverarbeitung zu beenden. Alle Felder in der Datei werden angezeigt, sodass Sie Felder für den Feed auswählen können.

>[!NOTE]
>
>A [!DNL x-product(Generates row)] wird bereitgestellt, wenn in den Daten ein Array gefunden wird. Dieses Feld generiert neue Zeilen für die verschachtelten Daten in einem Array als Eingabefelder. Wenn Sie beispielsweise eine Trefferzeile mit vielen Produktwerten in einem Array haben, werden in der Eingabedatei für jedes Produkt Zeilen generiert.

| **Standardangaben auswählen** | Wählen Sie Felder aus, die als Standardsatz von Standardfeldern identifiziert werden sollen. |
|---|---|
| **Alle auswählen** | Wählen Sie alle Felder in der Datei aus. |
| **Auswahl für alle aufheben** | Löschen Sie alle Felder in der Datei. |

**Schritt 3: Wählen Sie die Felder aus, die kopiert werden, um Zeilen zu generieren.**

Da neue Zeilen aus verschachtelten Werten in einem Array erstellt werden können, muss jede neue Zeile über eine Tracking-ID und einen Zeitstempel verfügen. In diesem Schritt können Sie die Felder auswählen, die aus dem übergeordneten Datensatz in Zeilen kopiert werden sollen, z. B. eine Tracking-ID und einen Zeitstempel. Sie können auch andere Werte auswählen, die Sie jeder Zeile hinzufügen möchten.

| **Standardangaben auswählen** | Wählen Sie einen Standardsatz von Standardfeldern aus, für die jeder Zeile neue Spaltenwerte hinzugefügt werden müssen, z. B. eine Tracking-ID und einen Zeitstempel. Beispiel: eine [!DNL hit_source] -Feld ist ein Standardwert, der jeder neuen Zeile hinzugefügt werden muss (er wird in der Liste als Standardwert definiert). Sie können jeder Zeile bei Bedarf weitere Spaltenwerte hinzufügen. |
|---|---|
| **Alle auswählen** | Wählen Sie alle Felder in der Datei aus. |
| **Auswahl für alle aufheben** | Löschen Sie alle Felder in der Datei. |

Verwenden Sie die **Suche** , um Werte in der Liste zu finden.

**Schritt 4: Geben Sie den Decoder-Namen an**

Weisen Sie der Feldergruppe einen Namen zu und speichern Sie sie als Decoder-Datei. Der Name sollte mit dem Decoder-Gruppennamen übereinstimmen, der in Ihrer Protokollquelle angegeben ist.

**Schritt 5: Speichern Sie die Decoder-Datei.**

Das Dateimenü wird geöffnet, um die Decoder-Datei zu benennen und als [!DNL .cfg] in der Datei **Protokolle** Ordner.
