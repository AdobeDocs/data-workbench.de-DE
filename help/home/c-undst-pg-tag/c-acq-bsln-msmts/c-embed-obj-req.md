---
description: Nachdem die HTML einer Seite von einem Browser angefordert wurde, fordert der Browser die eingebetteten Objekte, auf die in der HTML dieser Seite verwiesen wird, von einem Webserver an, um die vom Browser angezeigte Seite auszufüllen.
title: Erfassen eingebetteter Objektanfragen (Seiten-Tags)
uuid: 7fe561d1-aa5a-4ac9-82ba-aa27c7d208dd
exl-id: 593e49bc-9619-4e85-8ce3-2e9d23d175c9
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '604'
ht-degree: 4%

---

# Erfassen eingebetteter Objektanfragen (Seiten-Tags){#acquiring-embedded-object-requests-page-tags}

{{eol}}

Nachdem die HTML einer Seite von einem Browser angefordert wurde, fordert der Browser die eingebetteten Objekte, auf die in der HTML dieser Seite verwiesen wird, von einem Webserver an, um die vom Browser angezeigte Seite auszufüllen.

Solche eingebetteten Objektanfragen sind in den meisten Fällen Anfragen für Bilddateien oder JavaScript-Dateien, obwohl heute Hunderte oder vielleicht Tausende von Arten von eingebetteten Objekten im Internet verwendet werden. Viele dieser eingebetteten Objektanforderungen sind im Allgemeinen nicht für die Analyse oder Berichterstellung zur Geschäftsaktivität einer Website nützlich. viele solcher Anfragen sind daher für den Erwerb nicht wünschenswert, es sei denn, sie haben einen bestimmten Geschäftszweck, z. B. die Präsentation einer Werbung oder eine andere Messung der Site-Aktivität.

Beispielsweise kann es sich bei einem Bild um eine Anzeige handeln, und Sie möchten vielleicht wissen, dass die Anzeige für einen Besucher beeindruckt war. Ein JavaScript-Snippet kann verwendet werden, um eine Messung durchzuführen, dass der jeweilige Browser ein bestimmtes Merkmal aufweist, und ihn an einen [!DNL Sensor] für die Akquise. Jede Seite einer Site kann 10 oder 100 eingebettete Objektanfragen enthalten. Wenn eine Site die Protokollinformationen für jede dieser Anforderungen speichert, wird die Menge an Datenspeicherung, die erforderlich ist, um die Protokolldaten für zukünftige Analysen verfügbar zu halten, mit der Anzahl der eingebetteten Objektanforderungen für jede angeforderte Seite multipliziert. Aus diesem Grund [!DNL Site] ermöglicht Ihnen, die für die Analyse wichtigen Anforderungen beizubehalten und andere zu verwerfen, bevor unnötige Speicherkosten entstehen.

Durch Verwendung der Funktion zum Außerkraftsetzen, die in den Filterfunktionen für den Inhaltstyp von [!DNL Sensor] (Anfügen von &quot;Log=1&quot;an die Abfragezeichenfolge einer eingebetteten Objekt-Anfrage-URL), kann diese bestimmte eingebettete Objektanforderung und die zugehörigen Messdaten erfasst werden, ohne dass der Site-Manager alle Anforderungen dieses Typs speichern muss (z. B. alle `<image>` -Anfragen).

[!DNL Sensor] erfasst die Messdaten in der folgenden Tabelle für jede eingebettete Objektanforderung vom Webserver, vorausgesetzt, dass [!DNL Sensor] nicht konfiguriert ist, um sie herauszufiltern, oder dass der Filter überschrieben wurde. Die erfassten Informationen beziehen sich auf den Besucher, die Sitzung und nachfolgende Sitzungen über die Protokolleinträge x-trackingid oder cs(cookie) .

<table id="table_11BE08A798E743EC8E76F738F0CE5884">
 <thead>
  <tr>
   <th colname="col1" class="entry"> W3C-Name </th>
   <th colname="col2" class="entry"> Erfasste Daten </th>
   <th colname="col3" class="entry"> Erklärung </th>
   <th colname="col4" class="entry"> Beispiel </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> x-trackingid </td>
   <td colname="col2"> Tracking-ID (Unique Visitor) </td>
   <td colname="col3"> Kennung, die aus einem Cookie gelesen wird, das im Browser des Benutzers platziert wurde durch <span class="wintitle"> Sensor </span> auf Anfrage </td>
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
   <td colname="col4"> 200 </td>
  </tr>
  <tr>
   <td colname="col1"> cs-uri-system </td>
   <td colname="col2"> URI-Stem </td>
   <td colname="col3"> Der vom Client angeforderte "Stammteil"des URI </td>
   <td colname="col4"> pagedir/page.asp </td>
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
   <td colname="col4"> <span class="filepath"> www.domain.com </span> </td>
  </tr>
  <tr>
   <td colname="col1"> cs(referrer) </td>
   <td colname="col2"> Verweisende URL </td>
   <td colname="col3"> Inhalt des vom Client gesendeten HTTP-Referrer-Felds </td>
   <td colname="col4"> <span class="filepath"> https://www.referringsite.com </span> </td>
  </tr>
  <tr>
   <td colname="col1"> cs(user-agent) </td>
   <td colname="col2"> Benutzeragent </td>
   <td colname="col3"> Gerät, das verwendet wird, um eine Anfrage an den HTTP-Server zu senden </td>
   <td colname="col4"> <p>Mozilla/4.0+(kompatibel;+MSIE+6.0; </p> <p>+Windows+NT+5.1) </p> </td>
  </tr>
  <tr>
   <td colname="col1"> cs(cookie) </td>
   <td colname="col2"> Client-Cookies von Domäne </td>
   <td colname="col3"> Inhalt aller Cookies des Benutzers für die Site </td>
   <td colname="col4"> <p>KL_TC1 1038058778312 </p> <p>KL972 x1038058778312282052 </p> <p>KL_PVKL972 0 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> cs-uri-query </td>
   <td colname="col2"> Abfragezeichenfolge </td>
   <td colname="col3"> Der gegebenenfalls vom Client angeforderte Teil der Abfragezeichenfolge des URI </td>
   <td colname="col4"> PAGENAME=dynamic1&amp;link=3001 </td>
  </tr>
 </tbody>
</table>
