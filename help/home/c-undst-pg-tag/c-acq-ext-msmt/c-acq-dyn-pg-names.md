---
description: Bei einigen Sites ist es erforderlich, eingebettete Objektanforderungen zu verwenden, um Informationen an den Webserver zu übergeben, damit Details darüber, welche Seite tatsächlich bereitgestellt wurde, vom Sensor erfasst und für die Berichterstellung und Analyse verwendet werden können.
title: Erfassen dynamischer Seitennamen
uuid: eaa35023-bbfa-4eb9-9ab7-3986187e5537
exl-id: cd94caf0-b0dc-46c1-8f59-3ebb2f703286
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '594'
ht-degree: 1%

---

# Erfassen dynamischer Seitennamen{#acquiring-dynamic-page-names}

{{eol}}

Bei einigen Sites ist es erforderlich, eingebettete Objektanforderungen zu verwenden, um Informationen an den Webserver zu übergeben, damit Details darüber, welche Seite tatsächlich bereitgestellt wurde, vom Sensor erfasst und für die Berichterstellung und Analyse verwendet werden können.

Dies kann erforderlich sein, wenn die vom Webserver angezeigte URL der Seite nicht auf den Seiteninhalt hinweist, der dem Browser angezeigt wird. Dieser Fall beruht häufig auf der Verwendung von Personalisierungs- oder dynamischen Content-Management-Systemen, in denen der tatsächliche Inhalt, der auf einer Seite bereitgestellt wird, dynamisch von der URL, dem Cookie, den zugehörigen Daten und der Anwendungslogik bestimmt wird.

Die Implementierung eines eingebetteten Objekts zur Erfassung zusätzlicher Messungen sollte sich nur geringfügig auf die Gesamtleistung Ihrer Site auswirken. Adobe empfiehlt, eine JavaScript-Datei als Objekt einzubetten, mit dem die erweiterten Attribute erfasst werden. (Beachten Sie, dass eine JavaScript-Datei eingebettet werden kann, ohne dass sich dies auf das Layout und die Darstellung Ihrer Webseite auswirken könnte. Dies kann durch die Verwendung eines eingebetteten Bildes geschehen.) Um die innerhalb des eingebetteten Objekts übergebenen Daten genau zu erfassen, empfiehlt Adobe auch die Verwendung eines allgemeinen Namens. Zu Namenszwecken bezieht sich die Adobe auf dieses Objekt als [!DNL zig.js]. Die [!DNL zig.js] -Datei im entsprechenden Verzeichnis auf einem Webserver erstellt werden, auf dem [!DNL Sensor] installiert ist. Diese Datei muss vorhanden sein, damit die Anfrage keinen 404-Fehler-Code zurückgibt. Der Inhalt der Datei selbst ist nicht wichtig. Sie sollten eine leere Datei mit dem Namen [!DNL zig.js] , um den durch die Anfrage verursachten Netzwerkverkehr zu minimieren.

Für [!DNL Sensor] Um einen brauchbaren Namen für die Seite zu erfassen, die tatsächlich bereitgestellt wurde, müssen den dynamischen Seiten, die Sie verfolgen möchten oder denen Sie einen eindeutigen Seitennamen hinzufügen möchten, einige Zeilen JavaScript-Code hinzugefügt werden. Dieser Code bettet einen JavaScript-Ausschnitt in die Seite ein, wodurch eine im Tertiärbereich eingebettete Objektanforderung beim Laden der Seite an den Webserver gesendet wird. Diese Anfrage sendet Details über die bestimmte Seite, die an den Webserver zurückgegeben wurde. Der Name der Seite, die tatsächlich bereitgestellt wurde, wird als Variable in der Abfragezeichenfolge der eingebetteten Objektanforderung (in diesem Fall JavaScript) an den Webserver zurückgegeben.

Im Allgemeinen sollte die auf jeder dieser HTML-Seiten eingebettete Objektanforderung wie folgt aussehen:

```
<!-- BEGIN REFERENCE PAGE TAG-->
<script language="javascript">
var vlc = "0" //Capture Link Click  1=TRUE, 0=FALSE
var v = {};
v["_pn"] = "Application Form";
</script>

<script language="javascript" src=”https://www.myserver.com/path/to/zig.js" type="text/javascript"></script>

<noscript>
<img src="/path/to/zag.gif?Log=1&v_jd=1" border="0" width="1" height="1"/>
</noscript>

<!-- END REFERENCE PAGE TAG-->
```

[!DNL Log=1] gewährleistet, dass [!DNL Sensor] protokolliert die Anforderung trotz [!DNL Sensor] gegenteilige Filterregeln für Inhaltstypen, wie das Filtern aus JavaScript und Bildanforderungen, bevor sie gespeichert werden. Die deklarierte Variable v_pn gibt den Namen des tatsächlichen Seiteninhalts an, sodass [!DNL Site] kennt den Namen der Seite, die der Besucher tatsächlich angesehen hat. Der Wert v_pn kann manuell oder durch einen anderen Skript- oder Anwendungscode festgelegt werden.

Nachdem der Wert erfasst wurde, können Sie den Data Workbench-Server so konfigurieren, dass der Inhalt der Abfragezeichenfolgenvariablen (name=value pair, z. B. v_pn=Application Form) verwendet wird, die an die [!DNL zag.gif] URI (z. B. [!DNL https://www.mysite.com/pageserved.asp?v_pn=Application%20Form]) als Erweiterung der [!DNL zag.gif] URI. Zusätzlich zu den Grundlinienmessungen, die mit jeder HTTP-Anforderung erfasst werden, würde mit dieser Anfrage eine erweiterte Messung erfasst.

| Erfasste Daten | Erklärung | Beispiel |
|---|---|---|
| v_pn= | Wert, der der Abfragezeichenfolgenvariable v_pn zugeordnet ist | v_pn=Antragsformular |
