---
description: Bei einigen Sites ist es erforderlich, eingebettete Objektanforderungen zu verwenden, um Informationen an den Webserver weiterzugeben, damit Details darüber, welche Seite tatsächlich bereitgestellt wurde, von Sensor erfasst und für Berichte und Analyse verwendet werden können.
title: Erfassen dynamischer Seitennamen
uuid: eaa35023-bbfa-4eb9-9ab7-3986187e5537
exl-id: cd94caf0-b0dc-46c1-8f59-3ebb2f703286
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '594'
ht-degree: 1%

---

# Erfassen dynamischer Seitennamen{#acquiring-dynamic-page-names}

Bei einigen Sites ist es erforderlich, eingebettete Objektanforderungen zu verwenden, um Informationen an den Webserver weiterzugeben, damit Details darüber, welche Seite tatsächlich bereitgestellt wurde, von Sensor erfasst und für Berichte und Analyse verwendet werden können.

Dies kann erforderlich sein, wenn die vom Webserver angezeigte URL der Seite nicht auf den Seiteninhalt hinweist, der dem Browser angezeigt wird. Dieser Fall resultiert oft aus der Verwendung von Personalisierungs- oder dynamischen Content-Management-Systemen, in denen der tatsächliche Seiteninhalt per Fly durch die URL, das Cookie, zugehörige Daten und Anwendungslogik bestimmt wird.

Die Implementierung eines eingebetteten Objekts zum Sammeln zusätzlicher Messungen sollte sich nur minimal auf die Gesamtergebnisse Ihrer Site auswirken. Adobe empfiehlt, dass Sie eine JavaScript-Datei als Objekt einbetten, das zum Erfassen der erweiterten Attribute verwendet wird. (Beachten Sie, dass eine JavaScript-Datei eingebettet werden kann, ohne dass sich dies auf das Layout und die Darstellung Ihrer Webseite auswirken könnte. Dies kann durch die Verwendung eines eingebetteten Bildes geschehen.) Um die im eingebetteten Objekt weitergeleiteten Informationen genau zu erfassen, empfiehlt Adobe auch die Verwendung eines gemeinsamen Namens. Zu Benennungszwecken bezieht sich Adobe auf dieses Objekt als [!DNL zig.js]. Die Datei [!DNL zig.js] sollte im entsprechenden Verzeichnis auf einem Webserver erstellt werden, auf dem [!DNL Sensor] installiert ist. Diese Datei muss vorhanden sein, damit die Anforderung keinen 404-Fehlercode zurückgibt. Der Inhalt der Datei selbst ist nicht wichtig. Sie sollten eine leere Datei mit dem Namen [!DNL zig.js] verwenden, um die Anzahl des Netzwerkverkehrs zu minimieren, der durch die Anforderung verursacht wird.

Damit [!DNL Sensor] einen brauchbaren Namen für die tatsächlich bereitgestellte Seite erfassen kann, müssen den dynamischen Seiten, die Sie verfolgen möchten oder denen Sie einen eindeutigen Seitennamen hinzufügen möchten, einige Zeilen JavaScript-Code hinzugefügt werden. Dieser Code bettet ein JavaScript-Snippet in die Seite ein, wodurch beim Laden der Seite eine tertiäre eingebettete Objektanforderung an den Webserver gesendet wird. Bei dieser Anforderung werden Details zur jeweiligen Seite gesendet, die an den Webserver zurückgesendet wurde. Der Seitenname, der tatsächlich bereitgestellt wurde, wird als Variable in der Abfrage-Zeichenfolge der eingebetteten Objektanforderung (in diesem Fall JavaScript) an den Webserver zurückgegeben.

Im Allgemeinen sollte die auf jeder HTML-Seite eingebettete Objektanforderung wie folgt aussehen:

```
<!-- BEGIN REFERENCE PAGE TAG--> 
<script language="javascript"> 
var vlc = "0" //Capture Link Click  1=TRUE, 0=FALSE 
var v = {}; 
v["_pn"] = "Application Form"; 
</script> 
 
<script language="javascript" src=”http://www.myserver.com/path/to/zig.js" type="text/javascript"></script> 
 
<noscript> 
<img src="/path/to/zag.gif?Log=1&v_jd=1" border="0" width="1" height="1"/> 
</noscript> 
 
<!-- END REFERENCE PAGE TAG-->
```

[!DNL Log=1] stellt sicher, dass die Anforderung  [!DNL Sensor] protokolliert wird, obwohl die Filterregeln für  [!DNL Sensor] Inhaltstypen anders lauten, z. B. das Herausfiltern von JavaScript- und Bildanforderungen, bevor diese gespeichert werden. Die deklarierte Variable v_pn gibt den Namen des tatsächlich bereitgestellten Seiteninhalts an, sodass [!DNL Site] den Namen der Seite kennt, die der Besucher tatsächlich angezeigt hat. Der Wert v_pn kann manuell oder durch einen anderen Skript- oder Anwendungscode festgelegt werden.

Nachdem der Wert gesammelt wurde, können Sie den Data Workbench-Server so konfigurieren, dass der Inhalt der Abfrage-Zeichenfolgenvariablen (z. B. v_pn=Antragsformular), die an den [!DNL zag.gif]-URI angehängt wird (z. B. [!DNL http://www.mysite.com/pageserved.asp?v_pn=Application%20Form]), als Erweiterung des URI [!DNL zag.gif] verwendet wird. Zusätzlich zu den bei jeder HTTP-Anforderung erfassten Basiswerten wird mit dieser Anforderung eine erweiterte Messung erfasst.

| Erfasste Daten | Erklärung | Beispiel |
|---|---|---|
| v_pn= | Mit der Zeichenfolgenvariable v_pn verknüpfter Wert | v_pn=Antragsformular |
