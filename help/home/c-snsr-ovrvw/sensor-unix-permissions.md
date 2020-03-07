---
description: Informationen zu Sensor UNIX-Dateiberechtigungen, wie zum Beispiel dem Collector-Modul, dem Transmitter-Prozess, der Konfigurationsdatei und mehr.
title: Sensor UNIX-Dateiberechtigungen
uuid: 04d159b5-6569-48b6-a2db-9a0b40118ffe
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Sensor UNIX-Dateiberechtigungen{#sensor-unix-file-permissions}

Informationen zu Sensor UNIX-Dateiberechtigungen, wie zum Beispiel dem Collector-Modul, dem Transmitter-Prozess, der Konfigurationsdatei und mehr.

## Das Sammlermodul {#section-49c855baece24c4695184bfcbeeddebf}

<table id="table_0B972ABD2A5342CA8A6FE80EB666298A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Qualität </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Dateiname </p> </td> 
   <td colname="col2"> <p>mod_visual_sciences.so (auf Apache-Webservern und IBM HTTP-Servern) </p> <p>libvisual_sciences.so und J2EECollector.jar (auf J2EE-Anwendungsservern) </p> <p>aol_visual_sciences.so (auf AOL-Webservern) </p> <p>saf_visual_sciences.so (auf Sun Java-Webservern) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Standardberechtigungen </p> </td> 
   <td colname="col2"> <p>rwx r-x r-x (IBM HTTP und Apache 1.3.x) </p> <p>rwx rwx r-x (Apache 2.0.x) </p> <p>rwx —x —x (J2EE-, AOL- und Sun Java-Webserver) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Lesen Sie </p> </td> 
   <td colname="col2"> <p>Der Webserver, der gelegentlich als Root-Benutzer ausgeführt wird, jedoch häufiger unter einem bestimmten Benutzerkonto ausgeführt wird </p> <p>Wenn der Webserver unter einem Nicht-Stammkonto ausgeführt wird, müssen die Berechtigungen für diese Datei dem Konto das Lesen ermöglichen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Führt aus als </p> </td> 
   <td colname="col2"> <p>Ein untergeordneter Prozess im Webserver </p> <p>Untergeordnete Prozesse werden unter einem in Ihrer Webserverkonfiguration angegebenen Benutzerkonto ausgeführt. Auf vielen Servern ist dies ein spezielles Konto mit sehr eingeschränkten Rechten namens "none" — aber nicht alle Webserver verwenden dieses Konto. Überprüfen Sie die Konfigurationsdatei Ihres Webservers, um festzustellen, welches Benutzerkonto eingerichtet wurde. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Lesen von </p> </td> 
   <td colname="col2"> <p>txlogd.conf </p> <p>Die Datei diskQueue </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Schriftstücke in </td> 
   <td colname="col2"> Die Datei diskQueue </td> 
  </tr> 
 </tbody> 
</table>

## Der Transmitter-Prozess {#section-8af432472e9d4bd9a42270bf27adf33a}

<table id="table_3028CC9640D54016BD8CA7F9CAA34280"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Qualität </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Dateiname </td> 
   <td colname="col2"> trust_ca_cert.pem </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Standardberechtigungen </p> </td> 
   <td colname="col2"> <p>rw- r— r— (IBM HTTP-, AOL- und Sun Java-Webserver) </p> <p>rw- rw- r— (Apache-Webserver und J2EE-Anwendungsserver) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Lesen Sie </td> 
   <td colname="col2"> Das Transmitterprogramm </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Geschrieben von </td> 
   <td colname="col2"> -- </td> 
  </tr> 
 </tbody> 
</table>

## Die Konfigurationsdatei {#section-341d85f2abf34a69970a0ff91b7e9123}

<table id="table_79AC614F5435443CB3CFB457B8375704"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Qualität </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Dateiname </td> 
   <td colname="col2"> txlogd.conf </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Standardberechtigungen </p> </td> 
   <td colname="col2"> <p>rw- r— r— (IBM HTTP-, AOL- und Sun Java-Webserver) </p> <p>rw- rw- r— (Apache-Webserver und J2EE-Anwendungsserver) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Lesen Sie </td> 
   <td colname="col2"> <p>Sammlermodul </p> <p>Das Transmitterprogramm </p> <p>Der Administrator, der für die Installation, Konfiguration und Wartung von Sensor verantwortlich ist </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Geschrieben von </td> 
   <td colname="col2"> Der Administrator, der für die Installation, Konfiguration und Wartung von Sensor verantwortlich ist </td> 
  </tr> 
 </tbody> 
</table>

## Die Datei der Zertifizierungsstelle {#section-2818dff887b8456992bdc589fd8510f3}

<table id="table_ED8BEEEFA91245C3A6645D27B148A5A7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Qualität </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Dateiname </td> 
   <td colname="col2"> trust_ca_cert.pem </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Standardberechtigungen </p> </td> 
   <td colname="col2"> <p>rw- r— r— (IBM HTTP-, AOL- und Sun Java-Webserver) </p> <p>rw- rw- r— (Apache-Webserver und J2EE-Anwendungsserver) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Lesen Sie </td> 
   <td colname="col2"> Das Transmitterprogramm </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Geschrieben von </td> 
   <td colname="col2"> -- </td> 
  </tr> 
 </tbody> 
</table>

## Die Disk-Warteschlange {#section-0407c52744de41af867d0b7933a69256}

<table id="table_35DB32228E7443FF90BE24AB14CBE54B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Qualität </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Dateiname </td> 
   <td colname="col2"> Benutzerdefiniert </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Standardberechtigungen </td> 
   <td colname="col2"> rw- rw- rw- (Alle Servertypen) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Lesen Sie </p> </td> 
   <td colname="col2"> <p>Sammlermodul </p> <p>Das Transmitterprogramm </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Geschrieben von </p> </td> 
   <td colname="col2"> <p>Sammlermodul </p> <p>Das Transmitterprogramm </p> </td> 
  </tr> 
 </tbody> 
</table>

