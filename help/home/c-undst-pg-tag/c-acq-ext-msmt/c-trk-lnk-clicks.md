---
description: Schritte, die die Erfassung von Link-Klicks mithilfe des Referenzseiten-Tags erleichtern.
solution: Analytics
title: Linkklicks verfolgen
topic: Data workbench
uuid: e4c492d2-9c90-4ed7-b997-6c50bdf98f93
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Linkklicks verfolgen{#tracking-link-clicks}

Schritte, die die Erfassung von Link-Klicks mithilfe des Referenzseiten-Tags erleichtern.

Durch die Bereitstellung des können [!DNL Reference Page Tag]Messungsdaten mit den Links (oder href-Werten) erfasst werden, auf die Besucher während des Besuchs bestimmter Seiten klicken. Normalerweise umfasst diese Sammlung nicht die Implementierung zusätzlicher Link-IDs in Ihre HTML-Seiten.

Um die Erfassung von Link-Klicks mithilfe des [!DNL Reference Page Tag]zu erleichtern, führen Sie die folgenden Schritte aus:

1. Kopieren Sie den folgenden Code in die vorhandene Datei mit dem Namen [!DNL zig.js]:

   ```
   //REFERENCE LINK AND FORM CLICK PAGE TAG 
   //INITIATE FUNCTIONS ONLOAD 
   function addEvent(obj, evType, fn){  
    if (obj.addEventListener){  
      obj.addEventListener(evType, fn, false);  
      return true;  
    } else if (obj.attachEvent){  
      var r = obj.attachEvent("on"+evType, fn);  
      return r;  
    } else {  
      return false;  
    }  
   } 
   addEvent(window, 'load', startCapture); 
   addEvent(window, 'load', startCapture); 
   function startCapture(){ 
   //TO CAPTURE LINK CLICKS 
     if (vlc == "1"){captureLink();} 
     //TO CAPTURE FORM FIELD CLICKS 
     if (vfc == "1"){captureForm();} 
   } 
   //BEGIN LINK CAPTURE PAGE TAG 
   function captureLink(){ 
     if (document.links[0]){ 
       if (document.links){ 
         var links = document.links, link, k=0; 
         while(link=links[k++]) { 
           link.onclick = captureLinkName; 
    } 
       } 
     } 
   } 
   function captureLinkName() { 
     var lc=new Image(); 
     this.parent = this.parentNode; 
     lc.src='zag2.gif?linkname=' + escape(this.name) + "&cd=" + new Date().getTime(); 
   } 
   //END LINK CAPTURE PAGE TAG 
   //BEGIN FORM CLICK CAPTURE PAGE TAG 
   function captureForm(){ 
     if (document.forms[0]) { 
       if(document.forms){ 
    for(i=0; i<document.forms[0].elements.length; i++){ 
           var forms = document.forms[0].elements[i]; 
           forms.onfocus = captureFormName; 
         } 
       } 
     } 
   } 
   function captureFormName() { 
     var fc=new Image(); 
     fc.src='zag3.gif?fieldname=' + escape(this.name) + "&cd=" + new Date().getTime(); 
   } 
   //END FORM CLICK CAPTURE PAGE TAG
   ```

1. Erstellen oder platzieren Sie die Bilddatei mit dem Format 1 Pixel pro 1 Pixel [!DNL zag2.gif] in einem Verzeichnis, das auf Ihrem Webserver vorhanden ist.
1. Ändern Sie die [!DNL lc.src] Variable so, dass sie auf die entsprechende Domäne Ihrer Website verweist, von der aus auf die [!DNL zag2.gif]Datei verwiesen wird.

1. Stellen Sie sicher, dass für die Dateien [!DNL zag.gif] und [!DNL zig.js] Dateien geeignete Cache-Control-Header eingerichtet wurden.

1. Innerhalb der HTML-Dateien, aus denen Sie Link-Klickwerte erfassen möchten, [!DNL Reference Page Tag Execution Call] muss der Link geändert werden, um den Benutzer darüber zu informieren, dass er Link-Klicks für diese Seite erfasst [!DNL Page Tag Execution Script] . Ändern Sie dazu den Variablenwert vlc in &quot;1&quot;, wie im folgenden Codebeispiel hervorgehoben:

```
<!-- BEGIN REFERENCE PAGE TAG--> 
<script language="javascript"> 
var vlc = "1" //Capture Link Click  1=TRUE, 0=FALSE 
var vfc = "0"; //Capture Form Field Click  1=TRUE, 0=FALSE 
var v = {}; 
</script> 
 
<script language="javascript" src=”http://www.myserver.com/path/to/zig.js" type="text/javascript"></script> 
 
<noscript> 
<img src="/path/to/zag.gif?Log=1&v_jd=1" border="0" width="1" height="1"/> 
</noscript> 
 
<!-- END REFERENCE PAGE TAG-->
```

| Erfasste Daten | Erklärung | Beispiel |
|---|---|---|
| v_ln= | Wert, der die Impressionskampagne angibt | v_ln=&quot;About%20us&quot; |

