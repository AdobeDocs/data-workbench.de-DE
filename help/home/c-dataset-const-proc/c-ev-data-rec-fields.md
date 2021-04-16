---
description: Informationen zu den Datenfeldern, die der Data Workbench-Server zum Erstellen eines Datensatzes verarbeiten kann.
title: Felder für Ereignisdatensätze
uuid: b0232bfa-0a3b-4e3d-876e-6a15a3764eae
exl-id: 35433b87-991a-4fb9-ba6a-3217e89eb769
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1092'
ht-degree: 2%

---

# Felder für Ereignisdatensätze{#event-data-record-fields}

Informationen zu den Datenfeldern, die der Data Workbench-Server zum Erstellen eines Datensatzes verarbeiten kann.

* [Info zu Ereignis-Daten](../../home/c-dataset-const-proc/c-ev-data-rec-fields.md#section-3a0705f8c1824017aa4effed9903efbe)
* [Standardfelder für Ereignisdatensätze](../../home/c-dataset-const-proc/c-ev-data-rec-fields.md#section-a882ed7aa6af41eeb45a55bf8c1ca3d7)
* [Abgeleitete Felder](../../home/c-dataset-const-proc/c-ev-data-rec-fields.md#section-b6c57ee2aa31469fbd5dab90e52bc677)

## Info zu Ereignis-Daten {#section-3a0705f8c1824017aa4effed9903efbe}

Die zum Erstellen eines Datensatzes verwendeten Ereignis-Daten befinden sich in Dateien, die als Protokollquellen bezeichnet werden. Die in den Protokollquellen verfügbaren Daten werden als Ereignis-Daten bezeichnet, da jeder Datensatz einen Transaktionssatz oder eine Instanz eines Ereignisses mit einem zugehörigen Zeitstempel darstellt.

Die Ereignis-Daten einer Protokollquelle werden in Echtzeit von [!DNL Sensors] erfasst. Von den HTTP- und Anwendungsservern erfasste Ereignis-Daten werden an die Data Workbench-Server übertragen, die die Daten in komprimierte Protokolldateien ( [!DNL .vsl]) konvertieren. [!DNL Sensors] Ereignis-Daten, die sich in einer einfachen Datei, XML-Datei oder einer ODBC-Datenquelle befinden, werden vom Data Workbench-Server gelesen, der Dekodierer bereitstellt, die Sie definieren, um einen gemeinsamen Satz von Datenfeldern aus diesen verschiedenen Formaten zu extrahieren.

Die folgenden Abschnitte enthalten Informationen zu den Datenfeldern (Ereignis Data Record Field oder Log Entry Field), die von [!DNL Sensors] erfasst oder gelesen und dem Data Workbench-Server zur Verfügung gestellt werden.

>[!NOTE]
>
>Die Namen der Felder entsprechen im Allgemeinen den Benennungsregeln für das erweiterte Protokolldateiformat des W3C. Viele Felder haben Präfixe, die die Quelle der im Feld enthaltenen Informationen angeben:

* cs gibt die Kommunikation vom Client zum Server an.
* sc gibt die Kommunikation vom Server mit dem Client an.
* s zeigt Informationen vom Server an.
* c zeigt Informationen vom Client an.
* x zeigt Informationen an, die von einem Softwareprodukt der Adobe erstellt werden.

## Standardfelder für Ereignisdatensätze {#section-a882ed7aa6af41eeb45a55bf8c1ca3d7}

Protokolldateien ( [!DNL .vsl]) enthalten die Ereignis-Datenfelder, die von [!DNL Sensors] von Servern gesammelt und vom Data Workbench-Server bei der Datensatzerstellung verwendet werden. In der folgenden Tabelle werden die Felder in einem typischen Ereignis-Datensatz, wie von [!DNL Sensor] aufgezeichnet, Liste:

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
   <td colname="col2"> <p>Die IP-Adresse des Clients, wie sie in der an den Server gerichteten Anforderung enthalten ist. </p> <p> Beispiel: 207.68.146.68 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(cookie) </td> 
   <td colname="col2"> <p>Die Cookies, die vom Client mit der Anforderung gesendet werden. </p> <p> Beispiel: v1st=42FDF66DE610CF36; ASPSESSIONIDQCATDAQC=GPIBKEIBFBFIPLOJMKCAAMPEG; </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(Werber) </td> 
   <td colname="col2"> <p>Die HTTP-Werber-Zeichenfolge, die vom Client mit der Anforderung an den Server gesendet wird. </p> <p> Beispiel: <span class="filepath"> http://www.mysite.net/cgi-bin/websearch?qry </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(user-agent) </td> 
   <td colname="col2"> <p>Die vom Client gesendete Zeichenfolge mit der an den Server gerichteten Anforderung, die angibt, welcher Typ von Benutzeragent der Client ist. </p> <p> Beispiel: Mozilla/5.0 (Windows) U; Windows NT 5.1; en-US; rv:1.7) Gecko/20040707 Firefox/0.9.2 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-method </td> 
   <td colname="col2"> <p>Der Methodentyp der HTTP-Anforderung. </p> <p> Beispiel: GET </p> <p> Referenz: <span class="filepath"> http://www.w3.org/TR/2000/NOTE-shoplogfileformat-20001115/#field_method </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-uri-Abfrage </td> 
   <td colname="col2"> <p>Der Abfrage-String-Teil des URI (Stamm + Abfrage-Zeichenfolge = URI). Dem wird ein Fragezeichen vorangestellt (?) und kann ein oder mehrere durch kaufmännische Und-Zeichen (&amp;) getrennte Name-Wert-Paare enthalten. </p> <p> Beispiel: page=homepage </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-uri-stamm </td> 
   <td colname="col2"> <p>Der Stammteil von URI (Stamm + Abfrage string = URI). Der Stamm ist der tatsächliche oder logische Pfad zur angeforderten Ressource auf dem Server. </p> <p> Beispiel: <span class="filepath"> /index.asp </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> sc(content-type) </td> 
   <td colname="col2"> <p>Der Inhaltstyp der Ressource, die vom Client angefordert wird, wie vom Server gemeldet. </p> <p> Beispiele: text/html, image/png, image/gif, video/mpeg </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> sc-bytes </td> 
   <td colname="col2"> <p>Die Anzahl der Datenbyte, die vom Server an den Client als Antwort auf die Anforderung gesendet wird </p> <p> Beispiel: 4996 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> sc-status </td> 
   <td colname="col2"> <p>Der Statuscode, der vom Server an den Client zurückgegeben wird. </p> <p> Beispiel: 200 </p> <p> Referenz: <span class="filepath"> http://www.w3.org/Protocols/rfc2616/rfc2616-sec10.html </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> s-dns </td> 
   <td colname="col2"> <p>Der vollständig qualifizierte Domänenname oder die IP-Adresse des Hosts der angeforderten Ressource. </p> <p> Beispiel: <span class="filepath"> www.adobe.com </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> x-experiment </td> 
   <td colname="col2"> <p>Die Liste aller kontrollierten Experimentnamen und -gruppen, zu denen der Client zum Zeitpunkt der Anforderung gehört. </p> <p> Beispiel: VSHome_Exp.Group_1,VSRegistration_Exp.Group_2 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> x-timestamp </td> 
   <td colname="col2"> <p>Datum und Uhrzeit (GMT), zu der die Anforderung beim Server einging. Die Zeit wird als die Anzahl von 100 Nanosekunden seit dem 1. Januar 1600 ausgedrückt. </p> <p> Beispiel: 127710989320000000 wäre der X-timestamp-Wert für 11:28:52.00000000 am Dienstag, 13. September 2005. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> x-trackingid </td> 
   <td colname="col2"> <p>Der 64-Bit-Hexadezimalwert der eindeutigen Browser-ID, der in einem beständigen Cookie gefunden wird, wie er von einem <span class="wintitle">-Sensor </span> festgelegt und vom Client mit einer Anforderung an einen Server bereitgestellt wird. </p> <p> Beispiel: 42FDF66DE610CF36 </p> </td> 
  </tr> 
 </tbody> 
</table>

## Abgeleitete Felder {#section-b6c57ee2aa31469fbd5dab90e52bc677}

In der folgenden Tabelle sind Beispiele für Listen aufgeführt, die vom Data Workbench-Server aus den Datendatensatzfeldern des BasisEreignisses abgeleitet wurden:

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
   <td colname="col2"> Der Wert eines gegebenen Namens-Wert-Paars in einem Cookie. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(Werber-domain) </td> 
   <td colname="col2"> <p>Der Domänenname oder die IP-Adresse des HTTP-Referrer-URI. </p> <p> <p>Hinweis:  Dieses Feld ist schreibgeschützt. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(Werber-Host) </td> 
   <td colname="col2"> <p>Der gesamte Hostname des Werbers. </p> <p> Beispiel: Wenn cs(Werber) <span class="filepath"> http://my.domain.com/my/page </span> lautet, ist cs(Werber-host) <span class="filepath"> my.domain.com </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(Werber-Abfrage)(name) </td> 
   <td colname="col2"> <p>Der Wert einer Abfrage des Werbers. </p> <p> <p>Hinweis:  Sie können nicht mit dem Feld cs(Werber)(name) auf einen Zeichenfolgenwert für die Abfrage eines Werbers zugreifen. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-uri </td> 
   <td colname="col2"> <p>Der vollständige URI (Stamm + Abfrage-String = gesamter URI). </p> <p> Beispiel: <span class="filepath"> /shopping/checkout.html?product1=8Track&amp;product2=casette&amp;product3=cd </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-uri-Abfrage(name) </td> 
   <td colname="col2"> <p>Der mit dem angegebenen Namen verknüpfte Wert. Wenn mehrere Werte für den angegebenen Namen vorhanden sind, gibt dieses Feld den letzten dieser Werte zurück. </p> Beispiele: 
    <ul id="ul_47BBB2E3076A46629BFCDB2A460F700B"> 
     <li id="li_AC9BB29505A54AE4AFF49438530C9EA4"> Für den URI <span class="filepath"> /shopping/checkout.html?product1=8Track&amp;product2=casette&amp;product3=cd </span> gibt cs-uri-Abfrage(product3) cd zurück. </li> 
     <li id="li_B036C1D0B25748E0A155DDC9B1B999CB"> Für den URI <span class="filepath"> /shopping/checkout.html?product1=8Track&amp;product1=casette </span> gibt <span class="wintitle"> cs-uri-Abfrage(product1) </span> ein Casette zurück. </li> 
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
   <td colname="col2"> <p>x-timestamp, konvertiert in die lokale Zeitzone, die in der Datei <span class="filepath"> Transformation.cfg </span> für den Datensatz angegeben ist. Das Format ist JJJ-MM-TT HH:MM:SS.mmm. </p> <p> <p>Hinweis:  Sie können auch Zeitkonvertierungen wie x-local-timestring in der Datei <span class="filepath"> Log Processing.cfg </span> definieren. Weitere Informationen finden Sie unter <a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md"> Protokollverarbeitungskonfigurationsdatei </a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> x-log-source-id </td> 
   <td colname="col2"> <p>Die Kennung, die der Protokollquelle für einen bestimmten Protokolleintrag entspricht. Damit der Bezeichner aufgezeichnet werden kann, müssen Sie ihn im Feld <span class="wintitle"> Protokollquellen-ID </span> der Datei <span class="filepath"> Protokollverarbeitung.cfg </span> angeben, wenn Sie <span class="wintitle"> Sensor </span>, Protokolldatei oder ODBC-Datenquellen definieren. Weitere Informationen finden Sie unter <a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md"> Protokollverarbeitungskonfigurationsdatei </a>. </p> <p> Beispiel: von VSensor01. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> x-mask </td> 
   <td colname="col2"> Das Maskenmuster der Datenquellen <span class="wintitle"> Sensor </span> (abgeleitet aus den <span class="filepath"> .vsl </span>-Dateinamen). Bei einer Datei, deren Name im Format <span class="filepath"> YYYYMMDD-SENSORID.VSL </span> lautet, ist x-mask SENSORID. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> x-timestring </td> 
   <td colname="col2"> x-timestamp im Format JJJJ-MM-TT HH:MM:SS.mmm. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> x-unixtime </td> 
   <td colname="col2"> Die UNIX-Dezimalzeit, die von x-timestamp abgeleitet wird. </td> 
  </tr> 
 </tbody> 
</table>

[!DNL Sensor]kann bei Verwendung auf einem Server Ereignis-Datenfelder aus allen gültigen HTTP-Anforderungen, Antwortkopfzeilen oder -Variablen erfassen, die über die Server-API verfügbar sind. Um solche Datenfelder zu erfassen, müssen Sie die gewünschten Kopfzeilenfelder oder Variablen in der Konfigurationsdatei [!DNL txlogd.conf]für [!DNL Sensor] angeben. Weitere Informationen finden Sie unter *Data Workbench [!DNL Sensor] Guide*.
