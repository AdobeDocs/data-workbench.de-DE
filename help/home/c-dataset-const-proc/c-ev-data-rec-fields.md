---
description: Informationen zu den Datenfeldern, die der Data Workbench-Server zum Erstellen eines Datensatzes verarbeiten kann.
title: Felder für Ereignisdatensätze
uuid: b0232bfa-0a3b-4e3d-876e-6a15a3764eae
exl-id: 35433b87-991a-4fb9-ba6a-3217e89eb769
source-git-commit: 79981e92dd1c2e552f958716626a632ead940973
workflow-type: tm+mt
source-wordcount: '1089'
ht-degree: 2%

---

# Felder für Ereignisdatensätze{#event-data-record-fields}

Informationen zu den Datenfeldern, die der Data Workbench-Server zum Erstellen eines Datensatzes verarbeiten kann.

* [Über Ereignisdaten](../../home/c-dataset-const-proc/c-ev-data-rec-fields.md#section-3a0705f8c1824017aa4effed9903efbe)
* [Standardfelder für Ereignisdatensätze](../../home/c-dataset-const-proc/c-ev-data-rec-fields.md#section-a882ed7aa6af41eeb45a55bf8c1ca3d7)
* [Abgeleitete Felder](../../home/c-dataset-const-proc/c-ev-data-rec-fields.md#section-b6c57ee2aa31469fbd5dab90e52bc677)

## Über Ereignisdaten {#section-3a0705f8c1824017aa4effed9903efbe}

Die zum Erstellen eines Datensatzes verwendeten Ereignisdaten befinden sich in Dateien, die als Protokollquellen bezeichnet werden. Die in den Protokollquellen verfügbaren Daten werden als Ereignisdaten bezeichnet, da jeder Datensatz einen Transaktionsdatensatz oder eine einzelne Instanz eines Ereignisses mit einem zugehörigen Zeitstempel darstellt.

Die Ereignisdaten einer Protokollquelle werden in Echtzeit von [!DNL Sensors] erfasst. Ereignisdaten, die von [!DNL Sensors] von HTTP- und Anwendungsservern erfasst werden, werden an Data Workbench-Server übertragen, die die Daten in komprimierte Protokolldateien ( [!DNL .vsl]) konvertieren. Ereignisdaten, die sich in einer reduzierten Datei, XML-Datei oder einer ODBC-Datenquelle befinden, werden vom Data Workbench-Server gelesen, der Decoder bereitstellt, die Sie definieren, um einen gemeinsamen Satz von Datenfeldern aus diesen verschiedenen Formaten zu extrahieren.

Die folgenden Abschnitte enthalten Informationen zu den Datenfeldern (Ereignisdatensatzfelder oder Protokolleingabefelder genannt), die von [!DNL Sensors] erfasst oder gelesen und dem Data Workbench-Server zur Verfügung gestellt werden.

>[!NOTE]
>
>Die Namen der Felder folgen im Allgemeinen der Namenskonvention für das erweiterte W3C-Protokolldateiformat. Viele Felder weisen auf die Quelle der im Feld enthaltenen Informationen hin:

* cs gibt die Kommunikation vom Client zum Server an.
* sc gibt die Kommunikation vom Server zum Client an.
* s zeigt Informationen vom Server an.
* c zeigt Informationen vom Client an.
* x zeigt Informationen an, die von einem Adobe-Softwareprodukt erstellt werden.

## Standardfelder für Ereignisdatensätze {#section-a882ed7aa6af41eeb45a55bf8c1ca3d7}

Protokolldateien ( [!DNL .vsl]) enthalten die Felder der Ereignisdaten, die von Servern von [!DNL Sensors] erfasst und vom Data Workbench-Server bei der Erstellung des Datensatzes verwendet werden. In der folgenden Tabelle sind die Felder in einem typischen Ereignisdatensatz aufgeführt, der von [!DNL Sensor] aufgezeichnet wurde:

<table id="table_98E135FE4EAF44D6ADEB3C6C1C0BF6A4">
 <thead>
  <tr>
   <th colname="col1" class="entry"> Feld </th>
   <th colname="col2" class="entry"> Beschreibung </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> c-ip </td>
   <td colname="col2"> <p>Die IP-Adresse des Clients, wie sie in der Anfrage an den Server enthalten ist. </p> <p> Beispiel: 207.68.146.68 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> cs(cookie) </td>
   <td colname="col2"> <p>Die vom Client mit der Anfrage gesendeten Cookies. </p> <p> Beispiel: v1st=42FDF66DE610CF36; ASPSESSIONIDQCATDAQC=GPIBKEIBFBFIPLOJMKCAAMPETIPP; </p> </td>
  </tr>
  <tr>
   <td colname="col1"> cs(referrer) </td>
   <td colname="col2"> <p>Die HTTP-Referrer-Zeichenfolge, die vom Client mit der Anfrage an den Server gesendet wird. </p> <p> Beispiel: <span class="filepath"> https://www.mysite.net/cgi-bin/websearch?qry </span> </p> </td>
  </tr>
  <tr>
   <td colname="col1"> cs(user-agent) </td>
   <td colname="col2"> <p>Die Zeichenfolge, die vom Client mit seiner Anfrage an den Server gesendet wird und angibt, welcher Typ von Benutzeragent der Client ist. </p> <p> Beispiel: Mozilla/5.0 (Windows; U; Windows NT 5.1; en-US; rv:1.7) Gecko/20040707 Firefox/0.9.2 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> cs-method </td>
   <td colname="col2"> <p>Der Methodentyp der HTTP-Anforderung. </p> <p> Beispiel: GET </p> <p> Referenz: <span class="filepath"> https://www.w3.org/TR/2000/NOTE-shoplogfileformat-20001115/#field_method </span> </p> </td>
  </tr>
  <tr>
   <td colname="col1"> cs-uri-query </td>
   <td colname="col2"> <p>Der Teil der Abfragezeichenfolge des URI (Stamm + Abfragezeichenfolge = URI). Diesem ist ein Fragezeichen (?) vorangestellt. und kann ein oder mehrere Name-Wert-Paare enthalten, die durch kaufmännische Und-Zeichen (&amp;) getrennt sind. </p> <p> Beispiel: page=homepage </p> </td>
  </tr>
  <tr>
   <td colname="col1"> cs-uri-system </td>
   <td colname="col2"> <p>Der Stammteil des URI (Stamm + Abfragezeichenfolge = URI). Der Stamm ist der tatsächliche oder logische Pfad zur angeforderten Ressource auf dem Server. </p> <p> Beispiel: <span class="filepath"> /index.asp </span> </p> </td>
  </tr>
  <tr>
   <td colname="col1"> sc(content-type) </td>
   <td colname="col2"> <p>Der Inhaltstyp der vom Client angeforderten Ressource, wie vom Server gemeldet. </p> <p> Beispiele: text/html, image/png, image/gif, video/mpeg </p> </td>
  </tr>
  <tr>
   <td colname="col1"> sc-bytes </td>
   <td colname="col2"> <p>Die Anzahl der Bytes an Daten, die vom Server an den Client als Antwort auf die Anfrage gesendet wurden </p> <p> Beispiel: 4996 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> sc-status </td>
   <td colname="col2"> <p>Der Statuscode, der vom Server an den Client zurückgegeben wird. </p> <p> Beispiel: 200 </p> <p> Referenz: <span class="filepath"> https://www.w3.org/Protocols/rfc2616/rfc2616-sec10.html </span> </p> </td>
  </tr>
  <tr>
   <td colname="col1"> s-dns </td>
   <td colname="col2"> <p>Der vollständig qualifizierte Domänenname oder die IP-Adresse des Hosts der angeforderten Ressource. </p> <p> Beispiel: <span class="filepath"> www.adobe.com </span> </p> </td>
  </tr>
  <tr>
   <td colname="col1"> x-experiment </td>
   <td colname="col2"> <p>Die Liste aller kontrollierten Experimentnamen und -gruppen, zu denen der Client zum Zeitpunkt der Anfrage gehört. </p> <p> Beispiel: VSHome_Exp.Group_1,VSRegistration_Exp.Group_2 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> x-timestamp </td>
   <td colname="col2"> <p>Datum und Uhrzeit (GMT), zu der die Anfrage beim Server empfangen wurde. Die Zeit wird als Anzahl von 100 Nanosekunden seit dem 1. Januar 1600 ausgedrückt. </p> <p> Beispiel: 127710989320000000 wäre der x-timestamp-Wert für 11:28:52.0000000 am Dienstag, 13. September 2005. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> x-trackingid </td>
   <td colname="col2"> <p>Der 64-Bit-Hexadezimalwert der eindeutigen Browser-Kennung, die in einem persistenten Cookie gefunden wird, wie von einem <span class="wintitle"> Sensor </span> festgelegt und vom Client mit einer Anfrage an einen Server bereitgestellt. </p> <p> Beispiel: 42FDF66DE610CF36 </p> </td>
  </tr>
 </tbody>
</table>

## Abgeleitete Felder {#section-b6c57ee2aa31469fbd5dab90e52bc677}

In der folgenden Tabelle finden Sie Beispiele für Felder, die vom Data Workbench-Server aus den Datensatzfeldern für die Basisereignisse abgeleitet werden:

<table id="table_3B008F1314804A69AE69E8F94908F497">
 <thead>
  <tr>
   <th colname="col1" class="entry"> Feld </th>
   <th colname="col2" class="entry"> Beschreibung </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> cs(cookie)(name) </td>
   <td colname="col2"> Der Wert eines angegebenen Name-Wert-Paares in einem Cookie. </td>
  </tr>
  <tr>
   <td colname="col1"> cs(referrer-domain) </td>
   <td colname="col2"> <p>Der Domänenname oder die IP-Adresse des HTTP-Referrer-URI. </p> <p> <p>Hinweis:  Dieses Feld ist schreibgeschützt. </p> </p> </td>
  </tr>
  <tr>
   <td colname="col1"> cs(referrer-host) </td>
   <td colname="col2"> <p>Der gesamte Hostname des Referrers. </p> <p> Beispiel: Wenn cs(referrer) <span class="filepath"> https://my.domain.com/my/page </span> ist, ist cs(referrer-host) <span class="filepath"> my.domain.com </span>. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> cs(referrer-query)(name) </td>
   <td colname="col2"> <p>Der -Wert einer Abfragezeichenfolge des Referrers. </p> <p> <p>Hinweis:  Sie können nicht mit dem Feld cs(referrer)(name) auf einen Abfragezeichenfolgenwert des Referrers zugreifen. </p> </p> </td>
  </tr>
  <tr>
   <td colname="col1"> cs-uri </td>
   <td colname="col2"> <p>Der vollständige URI (Stamm + Abfragezeichenfolge = gesamter URI). </p> <p> Beispiel: <span class="filepath"> /shopping/checkout.html?product1=8Track&amp;product2=casette&amp;product3=cd </span> </p> </td>
  </tr>
  <tr>
   <td colname="col1"> cs-uri-query(name) </td>
   <td colname="col2"> <p>Der mit dem angegebenen Namen verknüpfte Wert. Wenn für den angegebenen Namen mehrere Werte vorhanden sind, gibt dieses Feld den letzten dieser Werte zurück. </p> Beispiele:
    <ul id="ul_47BBB2E3076A46629BFCDB2A460F700B">
     <li id="li_AC9BB29505A54AE4AFF49438530C9EA4"> Für den URI <span class="filepath"> /shopping/checkout.html?product1=8Track&amp;product2=casette&amp;product3=cd </span> gibt cs-uri-query(product3) cd zurück. </li>
     <li id="li_B036C1D0B25748E0A155DDC9B1B999CB"> Für den URI <span class="filepath"> /shopping/checkout.html?product1=8Track&amp;product1=casette </span> gibt <span class="wintitle"> cs-uri-query(product1) </span> eine Casette zurück. </li>
    </ul> <p> </p> </td>
  </tr>
  <tr>
   <td colname="col1"> ctime </td>
   <td colname="col2"> x-timestamp, ausgedrückt als Sekunden seit dem 1. Januar 1970. Dieses Feld wird auch als x-unixtime bezeichnet. </td>
  </tr>
  <tr>
   <td colname="col1"> Datum </td>
   <td colname="col2"> x-timestamp im Format JJJJ-MM-TT. </td>
  </tr>
  <tr>
   <td colname="col1"> time </td>
   <td colname="col2"> x-timestamp im Format HH:MM:SS. </td>
  </tr>
  <tr>
   <td colname="col1"> x-local-timestring </td>
   <td colname="col2"> <p>x-timestamp konvertiert in die lokale Zeitzone, die in der Datei <span class="filepath"> Transformation.cfg </span> für den Datensatz angegeben ist. Das Format lautet JJJ-MM-TT HH:MM:SS.mmm. </p> <p> <p>Hinweis:  Sie können auch Zeitkonvertierungen wie x-local-timestring in der Datei <span class="filepath"> Log Processing.cfg </span> definieren. Weitere Informationen finden Sie unter <a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md"> Konfigurationsdatei für die Protokollverarbeitung </a>. </p> </p> </td>
  </tr>
  <tr>
   <td colname="col1"> x-log-source-id </td>
   <td colname="col2"> <p>Die Kennung, die der Protokollquelle für einen bestimmten Protokolleintrag entspricht. Damit die Kennung aufgezeichnet werden kann, müssen Sie sie im Feld <span class="wintitle"> Protokollquellen-ID </span> der Datei <span class="filepath"> Protokollverarbeitung.cfg </span> angeben, wenn Sie <span class="wintitle"> Sensor </span>, Protokolldatei oder ODBC-Datenquellen definieren. Weitere Informationen finden Sie unter <a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md"> Konfigurationsdatei für die Protokollverarbeitung </a>. </p> <p> Beispiel: von VSensor01. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> x-mask </td>
   <td colname="col2"> Das Maskenmuster der <span class="wintitle"> Sensor </span>-Datenquellen (abgeleitet aus den Dateinamen <span class="filepath"> .vsl </span> ). Für eine Datei mit dem Namen <span class="filepath"> YYYYMMDD-SENSORID.VSL </span> ist x-mask SENSORID. </td>
  </tr>
  <tr>
   <td colname="col1"> x-timestring </td>
   <td colname="col2"> x-timestamp im Format JJJJ-MM-TT HH:MM:SS.mmm. </td>
  </tr>
  <tr>
   <td colname="col1"> x-unixtime </td>
   <td colname="col2"> Die UNIX-Dezimalzeit, die von x-timestamp abgeleitet wurde. </td>
  </tr>
 </tbody>
</table>

[!DNL Sensor], kann bei Verwendung auf einem Server Ereignisdatenfelder aus jeder gültigen HTTP-Anfrage-, Antwort-Header oder -Variablen erfassen, die über die Server-API für diesen verfügbar sind. Um solche Datenfelder zu erfassen, müssen Sie die gewünschten Kopfzeilenfelder oder Variablen in der Konfigurationsdatei [!DNL txlogd.conf]für [!DNL Sensor] angeben. Weitere Informationen finden Sie in der *Data Workbench [!DNL Sensor] Guide*.
