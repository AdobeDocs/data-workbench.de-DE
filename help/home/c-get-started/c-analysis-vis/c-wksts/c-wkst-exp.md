---
description: Grundlegende Informationen zu Arbeitsblattausdrücken und zur Verwendung von Zellenverweisen.
title: Ausdrücke in Arbeitsblättern
uuid: be57d6bd-3e13-4c90-9034-8e0f2b8315aa
exl-id: 1ff3ec24-0363-4b6c-8c91-31e49ed0f7c4
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '539'
ht-degree: 2%

---

# Ausdrücke in Arbeitsblättern{#worksheet-expressions}

{{eol}}

Grundlegende Informationen zu Arbeitsblattausdrücken und zur Verwendung von Zellenverweisen.

Das folgende Arbeitsblatt enthält Details zu den Besuchern, die die Seite &quot;Anwendungsassistent&quot;im Online-Antragsformular auf der Website einer Bank anzeigen.

![](assets/client-wkst.png)

* Spalte A zeigt eine Liste der Kategorien von Besuchern, die ausgewertet werden: Besucher, verweisende Besucher und verweisende Besucher von Referrer A.
* Spalte B zeigt die Anzahl der Besucher in jeder Kategorie an, die die Seite &quot;Jetzt beantragen&quot;angesehen haben.
* Spalte C zeigt die Besucher an, die die Seiten &quot;Jetzt anwenden&quot;und &quot;Anwendungsassistent&quot;angesehen haben.
* Spalte D enthält die Prozentsätze der Jetzt anwenden-Viewer in den drei Kategorien, die auch die Seite &quot;Anwendungsassistent&quot;angezeigt haben.

Das Arbeitsblatt zeigt an, dass ungefähr 55 Prozent der Besucher, die von Referrer A auf die Seite &quot;Jetzt anwenden&quot;verwiesen wurden, auch die Seite &quot;Anwendungsassistent&quot;aufgerufen haben.

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
   <td colname="col1"> <p>B3 </p> <p>Referrer Besucher, die die Seite "Jetzt beantragen"angezeigt haben </p> </td> 
   <td colname="col2"> <p><span class="filepath"> =Referred_Visitors[Page="/applynow/default.asp"]</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>B4 </p> <p>Referrer-Besucher von Referrer A, die die Seite "Jetzt beantragen"angezeigt haben </p> </td> 
   <td colname="col2"> <p> <span class="filepath"> =Referred_Visitors[Page="/applynow/default.asp" </span> </p> <p> UND <span class="filepath"> referrer="Ref A"]</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>C2 </p> <p>Besucher, die die Seite "Jetzt anwenden"und die Seite "Anwendungsassistent"angezeigt haben </p> </td> 
   <td colname="col2"> <p> <span class="filepath"> =Visitors[Page="/applynow/default.asp" </span> </p> <p> UND <span class="filepath"> Page="/applynow/appwizard.asp"]</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>C3 </p> <p>Referrer Besucher, die die Seite "Jetzt anwenden"und die Seite "Anwendungsassistent"angezeigt haben </p> </td> 
   <td colname="col2"> <p> <span class="filepath"> =Referred_Visitors[Page="/applynow/default.asp" </span> </p> <p> UND <span class="filepath"> Page="/applynow/appwizard.asp"]</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>C4 </p> <p>Referrer-Besucher von Referrer A, die die Seite "Jetzt anwenden"und die Seite "Anwendungsassistent"angezeigt haben </p> </td> 
   <td colname="col2"> <p> <span class="filepath"> =Referred_Visitors[Page="/applynow/default.asp"</span> </p> <p> UND <span class="filepath"> Page="/applynow/appwizard.asp"</span> </p> <p> UND <span class="filepath"> referrer="Ref A"]</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>D2 </p> <p>Prozentsatz der Besucher, die die Seite "Jetzt anwenden"und die Seite "Anwendungsassistent"angezeigt haben </p> </td> 
   <td colname="col2"> <p><span class="filepath"> =C2/B2*100</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>D3 </p> <p>Prozentsatz der verwiesenen Besucher, die die Seite "Jetzt anwenden"und die Seite "Anwendungsassistent"angezeigt haben </p> </td> 
   <td colname="col2"> <p><span class="filepath"> =C3/B3*100</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>D4 </p> <p>Prozentsatz der verwiesenen Besucher von Referrer A, die die Seite "Jetzt anwenden"und die Seite "Anwendungsassistent"angezeigt haben </p> </td> 
   <td colname="col2"> <p><span class="filepath"> =C4/B4*100</span> </p> </td> 
  </tr> 
 </tbody> 
</table>

Wie bei anderen Visualisierungen werden Arbeitsblätter automatisch aktualisiert, wenn Sie eine Auswahl in einer anderen Visualisierung im Arbeitsbereich treffen. Weitere Informationen zum Erstellen von Auswahlen finden Sie unter [Auswahlen in Visualisierungen](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-vis.md#concept-012870ec22c7476e9afbf3b8b2515746).

Im folgenden Webdatenbeispiel wurden in der Visualisierung Sitzungen nach Tag mehrere Tage mit Sitzungsdaten ausgewählt. Das Arbeitsblatt zeigt an, dass während des ausgewählten Zeitraums etwa 69 Prozent der Besucher von Referrer A, die die Seite &quot;Jetzt anwenden&quot;angesehen haben, auch die Seite &quot;Anwendungsassistent&quot;angezeigt haben. Ohne diese Auswahl (wie im Beispiel oben gezeigt) haben rund 55 Prozent der Besucher von Referrer A die Seite &quot;Jetzt anwenden&quot;sowie die Seite &quot;Anwendungsassistent&quot;angezeigt.

![](assets/client-exp.png)

## Verwenden von Zellreferenzen {#section-0004e315c9c94d359b1a8a39794ba555}

Sie können jede beliebige Zeichenfolge, ob allein oder innerhalb eines anderen Ausdrucks im Arbeitsblatt, durch eine Zellenreferenz ersetzen.

* **Einfache Zellreferenz:** Zelle A2 enthält den Text Besucher , der als Überschrift verwendet wird. Zelle B2 enthält [!DNL eval(A1)], die als [!DNL =Visitors].

* **Filterzellreferenz:** Zelle A5 enthält das gestrige Datum. Zelle B5 enthält [!DNL Visitors[ Day=A5 ]], was sich auf die Anzahl der Besucher gestern auswertet.

* **Verkettete Zellenreferenz:** Zelle A5 enthält das heutige Datum und Zelle A6 enthält den einstündigen Zeitraum zwischen 8:00 und 8:59 Uhr. Zelle B6 enthält [!DNL Visitors[ Hour=A5+” ”+A6 ]], was der Anzahl der Besucher von heute zwischen 8:00 und 9:00 Uhr entspricht.
