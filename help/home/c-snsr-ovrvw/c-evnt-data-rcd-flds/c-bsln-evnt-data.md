---
description: Informationen zu Datensatzfeldern zu Basisereignissen, die vom Sensor aufgezeichnet wurden.
solution: Insight
title: Felder für Ereignisdatensätze als Basiswert
uuid: aa36d332-089c-4ae2-98e2-a93d2fa023b7
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Felder für Ereignisdatensätze als Basiswert{#baseline-event-data-record-fields}

Informationen zu Datensatzfeldern zu Basisereignissen, die vom Sensor aufgezeichnet wurden.

<table id="table_E29606BB010E4DB48C463979B7BEC769"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Feld </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> c-ip </td> 
   <td colname="col2"> <p>Die IP-Adresse des Clients, wie sie in der an den Server gerichteten Anforderung enthalten ist. </p> <p>Beispiel: 207.68.146.68 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(cookie) </td> 
   <td colname="col2"> <p>Die Cookies, die vom Client mit der Anforderung gesendet werden. </p> <p>Beispiel: v1st=42FDF66DE610CF36; ASPSESSIONIDQCATDAQC=GPIBKEIBFBFIPLOJMKCAAMPEG; </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(referrer) </td> 
   <td colname="col2"> <p>Die vom Client mit der Anforderung an den Server gesendete HTTP-Referrer-Zeichenfolge. </p> <p>Beispiel: http://www.mysite.net/cgi-bin/websearch?qry </p> <p>Wenn Sie Seiten-Tags verwenden, ist die cs(referrer) die vollständige URL des Dokuments, das das Tag-Bild enthält, einschließlich HTTP oder HTTPs. </p> <p>Außerdem können Sie die Apache- (1.3, 2.0 und 2.2) und IIS-Sensoren so konfigurieren, dass der für die Anforderung verwendete Anschluss erfasst wird, der HTTP- und HTTPS-Anforderungen identifizieren kann. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(user-agent) </td> 
   <td colname="col2"> <p>Die vom Client gesendete Zeichenfolge mit der an den Server gerichteten Anforderung, die angibt, welcher Typ von Benutzeragent der Client ist. </p> <p>Beispiel: Mozilla/5.0 (Windows) U; Windows NT 5.1; en-US; rv:1.7) Gecko/20040707 Firefox/0.9.2 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-method </td> 
   <td colname="col2"> <p>Der Methodentyp der HTTP-Anforderung </p> <p>Beispiel: GET </p> <p>Referenz: http://www.w3.org/TR/2000/NOTE-shoplogfileformat-20001115/#field_method </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-uri-query </td> 
   <td colname="col2"> <p>Der Abfragezeichenfolgen-Teil des URI (Stamm + Abfragezeichenfolge = URI) </p> <p>Dem wird ein Fragezeichen vorangestellt (?) und kann ein oder mehrere durch kaufmännische Und-Zeichen (&amp;) getrennte Name-Wert-Paare enthalten. </p> <p>Beispiel: page=homepage </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-uri-stamm </td> 
   <td colname="col2"> <p>Der Stammteil von URI (Stamm + Abfragezeichenfolge = URI) </p> <p>Der Stamm ist der tatsächliche oder logische Pfad zur angeforderten Ressource auf dem Server. </p> <p>Beispiel: /index.asp </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> sc(content-type) </td> 
   <td colname="col2"> <p>Der Inhaltstyp der Ressource, die vom Client angefordert wird, wie vom Server gemeldet. </p> <p>Beispiele: text/html, image/png, image/gif, video/mpeg </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> sc-bytes </td> 
   <td colname="col2"> <p>Die Anzahl der Byte an Daten, die vom Server an den Client als Antwort auf die Anforderung gesendet werden. </p> <p>Beispiel: 4996 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> sc-status </td> 
   <td colname="col2"> <p>Der Statuscode, der vom Server an den Client zurückgegeben wird. </p> <p>Beispiel: 200 </p> <p>Referenz: http://www.w3.org/Protocols/rfc2616/rfc2616-sec10.html </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> s-dns </td> 
   <td colname="col2"> <p>Der vollständig qualifizierte Domänenname oder die IP-Adresse des Hosts der angeforderten Ressource. </p> <p>Beispiel: www.omniture.com </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> x-experiment </td> 
   <td colname="col2"> <p>Die Liste aller kontrollierten Experimentnamen und -gruppen, zu denen der Client zum Zeitpunkt der Anforderung gehört. </p> <p>Beispiel: Home_Exp.group_1,registration_exp.group_2 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> x-timestamp </td> 
   <td colname="col2"> <p>Datum und Uhrzeit (GMT), zu der die Anforderung beim Server einging. </p> <p>Die Zeit wird als die Anzahl von 100 Nanosekunden seit dem 1. Januar 1600 ausgedrückt. </p> <p>Beispiel: 127710989320000000 wäre der X-timestamp-Wert für 11:28:52.00000000 am Dienstag, 13. September 2005. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> x-trackingid </td> 
   <td colname="col2"> <p>Der 64-Bit-Hexadezimalwert der eindeutigen Browserkennung, der in einem beständigen Cookie gefunden wird, wie von einem <span class="wintitle"> Sensor festgelegt </span> und vom Client mit einer Anforderung an einen Server bereitgestellt. </p> <p>Beispiel: 42FDF66DE610CF36 </p> </td> 
  </tr> 
 </tbody> 
</table>

Die Variable [!DNL data workbench server] kann eine Reihe von Variablen aus den Datensatzfeldern für Basisereignisse ableiten. For more information, see the *Dataset Configuration Guide*.
