---
description: Informationen zu den vom Sensor aufgezeichneten Grundlinien-Ereignisdatensatzfeldern.
title: Standardfelder für Ereignisdatensätze
uuid: aa36d332-089c-4ae2-98e2-a93d2fa023b7
exl-id: ad3d8806-863a-4871-a35b-6680163f00ac
source-git-commit: 79981e92dd1c2e552f958716626a632ead940973
workflow-type: tm+mt
source-wordcount: '461'
ht-degree: 3%

---

# Standardfelder für Ereignisdatensätze{#baseline-event-data-record-fields}

Informationen zu den vom Sensor aufgezeichneten Grundlinien-Ereignisdatensatzfeldern.

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
   <td colname="col2"> <p>Die IP-Adresse des Clients, wie sie in der Anfrage an den Server enthalten ist. </p> <p>Beispiel: 207.68.146.68 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> cs(cookie) </td>
   <td colname="col2"> <p>Die vom Client mit der Anfrage gesendeten Cookies. </p> <p>Beispiel: v1st=42FDF66DE610CF36; ASPSESSIONIDQCATDAQC=GPIBKEIBFBFIPLOJMKCAAMPETIPP; </p> </td>
  </tr>
  <tr>
   <td colname="col1"> cs(referrer) </td>
   <td colname="col2"> <p>Die HTTP-Referrer-Zeichenfolge, die vom Client mit der Anfrage an den Server gesendet wird. </p> <p>Beispiel: https://www.mysite.net/cgi-bin/websearch?qry </p> <p>Wenn Sie Seiten-Tags verwenden, ist cs (referrer) die vollständige URL des Dokuments, das das Tag-Bild enthält, einschließlich HTTP oder HTTPs. </p> <p>Außerdem können Sie Apache (1.3, 2.0 und 2.2)- und IIS-Sensoren konfigurieren, um den für die Anfrage verwendeten Port zu erfassen, der HTTP- oder HTTPS-Anforderungen identifizieren kann. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> cs(user-agent) </td>
   <td colname="col2"> <p>Die Zeichenfolge, die vom Client mit seiner Anfrage an den Server gesendet wird und angibt, welcher Typ von Benutzeragent der Client ist. </p> <p>Beispiel: Mozilla/5.0 (Windows; U; Windows NT 5.1; en-US; rv:1.7) Gecko/20040707 Firefox/0.9.2 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> cs-method </td>
   <td colname="col2"> <p>Der Methodentyp der HTTP-Anforderung </p> <p>Beispiel: GET </p> <p>Referenz: https://www.w3.org/TR/2000/NOTE-shoplogfileformat-20001115/#field_method </p> </td>
  </tr>
  <tr>
   <td colname="col1"> cs-uri-query </td>
   <td colname="col2"> <p>Der Abfragezeichenfolgen-Teil des URI (Stamm + Abfragezeichenfolge = URI) </p> <p>Diesem ist ein Fragezeichen (?) vorangestellt. und kann ein oder mehrere Name-Wert-Paare enthalten, die durch kaufmännische Und-Zeichen (&amp;) getrennt sind. </p> <p>Beispiel: page=homepage </p> </td>
  </tr>
  <tr>
   <td colname="col1"> cs-uri-system </td>
   <td colname="col2"> <p>Der Stammteil des URI (Stamm + Abfragezeichenfolge = URI) </p> <p>Der Stamm ist der tatsächliche oder logische Pfad zur angeforderten Ressource auf dem Server. </p> <p>Beispiel: /index.asp </p> </td>
  </tr>
  <tr>
   <td colname="col1"> sc(content-type) </td>
   <td colname="col2"> <p>Der Inhaltstyp der vom Client angeforderten Ressource, wie vom Server gemeldet. </p> <p>Beispiele: text/html, image/png, image/gif, video/mpeg </p> </td>
  </tr>
  <tr>
   <td colname="col1"> sc-bytes </td>
   <td colname="col2"> <p>Die Anzahl der Bytes an Daten, die vom Server an den Client als Antwort auf die Anfrage gesendet wurden. </p> <p>Beispiel: 4996 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> sc-status </td>
   <td colname="col2"> <p>Der Statuscode, der vom Server an den Client zurückgegeben wird. </p> <p>Beispiel: 200 </p> <p>Referenz: https://www.w3.org/Protocols/rfc2616/rfc2616-sec10.html </p> </td>
  </tr>
  <tr>
   <td colname="col1"> s-dns </td>
   <td colname="col2"> <p>Der vollständig qualifizierte Domänenname oder die IP-Adresse des Hosts der angeforderten Ressource. </p> <p>Beispiel: www.omniture.com </p> </td>
  </tr>
  <tr>
   <td colname="col1"> x-experiment </td>
   <td colname="col2"> <p>Die Liste aller kontrollierten Experimentnamen und -gruppen, zu denen der Client zum Zeitpunkt der Anfrage gehört. </p> <p>Beispiel: home_exp.group_1,registration_exp.group_2 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> x-timestamp </td>
   <td colname="col2"> <p>Datum und Uhrzeit (GMT), zu der die Anfrage beim Server empfangen wurde. </p> <p>Die Zeit wird als Anzahl von 100 Nanosekunden seit dem 1. Januar 1600 ausgedrückt. </p> <p>Beispiel: 127710989320000000 wäre der x-timestamp-Wert für 11:28:52.0000000 am Dienstag, 13. September 2005. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> x-trackingid </td>
   <td colname="col2"> <p>Der 64-Bit-Hexadezimalwert der eindeutigen Browser-Kennung, die in einem persistenten Cookie gefunden wird, wie von einem <span class="wintitle"> Sensor </span> festgelegt und vom Client mit einer Anfrage an einen Server bereitgestellt. </p> <p>Beispiel: 42FDF66DE610CF36 </p> </td>
  </tr>
 </tbody>
</table>

Der [!DNL data workbench server] kann eine Reihe von Variablen aus den Datensatzfeldern für das Basisereignis ableiten. Weitere Informationen finden Sie im *Handbuch zur Datensatzkonfiguration*.
