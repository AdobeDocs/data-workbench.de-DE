---
description: Informationen über optionale Parameter der Datei Sensor txlogd.conf.
title: Optionale Parameter
uuid: 8515a571-93ce-49cd-9ded-c9273259d0ee
exl-id: 5141f215-979c-4eb8-8c2c-94eef5815743
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1484'
ht-degree: 1%

---

# Optionale Parameter{#optional-parameters}

{{eol}}

Informationen über optionale Parameter der Datei Sensor txlogd.conf.

<table id="table_5FF491A7A6C24E43A06A5C344BF05430"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> AddressFilter </td> 
   <td colname="col2"> <p>Ermöglicht die Filterung bestimmter IP-Adressen. </p> <p>Wenn Sie eine bestimmte Adresse filtern, wird ein "Paket"nicht protokolliert. Diese Funktion eliminiert interne oder überwachte Agenten vor der Protokollverarbeitung, wodurch die Protokollverarbeitung beschleunigt und die Datenspeicheranforderungen reduziert werden. Sie können beim Festlegen von Adressen Platzhalter verwenden. </p> <p>Beispiel: <span class="filepath"> AddressFilter 10.0.0.000</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ContentFilterInclude </p> <p>ContentFilterExclude </p> </td> 
   <td colname="col2"> <p>Geben Sie an, ob bestimmte Inhaltstypen in die Protokollierung einbezogen oder ausgeschlossen werden sollen. </p> <p>Die Parameterwerte werden dem Inhaltstyp der Antwort vorangestellt. </p> <p>Beispielsweise stimmt "image/"mit allen Bildinhaltstypen überein, während "image/gif"nur mit diesem Typ exakt übereinstimmt. Wenn für einen bestimmten Inhaltstyp mehrere Übereinstimmungen auftreten, wird die spezifischste Übereinstimmung verwendet. Daher könnten Sie "image/gif"im Parameter ContentFilterInclude und "image/"im Parameter ContentFilterExclude und "image/gif"-Antworten sind zulässig, aber alle anderen Bildtypen werden herausgefiltert. </p> <p>Beispiel: <span class="filepath"> ContentFilterInclude *</span> </p> <p>Beispiel: <span class="filepath"> ContentFilterExclude image/,text/css,application/x-javascript</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> DebugLogPath </td> 
   <td colname="col2"> <p>Legen Sie diesen Parameter nur bei der Arbeit mit Adobe Consulting Services fest. </p> <p>Aktiviert die Debug-Protokollierung für das Webmodul und den Transmitter. </p> <p>Sie verwenden diesen Parameter bei der <span class="wintitle"> Sensor</span> funktioniert nicht ordnungsgemäß. Nachdem dieser Parameter festgelegt wurde, müssen Sie eine leere Datei am angegebenen Pfad erstellen und allen Benutzern Schreibrechte zuweisen. Beispiel (in einer Unix-Shell auf dem Webserver): 
     <ul id="ul_7A067014A78048BF9D2F23DC66FF9E24"> 
      <li id="li_11C51EB9B9CC431585ECE9E8648F6122"><span class="filepath"> % cd /var/log</span> </li> 
      <li id="li_C56B2B5D49A543DBB258C5DE099B4AE5"><span class="filepath"> % touch vslog.txt</span> </li> 
      <li id="li_DA914383F813453AB6EF4F89279FD786"><span class="filepath"> % chmod a+w vslog.txt</span> </li> 
     </ul> </p> <p>Sie sollten die Debug-Protokollierung nur für einen kurzen Zeitraum aktivieren. Danach sollte die Protokolldatei zur Analyse an Adobe Consulting Services gesendet werden. </p> <p>Beispiel: <span class="filepath"> DebugLogPath /var/log/vslog.txt</span> </p> <p>Adobe empfiehlt, diesen Parameter zunächst in einer Testumgebung festzulegen, um die Auswirkungen auf Ihr System zu ermitteln. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> DisableField </td> 
   <td colname="col2"> <p>Deaktiviert das angegebene Feld </p> <p>Benutzer können Felder löschen, die sie nicht verwenden oder nicht speichern möchten. Wenn das Feld Zeichenfolgenwerte akzeptiert, wird beim Deaktivieren eine leere Zeichenfolge übergeben. Wenn das Feld numerische Werte akzeptiert, wird beim Deaktivieren die Zahl 0 (0) überschritten. Sie können die folgenden Felder deaktivieren: 
     <ul id="ul_4537B345EFAE449A9946DA0B52EA5C43"> 
      <li id="li_D674BC1982344C49B25A73EFF095C34A">sc-status </li> 
      <li id="li_6D647C845EB54B1B84C756DCDD7DD4CC">x-new-visitor </li> 
      <li id="li_65EB695B223040BCB9888375354B6E8B">x-trackingid </li> 
      <li id="li_41197A9CB961496B9CD26AA8457233FD">sc-bytes </li> 
      <li id="li_DCD45D7E21964B959299494FA719F453">c-ip </li> 
      <li id="li_7650796C6246484C8267ED9923596AFB">cs-method </li> 
      <li id="li_8941FCBBAA5E42EA9F04DA06EB91CAC5">cs-uri-system </li> 
      <li id="li_A10438D2DEBB4ADFB574BF7094F9F0C4">cs-uri-query </li> 
      <li id="li_1D83BA59AC8543319D1966BB8ED1D931">s-dns </li> 
      <li id="li_34A23CE1944F4AEFBE7D74E8D6D5BEE6">cs(referrer) </li> 
      <li id="li_B85D93C381BD440F82C711C9A6D56CE9">cs(cookie) </li> 
      <li id="li_18D9C084450149D6A8713EBDA0C02E5B">cs(user-agent) </li> 
      <li id="li_A175CAF03E51473E990BE4F31F198B42">cs(useragent) </li> 
      <li id="li_ED38ED31B2644F2FA1C86FF93ADB9CEF">sc(content-type) </li> 
      <li id="li_1173C0027C8A4638BDF35E9719CD9D4C">x-experiment </li> 
     </ul> </p> <p>Beispiel: <span class="filepath"> DisableField x-trackingid</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ExpFile </td> 
   <td colname="col2"> <p>Pfad zur Konfigurationsdatei für gesteuerte Experimente. </p> <p>Beispiel: <span class="filepath"> ExpFile C:\VisualSensor\experiment.txt</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ExpCookieURL </td> 
   <td colname="col2"> <p>Ressource, die bei Anforderung dazu führt, dass eine neue Tracking-ID generiert und der Benutzer in eine Experimentgruppe aufgenommen wird. </p> <p> <p>Hinweis: Diese Ressource muss nicht physisch auf dem Webserver vorhanden sein. </p> </p> <p>Beispiel: <span class="filepath"> ExpCookieURL /setcookie.htm</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ExpPartialMatch </td> 
   <td colname="col2"> <p>Wenn Sie Ihre gesteuerten Experimente aktivieren möchten, um Ihre gesamte Site oder ein ganzes Unterverzeichnis Ihrer Site an einen anderen Ort zu verweisen, setzen Sie diesen Parameter auf "on". Der Standardwert ist "off". </p> <p>Beispiel: <span class="filepath"> ExpPartialMatch off</span> </p> <p> <p>Hinweis: Seien Sie vorsichtig, wenn Sie diesen Parameter auf "ein"setzen. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> LogAllNewUsers </td> 
   <td colname="col2"> <p>Bestimmt, ob der erste Klick eines neuen Benutzers protokolliert wird, selbst wenn der Benutzer einen Dokumenttyp anfordert, der durch den Parameter ContentFilterExclude herausgefiltert wird. </p> <p>Die Standardeinstellung ist "Nein". </p> <p>In der Regel werden Bilddateien durch den Parameter ContentFilterExclude herausgefiltert. Wenn LogAllNewUsers auf "yes"gesetzt ist und das erste Dokument, das ein neuer Benutzer vom Server erhält, ein Bild ist, wird diese Anforderung protokolliert. Wenn der Parameter LogAllNewUsers entweder auf "Nein"gesetzt oder gar nicht festgelegt ist (und sofern Bilder vom Parameter ContentFilterExclude herausgefiltert werden) und das allererste Dokument, das ein neuer Benutzer vom Server erhält, ein Bild ist, wird diese Anforderung nicht protokolliert. </p> <p>Beispiel: <span class="filepath"> LogAllNewUsers</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> MaxPageLoadTime </td> 
   <td colname="col2"> <p>Die Zeit in Sekunden, die der Transmitter auf den Versand des nächsten Paketstapels wartet. </p> <p>Die Standardeinstellung ist „15“. </p> <p>Beispiel: <span class="filepath"> MaxPageLoadTime 15</span> </p> <p> <p>Hinweis: Ändern Sie diesen Parameterwert nicht, ohne sich zunächst an Adobe Consulting Services zu wenden. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> PrivacyID </td> 
   <td colname="col2"> <p>Aktiviert die Deaktivierung des Besucher-Trackings, mit dem Opt-out-Richtlinien eingehalten werden können. </p> <p>Wenn aktiviert, <span class="wintitle"> Sensor</span> protokolliert kein "Paket"für Besucher, deren V1st-Cookie auf die angegebene Datenschutz-ID gesetzt ist. Da keine Informationen für diese Besucher protokolliert werden, werden keine Informationen über diese Besucher an die <span class="keyword"> Data Workbench-Server</span> zur Verarbeitung. </p> <p>Um diese Funktion zu aktivieren, müssen Sie die folgenden Schritte ausführen: 
     <ol id="ol_5D658C5E4AB14F419029E0FFC52F1310"> 
      <li id="li_BF056439F92148169BF592731264C3CD"> PrivacyID muss mit dem Wert 0 (null) im Wert <span class="filepath"> txlogd.conf</span> -Datei für <span class="wintitle"> Sensor</span>. <p>Beispiel: <span class="filepath"> PrivacyID 0</span> </p> </li> 
      <li id="li_3E20F068C2F94512A92F284C80273B1C">Website-Eigentümer müssen Code schreiben, um Besucher-Cookies (V1st) so zu setzen, dass der Cookie-ID-Wert mit dem definierten PrivacyID-Wert übereinstimmt.<span class="filepath"> txlogd.conf</span>." </li> 
     </ol> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SiteTest </td> 
   <td colname="col2"> <p>Der Speicherort, an den der Sender (txlogd) regelmäßig Anfragen sendet, um zu sehen, ob die Website ordnungsgemäß funktioniert. </p> <p>Beachten Sie, dass der Speicherort im folgenden Format angegeben ist, nicht als URL: </p> <p>http,<i>serverAddress,port,/resource</i> </p> <p>where <i>serverAddress</i> Servername oder IP-Adresse ist, <i>port</i> der HTTP-Listening-Anschluss des Servers ist und <i>resource</i> ist die spezifische Ressource, die angefordert werden soll (kann eine Abfragezeichenfolge enthalten). </p> <p>Sie können mehrere SiteTest-Zeilen angeben. </p> <p>Beispiel: <span class="filepath"> SiteTest http,localhost,80,/test.html</span> </p> <p> <p>Hinweis: Derzeit wird nur HTTP unterstützt. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> TrackingCookie </td> 
   <td colname="col2"> <p>Der Name des Cookies, das im Browser des Besuchers gesetzt wird. </p> <p>Der Standardwert ist "v1st". </p> <p>Beispiel: <span class="filepath"> TrackingCookie v1st</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> VerifyCertName </td> 
   <td colname="col2"> <p>Gibt an, ob der Server mit dem CertName-Parameter überprüft werden soll </p> <p>Die Standardeinstellung ist "on". </p> <p>Beispiel: <span class="filepath"> VerifyCertName on</span> </p> </td> 
  </tr> 
 </tbody> 
