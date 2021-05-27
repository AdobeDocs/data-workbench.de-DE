---
description: Das Referenzseiten-Tag besteht aus einem Seiten-Tag-Ausführungsskript, das sich auf einem Webserver befindet und bei dem Aufruf dazu führt, dass alle clientseitigen Daten für die vom Site-Besucher angeforderte Seite erfasst werden.
title: Bearbeiten des Ausführungsskripts für Referenzseiten-Tags
uuid: 0db00b89-e420-423d-9b88-8b724baa828f
exl-id: bc922b59-716e-4e92-84b5-59a52620df03
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '231'
ht-degree: 7%

---

# Bearbeiten des Ausführungsskripts für Referenzseiten-Tags{#editing-the-reference-page-tag-execution-script}

Das Referenzseiten-Tag besteht aus einem Seiten-Tag-Ausführungsskript, das sich auf einem Webserver befindet und bei dem Aufruf dazu führt, dass alle clientseitigen Daten für die vom Site-Besucher angeforderte Seite erfasst werden.

Sie können das [!DNL Reference Page Tag Execution Script] ändern, um zusätzliche Informationen zu sammeln, die bei Bedarf bei der Zusammenstellung von Sitzungen mit dem Adobe Consulting Services-Team identifiziert werden können. Der [!DNL Reference Page Tag Execution Script] ist relativ klein, um große Download-Ergänzungen Ihrer Webseiten zu vermeiden.

Der folgende [!DNL Reference Page Tag Execution Script]-Code wird Ihnen in einer Datei mit dem Namen [!DNL zig.js] bereitgestellt:

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

Führen Sie die folgenden Schritte aus, um die Datenerfassung mithilfe von [!DNL Reference Page Tag] zu erleichtern:

1. Erstellen oder platzieren Sie die Bilddatei mit dem Namen [!DNL zag.gif] 1 Pixel pro Pixel in einem Verzeichnis auf Ihrem Webserver.
1. Ändern Sie die cd-Variable so, dass sie auf die entsprechende Domäne Ihrer Website oder Adobe-Domain der verwalteten Dienste verweist, von der aus auf die [!DNL zag.gif]-Datei verwiesen wird. Der Verweis auf die Datei wird durch Ausführung der Dateifunktionen [!DNL zig.js] erstellt. Beispiel:

   ```
   //www.mysite.com
   ```

1. Ändern Sie die cu-Variable so, dass sie auf den entsprechenden Pfad zum Speicherort der [!DNL zag.gif]-Datei verweist. Beispiel

   ```
   /scripts
   ```

1. Stellen Sie sicher, dass geeignete Cache-Control-Header für die Dateien [!DNL zag.gif] und [!DNL zig.js] eingerichtet sind.
