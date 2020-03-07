---
description: Der "Reference Page Tag Execution"-Aufruf wird in Webseiten eingefügt, für die Sie Messungsdaten erfassen möchten.
solution: Analytics
title: Hinzufügen von Seiten-Tag-Ausführungsaufrufen für Referenzseiten
topic: Data workbench
uuid: 8c682649-d1b1-40a6-a2b2-4ff5a92b732f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Hinzufügen von Seiten-Tag-Ausführungsaufrufen für Referenzseiten{#adding-reference-page-tag-execution-calls}

Der &quot;Reference Page Tag Execution&quot;-Aufruf wird in Webseiten eingefügt, für die Sie Messungsdaten erfassen möchten.

Sie sollte im Hauptteil des HTML-Dokuments enthalten sein und kann gegebenenfalls in einer globalen Include-Fußzeile platziert werden. Der Bericht [!DNL Reference Page Tag Execution Call] kann von Ihrem Team geändert werden, um zusätzliche Informationen zu erfassen, die bei der Zusammenstellung von Sitzungen mit dem Adobe Consulting Services-Team identifiziert werden können.

Um die Datenerfassung mithilfe des [!DNL Reference Page Tag]zu erleichtern, führen Sie die folgenden Schritte aus:

1. Kopieren Sie den folgenden Code in Ihren HTML-Dokumentkörper:

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

Stellen Sie sicher, dass die entsprechenden HTTP Cache-Control-Header auf Ihrem Webserver eingestellt wurden, um sicherzustellen, dass die Dateien [!DNL zig.js]und [!DNL zag.gif] Dateien nicht vom Browser zwischengespeichert werden. Sie können die HTTP Cache-Control-Header-Informationen mit einer der beiden Methoden festlegen. Die erste Methode besteht darin, einen HTTP-Header über den Webserver festzulegen. Die zweite Methode besteht darin, mithilfe eines Skripts einen HTTP-Header für jede bestimmte Seite oder jedes eingebettete Objekt festzulegen. Bei der Skriptmethode muss die Webseite mit einer Programmiersprache wie JSP oder ASP erstellt worden sein. Die Seite wird dann mit einem Skript versehen, sodass die entsprechenden Kopfzeileninformationen gesendet werden. Zwei offensichtliche Nachteile sind mit dieser Methode verbunden: 1) alle Seiten müssen kodiert sein, um die Kopfzeile zu senden, und 2) die Seiten können nicht statisches HTML sein, was sich auf die Leistung des Webservers auswirkt.

Websites, die auf Microsoft IIS ausgeführt werden, können den entsprechenden HTTP-Header über die Microsoft Management Console hinzufügen. Websites, die von Netscape iPlanet Webservern bereitgestellt werden, können dies erreichen, indem Sie die [!DNL obj.conf] Datei im Konfigurationsverzeichnis der Site bearbeiten. Der Apache Web Server bietet Webmastern die Möglichkeit, HTTP-Header mithilfe des mitgelieferten Moduls mod_headers anzupassen, wobei AOLServer mithilfe von Tcl-Modulen angepasst werden kann. Bevor Sie HTTP Cache-Control-Header implementieren, sollten Sie sich die Dokumentation zu Ihrer Webserver-Plattform ansehen.

Im Allgemeinen sollte der HTTP-Header wie folgt strukturiert sein:

```
Cache-Control: no-cache 
Pragma: no-cache 
Expires: -1
```