</table>

<table id="table_598C3CDA5AA440228AF88C3BE4A8F77C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> IISCaptureBytesSent </td> 
   <td colname="col2"> <p>Legen Sie diesen Parameter nur bei der Arbeit mit Adobe Consulting Services fest. </p> <p>Teilt das IIS <span class="wintitle"> Sensor</span> Welche von zwei möglichen Protokollierungs-"Hooks"sollte zum Protokollieren eines Pakets verwendet werden </p> <p>Verwenden Sie diesen Parameter, wenn IIS <span class="wintitle"> Sensor</span> protokolliert Pakete nicht korrekt. Dieser Parameter wird auf "Aus"gesetzt, wenn der standardmäßige Protokollierungs-Hook nicht ordnungsgemäß funktioniert. Die Standardeinstellung ist "on". </p> <p>Beispiel: <span class="filepath"> IISCaptureBytesGesendet für</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> IISUseAlternateHandler </td> 
   <td colname="col2"> <p>Legen Sie diesen Parameter nur bei der Arbeit mit Adobe Consulting Services fest. </p> <p>Teilt die <span class="wintitle"> Sensor</span> welche von zwei möglichen "Hooks"zum Setzen des v1st-Cookies verwendet werden sollte. </p> <p>Sie verwenden diesen Parameter beim IIS <span class="wintitle"> Sensor</span> setzt das v1st -Cookie nicht korrekt. Dieser Parameter wird auf "Ja"gesetzt, wenn der Standard-Erweiterungspunkt das v1st -Cookie nicht korrekt setzt. Die Standardeinstellung ist "Nein". </p> <p>Beispiel: <span class="filepath"> IISUseAlternateHandler</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>NewUserCacheControl </p> <p>CacheControl </p> </td> 
   <td colname="col2"> <p>Standardmäßig <span class="wintitle"> Sensor</span> sendet Cache-Steuerelement-Antwortheader bei jeder Anfrage. Wenn die Cache-Kontrollfunktion aktiviert ist <span class="wintitle"> Sensor</span> sendet einen Expires-Header mit dem Wert Thu, 01. Dezember 1994 16:00:00 GMT auf den Browser. </p> <p>Sie können die Antwortzeichenfolgen nach Bedarf ändern, indem Sie die beiden folgenden Zeilen im <span class="filepath"> txlogd.conf</span> Datei: </p> <p> <span class="filepath"> NewUserCacheControl</span> <i>&lt;<span class="filepath"> string1</span>&gt;</i> </p> <p> <span class="filepath"> CacheControl</span> <i>&lt;<span class="filepath"> string2</span>&gt;</i> </p> <p>Beispiel: </p> <p> <span class="filepath"> NewUserCacheControl no-cache=Set-Cookie</span> </p> <p> <span class="filepath"> CacheControl private,max-age=0,must-revalidate</span> </p> <p>Um das Senden von Cache-Steuerelement-Antwortheadern zu deaktivieren, geben Sie wie unten gezeigt einen Bindestrich für jede Zeile ein: </p> <p> <span class="filepath"> NewUserCacheControl -</span> </p> <p> <span class="filepath"> CacheControl -</span> </p> </td> 
  </tr> 
 </tbody> 
