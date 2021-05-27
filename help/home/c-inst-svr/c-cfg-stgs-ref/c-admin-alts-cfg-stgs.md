---
description: Anleitung zum Konfigurieren von Administratorwarnungen für Insight Server, Repeater oder Transform.
title: Konfigurationseinstellungen für Administrator-Warnhinweise
uuid: c2be2d1e-d81d-4d9f-ac94-4b642dad90b9
exl-id: c75e442e-33e6-4fc8-8368-29482f09e1cc
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '514'
ht-degree: 4%

---

# Konfigurationseinstellungen für Administrator-Warnhinweise{#administrative-alerts-configuration-settings}

Anleitung zum Konfigurieren von Administratorwarnungen für Insight Server, Repeater oder Transform.

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
   <td colname="col2"> Der Name der Kategorie. Eine Kategorie Standard ist erforderlich. Siehe Fehlerkategorien in dieser Tabelle. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Fehlerkategorien </td> 
   <td colname="col2"> Ermöglicht die Kategorisierung von Fehlern in Verbindung mit der Datei zur Fehlerkategorisierung. Jede Fehlerkategorie kann einen eigenen Satz von Empfängern und eine eigene "Einschränken"-Verzögerung aufweisen. Sie können beispielsweise eine Kategorie "Kritisch"mit einer Drosselverzögerung von 0 erstellen, sodass jeder kritische Fehler sofort per E-Mail an die in der Empfängerliste angegebenen Empfänger gesendet wird. Fehler, die nicht mit einer Unterzeichenfolge in der Datei mit der Fehlerkategorisierung übereinstimmen, werden der Kategorie "Standard"zugewiesen. Um eine neue Kategorie hinzuzufügen, klicken Sie mit der rechten Maustaste auf eine Zahl und klicken Sie auf <span class="uicontrol"> Neu hinzufügen </span> &gt; <span class="uicontrol"> Fehlerkategorie </span>. Sie können sie auch mithilfe der Rechtsklick-Aktion kopieren oder entfernen. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Datei mit Fehlerkategorisierung </td> 
   <td colname="col2"> <p>Der Name der Datei, die Sie zur Kategorisierung der einzelnen Warnhinweise verwenden möchten. Sie erstellen diese Datei mit Notepad. Diese Datei sollte in jeder Zeile drei Spalten enthalten, die durch Tabs voneinander getrennt sind. Die erste Spalte ist eine Zeichenfolge, die bei Fehlern übereinstimmt. Ein ^ Zeichen entspricht dem Anfang und ein $ entspricht dem Ende der Zeichenfolge. Alle anderen Zeichen werden wörtlich abgeglichen. Die zweite Spalte ist eine Kategorie für übereinstimmende Fehler, die sich in Fehlerkategorien befindet. Die dritte ist eine alternative Nachricht, die der eigentlichen Fehlermeldung in gesendeten E-Mails vorangestellt wird. Wenn keine Datei angegeben ist, werden alle Fehler als Standard kategorisiert. </p> <p>Ein Beispiel für diese Datei finden Sie in der Datei <span class="filepath"> Fehlerkategorien.txt </span> im Suchverzeichnis. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Von </td> 
   <td colname="col2"> <p>Adresse, die im "from"-Parameter der E-Mail-Nachricht angezeigt wird. </p> <p>Beispiel: <span class="filepath"> server_errors@mycompany.com </span></p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Minimaler Festplattenspeicher (MB) </td> 
   <td colname="col2"> Der Server erzeugt einen E-Mail-Warnhinweis, wenn der verfügbare Speicherplatz in einem vom Server verwendeten Verzeichnis unter diesen Wert fällt. Der Standardwert lautet 1000. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Zeitüberschreitung für Sensor-Warnhinweis (Min.) </td> 
   <td colname="col2"> <p>Der Server erzeugt einen E-Mail-Warnhinweis, wenn er innerhalb dieses Zeitfensters keine Daten von einem konfigurierten und zuvor verbundenen Sensor <span class="wintitle"> </span> empfangen hat. Der Standardwert lautet 15. </p> <p> <p>Hinweis:  <span class="wintitle"> Sensor </span> Alert Timeout funktioniert nur, wenn eine vorhandene Verbindung zu einem <span class="wintitle"> Sensor </span> abgebrochen wird. Wenn der Dienst des Servers angehalten und neu gestartet wird und die <span class="wintitle"> Sensoren </span> keine Verbindung herstellen, generiert der Server keine E-Mail-Warnungen. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Server-Adresse </td> 
   <td colname="col2"> <p>Die Adresse des SMTP-Servers für ausgehende E-Mails. </p> <p>Beispiel: <span class="filepath"> mail.mycompany.com </span></p> <p>Für die Verwendung der beschriebenen Funktionen ist ein SMTP-Server erforderlich. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Server-Kennwort </td> 
   <td colname="col2"> <p>Das Kennwort für die Anmeldung beim SMTP-Server. Dieser Parameter ist optional, es sei denn, die Anmeldung ist zum Senden von E-Mails erforderlich. </p> <p>Für die Verwendung der beschriebenen Funktionen ist ein SMTP-Server erforderlich. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Server-Benutzer </td> 
   <td colname="col2"> <p>Die Benutzer-ID/der Name für die Anmeldung beim SMTP-Server. Dieser Parameter ist optional, es sei denn, die Anmeldung ist zum Senden von E-Mails erforderlich. </p> <p>Für die Verwendung der beschriebenen Funktionen ist ein SMTP-Server erforderlich. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Drosselverzögerung (Sekunden) </td> 
   <td colname="col2"> Die Mindestanzahl von Sekunden, die zwischen zwei Fehlern in dieser Kategorie liegen müssen, damit eine E-Mail gesendet werden kann. Der Wert 0 sendet die E-Mail sofort. </td> 
  </tr> 
 </tbody> 
</table>
