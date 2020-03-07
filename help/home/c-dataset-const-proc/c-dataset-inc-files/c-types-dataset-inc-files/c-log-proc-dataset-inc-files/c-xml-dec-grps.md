---
description: Die Verarbeitung von XML-Dateien als Protokollquellen zum Definieren von Dekodierern zum Extrahieren von Daten aus der XML-Datei.
solution: Analytics
title: XML Decoder-Gruppen
topic: Data workbench
uuid: 8fc9ab80-9a71-4fe2-a646-e830ffeb67b9
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# XML Decoder-Gruppen{#xml-decoder-groups}

Die Verarbeitung von XML-Dateien als Protokollquellen zum Definieren von Dekodierern zum Extrahieren von Daten aus der XML-Datei.

>[!NOTE]
>
>Die Definition von XML-Decoder-Gruppen für XML-Protokollquellen erfordert Kenntnisse über die Struktur und den Inhalt der XML-Datei, die zu extrahierenden Daten und die Felder, in denen diese Daten gespeichert werden. Dieser Abschnitt enthält grundlegende Beschreibungen der Parameter, die Sie für Decoder angeben können. Die Art und Weise, wie Sie einen Decoder verwenden, hängt von der XML-Datei ab, die Ihre Quelldaten enthält.

Informationen zu den Formatanforderungen für XML-Protokollquellen finden Sie unter [Protokollquellen](../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-6714c720fac044cbb9af003bf401b2ea). Wenden Sie sich an Adobe, um Hilfe beim Definieren von XML-Decodern zu erhalten.

Die oberste Ebene eines XML-Decoders ist eine Decoder-Gruppe (XMLDecoderGroup), eine Gruppe von Decoder-Tabellen, die Sie verwenden, um Daten aus einer XML-Datei eines bestimmten Formats zu extrahieren. Wenn Sie XML-Dateien unterschiedlicher Formate haben, müssen Sie für jedes Format eine Decoder-Gruppe definieren. Jede Decoder-Gruppe besteht aus einer oder mehreren Decoder-Tabellen.

In der folgenden Tabelle werden der Parameter &quot;Tables&quot;und alle Unterparameter beschrieben, die Sie zum Definieren einer XML-Decoder-Gruppe angeben müssen.

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
   <td colname="col2"> <p>Jede Tabelle in einer Decoder-Gruppe stellt eine Datenebene dar, die aus der XML-Datei extrahiert werden soll. Wenn Sie beispielsweise Daten zu Besuchern extrahieren möchten, erstellen Sie eine Decoder-Tabelle, die aus den Informationen besteht, die Sie für jeden Besucher extrahieren möchten. Sie können auch Decoder-Tabellen in Decoder-Tabellen erstellen (siehe Untergeordnete Elemente). </p> <p> <b>So fügen Sie einer Decoder-Gruppe eine Tabelle hinzu</b> 
     <ul id="ul_C73CAD77440B4465B9FCE08BF4FA0749"> 
      <li id="li_C4B8CC5A85D942898F1EB76778105818"> Klicken Sie mit der rechten Maustaste auf <span class="uicontrol"> Tabellen </span> und klicken Sie auf <span class="uicontrol"> Neue hinzufügen </span> &gt; <span class="uicontrol"> XMLDecoderTabelle </span>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Felder </td> 
   <td colname="col2"> <p>Die erweiterten Felder (z. B. x-trackingid, x-email), in denen die Daten gespeichert werden. Die im Feld zu speichernden Daten werden durch die Unterfelder Pfad und/oder Vorgang bestimmt. </p> <p> Der Pfad ist die Feldebene innerhalb der strukturierten XML-Datei. Der Pfad eines Felds ist relativ zum Pfad der Tabelle, in der es definiert ist. Beispiele sind <span class="filepath"> "tag.tag.tag" </span> oder " <span class="filepath"> "tag.tag.@attribute </span>. Beachten Sie, dass bei Pfaden die Groß- und Kleinschreibung beachtet wird. </p> <p> Ein Vorgang wird auf jede Zeile im angegebenen Pfad angewendet, um eine Ausgabe zu erzeugen. Die folgenden Vorgänge sind verfügbar: 
     <ul id="ul_B264A411D7E3446288E7E69D62150B8B"> 
      <li id="li_5936E81C0EEF46AFB780E451A04A88E4"><b>LETZTE:</b> Das Feld nimmt den Wert des letzten Vorkommens des Pfads in der XML-Datei an. </li> 
      <li id="li_7BC4F24F2CA84C2EB64B06FE09B4CAF6"><b>RANDOM:</b> Weist dem Feld einen zufälligen Wert zu. Dieser Vorgang ist nützlich, wenn Sie eine eindeutige ID generieren müssen, z. B. für das x-trackingid-Feld. </li> 
      <li id="li_C1D34EA11BFB4859A25A275A9B63FB56"><b>INHERIT:</b> Das definierte Feld übernimmt seinen Wert aus dem entsprechenden Feld der übergeordneten Tabelle. </li> 
      <li id="li_F62FB8CD962E4E1495D9A2D5B7A78E2A"><b>"<i>Konstante </i>":</b> Die Konstante muss in Anführungszeichen gesetzt werden. Sie können einen konstanten Vorgang verwenden, um zu prüfen, ob ein bestimmter Pfad vorhanden ist; Wenn der Pfad vorhanden ist, wird dem Feld der Wert der Konstante zugewiesen. </li> 
     </ul> </p> <p> <b>So fügen Sie einer Decodertabelle ein Feld hinzu</b> </p> <p> 
     <ul id="ul_91D104D927424DEA9E788E43B2F6FEA9"> 
      <li id="li_5448B01EE82349569BBFC99C9604D7B8"> Klicken Sie mit der rechten Maustaste auf <span class="uicontrol"> Felder </span>und dann auf <span class="uicontrol"> Neu hinzufügen </span> &gt; <span class="uicontrol"> XMLDecoderField </span>. Definieren Sie Feld, Vorgang und Pfad nach Bedarf. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Pfad </td> 
   <td colname="col2"> <p>Die Ebene in der strukturierten XML-Datei, für die die Decoder-Tabelle Informationen enthält. Bei einer untergeordneten XML-Decoder-Tabelle ist der Pfad relativ zum Pfad der übergeordneten Tabelle. Beachten Sie, dass bei Pfaden die Groß- und Kleinschreibung beachtet wird. </p> <p> Wenn Ihre XML-Datei beispielsweise die Struktur enthält: </p> 

    &amp;lt;visitor&amp;gt;
    
    &amp;nbsp;
    
    ...
    
    &amp;nbsp;
    
    &amp;lt;/visitor&amp;gt;
    
    &amp;lt;/logdata&amp;gt;&amp;nbsp; &lt;/code> &lt;p> dann wäre der Pfad &lt;span class=&quot;filepath&quot;> logdata.visitor &lt;/span>. &lt;/p> &lt;/td>
