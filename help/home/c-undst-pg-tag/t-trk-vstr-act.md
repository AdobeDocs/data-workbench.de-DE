---
description: Websites, die mit Flash erstellt wurden, erfordern besondere Aufmerksamkeit hinsichtlich der Erfassung von Besucheraktionen, die innerhalb der Rich-Media-Inhalte durchgeführt werden.
title: Tracking der Besucheraktivität in Flash-basierten Rich-Media-Inhalten
uuid: fe2e75eb-0897-4f63-b582-b4f1fdce02a1
exl-id: f51c7034-a7fd-4575-80e1-18fc6513ca2b
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '713'
ht-degree: 5%

---

# Tracking der Besucheraktivität in Flash-basierten Rich-Media-Inhalten{#tracking-visitor-activity-within-flash-rich-media-content}

Websites, die mit Flash erstellt wurden, erfordern besondere Aufmerksamkeit hinsichtlich der Erfassung von Besucheraktionen, die innerhalb der Rich-Media-Inhalte durchgeführt werden.

Mit der ActionScript [!DNL Flash] können Sie einfache Änderungen an Ihren vorhandenen [!DNL Flash]-Filmen vornehmen, um die Verfolgung aller Besucherinteraktionen mit dem Film zu ermöglichen, z. B. Schaltflächen- oder Mausbewegungen.

Um das Tracking der Besucheraktivität in Ihrem [!DNL Flash]-Film zu erleichtern, führen Sie die folgenden Schritte aus:

1. Fügen Sie den folgenden ActionScript-Code zu Ihrem Film hinzu. Dieser Code stellt eine Funktion dar, die von Ereignissen im nachzuverfolgenden [!DNL Flash]-Film aufgerufen werden kann.

   ```
   // FLASH TAG CODE BEGIN 
   var FLASHTAGURI = "[PATH_TO_WEB_SERVER]/flashtag.txt"; 
   function tag(PAGENAME,VARIABLES) { 
   loadVariablesNum(FLASHTAGURI+”?”+"PAGENAME="+PAGENAME+"&"+VARIABLES,0); 
   } 
   // FLASH TAG CODE END
   ```

1. Erstellen Sie eine leere Datei mit dem Namen [!DNL flashtag.txt] und platzieren Sie die Datei auf Ihren Webservern.
1. Ersetzen Sie in der Funktion in Schritt 1 den Platzhalter \[[!DNL PATH_TO_WEB_SERVER]\] durch den vollständig qualifizierten oder relativen Pfad zum Speicherort der Datei [!DNL flashtag.txt]. Beispiel:

   ```
   var FLASHTAGURI = http://www.mysite.com/flashtag/flashtag.txt”;
   ```

1. Fügen Sie allen ActionScript-Ereignissen, die verfolgt werden sollen, den folgenden Code hinzu. Dieser Code stellt einen Funktionsaufruf dar, mit dem Daten zum Ereignis erfasst werden:

   ```
   on(release) {tag("[PUT_PAGE_NAME_HERE]","[PUT_ADDITIONAL_VAR_HERE]");}
   ```

   Dieses Beispiel zeigt die Verwendung des on(release)-Ereignisses. Die Funktion tag() kann jedoch durch jedes Ereignis referenziert werden, das Sie verfolgen möchten, z. B. ein on(press)-, on(rollover)-, on(rollout)- oder on(keypress)-Ereignis.

   Der Platzhalter \[[!DNL PUT_PAGE_NAME_HERE]\] sollte durch eine Zeichenfolge ersetzt werden, die den Namen der Seite oder des Ereignisses darstellt, die/das Sie verfolgen. Die Variable \[[!DNL PUT_PAGE_NAME_HERE]\]kann entweder manuell oder über einen Variablenverweis geändert werden, um einen eindeutigen Namen für die Seite oder das Ereignis in der Anwendung [!DNL Flash] anzugeben. Der Wert, der den Platzhalter \[[!DNL PUT_PAGE_NAME_HERE]\] ersetzt, kann aus einem einfachen Namen bestehen oder so strukturiert sein, dass er eine hierarchische Struktur ähnlich einer vollständigen URI darstellt. Beispiel:

   ```
   on(release) {tag(“/about_us/index.swf","[PUT_ADDITIONAL_VAR_HERE]");}
   ```

   Adobe empfiehlt, vor der Code-Implementierung eine schriftliche Spezifikation für Seitennamen und Ereignisnamen zu erstellen, um die Abstimmung von Geschäftsanforderungen und Entwicklungsaufgaben zu erleichtern und das Potenzial für zusätzliche Entwicklungszyklen zu reduzieren.

1. Falls gewünscht, können zusätzliche Variablen erfasst und mit Seiten oder Ereignissen im [!DNL Flash] -Film verknüpft werden. Ersetzen Sie dazu den Platzhalter \[[!DNL PUT_ADDITIONAL_VAR_HERE]\] durch einen Satz aus Name=Wert-Paaren, getrennt durch ein kaufmännisches Und-Zeichen (&amp;). Beispiel:

   ```
   on(release) {tag(“/about_us/index.swf"," var1=value1&var2=value2");}
   ```

   Die Variablen können entweder manuell oder über einen Variablenverweis geändert werden, um zusätzliche Attribute anzugeben, die erfasst und der Seite oder dem Ereignis zugeordnet werden. Wenn keine weiteren Variablen erfasst werden müssen, entfernen Sie \[[!DNL PUT_ADDITIONAL_VAR_HERE]\].

   Ihre Einrichtung des Besucher-Trackings in [!DNL Flash] Rich-Media-Inhalten ist jetzt abgeschlossen. Wenn das Ereignis aufgerufen wird, wird die Funktion Tag [!DNL (PAGENAME,VARIABLES)] aufgerufen, was dazu führt, dass eine HTTP-Anforderung für die folgende Datei erstellt wird. Diese Funktion wird zusätzlich zu anderen Funktionen aufgerufen, die wie in Ihrem [!DNL Flash]-Film definiert ausgelöst werden können:

   ```
   http://www.mysite.com/flashtag/flashtag.txt?PAGENAME=/about_us/index.swf&var1=value1&var2=value2
   ```

Die HTTP-Anforderung, die aus der Tag-ActionScript-Funktion [!DNL Flash] resultiert, führt dazu, dass die folgenden Informationen zu jedem Ereignis im [!DNL Flash]-Film erfasst werden. Die letzte Zeile in der Tabelle (W3C Name cs-uri-query) stellt die Informationen dar, die für die zusätzlichen Variablen erfasst wurden, die in Ihrem Funktionsaufruf angegeben sind.

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
   <td colname="col3"> Kennung, die von einem Cookie gelesen wird, das im Browser des Benutzers durch <span class="wintitle"> Sensor </span> auf der ursprünglichen Anforderung des Besuchers platziert wurde </td> 
   <td colname="col4"> v1st=3C94007B4E01F9C2 </td> 
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
   <td colname="col4"> Text/html </td> 
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
   <td colname="col3"> Der vom Client angeforderte Stammteil des URI </td> 
   <td colname="col4"> /flashtag/flashtag.txt </td> 
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
   <td colname="col4"> www.mysite.com </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(referrer) </td> 
   <td colname="col2"> Verweisende URL </td> 
   <td colname="col3"> Inhalt des vom Client gesendeten HTTP-Referrer-Felds </td> 
   <td colname="col4"></td> 
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
   <td colname="col4"> PAGENAME=/about_us/index.swf&amp;var1=value1&amp;var2=value2 </td> 
  </tr> 
 </tbody> 
</table>
