---
description: Der Sensor erfasst alle Messdaten, die bei Seitenanfragen (GET-Anfragen) an die Webserver übertragen werden, auf denen er installiert ist.
title: Erfassen von Daten zu Seitenanfragen
uuid: 06cf2b14-8d2c-483e-8a75-ce772798978f
exl-id: e42566a3-d5b4-4f1a-b8cd-1ea646041101
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '575'
ht-degree: 4%

---

# Erfassen von Daten zu Seitenanfragen{#acquiring-page-request-data}

Der Sensor erfasst alle Messdaten, die bei Seitenanfragen (GET-Anfragen) an die Webserver übertragen werden, auf denen er installiert ist.

[!DNL Sensor] erfasst diese Messdaten über die Anwendungsprogrammierschnittstelle des Webservers, direkt von der oder den Instanzen der Webserver-Software, die auf Ihrem Webserver ausgeführt wird. [!DNL Sensor] greift nicht auf die vom Webserver generierten Protokolldateien zu. Nachdem [!DNL Sensor] installiert und der Data Workbench-Server getestet wurde, kann die native Protokollierungsfunktion des Webservers deaktiviert werden, ohne dass sich dies auf die Datenerfassung auswirkt. In vielen Fällen wird durch die Deaktivierung der Protokollierung von Dateien auf lokalen Festplatten der Webserver-Computer die Seitenbereitstellungskapazität dieser Webserver verbessert, da eine relativ große Menge von festem Datenträger-I/O erforderlich ist, um diese Informationen auf der lokalen Festplatte des Webserver-Computers zu protokollieren.

[!DNL Sensor] erfasst Messungs- und Webanfragedaten direkt von jedem Webserverprozess und virtuellen Webserverprozess (falls zutreffend) und schreibt die Daten vorübergehend in eine Queue-Datei, eine fehlertolerante Speicherwarteschlange mit festem Festplattenabbau auf dem Webserver-Computer. Der Sensor Transmitter-Dienst (oder Daemon je nach Plattform) ruft Daten aus der Queue-Datei ab und komprimiert und verschlüsselt sie dann, bevor sie zur langfristigen Speicherung an den Data Workbench-Server übermittelt werden. Mit [!DNL Sensor] werden Daten nur dann auf Ihren Webserver-Computern in der Queue-Datei gesammelt, wenn Sie ein Netzwerk- oder ein anderes Problem haben, das die Übertragung verhindert. Die Queue-Datei ermöglicht die effiziente lokale Speicherung von Stunden bis Tagen von Web-Anfragedaten, um die Daten zu schützen, wenn ein Netzwerk- oder Systemfehler nicht zulässt, dass die Daten in Echtzeit an den Data Workbench-Server übermittelt werden.

[!DNL Sensor] erfasst Messdaten aus jedem physischen und logischen Webserverprozess, filtert sie nach Inhaltstyp, komprimiert sie, verschlüsselt sie und streamt sie an den Data Workbench-Server.

Die folgende Tabelle enthält die Protokollinformationen, die von [!DNL Sensor] für jede nicht anhand der Konfigurationsdatei [!DNL Sensor’s] herausgefilterte GET-Anfrage erfasst werden:

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
   <td colname="col2"> Tracking-ID (Unique Visitor) </td> 
   <td colname="col3"> Kennung, die von einem Cookie gelesen wird, das im Browser des Benutzers durch <span class="wintitle"> Sensor </span> auf der ursprünglichen Anforderung des Besuchers platziert wurde </td> 
   <td colname="col4"> V1st=3C94007B4E01F9C2 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Datum </p> <p>Zeit </p> </td> 
   <td colname="col2"> Zeitstempel </td> 
   <td colname="col3"> Zeitpunkt, zu dem die Anfrage vom Server verarbeitet wurde (Genauigkeit 100 ns); Genauigkeit hängt von der Serverumgebung und NTP ab) </td> 
   <td colname="col4"> 21.11.2002 17:21:45.123 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> sc(content-type) </td> 
   <td colname="col2"> Content-Typ </td> 
   <td colname="col3"> Typ des vom Server zurückgegebenen Objekts </td> 
   <td colname="col4"> text/html </td> 
  </tr> 
  <tr> 
   <td colname="col1"> sc-status </td> 
   <td colname="col2"> HTTP-Antwortstatus-Code </td> 
   <td colname="col3"> Vom Server generierter numerischer Code, der den Status der HTTP-Server-Antwort angibt </td> 
   <td colname="col4"> 404 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-uri-system </td> 
   <td colname="col2"> URI-Stem </td> 
   <td colname="col3"> Der vom Client angeforderte Stammteil des URI </td> 
   <td colname="col4"> <span class="filepath"> pagedir/page.asp  </span> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> c-ip </td> 
   <td colname="col2"> Client-IP </td> 
   <td colname="col3"> IP-Adresse des anfragenden Clients </td> 
   <td colname="col4"> 127,0,0,1 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> s-dns </td> 
   <td colname="col2"> Server Domain Name </td> 
   <td colname="col3"> Domänenname des Webservers, der die Anforderung verarbeitet </td> 
   <td colname="col4"> <span class="filepath"> www.domain.com  </span> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(referrer) </td> 
   <td colname="col2"> Verweisende URL </td> 
   <td colname="col3"> Inhalt des vom Client gesendeten HTTP-Referrer-Felds </td> 
   <td colname="col4"> <span class="filepath"> http://www.referringsite.com  </span> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(user-agent) </td> 
   <td colname="col2"> Benutzeragent </td> 
   <td colname="col3"> Gerät, das verwendet wird, um eine Anfrage an den HTTP-Server zu senden </td> 
   <td colname="col4"> Mozilla/4.0+(kompatibel;+MSIE+6.0; +Windows+NT+5.1) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(cookie) </td> 
   <td colname="col2"> Client-Cookies von Domäne </td> 
   <td colname="col3"> Inhalt aller Cookies des Benutzers für die Site </td> 
   <td colname="col4"> <p>KL_TC1 1038058778312 </p> <p>KL972x1038058778312282052 </p> <p>KL_PVKL972 0 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-uri-query </td> 
   <td colname="col2"> Abfragezeichenfolge </td> 
   <td colname="col3"> Der gegebenenfalls vom Client angeforderte Teil der Abfragezeichenfolge des URI </td> 
   <td colname="col4"> PAGENAME=dynamic1&amp;link=3001 </td> 
  </tr> 
 </tbody> 
</table>