</tr> 
  <tr> 
   <td colname="col1"> Tabelle </td> 
   <td colname="col2"> <p>Der Wert dieses Parameters sollte immer "Log Entry"lauten. </p> <p> <p>Hinweis:  Ändern Sie diesen Wert nicht ohne Rücksprache mit Adobe. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Kinder </td> 
   <td colname="col2"> <p>Optional. Eine oder mehrere eingebettete Decoder-Tabellen. Jedes untergeordnete Element enthält die oben beschriebenen Parameter "Felder", "Pfad"und "Tabelle". </p> <p> <b>So fügen Sie einer Decodertabelle ein untergeordnetes Element hinzu</b> </p> <p> 
     <ul id="ul_902AC6CA5D66457D84CBA3194FF49BBE"> 
      <li id="li_07B4D60E7E2E4630B4878691E575936A"> Klicken Sie mit der rechten Maustaste auf <span class="uicontrol"> Untergeordnete Elemente </span> und klicken Sie auf <span class="uicontrol"> Neue hinzufügen </span> &gt; <span class="uicontrol"> XMLDecoderTabelle </span>. Definieren Sie Feld, Vorgang und Pfad nach Bedarf. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

Um eine XML-Datei als Protokollquelle für einen Datensatz zu verwenden, müssen XML-Decoder-Gruppen und -Tabellen definiert werden, um die zu verarbeitenden Informationen in den Datensatz zu extrahieren. In diesem Beispiel können Sie sehen, wie Decoder-Gruppen und -Tabellen für eine XML-Protokollquelle für einen Webdataset definiert werden.

Die folgende XML-Datei enthält Informationen zu einem Website-Besucher, einschließlich einer Experience Cloud ID, E-Mail-Adresse, physischer Adresse und Informationen zu den Seitenansichten des Besuchers.

![](assets/xmlFile_LogSource.png)

Da wir eine einzelne XML-Datei haben, benötigen wir nur eine Decoder-Gruppe, die wir &quot;XML-Musterformat&quot;nennen. Diese Decoder-Gruppe gilt für alle anderen XML-Dateien im gleichen Format wie diese Datei. Um mit der Erstellung von XML-Decoder-Tabellen innerhalb dieser Decoder-Gruppe zu beginnen, müssen wir zunächst festlegen, welche Informationen extrahiert werden sollen und in welchen Feldern die Daten gespeichert werden.

In diesem Beispiel extrahieren wir Informationen über den Besucher und die mit diesem Besucher verbundenen Seitenansichten. Dazu erstellen wir eine übergeordnete XML-Decoder-Tabelle mit Informationen zum Besucher und eine eingebettete (untergeordnete) XML-Decoder-Tabelle mit Informationen zu den Seitenansichten des Besuchers.

**Die Informationen für die übergeordnete Tabelle (Besucher) lauten wie folgt:**

