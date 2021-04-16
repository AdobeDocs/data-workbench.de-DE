---
description: Nachdem der HTML-Code einer Seite von einem Browser angefordert wurde, fordert der Browser die eingebetteten Objekte, auf die im HTML-Code dieser Seite verwiesen wird, von einem Webserver an, die vom Browser angezeigte Seite auszufüllen.
title: Erfassen eingebetteter Objektanfragen (Seiten-Tags)
uuid: 7fe561d1-aa5a-4ac9-82ba-aa27c7d208dd
exl-id: 593e49bc-9619-4e85-8ce3-2e9d23d175c9
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '604'
ht-degree: 4%

---

# Erfassen eingebetteter Objektanfragen (Seiten-Tags){#acquiring-embedded-object-requests-page-tags}

Nachdem der HTML-Code einer Seite von einem Browser angefordert wurde, fordert der Browser die eingebetteten Objekte, auf die im HTML-Code dieser Seite verwiesen wird, von einem Webserver an, die vom Browser angezeigte Seite auszufüllen.

Solche Anforderungen an eingebettete Objekte sind am häufigsten Anforderungen für Bilddateien oder JavaScript-Dateien, obwohl heute Hunderte oder vielleicht Tausende von Arten von eingebetteten Objekten im Internet verwendet werden. Viele dieser Anforderungen an eingebettete Objekte sind im Allgemeinen nicht für die Analyse oder den Berichte auf der geschäftlichen Aktivität einer Website nützlich. Viele solcher Anfragen sind daher für den Erwerb nicht wünschenswert, es sei denn, sie haben einen bestimmten Geschäftszweck, wie z.B. die Anzeige einer Werbung oder die Durchführung einer anderen Messung der Site-Aktivität.

Ein Bild kann beispielsweise eine Werbung sein, und Sie möchten vielleicht wissen, dass die Werbung auf einem Besucher beeindruckt war. Ein JavaScript-Snippet kann verwendet werden, um eine Messung durchzuführen, die besagt, dass der jeweilige Browser eine bestimmte Eigenschaft aufweist, und es zur Akquise an ein [!DNL Sensor] zurückzusenden. Jede Seite auf einer Site kann 10 oder 100 eingebettete Objektanforderungen enthalten. Wenn eine Site die Protokollinformationen für jede dieser Anforderungen speichert, wird die Datenspeicherung der Daten, die erforderlich ist, um die Protokolldaten für die zukünftige Analyse verfügbar zu halten, mit der Anzahl der eingebetteten Objektanforderungen für jede angeforderte Seite multipliziert. [!DNL Site] ermöglicht Ihnen daher, die für die Analyse wichtigen Anforderungen zu behalten und andere zu verwerfen, bevor Sie unnötige Kosten für die Datenspeicherung verursachen.

Durch die Verwendung der Funktion zum Überschreiben von Daten, die in den Filterfunktionen für Inhaltstypen von [!DNL Sensor] bereitgestellt wird (Anfügen von &quot;Log=1&quot;an die Abfrage-Zeichenfolge einer URL für eine eingebettete Objektanforderung), können diese spezielle eingebettete Objektanforderung und die zugehörigen Messungsdaten erfasst werden, ohne dass der Site-Manager alle Anforderungen dieses Typs speichern muss (z. B. alle `<image>`-Anforderungen).

[!DNL Sensor] erfasst die Messungsdaten in der folgenden Tabelle für jede vom Webserver erstellte eingebettete Objektanforderung, vorausgesetzt, dass sie nicht für das Herausfiltern konfiguriert  [!DNL Sensor] ist oder der Filter überschrieben wurde. Die erfassten Informationen beziehen sich auf den Besucher und die Sitzung und die nachfolgenden Sitzungen über die Einträge im Feld x-trackingid oder cs(cookie).

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
   <td colname="col2"> Tracking-ID (eindeutiger Besucher) </td> 
   <td colname="col3"> Bezeichner, der von einem Cookie gelesen wird, das bei einer ersten Anforderung von <span class="wintitle"> Sensor </span> im Browser des Benutzers platziert wurde </td> 
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
   <td colname="col4"> 200 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-uri-stamm </td> 
   <td colname="col2"> URI-Stamm </td> 
   <td colname="col3"> Der vom Client angeforderte "stamm"-Teil des URI </td> 
   <td colname="col4"> pagedir/page.asp </td> 
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
   <td colname="col4"> <p>Mozilla/4.0+(kompatibel;+MSIE+6.0; </p> <p>+Windows+NT+5.1) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(cookie) </td> 
   <td colname="col2"> Client-Cookies von Domäne </td> 
   <td colname="col3"> Inhalt aller Cookies des Benutzers für die Site </td> 
   <td colname="col4"> <p>KL_TC1 1038058778312 </p> <p>KL972 x 1038058778312282052 </p> <p>KL_PVKL972 0 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-uri-Abfrage </td> 
   <td colname="col2"> Abfragezeichenfolge </td> 
   <td colname="col3"> Der vom Client angeforderte Teil der vom Client angeforderten Abfrage-Zeichenfolge </td> 
   <td colname="col4"> PAGENAME=dynamic1&amp;link=3001 </td> 
  </tr> 
 </tbody> 
</table>
