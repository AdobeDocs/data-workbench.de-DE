---
description: Anweisungen zum Konfigurieren der Kommunikation für Insight Server oder Repeater.
title: Konfigurationseinstellungen für die Kommunikation
uuid: 03297cf0-eb55-4db0-b692-eba24fcf947c
exl-id: a35788d1-de36-4350-a107-eee392e44503
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
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
>Wenden Sie sich vor der Änderung von Parametern, die nicht in dieser Tabelle aufgeführt sind, an die Adobe.

<table id="table_C87F1150E53548F484A8C0CFE91F1079"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Zugriffssteuerungsdatei </td> 
   <td colname="col2"> <p>Speicherort der Datei <span class="filepath"> Access Control.cfg </span> . Der Standardspeicherort ist der Ordner <span class="filepath"> Zugriffssteuerung </span> im Installationsordner <span class="keyword"> Insight Server </span> oder <span class="wintitle"> Repeater </span> . </p> <p>Beispiel: <code>Access Control File = Path: Access Control\\Access Control.cfg</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Zugriffsprotokollverzeichnis </td> 
   <td colname="col2"> <p>Ordner, dem Sie die Prüfprotokolle zuordnen möchten. </p> <p>Beispiel: <code>Access Log Directory = string: Audit\\</code> </p> <p> <p>Hinweis:  Sie können Prüfprotokolle einem anderen lokalen Laufwerk zuordnen (Beispiel: <span class="filepath"> Zeichenfolge: P:\\Audit\\ </span>), aber ordnen Sie die Prüfprotokolle nicht einem Netzlaufwerk zu. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Zugriffsprotokoll Verbose </td> 
   <td colname="col2"> Dieser Parameter kann auf true oder false gesetzt werden. Sie wird verwendet, um die Filterung von Auditprotokollen zu aktivieren und zu deaktivieren. Um sicherzustellen, dass jede Anfrage protokolliert wird, setzen Sie den Parameter auf True . </td> 
  </tr> 
  <tr> 
   <td colname="col1"> IP-Schnittstelle </td> 
   <td colname="col2"> <p>IP-Adresse, die verwendet wird, wenn zwei Netzwerkkarten für den Zugriff auf zwei verschiedene Netzwerke verfügbar sind. </p> <p>Beispiel: <code>IP Interface = string: &lt; IP Address &gt;</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Anschluss </td> 
   <td colname="col2"> <p>Nicht sicherer (HTTP) Port, auf dem der <span class="keyword"> Insight Server </span> oder <span class="wintitle"> Repeater </span> lauscht. Der Standardanschluss ist 80. Wenn Sie den Wert 0 eingeben, werden nicht sichere Verbindungen deaktiviert. </p> <p>Beispiel: <code>Port = int: 80</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL-Ciphers </td> 
   <td colname="col2"> Einige Umgebungen erfordern eine höhere Kommunikationssicherheit als andere. Wenn Sie eine bestimmte SSL-Verschlüsselungs-Suite verwenden möchten, können Sie sie mit diesem Parameter angeben. <p>Beispiel: <code>SSL Ciphers = string: AES256-SHA256</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL-Anschluss </td> 
   <td colname="col2"> <p>Sicherer (über SSL) Port, auf dem der <span class="keyword"> Insight Server </span> oder <span class="wintitle"> Repeater </span> lauscht. Der Standardanschluss ist 443. Wenn Sie den Wert 0 eingeben, werden sichere Verbindungen deaktiviert. </p> <p>Beispiel: <span class="filepath"></span> </p> <code>SSL Port = int: 443</code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>n=</i>LoggingServer: </td> 
   <td colname="col2"> Überschrift für Einstellungen des Protokollierungsservers. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Kundenname </td> 
   <td colname="col2"> <p>Kundenname, der für nicht angegebene Kunden in Administratorwarnungen angezeigt wird, wie im folgenden Beispiel gezeigt: </p> <p>"Keine Daten von Sensor XYZ für Kunden "Nicht angegeben"in 15 empfangen." </p> <p>Beispiel: <code> 1&nbsp;=&nbsp;LoggingServer:&nbsp; 
      &nbsp;&nbsp;Customer&nbsp;Name&nbsp;=&nbsp;string:&nbsp;CompanyAB </code> </p> <p>Unter Verwendung des obigen Beispiels würden administrative Warnhinweise für nicht spezifizierte Kunden jetzt wie folgt gelesen: </p> <p>"Keine Daten von Sensor XYZ für Kunden "CompanyAB"in 15." </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <i>n=</i>FileServer: </p> <p> Lokaler Pfad = Zeichenfolge: Protokolle\\ </p> </td> 
   <td colname="col2"> <p>Ordner, in dem Sie die Protokolldateien speichern möchten. </p> <p>Beispiel: </p> <code> 9&nbsp;=&nbsp;FileServer:&nbsp; 
     &nbsp;&nbsp;Local&nbsp;Path&nbsp;=&nbsp;string:&nbsp;Logs\\ </code> <p>Um über den Server-Datei-Manager </span> auf diesen Ordner zugreifen zu können, muss der in diesem Parameter angegebene Speicherort mit dem Speicherort übereinstimmen, den Sie im Parameter "Log Paths"in der Datei <span class="filepath"> Log Processing.cfg </span> angegeben haben. <span class="wintitle"> Weitere Informationen zum Ändern des Protokollverzeichnisses in der Datei <span class="filepath"> Log Processing.cfg </span> finden Sie im Kapitel "Konfigurationsdatei für Protokollverarbeitung"im <i>Handbuch zur Datensatzkonfiguration</i>. </span></p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <i>n=</i>FileServer: </p> <p> Lokaler Pfad = Zeichenfolge: Audit\\ </p> </td> 
   <td colname="col2"> <p>Ordner, dem Sie die Prüfprotokolle zuordnen möchten. </p> <p>Beispiel: </p> <code> 5&nbsp;=&nbsp;FileServer:&nbsp; 
     &nbsp;&nbsp;Local&nbsp;Path&nbsp;=&nbsp;string:&nbsp;Audit\\ </code> <p>Hinweis:  <p>Sie können Prüfprotokolle einem anderen lokalen Laufwerk zuordnen (Beispiel: <span class="filepath"> Zeichenfolge: P:\\Audit\\ </span>), aber ordnen Sie die Prüfprotokolle nicht einem Netzlaufwerk zu. </p> <p>Um über den Server-Datei-Manager </span> auf diesen Ordner zugreifen zu können, muss der in diesem Parameter angegebene Speicherort mit dem Speicherort übereinstimmen, den Sie im Parameter "Access Log Directory"in dieser Datei angegeben haben.<span class="wintitle"> </span></p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>n=</i>NormalizeServer: </td> 
   <td colname="col2"> <p>Dieser Parameter gilt nur für <span class="keyword"> Insight Server </span>. </p> <p>Weitere Informationen zum Angeben des zentralen Normalisierungsservers für den Cluster <span class="keyword"> Insight Server </span> finden Sie im Kapitel "Konfigurationsdatei für Protokollverarbeitung"im <i>Handbuch zur Datensatzkonfiguration</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <i>n=</i>ReportStatusServer: </p> <p> URI = string: /ReportStatus.vsp </p> </td> 
   <td colname="col2"> <p>Dieser Parameter gilt nur für <span class="keyword"> Insight Server </span>. </p> <p>Ermöglicht die Anzeige des Status <span class="keyword"> des Berichts </span> in der Oberfläche für den detaillierten Status für <span class="keyword"> Insight Server </span>. </p> </td> 
  </tr> 
 </tbody> 
</table>