* Eine Datentypkennung für jede Datenzeile in der XML-Datei. Wir verwenden VISITOR als unseren Bezeichner, damit wir schnell Datenzeilen identifizieren können, die sich auf den Besucher und nicht auf die Seitenansichten beziehen. Wir können diesen Wert im Feld x-rowtype speichern.
* Die Besucher-ID, die wir im Feld x-trackingid speichern.
* Die E-Mail-Adresse des Besuchers (contact.email), die wir im Feld x-email speichern.
* Der Registrierungsstatus des Besuchers. Wenn der Besucher ein registrierter Benutzer ist, können wir den Wert &quot;1&quot;im Feld &quot;x-is-registered&quot;speichern.
* Der Wert &quot;Pfad&quot;ist [!DNL logdata.visitor]und der Wert &quot;Tabelle&quot; [!DNL Log Entry]. Informationen zu diesen Parametern finden Sie in der Tabelle XMLDecoderGroup oben.

**Informationen für die untergeordnete Tabelle (Seitenansichten) lauten wie folgt:**

* Eine Datentypkennung für jede Datenzeile in der XML-Datei. Wir verwenden &quot;PAGEVIEW&quot;als unsere Kennung, damit wir schnell Datenzeilen identifizieren können, die sich auf die Seitenansichten des Besuchers und nicht nur auf den Besucher beziehen. Dieser Wert wird im Feld x-rowtype gespeichert.
* Die Besucher-ID. Dieser Wert wird von der übergeordneten Tabelle übernommen und im Feld x-trackingid gespeichert.
* Der Zeitstempel jeder Seitenansicht, der im Feld x-event-time gespeichert wird.
* Der URI jeder Seitenansicht, die im Stammfeld cs-uri gespeichert wird.
* Der Wert &quot;Pfad&quot;ist &quot;pageview&quot;und der Wert &quot;Tabelle&quot;lautet &quot;Protokolleintrag&quot;. Informationen zu diesen Parametern finden Sie in der Tabelle XMLDecoderGroup oben.

Die folgende Bildschirmaufzeichnung zeigt einen Teil der [!DNL Log Processing Dataset Include] Datei mit der resultierenden XML-Decoder-Gruppe für die XML-Beispieldatei, basierend auf der diskutierten Struktur der übergeordneten und untergeordneten XML-Decoder-Tabellen.

![](assets/cft_LogProc_xmldecodergroup_top.png)

![](assets/cfg_LogProcessingInclude_XMLDecoderGroup_bottom.png)

Eine Tabelle mit der Ausgabe dieses Decoders für unsere XML-Musterdatei sieht wie folgt aus:

| x-rowtype | cs—uri-stamm | x-email | x-is-registered | x-event-time | x-tracking-id |
|---|---|---|---|---|---|
| BESUCHER |  | foo@bar.com | 1 |  | 1 |
| PAGEVIEW | /index.html |  |  | 2006-01-01 08:00:00 | 1 |
| PAGEVIEW | / |  |  | 2006-01-01 08:00:30 | 1 |

Sie können eine Tabelle wie die oben stehende in Data Workbench erstellen, indem Sie eine field-Viewer-Oberfläche verwenden. Informationen zur Benutzeroberfläche des field-Viewers finden Sie unter [DataSet-Konfigurationstools](../../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md#concept-6e058b7691834cf79dcfd1573f78d4f5).

## Verwenden von #value für das XML-Element zum Lesen des Attributwerts {#section-88758428afb94f0baa5a986604d53bc1}

You can now use the **[!DNL #value]** tag in XML paths to pull the value of an XML element.

Wenn Sie beispielsweise zuvor einen Pfad von links angeben, können Sie den Wert des **`<Hit><Page name="Home Page" index="20">home.html</Page></Hit>`** `<Page>` Tags nicht lesen. Um den Wert eines `<Page>` Tags und dessen Attribute zu lesen, können Sie [!DNL Hit.Page.@name] bzw. [!DNL Hit.Page.@index] verwenden. Sie können den Wert des Tags auch mithilfe des **`Hit.Page.#value`** Ausdrucks abrufen.

Sie können beispielsweise den Wert des Tags lesen, `<varValue>` indem Sie dem Decoder das folgende Feld hinzufügen:

```
7 = XMLDecoderField: 
Field = string: x-varvalue-name-added 
Operation = string: LAST 
Path = string:  
<b>#value</b> 
Path = string: varValue 
Table = string: Log Entry
```

Gleichermaßen können Sie den Wert des Tags lesen, `<Rep>` indem Sie dem Decoder das folgende Feld hinzufügen:

```
7 = XMLDecoderField: 
Field = string: x-rep-name-added 
Operation = string: LAST 
Path = string: Rep.# 
<b>value</b> 
Path = string: Reps 
Table = string: Log Entry
```

Um den Wert des Element-Tags ohne Attribut zu lesen, können hingegen ein `<text>` Tag unter einem `<line>` -Tag und sein Wert direkt gelesen werden, indem &quot; [!DNL text]&quot;in einem Pfad angegeben oder verwendet wird, [!DNL line.text]je nachdem, wie Sie den Decoder erstellt haben.

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
