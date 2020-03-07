---
description: Grundlegende Informationen zu Arbeitsblattausdrücken und zur Verwendung von Zellenverweisen.
solution: Analytics
title: Arbeitsblattausdrücke
topic: Data workbench
uuid: be57d6bd-3e13-4c90-9034-8e0f2b8315aa
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Arbeitsblattausdrücke{#worksheet-expressions}

Grundlegende Informationen zu Arbeitsblattausdrücken und zur Verwendung von Zellenverweisen.

Das folgende Arbeitsblatt enthält Details zu den Besuchern, die die Seite &quot;Anwendungsassistent&quot;im Online-Antragsformular auf der Website einer Bank anzeigen.

![](assets/client-wkst.png)

* Spalte A zeigt eine Liste der Kategorien von Besuchern, die ausgewertet werden: Besucher, verweisende Besucher und verweisende Besucher von Referrer A.
* Spalte B zeigt die Anzahl der Besucher in jeder Kategorie an, die die Seite &quot;Jetzt beantragen&quot;angezeigt haben.
* Spalte C zeigt die Besucher an, die die Seiten &quot;Jetzt beantragen&quot;und &quot;Anwendungsassistent&quot;angezeigt haben.
* Spalte D enthält die Prozentsätze der Viewer für &quot;Jetzt anwenden&quot;in den drei Kategorien, die auch die Seite &quot;Anwendungsassistent&quot;aufgerufen haben.

Das Arbeitsblatt zeigt an, dass ungefähr 55 Prozent der Besucher, die über Referrer A auf die Seite &quot;Jetzt beantragen&quot;verwiesen, auch die Seite &quot;Anwendungsassistent&quot;aufgerufen haben.

Die folgende Tabelle enthält Beispielformeln für das Arbeitsblatt im vorherigen Beispiel:

<table id="table_0F5EFDB58040465AB599E6BE93324822"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Arbeitsblattzelle </th> 
   <th colname="col2" class="entry"> Formel </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>B2 </p> <p>Besucher, die die Seite "Jetzt beantragen"angezeigt haben </p> </td> 
   <td colname="col2"> <p><span class="filepath"> =Visitors[Page="/applynow/default.asp"]</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>B3 </p> <p>Referrer, die die Seite "Jetzt beantragen"angezeigt haben </p> </td> 
   <td colname="col2"> <p><span class="filepath"> =Referred_Visitors[page="/applynow/default.asp"]</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>B4 </p> <p>Verweisende Besucher von Referrer A, die die Seite "Jetzt beantragen"angezeigt haben </p> </td> 
   <td colname="col2"> <p> <span class="filepath"> =Referred_Visitors[page="/applynow/default.asp" </span> </p> <p> AND <span class="filepath"> Referrer="Ref A"]</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>C2 </p> <p>Besucher, die die Seite "Jetzt beantragen"und die Seite "Anwendungsassistent"angezeigt haben </p> </td> 
   <td colname="col2"> <p> <span class="filepath"> =Visitors[page="/applynow/default.asp" </span> </p> <p> AND <span class="filepath"> Page="/applynow/appwizard.asp"]</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>C3 </p> <p>Referrer, die die Seite "Jetzt beantragen"und den Anwendungsassistenten angezeigt haben </p> </td> 
   <td colname="col2"> <p> <span class="filepath"> =Referred_Visitors[page="/applynow/default.asp" </span> </p> <p> AND <span class="filepath"> Page="/applynow/appwizard.asp"]</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>C4 </p> <p>Verweisende Besucher von Referrer A, die die Seite "Jetzt beantragen"und die Seite "Anwendungsassistent"angezeigt haben </p> </td> 
   <td colname="col2"> <p> <span class="filepath"> =Referred_Visitors[page="/applynow/default.asp"</span> </p> <p> AND <span class="filepath"> Page="/applynow/appwizard.asp"</span> </p> <p> AND <span class="filepath"> Referrer="Ref A"]</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>D2 </p> <p>Prozentsatz der Besucher, die die Seite "Jetzt beantragen"und die Seite "Anwendungsassistent"angezeigt haben </p> </td> 
   <td colname="col2"> <p><span class="filepath"> =C2/B2*100</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>D3 </p> <p>Prozentsatz der verwiesenen Besucher, die die Seite "Jetzt beantragen"und die Seite "Anwendungsassistent"angezeigt haben </p> </td> 
   <td colname="col2"> <p><span class="filepath"> =C3/B3*100</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>D4 </p> <p>Prozentsatz der verweisenden Besucher von Referrer A, die die Seite "Jetzt beantragen"und die Seite "Anwendungsassistent"angezeigt haben </p> </td> 
   <td colname="col2"> <p><span class="filepath"> =C4/B4*100</span> </p> </td> 
  </tr> 
 </tbody> 
</table>

Wie bei anderen Visualisierungen werden Arbeitsblätter automatisch aktualisiert, wenn Sie eine Auswahl in einer anderen Visualisierung im Arbeitsbereich treffen. Weitere Informationen zum Erstellen von Auswahlen finden Sie unter [Vornehmen von Auswahlen in Visualisierungen](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-vis.md#concept-012870ec22c7476e9afbf3b8b2515746).

Im folgenden Webdatenbeispiel wurden mehrere Sitzungsdaten in der Visualisierung &quot;Sitzungen nach Tag&quot;ausgewählt. Das Arbeitsblatt zeigt an, dass während des ausgewählten Zeitraums etwa 69 Prozent der Besucher von Referrer A, die die Seite &quot;Jetzt beantragen&quot;aufgerufen haben, auch die Seite &quot;Anwendungsassistent&quot;aufgerufen haben. Ohne diese Auswahl (wie im obigen Beispiel gezeigt) sahen etwa 55 Prozent der Besucher von Referrer A die Seite &quot;Jetzt beantragen&quot;sowie die Seite &quot;Anwendungsassistent&quot;an.

![](assets/client-exp.png)

## Verwenden von Zellverweisen {#section-0004e315c9c94d359b1a8a39794ba555}

Sie können jede beliebige Zeichenfolge, ob als solche oder in einem anderen Ausdruck im Arbeitsblatt, durch eine Zellenreferenz ersetzen.

* **Einfache Zellenreferenz:** Zelle A2 enthält den Text &quot;Besucher&quot;, der als Überschrift verwendet wird. Zelle B2 enthält [!DNL eval(A1)], was als [!DNL =Visitors].

* **Filterzellreferenz:** Zelle A5 enthält das Datum des Vorgestern. Zelle B5 enthält [!DNL Visitors[ Day=A5 ]], was die Anzahl der Besucher gestern auswertet.

* **Verkettete Zellenreferenz:** Zelle A5 enthält das aktuelle Datum und Zelle A6 enthält den einstündigen Zeitraum von 08:00 bis 08:59 Uhr. Die Zelle B6 enthält [!DNL Visitors[ Hour=A5+&quot;&quot;+A6 ]], die die Anzahl der Besucher heute zwischen 08:00 und 09:00 Uhr auswertet.

