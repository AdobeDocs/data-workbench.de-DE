---
description: Mit Flash gebaute Websites erfordern besondere Aufmerksamkeit in Bezug auf die Erfassung von Besuchern, die in Rich-Media-Inhalten ausgeführt werden.
title: Tracking der Besucheraktivität in Flash-basierten Rich-Media-Inhalten
uuid: fe2e75eb-0897-4f63-b582-b4f1fdce02a1
exl-id: f51c7034-a7fd-4575-80e1-18fc6513ca2b
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '713'
ht-degree: 5%

---

# Tracking der Besucheraktivität in Flash-basierten Rich-Media-Inhalten{#tracking-visitor-activity-within-flash-rich-media-content}

Mit Flash gebaute Websites erfordern besondere Aufmerksamkeit in Bezug auf die Erfassung von Besuchern, die in Rich-Media-Inhalten ausgeführt werden.

Mit der ActionScript [!DNL Flash] können Sie einfache Änderungen an Ihren vorhandenen [!DNL Flash]-Filmen vornehmen, um die Verfolgung aller Besucher-Interaktionen mit dem Film zu ermöglichen, z. B. Schaltflächen- oder Mausbewegungen.

Gehen Sie wie folgt vor, um die Verfolgung der Aktivität von Besuchern in Ihrem [!DNL Flash]-Film zu erleichtern:

1. hinzufügen Sie den folgenden ActionScript-Code in Ihren Film ein. Dieser Code stellt eine Funktion dar, die von Ereignissen innerhalb des zu verfolgenden [!DNL Flash]-Films aufgerufen werden kann.

   ```
   // FLASH TAG CODE BEGIN 
   var FLASHTAGURI = "[PATH_TO_WEB_SERVER]/flashtag.txt"; 
   function tag(PAGENAME,VARIABLES) { 
   loadVariablesNum(FLASHTAGURI+”?”+"PAGENAME="+PAGENAME+"&"+VARIABLES,0); 
   } 
   // FLASH TAG CODE END
   ```

1. Erstellen Sie eine leere Datei mit dem Namen [!DNL flashtag.txt] und legen Sie die Datei auf Ihren Webservern ab.
1. Ersetzen Sie in der Funktion in Schritt 1 den Platzhalter \[[!DNL PATH_TO_WEB_SERVER]\] durch den vollständig qualifizierten oder relativen Pfad zum Speicherort der Datei [!DNL flashtag.txt]. Beispiel:

   ```
   var FLASHTAGURI = http://www.mysite.com/flashtag/flashtag.txt”;
   ```

1. hinzufügen Sie den folgenden ActionScript-Code für alle zu verfolgenden Ereignis. Dieser Code stellt einen Funktionsaufruf dar, mit dem Daten zum Ereignis erfasst werden:

   ```
   on(release) {tag("[PUT_PAGE_NAME_HERE]","[PUT_ADDITIONAL_VAR_HERE]");}
   ```

   In diesem Beispiel wird die Verwendung des Ereignisses on(release) veranschaulicht. Die Funktion tag() kann jedoch über jedes Ereignis referenziert werden, das Sie verfolgen möchten, z. B. ein on(press)-, on(rollover)-, on(rollout)- oder on(keypress)-Ereignis.

   Der Platzhalter \[[!DNL PUT_PAGE_NAME_HERE]\] sollte durch eine Zeichenfolge ersetzt werden, die den Namen der zu verfolgenden Seite oder des zu verfolgenden Ereignisses darstellt. Die Variable \[[!DNL PUT_PAGE_NAME_HERE]\]kann entweder manuell oder durch Variablenverweis geändert werden, um einen eindeutigen Namen für die Seite oder das Ereignis in der Anwendung [!DNL Flash] anzugeben. Der Wert, der den Platzhalter \[[!DNL PUT_PAGE_NAME_HERE]\] ersetzt, kann aus einem einfachen Namen bestehen oder so strukturiert sein, dass er eine hierarchische Struktur darstellt, die einer vollständigen URI ähnlich ist. Beispiel:

   ```
   on(release) {tag(“/about_us/index.swf","[PUT_ADDITIONAL_VAR_HERE]");}
   ```

   Adobe empfiehlt, dass Sie vor der Codebereitstellung eine schriftliche Spezifikation für Seitennamen und Ereignis-Namen erstellen, um die Anpassung der Geschäftsanforderungen und Entwicklungs-Aufgaben zu erleichtern und das Potenzial für zusätzliche Entwicklungszyklen zu reduzieren.

