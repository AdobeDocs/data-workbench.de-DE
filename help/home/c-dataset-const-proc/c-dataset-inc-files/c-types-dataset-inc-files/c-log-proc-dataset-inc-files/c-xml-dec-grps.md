---
description: Die Verarbeitung von XML-Dateien als Protokollquellen zum Definieren von Decodern zum Extrahieren von Daten aus der XML-Datei.
title: XML-Decoder-Gruppen
uuid: 8fc9ab80-9a71-4fe2-a646-e830ffeb67b9
exl-id: 0b0534b7-8596-4528-a643-8a9b41dcaa33
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1295'
ht-degree: 1%

---

# XML-Decoder-Gruppen{#xml-decoder-groups}

Die Verarbeitung von XML-Dateien als Protokollquellen zum Definieren von Decodern zum Extrahieren von Daten aus der XML-Datei.

>[!NOTE]
>
>Die Definition von XML-Decodergruppen für XML-Protokollquellen erfordert Kenntnisse über die Struktur und den Inhalt der XML-Datei, die zu extrahierenden Daten und die Felder, in denen diese Daten gespeichert werden. Dieser Abschnitt enthält grundlegende Beschreibungen der Parameter, die Sie für Decoder angeben können. Wie Sie Decoder verwenden, hängt von der XML-Datei ab, die Ihre Quelldaten enthält.

Informationen zu den Formatanforderungen für XML-Protokollquellen finden Sie unter [Protokollquellen](../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-6714c720fac044cbb9af003bf401b2ea). Wenden Sie sich zur Unterstützung bei der Definition von XML-Decodern an die Adobe.

Die oberste Ebene eines XML-Decoders ist eine Decodergruppe (XMLDecoderGroup), die aus einer Reihe von Decodertabellen besteht, mit denen Sie Daten aus einer XML-Datei eines bestimmten Formats extrahieren. Wenn Sie XML-Dateien mit unterschiedlichen Formaten haben, müssen Sie für jedes Format eine Decoder-Gruppe definieren. Jede Decodergruppe besteht aus einer oder mehreren Decodertabellen.

In der folgenden Tabelle werden der Parameter Tabellen und alle Unterparameter beschrieben, die Sie zum Definieren einer XML-Decoder-Gruppe angeben müssen.

<table id="table_06C40C5149E94548A1B0C2ED4397624B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Tabellen </td> 
   <td colname="col2"> <p>Jede Tabelle in einer Decoder-Gruppe stellt eine Datenebene dar, die aus der XML-Datei extrahiert werden soll. Wenn Sie beispielsweise Daten zu Besuchern extrahieren möchten, erstellen Sie eine Decoder-Tabelle, die aus den Informationen besteht, die Sie für jeden Besucher extrahieren möchten. Sie können auch Decodertabellen in Decodertabellen erstellen (siehe Untergeordnete Elemente). </p> <p> <b>So fügen Sie eine Tabelle zu einer Decoder-Gruppe hinzu</b> 
     <ul id="ul_C73CAD77440B4465B9FCE08BF4FA0749"> 
      <li id="li_C4B8CC5A85D942898F1EB76778105818"> Klicken Sie mit der rechten Maustaste auf <span class="uicontrol"> Tabellen </span> und klicken Sie auf <span class="uicontrol"> Hinzufügen neuer </span> &gt; <span class="uicontrol"> XMLDecoderTable </span>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Felder </td> 
   <td colname="col2"> <p>Die erweiterten Felder (z. B. x-trackingid, x-email), in denen die Daten gespeichert werden. Die im Feld zu speichernden Daten werden durch die Unterfelder Pfad und/oder Vorgang bestimmt. </p> <p> Der Pfad ist die Feldebene innerhalb der strukturierten XML-Datei. Der Pfad eines Felds ist relativ zum Pfad der Tabelle, in der es definiert ist. Beispiele sind <span class="filepath"> tag.tag.tag </span> oder <span class="filepath"> tag.tag.tag.@attribute </span> Beachten Sie, dass bei Pfaden zwischen Groß- und Kleinschreibung unterschieden wird. </p> <p> Ein Vorgang wird auf jede Zeile im angegebenen Pfad angewendet, um eine Ausgabe zu erzeugen. Die folgenden Vorgänge sind verfügbar: 
     <ul id="ul_B264A411D7E3446288E7E69D62150B8B"> 
      <li id="li_5936E81C0EEF46AFB780E451A04A88E4"><b>LAST: </b> Das Feld nimmt den Wert des letzten Vorkommens des Pfads in der XML-Datei an. </li> 
      <li id="li_7BC4F24F2CA84C2EB64B06FE09B4CAF6"><b>RANDOM: </b> Weist dem Feld einen zufälligen Wert zu. Dieser Vorgang ist nützlich, wenn Sie eine eindeutige ID generieren müssen, z. B. für das x-trackingid-Feld. </li> 
      <li id="li_C1D34EA11BFB4859A25A275A9B63FB56"><b>INHERIT:</b> Das definierte Feld erbt seinen Wert aus dem entsprechenden Feld der übergeordneten Tabelle. </li> 
      <li id="li_F62FB8CD962E4E1495D9A2D5B7A78E2A"><b>"<i>Konstante  </i>":</b> Die Konstante muss in Anführungszeichen gesetzt werden. Sie können einen konstanten Vorgang verwenden, um zu überprüfen, ob ein bestimmter Pfad vorhanden ist. Wenn der Pfad vorhanden ist, wird dem Feld der Wert der Konstante zugewiesen. </li> 
     </ul> </p> <p> <b>So fügen Sie ein Feld zu einer Decodertabelle hinzu</b> </p> <p> 
     <ul id="ul_91D104D927424DEA9E788E43B2F6FEA9"> 
      <li id="li_5448B01EE82349569BBFC99C9604D7B8"> Klicken Sie mit der rechten Maustaste auf <span class="uicontrol"> Felder </span> und klicken Sie dann auf <span class="uicontrol"> Hinzufügen neuer </span> &gt; <span class="uicontrol"> XMLDecoderField </span>. Definieren Sie Feld, Vorgang und Pfad nach Bedarf. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Path </td> 
   <td colname="col2"> <p>Die Ebene innerhalb der strukturierten XML-Datei, für die die Decoder-Tabelle Informationen enthält. Bei einer untergeordneten XML-Decodertabelle ist der Pfad relativ zum Pfad der übergeordneten Tabelle. Beachten Sie, dass bei Pfaden zwischen Groß- und Kleinschreibung unterschieden wird. </p> <p> Wenn Ihre XML-Datei beispielsweise die Struktur enthält: </p> 

    &amp;lt;visitor&amp;gt;
    
    &amp;nbsp;
    
    ..
    
    &amp;nbsp;
    
    &amp;lt;/visitor&amp;gt;
    
    &amp;lt;/logdata&amp;gt;&amp;nbsp;   &lt;p> dann wäre der Pfad &lt;span class=&quot;filepath&quot;>logdata.visitor&lt;/span> . &lt;/p> &lt;/td>
