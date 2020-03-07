---
description: Bei einigen Sites ist es erforderlich, eingebettete Objektanforderungen zu verwenden, um Informationen an den Webserver weiterzugeben, damit Details darüber, welche Seite tatsächlich bereitgestellt wurde, von Sensor erfasst und für die Berichterstellung und Analyse verwendet werden können.
solution: Analytics
title: Abrufen dynamischer Seitennamen
topic: Data workbench
uuid: eaa35023-bbfa-4eb9-9ab7-3986187e5537
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Abrufen dynamischer Seitennamen{#acquiring-dynamic-page-names}

Bei einigen Sites ist es erforderlich, eingebettete Objektanforderungen zu verwenden, um Informationen an den Webserver weiterzugeben, damit Details darüber, welche Seite tatsächlich bereitgestellt wurde, von Sensor erfasst und für die Berichterstellung und Analyse verwendet werden können.

Dies kann erforderlich sein, wenn die vom Webserver angezeigte URL der Seite nicht auf den Seiteninhalt hinweist, der dem Browser angezeigt wird. Dieser Fall resultiert oft aus der Verwendung von Personalisierungs- oder dynamischen Content-Management-Systemen, in denen der tatsächliche Inhalt, der auf einer Seite bereitgestellt wird, spontan von der URL, dem Cookie, den zugehörigen Daten und der Anwendungslogik bestimmt wird.

Die Implementierung eines eingebetteten Objekts zum Sammeln zusätzlicher Messungen sollte sich nur minimal auf die Gesamtergebnisse Ihrer Site auswirken. Adobe empfiehlt, eine JavaScript-Datei als Objekt zum Erfassen der erweiterten Attribute einzubetten. (Beachten Sie, dass eine JavaScript-Datei eingebettet werden kann, ohne dass sich dies auf das Layout und die Darstellung Ihrer Webseite auswirken könnte. Dies kann durch die Verwendung eines eingebetteten Bildes geschehen.) Um die im eingebetteten Objekt weitergeleiteten Informationen genau zu erfassen, empfiehlt Adobe außerdem die Verwendung eines allgemeinen Namens. Zur Benennung verweist Adobe auf dieses Objekt als [!DNL zig.js]. Die [!DNL zig.js] Datei sollte im entsprechenden Verzeichnis auf einem Webserver erstellt werden, auf dem sie installiert [!DNL Sensor] ist. Diese Datei muss vorhanden sein, damit die Anforderung keinen 404-Fehlercode zurückgibt. Der Inhalt der Datei selbst ist nicht wichtig. Sie sollten eine leere Datei mit dem Namen verwenden, [!DNL zig.js] um den Netzwerkverkehr, der durch die Anforderung verursacht wird, zu minimieren.

Damit ein benutzerdefinierter Name für die tatsächlich bereitgestellte Seite erfasst [!DNL Sensor] werden kann, müssen den dynamischen Seiten, die Sie verfolgen möchten oder denen Sie einen eindeutigen Seitennamen hinzufügen möchten, einige Zeilen JavaScript-Code hinzugefügt werden. Dieser Code bettet ein JavaScript-Snippet in die Seite ein, wodurch beim Laden der Seite eine tertiäre eingebettete Objektanforderung an den Webserver gesendet wird. Bei dieser Anforderung werden Details zur jeweiligen Seite gesendet, die an den Webserver zurückgesendet wurde. Der Name der tatsächlich bereitgestellten Seite wird als Variable in der Abfragezeichenfolge der eingebetteten Objektanforderung (in diesem Fall JavaScript) an den Webserver zurückgegeben.

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

[!DNL Log=1] stellt sicher, dass die Anforderung [!DNL Sensor] protokolliert wird, obwohl die Filterregeln des [!DNL Sensor] Inhaltstyps anders lauten, z. B. das Filtern von JavaScript- und Bildanforderungen, bevor diese gespeichert werden. Die deklarierte Variable v_pn identifiziert den Namen des tatsächlichen Seiteninhalts, der bereitgestellt wird, damit der Name der Seite, die der Besucher tatsächlich angesehen hat, [!DNL Site] bekannt ist. Der Wert v_pn kann manuell oder durch einen anderen Skript- oder Anwendungscode festgelegt werden.

Nachdem der Wert erfasst wurde, können Sie den Data Workbench-Server so konfigurieren, dass der Inhalt der Abfragezeichenfolgen-Variablen (Name=Wert, z. B. v_pn=Anwendungsformular), die an den [!DNL zag.gif] URI angehängt wird (z. B. [!DNL http://www.mysite.com/pageserved.asp?v_pn=Application%20Form]), als Erweiterung des [!DNL zag.gif] URI verwendet wird. Zusätzlich zu den bei jeder HTTP-Anforderung erfassten Basiswerten wird mit dieser Anforderung eine erweiterte Messung erfasst.

| Erfasste Daten | Erklärung | Beispiel |
|---|---|---|
| v_pn= | Mit der Abfragezeichenfolgen-Variable v_pn verknüpfter Wert | v_pn=Antragsformular |

