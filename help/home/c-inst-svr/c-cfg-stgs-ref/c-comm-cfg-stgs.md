---
description: Anweisungen zum Konfigurieren der Kommunikation für Insight Server oder Repeater.
solution: Insight
title: Konfigurationseinstellungen für die Kommunikation
uuid: 03297cf0-eb55-4db0-b692-eba24fcf947c
translation-type: tm+mt
source-git-commit: 638eca495223fc9d5326bf9462a9c289d6fe2d9e
workflow-type: tm+mt
source-wordcount: '508'
ht-degree: 5%

---


# Konfigurationseinstellungen für die Kommunikation{#communications-configuration-settings}

Anweisungen zum Konfigurieren der Kommunikation für Insight Server oder Repeater.

Füllen Sie die Parameter in der folgenden Datei aus:

[!DNL Product Name installation directory\Components\Communications.cfg]

>[!NOTE]
>
>Bitte kontaktieren Sie die Adobe, bevor Sie Parameter ändern, die nicht in dieser Tabelle aufgeführt sind.

<table id="table_C87F1150E53548F484A8C0CFE91F1079"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Zugriffskontrolle </td> 
   <td colname="col2"> <p>Speicherort der <span class="filepath"> Datei "Zugriffskontrolle.cfg" </span> . Der Standardspeicherort ist der <span class="filepath"> Zugriffskontrolle- </span> Ordner im Installationsordner von <span class="keyword"> Insight Server </span> oder <span class="wintitle"> Repeater </span> . </p> <p>Beispiel: <code>Access Control File = Path: Access Control\\Access Control.cfg</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Protokollverzeichnis </td> 
   <td colname="col2"> <p>Ordner, dem die Prüfprotokolle zugeordnet werden sollen. </p> <p>Beispiel: <code>Access Log Directory = string: Audit\\</code> </p> <p> <p>Hinweis:  Sie können Prüfprotokolle einem anderen lokalen Laufwerk zuordnen (Beispiel: <span class="filepath"> Zeichenfolge: P:\\Audit\\ </span>), aber ordnen Sie keine Prüfprotokolle einem Netzlaufwerk zu. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Zugriffsprotokoll-Funktion </td> 
   <td colname="col2"> Dieser Parameter kann auf true oder false eingestellt werden. Es wird verwendet, um die Filterung von Prüfprotokollen zu aktivieren und zu deaktivieren. Um sicherzustellen, dass jede Anforderung protokolliert wird, setzen Sie den Parameter auf True. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> IP-Schnittstelle </td> 
   <td colname="col2"> <p>IP-Adresse, die verwendet wird, wenn zwei Netzwerkkarten für den Zugriff auf zwei verschiedene Netzwerke verfügbar sind. </p> <p>Beispiel: <code>IP Interface = string: &lt; IP Address &gt;</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Anschluss </td> 
   <td colname="col2"> <p>Nicht sicherer (HTTP) Anschluss, auf dem der <span class="keyword"> Insight-Server </span> oder <span class="wintitle"> -Repeater </span> lauscht. Der Standardanschluss ist 80. Durch Eingabe des Werts 0 werden nicht sichere Verbindungen deaktiviert. </p> <p>Beispiel: <code>Port = int: 80</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL-Ciphers </td> 
   <td colname="col2"> Einige Umgebung erfordern eine höhere Kommunikationssicherheit als andere. Wenn Sie eine bestimmte SSL-Chipher-Suite verwenden möchten, können Sie diese mit diesem Parameter angeben. <p>Beispiel: <code>SSL Ciphers = string: AES256-SHA256</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL-Anschluss </td> 
   <td colname="col2"> <p>Sicherer Anschluss (über SSL), auf dem der <span class="keyword"> Insight-Server </span> oder <span class="wintitle"> -Repeater </span> lauscht. Der Standardanschluss ist 443. Durch Eingabe des Werts 0 werden sichere Verbindungen deaktiviert. </p> <p>Beispiel: <span class="filepath"></span> </p> <code>SSL Port = int: 443</code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>n=</i>LoggingServer: </td> 
   <td colname="col2"> Überschrift für Einstellungen des Protokollierungsservers. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Kundenname </td> 
   <td colname="col2"> <p>Der Kundenname wird für nicht angegebene Kunden in Administratorwarnungen wie im folgenden Beispiel angezeigt: </p> <p>"Keine Daten von Sensor XYZ für Kunden "Nicht angegeben"in 15." </p> <p>Beispiel: <code> 1&nbsp;=&nbsp;LoggingServer:&nbsp; 
      &nbsp;&nbsp;Customer&nbsp;Name&nbsp;=&nbsp;string:&nbsp;CompanyAB </code> </p> <p>Im obigen Beispiel würden Administratorwarnungen für nicht angegebene Kunden nun wie folgt lauten: </p> <p>"Keine Daten von Sensor XYZ für Kunden "CompanyAB"in 15." </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <i>n=</i>FileServer: </p> <p> Local Path = string: Protokolle\\ </p> </td> 
   <td colname="col2"> <p>Ordner, in dem Sie die Protokolldateien speichern möchten. </p> <p>Beispiel: </p> <code> 9&nbsp;=&nbsp;FileServer:&nbsp; 
     &nbsp;&nbsp;Local&nbsp;Path&nbsp;=&nbsp;string:&nbsp;Logs\\ </code> <p>Um über den <span class="wintitle"> Server Files Manager auf diesen Ordner zugreifen zu können, muss der in diesem Parameter angegebene Speicherort mit dem Speicherort übereinstimmen, den Sie im Parameter "Log Paths"in der </span>Datei "Log Processing.cfg"angegeben <span class="filepath"> </span> haben. Weitere Informationen zum Ändern des Protokollverzeichnisses in der <span class="filepath"> Datei " </span> Log Processing.cfg"finden Sie im Kapitel "Konfigurationsdatei für die Protokollverarbeitung"im Handbuch zur <i>Konfiguration</i>des Datensatzes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <i>n=</i>FileServer: </p> <p> Local Path = string: Audit\ </p> </td> 
   <td colname="col2"> <p>Ordner, dem die Prüfprotokolle zugeordnet werden sollen. </p> <p>Beispiel: </p> <code> 5&nbsp;=&nbsp;FileServer:&nbsp; 
     &nbsp;&nbsp;Local&nbsp;Path&nbsp;=&nbsp;string:&nbsp;Audit\\ </code> <p>Hinweis:  <p>Sie können Prüfprotokolle einem anderen lokalen Laufwerk zuordnen (Beispiel: <span class="filepath"> Zeichenfolge: P:\\Audit\\ </span>), aber ordnen Sie keine Prüfprotokolle einem Netzlaufwerk zu. </p> <p>Um über den <span class="wintitle"> </span>Server Files Manager auf diesen Ordner zugreifen zu können, muss der in diesem Parameter angegebene Speicherort mit dem Speicherort übereinstimmen, den Sie im Parameter Zugriffsprotokoll-Verzeichnis in dieser Datei angegeben haben. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>n=</i>NormalizeServer: </td> 
   <td colname="col2"> <p>Dieser Parameter gilt nur für <span class="keyword"> Insight Server </span>. </p> <p>Weitere Informationen zum Festlegen des zentralisierten Normalisierungsservers für Ihren <span class="keyword"> Insight Server- </span> Cluster finden Sie im Kapitel "Konfigurationsdatei für Protokollverarbeitung"des <i>Dataset-Konfigurationsleitfadens</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <i>n=</i>ReportStatusServer: </p> <p> URI = String: /ReportStatus.vsp </p> </td> 
   <td colname="col2"> <p>Dieser Parameter gilt nur für <span class="keyword"> Insight Server </span>. </p> <p>Ermöglicht die Ansicht des <span class="keyword"> Berichtstatus in der Detaillierten Statusoberfläche für </span> Insight Server <span class="keyword"> </span>. </p> </td> 
  </tr> 
 </tbody> 
</table>
