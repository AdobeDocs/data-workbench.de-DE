---
description: Der Ausführungsaufruf für Referenzseiten-Tags wird in Webseiten eingefügt, für die Sie Messdaten erfassen möchten.
title: Hinzufügen von Ausführungsaufrufen für Referenzseiten-Tags
uuid: 8c682649-d1b1-40a6-a2b2-4ff5a92b732f
exl-id: a4f9ab2b-50e8-4e0b-9c87-80dffb697316
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 3%

---

# Hinzufügen von Ausführungsaufrufen für Referenzseiten-Tags{#adding-reference-page-tag-execution-calls}

{{eol}}

Der Ausführungsaufruf für Referenzseiten-Tags wird in Webseiten eingefügt, für die Sie Messdaten erfassen möchten.

Sie sollte im Hauptteil des HTML-Dokuments enthalten sein und kann gegebenenfalls in eine globale Include-Fußzeile eingefügt werden. Die [!DNL Reference Page Tag Execution Call] kann von Ihrem Team geändert werden, um zusätzliche Informationen zu sammeln, die bei erforderlichen Zusammenkünften mit dem Adobe Consulting Services-Team ermittelt werden können.

Erleichterung der Datenerhebung durch Verwendung der [!DNL Reference Page Tag]führen Sie die folgenden Schritte aus:

1. Kopieren Sie den folgenden Code in Ihren HTML-Dokumenttext:

   ```
   <!--//BEGIN REFERENCE PAGE TAG--> 
   <script language="javascript"> 
   var vlc = "0" //Capture Link Click  1=TRUE, 0=FALSE 
   var v = {}; 
   </script> 
   
   <!--//MODIFIY PATH TO ZIG.JS--> 
   <script language="javascript" src="/path/to/zig.js" type="text/javascript"></script> 
   <!--//END REFERENCE PAGE TAG--> 
   
   <noscript> 
   <img src="/path/to/zag.gif?Log=1&v_jd=1" border="0" width="1" height="1"/> 
   </noscript> 
   <!-- END REFERENCE PAGE TAG-->
   ```

1. Ändern Sie den Pfad zum Speicherort der [!DNL zig.js] und [!DNL zag.gif] Dateien. Beispiel:

   ```
   //www.mysite.com/scripts/zig.js 
   //www.mysite.com/images/zag.gif 
   ```

Stellen Sie sicher, dass auf Ihrem Webserver die entsprechenden HTTP Cache-Control-Header festgelegt wurden, um sicherzustellen, dass die [!DNL zig.js]und [!DNL zag.gif] -Dateien werden vom Browser nicht zwischengespeichert. Sie können die HTTP Cache-Control-Header-Informationen mit einer von zwei Methoden festlegen. Die erste Methode besteht darin, einen HTTP-Header über den Webserver festzulegen. Die zweite Methode besteht darin, mithilfe eines Skripts einen HTTP-Header für jede bestimmte Seite oder jedes eingebettete Objekt festzulegen. Mit der Skriptmethode muss die Webseite mit einer Programmiersprache wie JSP oder ASP erstellt worden sein. Die Seite wird dann mit einem Skript so geschrieben, dass die entsprechenden Kopfzeileninformationen gesendet werden. Diese Methode ist von zwei offensichtlichen Nachteilen begleitet: 1) alle Seiten müssen codiert sein, um die Kopfzeile zu senden, und 2) die Seiten dürfen kein statisches HTML sein, was sich auf die Leistung des Webservers auswirkt.

Websites, die auf Microsoft IIS ausgeführt werden, können den entsprechenden HTTP-Header über die Microsoft Management Console hinzufügen. Websites von Netscape iPlanet Web-Servern können dies durch die Bearbeitung der [!DNL obj.conf] -Datei im Konfigurationsverzeichnis der Site. Der Apache-Webserver bietet Webmastern die Möglichkeit, HTTP-Header mithilfe des integrierten Moduls mod_headers anzupassen, wobei der AOLServer durch die Verwendung von TCL-Modulen anpassbar wird. Bevor Sie HTTP Cache-Control-Header implementieren, sollten Sie die Dokumentation für Ihre Webserver-Plattform lesen.

Im Allgemeinen sollte der HTTP-Header wie folgt strukturiert sein:

```
Cache-Control: no-cache 
Pragma: no-cache 
Expires: -1
```
