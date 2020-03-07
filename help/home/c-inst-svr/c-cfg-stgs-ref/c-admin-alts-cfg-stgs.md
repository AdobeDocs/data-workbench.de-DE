---
description: Anweisungen zum Konfigurieren von Administratorwarnungen für Insight Server, Repeater oder Transform.
solution: Insight
title: Konfigurationseinstellungen für Administratorwarnungen
uuid: c2be2d1e-d81d-4d9f-ac94-4b642dad90b9
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Konfigurationseinstellungen für Administratorwarnungen{#administrative-alerts-configuration-settings}

Anweisungen zum Konfigurieren von Administratorwarnungen für Insight Server, Repeater oder Transform.

Füllen Sie die Parameter in der folgenden Datei aus:

[!DNL Product Name installation directory\Components\Administrative Alerts.cfg]

<table id="table_5A2298906D5F4215B8FAC42CACBC0002"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Kategorie </td> 
   <td colname="col2"> Der Name der Kategorie. Eine Kategorie von "Standard"ist erforderlich. Siehe Fehlerkategorien in dieser Tabelle. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Fehlerkategorien </td> 
   <td colname="col2"> Ermöglicht die Kategorisierung von Fehlern in Verbindung mit der Datei zur Fehlerkategorisierung. Jede Fehlerkategorie kann einen eigenen Satz Empfänger und eine eigene Throttle Delay haben. Sie können beispielsweise eine kritische Kategorie mit einer Drosselverzögerung von 0 erstellen, sodass jeder kritische Fehler sofort per E-Mail an die in der Liste der Empfänger angegebenen Empfänger gesendet wird. Fehler, die nicht mit einer Unterzeichenfolge in der Datei zur Fehlerkategorisierung übereinstimmen, werden der Kategorie "Standard"zugewiesen. Um eine neue Kategorie hinzuzufügen, klicken Sie mit der rechten Maustaste auf eine Zahl und klicken Sie auf <span class="uicontrol"> Neu hinzufügen </span> &gt; <span class="uicontrol"> Fehlerkategorie </span>. Sie können sie auch mit der Aktion mit der rechten Maustaste kopieren oder entfernen. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Fehlerkategorisierungsdatei </td> 
   <td colname="col2"> <p>Der Name der Datei, die Sie zur Kategorisierung der einzelnen Warnungen verwenden möchten. Sie erstellen diese Datei mit Notepad. Diese Datei sollte drei Spalten in jeder Zeile enthalten, die durch Registerkarten voneinander getrennt sind. Die erste Spalte ist eine Zeichenfolge, die bei Fehlern übereinstimmt. Ein ^-Zeichen entspricht dem Anfang und ein $ entspricht dem Ende der Zeichenfolge; alle anderen Zeichen wörtlich übereinstimmen. Die zweite Spalte ist eine Kategorie für übereinstimmende Fehler, die sich in "Fehlerkategorien"befindet. Die dritte ist eine alternative Meldung, die der eigentlichen Fehlermeldung in gesendeten E-Mails vorangestellt wird. Wenn keine Datei angegeben ist, werden alle Fehler als Standard kategorisiert. </p> <p>Ein Beispiel für diese Datei finden Sie in der Datei " <span class="filepath"> Error categories.txt" </span> im Suchverzeichnis. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Von </td> 
   <td colname="col2"> <p>Adresse, die im Parameter "from"der E-Mail-Nachricht angezeigt wird. </p> <p>Beispiel: <span class="filepath"> server_errors@mycompany.com </span></p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Minimaler Speicherplatz (MB) </td> 
   <td colname="col2"> Der Server generiert eine E-Mail-Warnung, wenn der verfügbare Speicherplatz in einem vom Server verwendeten Verzeichnis unter diesen Wert fällt. Der Standardwert lautet 1000. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensor Alert Timeout (min) </td> 
   <td colname="col2"> <p>Der Server generiert eine E-Mail-Warnung, wenn er innerhalb dieses Zeitfensters keine Daten von einem konfigurierten und zuvor angeschlossenen <span class="wintitle"> Sensor </span> erhalten hat. Der Standardwert lautet 15. </p> <p> <p>Hinweis:  Der <span class="wintitle"> Sensor- </span> Warnhinweis-Timeout funktioniert nur, wenn eine bestehende Verbindung zu einem <span class="wintitle"> Sensor </span> abgebrochen wird. Wenn der Dienst des Servers beendet und neu gestartet wird und die <span class="wintitle"> Sensoren </span> keine Verbindung herstellen, generiert der Server keine E-Mail-Warnungen. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Server-Adresse </td> 
   <td colname="col2"> <p>Die Adresse des SMTP-Servers für ausgehende E-Mails. </p> <p>Beispiel: <span class="filepath"> mail.mycompany.com </span></p> <p>Für die Verwendung der beschriebenen Funktionen ist ein SMTP-Server erforderlich. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Serverkennwort </td> 
   <td colname="col2"> <p>Das Kennwort für die Anmeldung beim SMTP-Server. Dieser Parameter ist optional, es sei denn, die Anmeldung ist zum Senden von E-Mails erforderlich. </p> <p>Für die Verwendung der beschriebenen Funktionen ist ein SMTP-Server erforderlich. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Serverbenutzer </td> 
   <td colname="col2"> <p>Die Benutzer-ID/der Name für die Anmeldung beim SMTP-Server. Dieser Parameter ist optional, es sei denn, die Anmeldung ist zum Senden von E-Mails erforderlich. </p> <p>Für die Verwendung der beschriebenen Funktionen ist ein SMTP-Server erforderlich. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Zeitverzögerung (Sekunden) </td> 
   <td colname="col2"> Die Mindestdauer von Sekunden, die zwischen zwei Fehlern in dieser Kategorie verstreichen muss, damit eine E-Mail gesendet werden kann. Bei einem Wert von 0 wird die E-Mail sofort gesendet. </td> 
  </tr> 
 </tbody> 
</table>

