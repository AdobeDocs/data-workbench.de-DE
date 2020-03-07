---
description: Das Referenzseiten-Tag besteht aus einem Seiten-Tag-Ausführungsskript, das sich auf einem Webserver befindet, und bei einem Aufruf werden alle clientseitigen Daten für die vom Site-Besucher angeforderte Seite erfasst.
solution: Analytics
title: Bearbeiten des Skripts für die Ausführung des Referenzseitentags
topic: Data workbench
uuid: 0db00b89-e420-423d-9b88-8b724baa828f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Bearbeiten des Skripts für die Ausführung des Referenzseitentags{#editing-the-reference-page-tag-execution-script}

Das Referenzseiten-Tag besteht aus einem Seiten-Tag-Ausführungsskript, das sich auf einem Webserver befindet, und bei einem Aufruf werden alle clientseitigen Daten für die vom Site-Besucher angeforderte Seite erfasst.

Sie können die ändern, [!DNL Reference Page Tag Execution Script] um zusätzliche Informationen zu erfassen, die möglicherweise bei der Anforderungserfassung von Sitzungen mit dem Adobe Consulting Services-Team identifiziert werden. Die Größe [!DNL Reference Page Tag Execution Script] ist relativ klein, um große Download-Ergänzungen Ihrer Webseiten zu vermeiden.

Der folgende [!DNL Reference Page Tag Execution Script] Code wird in einer Datei mit dem Namen bereitgestellt [!DNL zig.js]:

```
//REFERENCE PAGE TAG 
// CONSTANTS 
var ct = "<img src="; 
var cd = "[PATH_TO_WEB_SERVER]"; //this should contain the domain of 
                               //the web site that will host the 
                                //page tag 
 
var cu = "[PATH_TO_WEB_PAGE_TAG_CODE]/zag.gif?Log=1";  
                                 //this should contain the full path to 
                                 //the zag.gif file (excluding domain) 
                                 //and include the query string of log=1 
var ce = ">"; 
var c = {}; 
c["sw"] = screen.width; 
c["sh"] = screen.height; 
c["cd"] = screen.colorDepth; 
var co = ""; 
 
for ( cKey in c ) { 
co = co+"&"+cKey+"="+escape(c[cKey]); 
} 
document.write(ct,cd,cu,co,ce); 
 
var d = {}; 
d["dt"] = document.title; 
d["dr"] = document.referrer; 
d["cb"] = new Date().getTime(); 
var vo = ""; 
 
if (typeof v != "undefined") { 
for ( vKey in v ) { 
vo = vo+"&"+vKey+"="+escape(v[vKey]); 
} 
} 
for ( dKey in d ) { 
vo = vo+"&"+dKey+"="+escape(d[dKey]); 
} 
document.write(ct,cd,cu,vo,ce); 
//END REFERENCE PAGE TAG 
```

Um die Datenerfassung mithilfe des [!DNL Reference Page Tag]zu erleichtern, führen Sie die folgenden Schritte aus:

1. Erstellen oder platzieren Sie die Bilddatei mit dem Format 1 Pixel pro 1 Pixel [!DNL zag.gif] in einem Verzeichnis, das auf Ihrem Webserver vorhanden ist.
1. Ändern Sie die cd-Variable so, dass sie auf die entsprechende Domäne Ihrer Website oder der von Adobe verwalteten Dienste verweist, von der aus auf die [!DNL zag.gif] Datei verwiesen wird. Der Verweis auf die Datei wird durch die Ausführung der [!DNL zig.js] Dateifunktionen erstellt. Beispiel:

   ```
   //www.mysite.com
   ```

1. Ändern Sie die cu-Variable, um auf den entsprechenden Pfad zum Speicherort der [!DNL zag.gif] Datei zu verweisen. Beispiel

   ```
   /scripts
   ```

1. Stellen Sie sicher, dass für die Dateien [!DNL zag.gif] und [!DNL zig.js] Dateien geeignete Cache-Control-Header eingerichtet wurden.