1. Bei Bedarf können zusätzliche Variablen erfasst und mit Seiten oder Ereignissen im Film [!DNL Flash] verknüpft werden. Ersetzen Sie dazu den Platzhalter \[[!DNL PUT_ADDITIONAL_VAR_HERE]\] durch einen Satz aus Paaren für name=Wert, die durch ein kaufmännisches Und (&amp;) voneinander getrennt sind. Beispiel:

   ```
   on(release) {tag(“/about_us/index.swf"," var1=value1&var2=value2");}
   ```

   Die Variablen können entweder manuell oder durch Variablenverweis geändert werden, um zusätzliche Attribute anzugeben, die erfasst und der Seite oder dem Ereignis zugeordnet werden sollen. Wenn keine weiteren zu erfassenden Variablen vorhanden sind, entfernen Sie \[[!DNL PUT_ADDITIONAL_VAR_HERE]\].

   Ihre Einrichtung zur Verfolgung von Besuchern in Rich-Media-Inhalten [!DNL Flash] ist jetzt abgeschlossen. Wenn das Ereignis aufgerufen wird, wird die Funktion Tag [!DNL (PAGENAME,VARIABLES)] aufgerufen, wodurch eine HTTP-Anforderung für die folgende Datei gesendet wird. Diese Funktion wird zusätzlich zu anderen Funktionen aufgerufen, die wie im [!DNL Flash]-Film definiert ausgelöst werden können:

   ```
   http://www.mysite.com/flashtag/flashtag.txt?PAGENAME=/about_us/index.swf&var1=value1&var2=value2
   ```

Die HTTP-Anforderung, die sich aus der Tag-ActionScript-Funktion ergibt, führt dazu, dass die folgenden Informationen zu jedem Ereignis im [!DNL Flash]-Film erfasst werden. [!DNL Flash] Die letzte Zeile in der Tabelle (W3C-Name cs-uri-Abfrage) stellt die Informationen dar, die für die im Funktionsaufruf angegebenen zusätzlichen Variablen erfasst werden.

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
   <td colname="col2"> Tracking-ID (eindeutiger Besucher) </td> 
   <td colname="col3"> Bezeichner, der von einem Cookie gelesen wird, das bei der ursprünglichen Anforderung des Besuchers im Browser des Benutzers von <span class="wintitle"> Sensor </span> platziert wurde </td> 
   <td colname="col4"> v1st=3C94007B4E01F9C2 </td> 
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
   <td colname="col4"> 127,0,0,1 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> s-dns </td> 
   <td colname="col2"> Servername </td> 
   <td colname="col3"> Domänenname des Webservers, der die Anforderung verarbeitet </td> 
   <td colname="col4"> www.mysite.com </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(Werber) </td> 
   <td colname="col2"> Verweisende URL </td> 
   <td colname="col3"> Inhalt des vom Client gesendeten HTTP-Werber-Felds </td> 
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
   <td colname="col1"> cs-uri-Abfrage </td> 
   <td colname="col2"> Abfragezeichenfolge </td> 
   <td colname="col3"> Der vom Client angeforderte Teil der vom Client angeforderten Abfrage-Zeichenfolge </td> 
   <td colname="col4"> PAGENAME=/about_us/index.swf&amp;var1=value1&amp;var2=value2 </td> 
  </tr> 
 </tbody> 
</table>