</tr> 
  <tr> 
   <td colname="col1"> Tabelle </td> 
   <td colname="col2"> <p>Der Wert dieses Parameters sollte immer "Protokolleintrag"lauten. </p> <p> <p>Hinweis:  Ändern Sie diesen Wert nicht, ohne die Adobe zu konsultieren. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Kinder </td> 
   <td colname="col2"> <p>Optional. Eine oder mehrere eingebettete Decoder-Tabellen. Jedes untergeordnete Element enthält die oben beschriebenen Parameter "Felder", "Pfad"und "Tabelle". </p> <p> <b>Hinzufügen eines untergeordneten Elements zu einer Decodertabelle</b> </p> <p> 
     <ul id="ul_902AC6CA5D66457D84CBA3194FF49BBE"> 
      <li id="li_07B4D60E7E2E4630B4878691E575936A"> Klicken Sie mit der rechten Maustaste auf <span class="uicontrol"> Untergeordnete Elemente </span> und klicken Sie auf <span class="uicontrol"> Hinzufügen neuer </span> &gt; <span class="uicontrol"> XMLDecoderTable </span>. Definieren Sie Feld, Vorgang und Pfad nach Bedarf. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

Um eine XML-Datei als Protokollquelle für einen Datensatz zu verwenden, müssen XML-Decoder-Gruppen und -Tabellen definiert werden, um die zu verarbeitenden Informationen in den Datensatz zu extrahieren. In diesem Beispiel erfahren Sie, wie Sie Decodergruppen und Tabellen für eine XML-Beispielprotokollquelle für einen Webdatensatz definieren.

Die folgende XML-Datei enthält Informationen zu einem Website-Besucher, einschließlich einer Experience Cloud-ID, E-Mail-Adresse, physischen Adresse und Informationen zu den Seitenansichten des Besuchers.

![](assets/xmlFile_LogSource.png)

Da wir nur eine XML-Datei haben, benötigen wir nur eine Decoder-Gruppe, die wir &quot;XML-Beispielformat&quot;nennen. Diese Decoder-Gruppe gilt für alle anderen XML-Dateien im gleichen Format wie diese Datei. Um mit der Erstellung von XML-Decodertabellen innerhalb dieser Decoder-Gruppe zu beginnen, müssen wir zunächst festlegen, welche Informationen wir extrahieren und in welchen Feldern die Daten gespeichert werden sollen.

In diesem Beispiel extrahieren wir Informationen über den Besucher und die mit diesem Besucher verbundenen Seitenansichten. Dazu erstellen wir eine übergeordnete XML-Decodertabelle der obersten Ebene mit Informationen zum Besucher und eine eingebettete (untergeordnete) XML-Decodertabelle mit Informationen zu den Seitenansichten des Besuchers.

**Die Informationen für die übergeordnete (Besucher-)Tabelle lauten wie folgt.**

