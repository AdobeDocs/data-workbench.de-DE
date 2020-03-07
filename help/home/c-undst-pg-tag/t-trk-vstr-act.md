---
description: Mit Flash erstellte Websites erfordern besondere Aufmerksamkeit in Bezug auf die Erfassung von Besucheraktionen, die innerhalb der Rich-Media-Inhalte durchgeführt werden.
solution: Analytics
title: Verfolgung der Besucheraktivität in Flash-Rich-Media-Inhalten
topic: Data workbench
uuid: fe2e75eb-0897-4f63-b582-b4f1fdce02a1
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Verfolgung der Besucheraktivität in Flash-Rich-Media-Inhalten{#tracking-visitor-activity-within-flash-rich-media-content}

Mit Flash erstellte Websites erfordern besondere Aufmerksamkeit in Bezug auf die Erfassung von Besucheraktionen, die innerhalb der Rich-Media-Inhalte durchgeführt werden.

Mit [!DNL Flash] ActionScript können Sie einfache Änderungen an Ihren vorhandenen [!DNL Flash] Filmen vornehmen, um die Verfolgung aller Besucherinteraktionen mit dem Film zu ermöglichen, z. B. Klicks auf Schaltflächen oder Mausbewegungen.

Gehen Sie wie folgt vor, um die Verfolgung der Besucheraktivität in Ihrem [!DNL Flash] Film zu erleichtern:

1. Fügen Sie dem Film den folgenden ActionScript-Code hinzu. Dieser Code stellt eine Funktion dar, die von Ereignissen innerhalb des [!DNL Flash] Films aufgerufen werden kann, den Sie verfolgen möchten.

   ```
   // FLASH TAG CODE BEGIN 
   var FLASHTAGURI = "[PATH_TO_WEB_SERVER]/flashtag.txt"; 
   function tag(PAGENAME,VARIABLES) { 
   loadVariablesNum(FLASHTAGURI+”?”+"PAGENAME="+PAGENAME+"&"+VARIABLES,0); 
   } 
   // FLASH TAG CODE END
   ```

1. Erstellen Sie eine leere Datei mit dem Namen [!DNL flashtag.txt] und legen Sie die Datei auf Ihren Webservern ab.
1. Ersetzen Sie in der Funktion in Schritt 1 den Platzhalter [!DNL [PATH_TO_WEB_SERVER]] durch den vollständig qualifizierten oder relativen Pfad zum Speicherort der [!DNL flashtag.txt] Datei. Beispiel:

   ```
   var FLASHTAGURI = http://www.mysite.com/flashtag/flashtag.txt”;
   ```

1. Fügen Sie allen zu verfolgenden Ereignissen den folgenden ActionScript-Code hinzu. Dieser Code stellt einen Funktionsaufruf dar, mit dem Daten zum Ereignis erfasst werden:

   ```
   on(release) {tag("[PUT_PAGE_NAME_HERE]","[PUT_ADDITIONAL_VAR_HERE]");}
   ```

   In diesem Beispiel wird die Verwendung des on(release)-Ereignisses veranschaulicht. Die Funktion tag() kann jedoch durch jedes Ereignis referenziert werden, das Sie verfolgen möchten, z. B. ein on(press)-, on(rollover)-, on(rollout)- oder on(keypress)-Ereignis.

   Der Platzhalter [!DNL [PUT_PAGE_NAME_HERE]] sollte durch eine Zeichenfolge ersetzt werden, die den Namen der Seite oder des Ereignisses darstellt, die/das Sie verfolgen. Die Variable [!DNL [PUT_PAGE_NAME_HERE]]kann entweder manuell oder durch Variablenverweis geändert werden, um einen eindeutigen Namen für die Seite oder das Ereignis in der [!DNL Flash] Anwendung anzugeben. Der Wert, der den Platzhalter [!DNL [PUT_PAGE_NAME_HERE]] ersetzt, kann aus einem einfachen Namen bestehen oder so strukturiert sein, dass er eine hierarchische Struktur ähnlich einer vollständigen URI darstellt. Beispiel:

   ```
   on(release) {tag(“/about_us/index.swf","[PUT_ADDITIONAL_VAR_HERE]");}
   ```

   Adobe empfiehlt, dass Sie vor der Codebereitstellung eine schriftliche Spezifikation für Seitennamen und Ereignisnamen erstellen, um die Anpassung von Geschäftsanforderungen und Entwicklungsaufgaben zu erleichtern und das Potenzial für zusätzliche Entwicklungszyklen zu reduzieren.

1. Bei Bedarf können zusätzliche Variablen erfasst und mit Seiten oder Ereignissen im [!DNL Flash] Film verknüpft werden. Ersetzen Sie dazu den Platzhalter [!DNL [PUT_ADDITIONAL_VAR_HERE]] durch einen Satz aus Paaren für name=Wert, die durch ein kaufmännisches Und (&amp;) getrennt sind. Beispiel:

   ```
   on(release) {tag(“/about_us/index.swf"," var1=value1&var2=value2");}
   ```

   Die Variablen können entweder manuell oder durch Variablenverweis geändert werden, um zusätzliche Attribute anzugeben, die erfasst und der Seite oder dem Ereignis zugeordnet werden sollen. Wenn keine weiteren zu erfassenden Variablen vorhanden sind, entfernen Sie [!DNL [PUT_ADDITIONAL_VAR_HERE]].

   Ihre Einrichtung zur Besucherverfolgung in Rich-Media- [!DNL Flash] Inhalten ist nun abgeschlossen. Wenn das Ereignis aufgerufen wird, wird die Tag- [!DNL (PAGENAME,VARIABLES)] Funktion aufgerufen, wodurch eine HTTP-Anforderung für die folgende Datei gesendet wird. Diese Funktion wird zusätzlich zu anderen Funktionen aufgerufen, die wie im [!DNL Flash] Film definiert ausgelöst werden können:

   ```
   http://www.mysite.com/flashtag/flashtag.txt?PAGENAME=/about_us/index.swf&var1=value1&var2=value2
   ```

Die HTTP-Anforderung, die sich aus der [!DNL Flash] Tag-ActionScript-Funktion ergibt, führt dazu, dass die folgenden Informationen zu jedem Ereignis im [!DNL Flash] Film erfasst werden. Die letzte Zeile in der Tabelle (W3C-Name cs-uri-query) stellt die Informationen dar, die für die im Funktionsaufruf angegebenen zusätzlichen Variablen erfasst werden.

<table id="table_A7ED9D38F36B4405947B2F48EA94D3C4"> 
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
   <td colname="col3"> Kennung, die von einem Cookie gelesen wird, das in der ursprünglichen Anforderung des Besuchers im Browser des Benutzers durch <span class="wintitle"> Sensor </span> platziert wurde </td> 
   <td colname="col4"> v1st=3C94007B4E01F9C2 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Datum </p> <p>Zeit </p> </td> 
   <td colname="col2"> Zeitstempel </td> 
   <td colname="col3"> Zeitpunkt, zu dem die Anforderung vom Server verarbeitet wurde (mit 100 ns Genauigkeit; Genauigkeit hängt von der Serverumgebung und NTP ab. </td> 
   <td colname="col4"> 2002-11-21 17:21:45.123 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> sc(content-type) </td> 
   <td colname="col2"> Content-Typ </td> 
   <td colname="col3"> Vom Server zurückgegebener Objekttyp </td> 
   <td colname="col4"> Text/html </td> 
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
   <td colname="col3"> Der vom Client angeforderte Stammteil des URI </td> 
   <td colname="col4"> /flashtag/flashtag.txt </td> 
  </tr> 
  <tr> 
   <td colname="col1"> c-ip </td> 
   <td colname="col2"> Client-IP </td> 
   <td colname="col3"> IP-Adresse des anfordernden Kunden </td> 
   <td colname="col4"> 127.0.0.1 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> s-dns </td> 
   <td colname="col2"> Servername </td> 
   <td colname="col3"> Domänenname des Webservers, der die Anforderung verarbeitet </td> 
   <td colname="col4"> www.mysite.com </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(referrer) </td> 
   <td colname="col2"> Verweisende URL </td> 
   <td colname="col3"> Inhalt des vom Client gesendeten Felds "HTTP Referrer" </td> 
   <td colname="col4"></td> 
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
   <td colname="col1"> cs-uri-query </td> 
   <td colname="col2"> Abfragezeichenfolge </td> 
   <td colname="col3"> Der vom Client angeforderte Abfragezeichenfolgen-Teil des URI, falls vorhanden </td> 
   <td colname="col4"> PAGENAME=/about_us/index.swf&amp;var1=value1&amp;var2=value2 </td> 
  </tr> 
 </tbody> 
</table>

