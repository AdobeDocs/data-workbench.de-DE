---
description: Schritte, die die Erfassung von Link-Klicks mithilfe des Referenzseiten-Tags erleichtern.
title: Tracking von Link-Klicks
uuid: e4c492d2-9c90-4ed7-b997-6c50bdf98f93
exl-id: 0cb743e6-5c6e-4f80-bc77-83d1e706c92b
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 3%

---

# Tracking von Link-Klicks{#tracking-link-clicks}

{{eol}}

Schritte, die die Erfassung von Link-Klicks mithilfe des Referenzseiten-Tags erleichtern.

Durch die Bereitstellung der [!DNL Reference Page Tag]können Messdaten gesammelt werden, die die Links (oder href-Werte) angeben, auf die Besucher beim Besuch bestimmter Seiten klicken. Normalerweise umfasst diese Sammlung nicht die Implementierung zusätzlicher Link-IDs in Ihre HTML-Seiten.

So erleichtern Sie die Erfassung von Link-Klicks durch Verwendung der [!DNL Reference Page Tag]führen Sie die folgenden Schritte aus:

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

1. Erstellen oder platzieren Sie die Bilddatei mit dem Namen 1 Pixel pro 1 Pixel [!DNL zag2.gif] in ein Verzeichnis auf Ihrem Webserver.
1. Ändern Sie die [!DNL lc.src] zur Referenzierung der entsprechenden Domäne Ihrer Website, von der aus die Variable [!DNL zag2.gif]-Datei referenziert wird.

1. Stellen Sie sicher, dass geeignete Cache-Control-Header für die [!DNL zag.gif] und [!DNL zig.js] Dateien.

1. In den HTML-Dateien, aus denen Sie Link-Klickwerte erfassen möchten, muss die [!DNL Reference Page Tag Execution Call] muss geändert werden, um die [!DNL Page Tag Execution Script] , um Link-Klicks für diese Seite zu erfassen. Ändern Sie dazu den Wert der vlc-Variablen in &quot;1&quot;, wie im folgenden Codebeispiel hervorgehoben:

```
<!-- BEGIN REFERENCE PAGE TAG-->
<script language="javascript">
var vlc = "1" //Capture Link Click  1=TRUE, 0=FALSE
var vfc = "0"; //Capture Form Field Click  1=TRUE, 0=FALSE
var v = {};
</script>

<script language="javascript" src=”https://www.myserver.com/path/to/zig.js" type="text/javascript"></script>

<noscript>
<img src="/path/to/zag.gif?Log=1&v_jd=1" border="0" width="1" height="1"/>
</noscript>

<!-- END REFERENCE PAGE TAG-->
```

| Erfasste Daten | Erklärung | Beispiel |
|---|---|---|
| v_ln= | Wert, der die Impressionskampagne angibt | v_ln=&quot;About%20US&quot; |