* Eine Datentypkennung für jede Datenzeile in der XML-Datei. Wir verwenden VISITOR als unsere Kennung, damit wir schnell Datenzeilen für den Besucher und nicht für die Seitenansichten identifizieren können. Wir können diesen Wert im Feld x-rowtype speichern.
* Die Besucher-ID, die wir im Feld x-trackingid speichern.
* Die E-Mail-Adresse des Besuchers (contact.email), die wir im Feld x-email speichern.
* Der Registrierungsstatus des Besuchers. Wenn der Besucher ein registrierter Benutzer ist, können wir den Wert &quot;1&quot;im Feld &quot;x-is-registered&quot;speichern.
* Der Pfadwert ist [!DNL logdata.visitor] und der Tabellenwert [!DNL Log Entry]. Weitere Informationen zu diesen Parametern finden Sie in der obigen Tabelle XMLDecoderGroup .

**Die Informationen für die untergeordnete Tabelle (Seitenansichten) lauten wie folgt:**

* Eine Datentypkennung für jede Datenzeile in der XML-Datei. Wir verwenden &quot;PAGEVIEW&quot;als unsere Kennung, damit wir Datenzeilen, die sich auf die Seitenansichten des Besuchers und nicht nur auf den Besucher beziehen, schnell identifizieren können. Dieser Wert wird im Feld x-rowtype gespeichert.
* Die ID des Besuchers. Dieser Wert wird von der übergeordneten Tabelle übernommen und im Feld x-trackingid gespeichert.
* Der Zeitstempel jeder Seitenansicht, der im Feld x-event-time gespeichert wird.
* Der URI jeder Seitenansicht, der im Feld cs-uri-stamm gespeichert wird.
* Der Pfadwert ist &quot;pageview&quot;und der Tabellenwert &quot;Log Entry&quot;. Weitere Informationen zu diesen Parametern finden Sie in der obigen Tabelle XMLDecoderGroup .

Die folgende Bildschirmaufzeichnung zeigt einen Teil der [!DNL Log Processing Dataset Include]-Datei mit der resultierenden XML-Decoder-Gruppe für die XML-Beispieldatei, basierend auf der diskutierten Struktur der übergeordneten und untergeordneten XML-Decodertabellen.

![](assets/cft_LogProc_xmldecodergroup_top.png)

![](assets/cfg_LogProcessingInclude_XMLDecoderGroup_bottom.png)

Eine Tabelle, die die Ausgabe dieses Decoders für unsere XML-Beispieldatei anzeigt, sieht etwa wie folgt aus:

| x-rowtype | cs—uri-system | x-email | x-is-registered | x-event-time | x-tracking-id |
|---|---|---|---|---|---|
| BESUCHER |  | foo@bar.com | 1 |  | 1 |
| PAGEVIEW | /index.html |  |  | 01.01.2006 08:00:00 | 1 |
| PAGEVIEW | / |  |  | 01.01.2006 08:00:30 | 1 |

Sie können eine Tabelle wie die oben stehende in Data Workbench erstellen, indem Sie eine Feld-Viewer-Oberfläche verwenden. Informationen zur Benutzeroberfläche des Feld-Viewers finden Sie unter [Tools für die Datensatzkonfiguration](../../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md#concept-6e058b7691834cf79dcfd1573f78d4f5).

## Verwenden von #value on XML element zum Lesen des Attributwerts {#section-88758428afb94f0baa5a986604d53bc1}

Sie können jetzt das Tag **[!DNL #value]** in XML-Pfaden verwenden, um den Wert eines XML-Elements abzurufen.

Wenn Sie beispielsweise zuvor den Pfad **`<Hit><Page name="Home Page" index="20">home.html</Page></Hit>`** angegeben haben, können Sie den Wert des Tags `<Page>` nicht lesen. Zum Lesen des Werts eines `<Page>`-Tags und seiner Attribute können Sie [!DNL Hit.Page.@name] bzw. [!DNL Hit.Page.@index] verwenden. Sie können den Wert des Tags auch mit dem Ausdruck **`Hit.Page.#value`** abrufen.

Sie können beispielsweise den Wert von Tag `<varValue>` lesen, indem Sie im Decoder folgendes Feld hinzufügen:

```
7 = XMLDecoderField: 
Field = string: x-varvalue-name-added 
Operation = string: LAST 
Path = string:  
<b>#value</b> 
Path = string: varValue 
Table = string: Log Entry
```

Auf ähnliche Weise können Sie den Wert des Tags `<Rep>` lesen, indem Sie im Decoder folgendes Feld hinzufügen:

```
7 = XMLDecoderField: 
Field = string: x-rep-name-added 
Operation = string: LAST 
Path = string: Rep.# 
<b>value</b> 
Path = string: Reps 
Table = string: Log Entry
```

Um dagegen den Wert des Element-Tags ohne Attribut zu lesen, können ein `<text>`-Tag unter einem `<line>`-Tag und sein Wert direkt gelesen werden, indem &quot; [!DNL text]&quot;in einem Pfad angegeben oder [!DNL line.text] verwendet wird, je nachdem, wie Sie den Decoder erstellt haben.

```
2 = XMLDecoderField: 
Field = string: x-chat-text 
Operation = string: LAST 
Path = string:  
<b>text</b> 
Path = string:  
<b>line</b> 
Table = string: Log Entry
```