</table>

<table id="table_88696CCA93874BB683538BD614E07890"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> In diesem Parameter ... </th> 
   <th colname="col2" class="entry"> Legen Sie... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> ApacheUseAlternateHandler </td> 
   <td colname="col2"> <p>Legen Sie diesen Parameter nur bei der Arbeit mit Adobe Consulting Services fest. </p> <p>Teilt die <span class="wintitle"> Sensor</span> welche von zwei möglichen "Hooks"zum Setzen des v1st-Cookies verwendet werden sollte. </p> <p>Sie verwenden diesen Parameter beim Apache <span class="wintitle"> Sensor</span> setzt das v1st -Cookie nicht korrekt. Dieser Parameter wird auf "Ja"gesetzt, wenn der Standard-Erweiterungspunkt das v1st -Cookie nicht korrekt setzt. Die Standardeinstellung ist "Nein". </p> <p>Beispiel: <span class="filepath"> ApacheUseAlternateHandler</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ApacheUseBeideHandlers </td> 
   <td colname="col2"> <p>Legen Sie diesen Parameter nur bei der Arbeit mit Adobe Consulting Services fest. </p> <p>beauftragt die <span class="wintitle"> Sensor</span> , um zu versuchen, das v1st -Cookie in beiden Hooks festzulegen. </p> <p>Sie verwenden diesen Parameter beim Apache <span class="wintitle"> Sensor</span> setzt das v1st -Cookie nicht korrekt. Die Standardeinstellung ist "Ja". </p> <p>Wenn der Wert auf "Ja"gesetzt und das v1st-Cookie im ersten Hook nicht richtig gesetzt ist, wird der zweite Hook verwendet. Wenn Sie auf "Nein"setzen, legen Sie den Parameter ApacheUseAlternateHandler fest, um anzugeben, welcher Erweiterungspunkt zum Setzen des v1st-Cookies verwendet werden soll. </p> <p>Beispiel: <span class="filepath"> ApacheUseBeideHandlers yes</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>NewUserCacheControl </p> <p>CacheControl </p> </td> 
   <td colname="col2"> <p>Standardmäßig <span class="wintitle"> Sensor</span> sendet Cache-Steuerelement-Antwortheader bei jeder Anfrage. Wenn die Cache-Kontrollfunktion aktiviert ist <span class="wintitle"> Sensor</span> sendet einen Expires-Header mit dem Wert Thu, 01. Dezember 1994 16:00:00 GMT auf den Browser. </p> <p>Sie können die Antwortzeichenfolgen nach Bedarf ändern, indem Sie die beiden folgenden Zeilen im <span class="filepath"> txlogd.conf</span> Datei: </p> <p> <span class="filepath"> NewUserCacheControl</span> <i>&lt;<span class="filepath"> string1</span>&gt;</i> </p> <p> <span class="filepath"> CacheControl</span> <i>&lt;<span class="filepath"> string2</span>&gt;</i> </p> <p>Beispiel: </p> <p> <span class="filepath"> NewUserCacheControl no-cache=Set-Cookie</span> </p> <p> <span class="filepath"> CacheControl private,max-age=0,must-revalidate</span> </p> <p>Um das Senden von Cache-Steuerelement-Antwortheadern zu deaktivieren, geben Sie wie unten gezeigt einen Bindestrich für jede Zeile ein: </p> <p> <span class="filepath"> NewUserCacheControl -</span> </p> <p> <span class="filepath"> CacheControl -</span> </p> <p> <p>Hinweis: Adobe empfiehlt, diese Funktion nicht zu deaktivieren. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

