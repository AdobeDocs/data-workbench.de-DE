---
description: Sensor erfasst alle Messdaten, die bei Seitenanfragen (GET) an die Webserver gesendet werden, auf denen er installiert wurde.
title: Erfassen von Daten zu Seitenanfragen
uuid: 06cf2b14-8d2c-483e-8a75-ce772798978f
exl-id: e42566a3-d5b4-4f1a-b8cd-1ea646041101
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '575'
ht-degree: 4%

---

# Erfassen von Daten zu Seitenanfragen{#acquiring-page-request-data}

Sensor erfasst alle Messdaten, die bei Seitenanfragen (GET) an die Webserver gesendet werden, auf denen er installiert wurde.

[!DNL Sensor] erfasst diese Messungsdaten über die Anwendungsprogrammierschnittstelle des Webservers, direkt von der oder den Instanzen der Webserver-Software, die auf Ihrem Webserver ausgeführt wird. [!DNL Sensor] greift nicht auf die vom Webserver generierten Protokolldateien zu. Nachdem [!DNL Sensor] und der Data Workbench-Server installiert und getestet wurden, kann die native Protokollierungsfunktion des Webservers deaktiviert werden, ohne dass dies die Datenerfassung beeinträchtigt. In vielen Fällen verbessert die Deaktivierung der Dateiprotokollierung auf den lokalen Festplatten der Webserver-Computer die Seitenbereitstellungskapazität dieser Webserver, da eine relativ große Menge an festem Datenträger-I/O erforderlich ist, um diese Informationen auf dem lokalen Datenträger des Webservercomputers zu protokollieren.

[!DNL Sensor] erfasst Mess- und Webanforderungsdaten direkt von jedem Webserverprozess und virtuellen Webserverprozess (falls zutreffend) und schreibt die Daten zeitweise in eine Warteschlange, eine fehlertolerante Speicherwarteschlange mit festem Datenträger-Backup, auf dem Webserver-Computer. Der Sensor Transmitter-Dienst (oder je nach Plattform Daemon) ruft Daten aus der Warteschlangendatei ab und komprimiert sie dann und verschlüsselt sie, bevor sie für eine langfristige Datenspeicherung an den Data Workbench-Server übermittelt werden. Mit [!DNL Sensor] werden Daten nur dann auf Ihren Webservercomputern in der Warteschlange-Datei gespeichert, wenn Sie ein Netzwerk- oder ein anderes Problem haben, das die Übertragung verhindert. Die Warteschlangendatei ermöglicht eine effiziente lokale Datenspeicherung von Stunden- bis Wochentagen von Webanforderungsdaten, um die Daten zu schützen, wenn ein Netzwerk- oder Systemfehler die Übertragung der Daten an den Data Workbench-Server nicht in Echtzeit zulässt.

[!DNL Sensor] erfasst Messungsdaten aus jedem physischen und logischen Webserverprozess, Filter sie nach Inhaltstyp, komprimiert sie, verschlüsselt sie und sendet sie an den Data Workbench-Server.

Die folgende Tabelle enthält die Felder mit Protokollinformationen, die von [!DNL Sensor] für jede nicht auf der Grundlage der Konfigurationsdatei [!DNL Sensor’s] herausgefilterte GET erfasst werden:

<table id="table_5F65474150EC41648B35D0B031FB9B15"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> W3C-Name </th> 
   <th colname="col2" class="entry"> Erfasste Daten </th> 
   <th colname="col3" class="entry"> Erklärung </th> 
   <th colname="col4" class="entry"> Erklärung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> x-trackingid </td> 
   <td colname="col2"> Tracking-ID (eindeutiger Besucher) </td> 
   <td colname="col3"> Bezeichner, der von einem Cookie gelesen wird, das bei der ursprünglichen Anforderung des Besuchers im Browser des Benutzers von <span class="wintitle"> Sensor </span> platziert wurde </td> 
   <td colname="col4"> V1st=3C94007B4E01F9C2 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Datum </p> <p>Zeit </p> </td> 
   <td colname="col2"> Zeitstempel </td> 
   <td colname="col3"> Zeitpunkt, zu dem die Anforderung vom Server verarbeitet wurde (mit 100 ns Genauigkeit; Genauigkeit hängt von der Umgebung des Servers und NTP ab. </td> 
   <td colname="col4"> 2002-11-21 17:21:45.123 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> sc(content-type) </td> 
   <td colname="col2"> Content-Typ </td> 
   <td colname="col3"> Vom Server zurückgegebener Objekttyp </td> 
   <td colname="col4"> text/html </td> 
  </tr> 
  <tr> 
   <td colname="col1"> sc-status </td> 
   <td colname="col2"> HTTP-Antwortstatuscode </td> 
   <td colname="col3"> Vom Server generierter numerischer Code, der den Status der Antwort des HTTP-Servers angibt </td> 
   <td colname="col4"> 404 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-uri-stamm </td> 
   <td colname="col2"> URI-Stamm </td> 
   <td colname="col3"> Der vom Client angeforderte Stammteil des URI </td> 
   <td colname="col4"> <span class="filepath"> pagedir/page.asp  </span> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> c-ip </td> 
   <td colname="col2"> Client-IP </td> 
   <td colname="col3"> IP-Adresse des anfordernden Kunden </td> 
   <td colname="col4"> 127,0,0,1 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> s-dns </td> 
   <td colname="col2"> Servername </td> 
   <td colname="col3"> Domänenname des Webservers, der die Anforderung verarbeitet </td> 
   <td colname="col4"> <span class="filepath"> www.domain.com  </span> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(Werber) </td> 
   <td colname="col2"> Verweisende URL </td> 
   <td colname="col3"> Inhalt des vom Client gesendeten HTTP-Werber-Felds </td> 
   <td colname="col4"> <span class="filepath"> http://www.referringsite.com  </span> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(user-agent) </td> 
   <td colname="col2"> Benutzeragent </td> 
   <td colname="col3"> Gerät, das zum Anfordern an den HTTP-Server verwendet wird </td> 
   <td colname="col4"> Mozilla/4.0+(kompatibel;+MSIE+6.0; +Windows+NT+5.1) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(cookie) </td> 
   <td colname="col2"> Client-Cookies von Domäne </td> 
   <td colname="col3"> Inhalt aller Cookies des Benutzers für die Site </td> 
   <td colname="col4"> <p>KL_TC1 1038058778312 </p> <p>KL972x1038058778312282052 </p> <p>KL_PVKL972 0 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-uri-Abfrage </td> 
   <td colname="col2"> Abfragezeichenfolge </td> 
   <td colname="col3"> Der vom Client angeforderte Teil der vom Client angeforderten Abfrage-Zeichenfolge </td> 
   <td colname="col4"> PAGENAME=dynamic1&amp;link=3001 </td> 
  </tr> 
 </tbody> 
</table>
