---
description: Das Marketing Ihrer Website kann die Platzierung von Anzeigen in Form von Bildern oder anderen Rich-Media-Dateien (bereitgestellt von Ihrem Webserver) auf Websites von Drittanbietern beinhalten.
title: Messen von Anzeigen-Impressions
uuid: ca2bd6bf-4f49-406c-b47a-18d6abfb48a4
exl-id: 77cd816e-63a4-4080-ac65-0661e1de4ec0
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '245'
ht-degree: 4%

---

# Messen von Anzeigen-Impressions{#measuring-advertisement-impression}

Das Marketing Ihrer Website kann die Platzierung von Anzeigen in Form von Bildern oder anderen Rich-Media-Dateien (bereitgestellt von Ihrem Webserver) auf Websites von Drittanbietern beinhalten.

In solchen Fällen möchten Sie möglicherweise sowohl die Impression der Anzeige in einem Browser als auch den nachfolgenden Clickthrough, falls dieser eintritt, an die Ziel-URL der Werbung auf Ihrer Website messen.

Bei Anzeigen in Form von Bildern führt das Anhängen von [!DNL Log=1] an die Abfragezeichenfolge zur Bildanforderung und damit zur Anzeige-Impression, die von [!DNL Sensor] zu Analysezwecken erfasst wird.

```
<!—REFERENCE IMPRESSION TAG-> 
<IMG SRC="http://www.mysite.com/images/zag.gif?Log=1&v_ic=CAMPAIGN 1&v_ica=72890ab&v_icr=http://money.cnn.com/markets/"/>
<!--END REFERENCE IMPRESSION TAG-->
```

| Erfasste Daten | Erklärung | Beispiel |
|---|---|---|
| v_ic= | Wert, der die Impressionskampagne angibt | v_ic=&quot;CAMPAIGN1&quot; |
| v_ica= | Wert, der das Impression Campaign-Asset angibt | v_ica=&quot;72890ab&quot; |
| v_icr= | Wert, der den Referrer &quot;Impression Campaign&quot;angibt | v_icr=&quot;http://money.cnn.com/markets/ |

Zusätzlich zum Anhängen von [!DNL Log=1] an die Bildanforderung sollte der URL, die von der Werbung zur Zielseite Ihrer Website führt, eine Kennung hinzugefügt werden, um die Werbung zu verfolgen, die zu dem Clickthrough geführt hat, und um die Clickthrough-Rate zurück zur jeweiligen Kampagne für diese Anzeige zu verfolgen.

```
<a href=”www.mysite.com/path/to/landingpage?Log=1&v_c=CAMPAIGN&v_ca=72890ab&v_cr=http://money.cnn.com/markets/”>
Click Here
</a>
```

<table id="table_B87134C522EF4AC9BD2AFA6F4A0CF574"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Erfasste Daten </th> 
   <th colname="col2" class="entry"> Erklärung </th> 
   <th colname="col3" class="entry"> Beispiel </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> v_c= </td> 
   <td colname="col2"> Wert, der die Clickthrough-Kampagne angibt </td> 
   <td colname="col3"> v_c="CAMPAIGN1" </td> 
  </tr> 
  <tr> 
   <td colname="col1"> v_ca= </td> 
   <td colname="col2"> Wert, der das Clickthrough-Kampagnen-Asset angibt </td> 
   <td colname="col3"> v_ca="72890ab" </td> 
  </tr> 
  <tr> 
   <td colname="col1"> v_cr= </td> 
   <td colname="col2"> Wert, der den Clickthrough-Kampagnen-Referrer angibt </td> 
   <td colname="col3"> <p> <span class="filepath"> v_cr="http://money.cnn.com/</span> </p> <p>märkte/ </p> </td> 
  </tr> 
 </tbody> 
</table>