<table id="table_BF01F6265B8544DA9D9AD2C80A64C0F3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> In diesem Parameter ... </th> 
   <th colname="col2" class="entry"> Legen Sie... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> ApacheUseAlternateHandler </td> 
   <td colname="col2"> <p>Legen Sie diesen Parameter nur bei der Arbeit mit Adobe Consulting Services fest. </p> <p>Teilt die <span class="wintitle"> Sensor</span> welche von zwei möglichen "Hooks"zum Setzen des v1st-Cookies verwendet werden sollte. </p> <p>Sie verwenden diesen Parameter beim Apache <span class="wintitle"> Sensor</span> setzt das v1st -Cookie nicht korrekt. Dieser Parameter wird auf "Ja"gesetzt, wenn der Standard-Erweiterungspunkt das v1st -Cookie nicht korrekt setzt. Die Standardeinstellung ist "Nein". </p> <p>Beispiel: <span class="filepath"> ApacheUseAlternateHandler</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ApacheUseBeideHandlers </td> 
   <td colname="col2"> <p>Legen Sie diesen Parameter nur bei der Arbeit mit Adobe Consulting Services fest. </p> <p>beauftragt die <span class="wintitle"> Sensor</span> , um zu versuchen, das v1st -Cookie in beiden Hooks festzulegen. </p> <p>Sie verwenden diesen Parameter beim Apache <span class="wintitle"> Sensor</span> setzt das v1st -Cookie nicht korrekt. Die Standardeinstellung ist "Ja". </p> <p>Wenn der Wert auf "Ja"gesetzt und das v1st-Cookie im ersten Hook nicht richtig gesetzt ist, wird der zweite Hook verwendet. Wenn Sie auf "Nein"setzen, legen Sie den Parameter ApacheUseAlternateHandler fest, um anzugeben, welcher Erweiterungspunkt zum Setzen des v1st-Cookies verwendet werden soll. </p> <p>Beispiel: <span class="filepath"> ApacheUseBeideHandlers yes</span> </p> </td> 
  </tr> 
 </tbody> 
</table>
