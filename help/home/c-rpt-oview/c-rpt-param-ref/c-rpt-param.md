---
description: Informationen zu Report.cfg-Parametern.
title: Parameter für „Report.cfg“
uuid: 7a20f4f6-99e6-401a-ba3c-c508881c0f0d
exl-id: 31e4de5f-f7e8-4a35-b5c6-6ad8ef79a259
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '2348'
ht-degree: 2%

---

# Parameter für „Report.cfg“{#report-cfg-parameters}

Informationen zu Report.cfg-Parametern.

Das in [Berichtssatz konfigurieren](../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/t-config-rpt-set.md#task-cfb2fd0c28bc48c2acdd582fe0d670d0) dargestellte Beispiel [!DNL Report.cfg] enthält standardmäßig nur die in der Datei [!DNL Report.cfg] enthaltenen Parameter. Die folgende Tabelle enthält Beschreibungen aller verfügbaren [!DNL Report.cfg]-Dateiparameter.

Wenn Sie zusätzliche Parameter zu einer [!DNL Report.cfg]-Datei hinzufügen müssen, müssen Sie dies mit einem Texteditor tun. Anweisungen dazu, einschließlich Beispiele zur Definition der einzelnen Parametereinträge, finden Sie unter [Bearbeiten vorhandener Report.cfg-Dateien](../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/c-edit-ex-rpt-files.md#concept-96fd57159f454defa09bd18655a12887).

>[!NOTE]
>
>Die Parameter in dieser Tabelle sind in alphabetischer Reihenfolge aufgeführt. Wenn Sie die Datei [!DNL Report.cfg] in der Data Workbench öffnen, werden die Vektoren in alphabetischer Reihenfolge aufgelistet, gefolgt von den einzelnen in alphabetischer Reihenfolge aufgelisteten Parametern.

<table id="table_F55E925EA34F43B6832788BB6878BB4A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Warnschwellenwert </td> 
   <td colname="col2"> <p><i>Optional</i>. Dieser Parameter gilt nur für Berichte mit Metrikindikatoren. Anzahl der Metrikindikatoren, die im Arbeitsblatt angezeigt werden müssen, bevor ein Warnbericht gesendet wird. </p> <p>Wenn nur eine Metrik im Arbeitsblatt für Metrikindikatoren überwacht wird, setzen Sie den Schwellenwert auf 1. Der Bericht wird generiert, wenn die Metrik im Arbeitsblatt zu einem Nach-oben-/Nach-unten-Pfeil oder X ausgewertet wird. Wenn mehr als eine Metrik im Bericht überwacht wird, können Sie die Anzahl der Metrikindikatoren auswählen, die vor der Berichterstellung zu einem Nach-oben-/Nach-unten-Pfeil oder einem X ausgewertet werden müssen. Wenn beispielsweise zwei Metriken überwacht werden: 
     <ul id="ul_A64E8A2306B14371A233D372B956F64D"> 
      <li id="li_2A3020ED350644A3954C36D3EB0B86D4">Wenn der Schwellenwert auf 1 gesetzt ist, wird der Bericht generiert, wenn eine der Metriken im Arbeitsblatt zu einem Nach-oben-/Nach-unten-Pfeil oder einem X ausgewertet wird. </li> 
      <li id="li_DA4EF4984880483DA48322D9D57B9240">Wenn der Schwellenwert auf 2 gesetzt ist, müssen beide Metriken zu einem Nach-oben-/Nach-unten-Pfeil oder einem X ausgewertet werden, bevor der Bericht generiert wird. </li> 
     </ul> </p> <p>Weitere Informationen zu Metrikindikatoren finden Sie im <i>Data Workbench-Benutzerhandbuch</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Berichtgenerierung zulassen </td> 
   <td colname="col2"> <p>Gibt an, ob <span class="keyword"> Report Server </span> beim Erstellen oder Ändern dieser Berichte automatisch bestimmte Berichte generiert oder neu generiert. Die Optionen sind "true"oder "false". Wenn der Wert auf "true"gesetzt ist, führt das Erstellen oder Ändern eines Berichtsarbeitsbereichs dazu, dass <span class="keyword"> Report Server </span> diesen Bericht für die letzte Ausführung neu generiert. </p> <p> <p>Hinweis:  Wenn Sie die Datei <span class="filepath"> Report.cfg </span> ändern, führt <span class="keyword"> Report Server </span> dazu, dass alle Berichte, die von der Datei <span class="filepath"> Report.cfg </span> gesteuert werden, neu generiert werden. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Anlagen </td> 
   <td colname="col2"> <p><i>Optional</i>. Bereichs-ID für den Namen und Inhaltstyp aller Anlagen, die mit per E-Mail verteilten Berichten ausgehen, einschließlich der Anzahl der Anlagen. </p> <p>So fügen Sie eine neue Anlage hinzu: 
     <ol id="ol_CBDC1E95D34A4D08A862680127438433"> 
      <li id="li_784C48C540534F4CBB35BBDA6BC5F48E">Öffnen Sie die Datei <span class="filepath"> Report.cfg </span> in Data Workbench. </li> 
      <li id="li_0709ADDDDF2E469FAB10761B46173136">Klicken Sie mit der rechten Maustaste auf <span class="uicontrol"> Anlagen </span> und klicken Sie auf <span class="uicontrol"> Neues untergeordnetes Element hinzufügen </span> &gt; <span class="uicontrol"> Anhang </span>. </li> 
     </ol> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Content-Typ </td> 
   <td colname="col2"> <p>Inhaltstyp der anzuhängenden Datei. </p> <p>Beispiel: image/jpeg </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dateiname </td> 
   <td colname="col2"> <p>Speicherort und Name der Datei, die angehängt werden soll. </p> <p>Beispiel: <span class="filepath"> c:\myimage.jpg </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Farbset </td> 
   <td colname="col2"> Gibt das Farbschema an, das für <span class="filepath"> .png </span>-Dateien verwendet werden soll. 0 für einen schwarzen Hintergrund verwendet wird; 1 ist für einen weißen Hintergrund vorgesehen; und 2 für ein Graustufenbild. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Befehl zur Ausführung </td> 
   <td colname="col2"> <i>Optional</i>. Ein Batch-Befehl oder eine ausführbare Datei, die nach der Erstellung des Berichtssatzes ausgeführt wird. Wenn ein Start des Kommando-Shell-Interpreters erforderlich ist, muss dem Befehl cmd /c vorangestellt werden. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Excel-Standardvorlage </td> 
   <td colname="col2"> <p><i>Optional</i>. Dateiname der allgemeinen Excel-Vorlagendatei ( <span class="filepath"> .xls </span> oder <span class="filepath"> .xlsx </span>), die Sie zum Generieren von Berichten als Excel-Dateien verwenden möchten. Dieser Parameter unterstützt vollständige Dateipfade, z. B. <span class="filepath"> c:\templates\mytemplate.xls </span>. </p> <p>Diese Datei wird für alle Excel-Berichte verwendet, es sei denn, eine Vorlage wurde speziell für einen bestimmten Bericht definiert. Siehe <a href="../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/c-gen-rpts-ex-files.md#section-40ab11916f464b1a88214ab969da6751"> Verwenden einer Vorlagendatei </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Name der Dimension </td> 
   <td colname="col2"> <i>Optional</i>. Name der Dimension, für die Sie einen Bericht dynamisch erstellen möchten. Wenn Sie einen Dimensionsnamen in diesen Parameter eingeben, müssen Sie einen Wert entweder in den Parameter "Lookup File"oder in den Parametern "Top N Metrik"und "Top N Wert"eingeben. Die in diesem Parameter benannte Dimension muss im Datensatz vorhanden sein, für den Berichte erstellt werden. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nur E-Mail bei Perfektion </td> 
   <td colname="col2"> <i>Optional</i>. Hiermit kann der Benutzer festlegen, dass ein Berichtssatz nur gesendet werden soll, wenn während der Ausführung keine Fehler aufgetreten sind. Die Optionen sind "true"und "false". Der Standardwert ist „false“. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Enddatum </td> 
   <td colname="col2"> <p><i>Optional</i>. Datum und Uhrzeit der letzten Ausführung des Berichts. Diese Zeit basiert auf der Ausführungszeit des Datensatzes. </p> <p>Format: MM/TT/JJJJ hh:mm Zeitzone unter Verwendung der 24-Stunden-Syntax für die Zeit </p> <p>Beispiel: 08/01/2007 12:01 EDT </p> <p>Weitere Informationen zu Zeitzoneneinstellungen finden Sie im <i>Handbuch zur Datensatzkonfiguration</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Alle </td> 
   <td colname="col2"> Häufigkeit der Berichtserstellung: Tag, Woche oder Monat. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Zeitüberschreitung bei Excel-Watchdog (Sekunden) </td> 
   <td colname="col2"> <p><i>Optional</i>. Die Anzahl der Sekunden, die <span class="keyword"> Report Server </span> warten soll, bis Microsoft Excel beim Generieren eines Berichts als Excel-Datei reagiert, bevor <span class="keyword"> Report Server </span> entscheidet, dass Excel nicht reagiert, und den Prozess beendet. Durch Verwendung dieses Parameters wird <span class="keyword"> Report Server </span> aktiviert, um Excel zu beenden, wenn es nicht mehr reagiert, und Ihre Nicht-Excel-Berichte weiter zu verarbeiten. Der Standardwert ist 300.0. Um diese Funktion zu deaktivieren, setzen Sie diesen Parameter auf 0.0. </p> <p>Stellen Sie sicher, dass der von Ihnen definierte Wert ausreichend lang ist, um den Export des Berichts nach Excel zu ermöglichen. Andernfalls kann <span class="keyword"> Report Server </span> Excel vorzeitig beenden und Ihr Bericht wird nicht generiert. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Filterformel </td> 
   <td colname="col2"> <p><i>Optional</i>. Filter, der auf jeden Arbeitsbereich im Berichtssatz angewendet wird. </p> <p>Weitere Informationen finden Sie in der <a href="https://experienceleague.adobe.com/docs/data-workbench/using/client/t-open-ins.html#Syntax_for_Filter_Expressions" format="http" scope="external">-Syntax zum Erstellen von Filtern </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Gamma-Korrektur </td> 
   <td colname="col2"> <p>Gamma-Einstellung für <span class="filepath"> .png </span> Dateiausgabe. Die Standardeinstellung ist „1.6“. </p> <p> <p>Hinweis:  Adobe empfiehlt, diesen Wert nicht zu ändern. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Logos ausblenden </td> 
   <td colname="col2"> Gibt an, ob Report Server die Logos beim Generieren von Berichten ausblendet. Die Optionen sind <span class="filepath"> true </span> oder <span class="filepath"> false </span>. Wenn der Wert auf <span class="filepath"> false </span> gesetzt ist, wird Ihr Bericht mit dem Berichtlogo generiert. Der Standardwert ist <span class="filepath"> false </span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Suchdatei </td> 
   <td colname="col2"> <p><i>Optional</i>. Wenn dieser Parameter ausgefüllt ist, wird Report Server im dynamischen Modus ausgeführt und generiert Berichte für jedes Element der Dimension, das im Parameter "Dimension Name"angegeben ist. Diese Datei muss zwei tabulatorgetrennte Spalten ohne Kopfzeile enthalten. </p> <p> 
     <ul id="ul_378D4104BB5141C4A013EFE881BFFC6A"> 
      <li id="li_6F2C89A286B24FFE8EE8C82D278D0633">Spalte 1 enthält eine Liste von Dimensionselementen. </li> 
      <li id="li_4BD1CAA77FEC43268B40489BC5E5E6F7">Spalte 2 enthält die E-Mail-Adressen der Empfänger des Berichts. Ein Bericht für ein bestimmtes Element in Spalte 1 wird in derselben Zeile in Spalte 2 an die E-Mail-Adresse gesendet. Sie können mehrere E-Mail-Adressen eingeben, indem Sie sie durch Kommas (ohne Leerzeichen) trennen. Wenn Berichte nicht per E-Mail versendet werden sollen, kann diese Spalte leer sein, muss aber vorhanden sein. </li> 
     </ul> </p> <p> <p>Hinweis:  Wenn Sie in diesen Parameter einen Wert eingeben, müssen Sie einen Dimension im Parameter "Name der "eingeben. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nur Benachrichtigung </td> 
   <td colname="col2"> Mit dieser Einstellung <span class="wintitle"> Report Server </span> können Sie Data Workbench so konfigurieren, dass eine E-Mail gesendet wird, wenn ein Bericht generiert wird. Wenn Sie diesen Wert auf <span class="filepath"> true </span> setzen, wird der Bericht nicht gesendet, sondern eine E-Mail gesendet, in der der angemeldete Benutzer darüber informiert wird, dass der Bericht generiert wurde. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> E-Mail-Bericht </td> 
   <td colname="col2"> <p>Bereichs-ID zum Verteilen von Berichten per E-Mail. Um Berichte per E-Mail zu verteilen, müssen Sie die folgenden Parameter für den Eintrag <span class="wintitle"> E-Mail-Bericht </span> eingeben. Alle Berichte im Berichtssatz werden in einer Nachricht an die im Parameter Empfänger angegebenen E-Mail-Adressen gesendet. </p> <p> <p>Hinweis:  Report Server sendet nur E-Mails, die mindestens einen Bericht generiert haben. </p> </p> <p>Um das Versenden von Berichten per E-Mail zu ermöglichen, müssen Sie mindestens die folgenden Parameter für diesen Eintrag eingeben: 
     <ul id="ul_539D64D61A8B4F1E95D889C6610EE3B8"> 
      <li id="li_D2EDBEE57BFE4FD4BB66F63AE561F1E2">SMTP-Server </li> 
      <li id="li_4EEFE6CDA3384FE38149CE8DCBEFF847">Empfänger </li> 
      <li id="li_CF9F0CF7ECFC4D88A7F4F11BAC4938D6">Absenderadresse </li> 
      <li id="li_40BFDCDC9640488EBB450CF8579DA250">Nur Benachrichtigung </li> 
     </ul> </p> <p> <p>Hinweis:  Informationen zum Versand von Berichten per E-Mail nach der erneuten Generierung eines Berichtssatzes finden Sie unter <a href="../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/c-edit-ex-rpt-files.md#concept-96fd57159f454defa09bd18655a12887"> Bearbeiten vorhandener Report.cfg-Dateien </a>. </p> </p> <p>Der Wert Nur Benachrichtigung ist in den Versionen 5.4x und 5.5x verfügbar. </p> <p>Für eine große Gruppe von Empfängern, die benachrichtigt werden sollen (mehr als 20), wird dringend empfohlen, E-Mail-Verteilungslisten zu verwenden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Body XSL-Vorlage </td> 
   <td colname="col2"> <p><i>Optional</i>. Pfad der XSL-Vorlagendatei, die auf die Datei <span class="filepath"> reports.xml </span> angewendet werden soll. Durch Verwendung dieses Parameters kann Report Server Ihre Berichte in der verteilten E-Mail statt als Anhänge senden. Der resultierende Text wird als Textkörper der E-Mail-Nachricht verwendet. </p> <p>Eine Beispieldatei finden Sie unter <a href="../../../home/c-rpt-oview/c-rpt-sample-files/c-rpt-sample-files.md#concept-a06b93f21c5d4888be335fa2281b2a87"> BerichtsBeispieldateien </a> . </p> <p>Weitere Informationen zur Extensible Stylesheet Language (XSLT) finden Sie unter <a href="http://www.w3.org/Style/XSL/" format="http" scope="external"> The Extensible Stylesheet Language Family </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Empfänger </td> 
   <td colname="col2"> E-Mail-Adressen der Personen, an die Sie den Bericht senden möchten. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Absenderadresse </td> 
   <td colname="col2"> E-Mail-Adresse des Absenders. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Absendername </td> 
   <td colname="col2"> Optional. Name des Absenders. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SMTP-Server </td> 
   <td colname="col2"> Die Adresse des SMTP-Servercomputers sowie das Kennwort und der Benutzername, die für die Authentifizierung erforderlich sind. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Betreff </td> 
   <td colname="col2"> <i>Optional</i>. Betreffzeile, die die zu sendende E-Mail beschreibt. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nur Benachrichtigung </td> 
   <td colname="col2"> Damit können Sie Data Workbench so konfigurieren, dass eine E-Mail gesendet wird, wenn ein Hintergrundbericht generiert wird. Wenn Sie diesen Wert auf True setzen, wird der Bericht nicht gesendet, sondern eine E-Mail gesendet, in der der angemeldete Benutzer mit dem Berichtspeicherort verknüpft wird. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Output Root </td> 
   <td colname="col2"> <p><i>Optional</i>. Ausgabespeicherort der generierten Berichtssätze. Die Standardeinstellung ist der Ordner <i>&lt;Profilname&gt;</i>\Berichte im Installationsordner von Report Server. </p> <p>Um <span class="keyword"> Report Server </span> für die Ausgabe von Berichten an ein Portal zu konfigurieren, setzen Sie den <span class="wintitle"> Output Root </span> auf den Dokumentenstamm des Webservers, der für das Portal verwendet wird. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Preload Query Filter </td> 
   <td colname="col2"> <p><i>Optional</i>. Dieser Parameter gilt nur für den Berichtstyp <span class="wintitle"> Top-Dimension-Element </span> . </p> <p>Der Name des Filters, den Sie auf die Abfrage anwenden möchten, die ausgeführt werden muss, um die Top-N-Dimensionselemente zu bestimmen, bevor der Bericht generiert werden kann. Die Standardeinstellung ist <span class="wintitle"> Broken_Session_Filter </span>. Weitere Informationen zum <span class="wintitle"> "Broken Session Filter </span>"finden Sie im <i>Data Workbench-Benutzerhandbuch</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Berichtstypen </span> </td> 
   <td colname="col2"> <p>Format(e), in dem/denen Sie die Ausgabe generieren möchten. Sie können eine oder alle der folgenden Optionen verwenden, um den Berichtssatz in mehreren Formaten gleichzeitig auszugeben: 
     <ul id="ul_FAF024F73F6B4F2C9D6760441E8F0CF9"> 
      <li id="li_04A3E0C7812B43E7BBFCDA8C3EA21CFC">Excel erstellt eine Excel-Arbeitsmappe mit einer Visualisierung pro Arbeitsblatt. Verwenden Sie in der Regel Excel-Dateien für die E-Mail-Verteilung. Siehe <a href="../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/c-gen-rpts-ex-files.md#concept-0b0fdb938805422d95c5f6fe706f09ee"> Erstellen von Berichten als Microsoft Excel-Dateien </a>. Informationen zur Verwendung einer Vorlagendatei finden Sie unter <a href="../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/c-gen-rpts-ex-files.md#section-40ab11916f464b1a88214ab969da6751"> Verwenden einer Vorlagendatei </a>. </li> 
      <li id="li_CD1BDDEDE85349CE8C736887BB5E4726">png erstellt Grafikdateien des Portable Network. Verwenden Sie in der Regel <span class="filepath"> .png </span> -Dateien für die Anzeige in einem Webbrowser (Portal). </li> 
      <li id="li_869DA266E6A041A5BD343537743FAC79">Miniaturansichten erstellen eine Miniaturansicht ( <span class="filepath"> .jpg </span>-Datei) des Arbeitsbereichs. Die Standardgröße beträgt 240 x 180. Um die Standardgröße zu ändern, bearbeiten Sie die Parameter Miniatur X und Miniatur Y . </li> 
     </ul> </p> <p>Um beim Bearbeiten von <span class="filepath"> Report.cfg </span> in Data Workbench einen neuen Berichtstyp hinzuzufügen, klicken Sie mit der rechten Maustaste auf <span class="uicontrol"> Berichtstypen </span>, klicken Sie auf <span class="uicontrol"> Neues untergeordnetes Element hinzufügen </span> und wählen Sie den gewünschten Berichtstyp aus. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Anfangsdatum </td> 
   <td colname="col2"> <p>Das erste Datum und die erste Uhrzeit, zu der der Bericht ausgeführt werden soll. Diese Zeit basiert auf der Ausführungszeit des Datensatzes. </p> <p>Format: MM/TT/JJJ hh:mm Zeitzone unter Verwendung der 24-Stunden-Syntax für die Zeit. </p> <p>Weitere Informationen zu Zeitzoneneinstellungen finden Sie im <i>Handbuch zur Datensatzkonfiguration</i>. </p> <p> <p>Hinweis:  Die Berichte werden gestartet, sobald die Zeitstempel der Daten im Profil mit dem angegebenen Datum und der angegebenen Uhrzeit übereinstimmen. </p> </p> <p>Beispiel: </p> <p>Wenn das Startdatum 08/08/2006 12:00 EST ist, werden Berichte für Daten mit einem Zeitstempel vom 08/08/2006 12:00 EST und höher ausgeführt. 
     <ul id="ul_EEF6F61B55E440DFB3348A9B10DFA5F1"> 
      <li id="li_133374F1287D4631BCAE7691E3FC93B6">Die täglichen Berichte werden für den 08.08.2006 und danach jeden Tag für Daten mit hh:mm = 12:00 EST ausgeführt. </li> 
      <li id="li_89514719C5F94D789E4A1049D2CD5F93">Die wöchentlichen Berichte werden für den 08.08.2006 und danach für jeden 7. Tag für Daten mit hh:mm = 12:00 EST ausgeführt. </li> 
      <li id="li_EB986D04FA664DB89C66B0FC1CE4D36B">Die monatlichen Berichte werden für den 08.08.2006 und für den achten Tag jedes Monats danach für Daten mit hh:mm = 12:00 EST ausgeführt. </li> 
     </ul> </p> <p>Die Metrik <span class="wintitle"> Berichtszeit </span> wirkt sich auf die Berichtsdimensionen "Letzte N"aus, z. B. "Letzte 7 Tage", "Gestern"und "Vor 3 Wochen". Bei Abfragen in Report Server gibt die Metrik <span class="wintitle"> Berichtszeit </span> ( <span class="filepath"> Berichtszeit.metric </span>) das Datum und die Uhrzeit an, für die die Berichte ausgeführt werden. Dies ist zunächst das Datum und die Uhrzeit, die im Parameter Startdatum angegeben sind und dann um den Zeitraum erhöht werden, der durch den Parameter Alle angegeben wird. Bei Abfragen in Data Workbench basiert die Metrik <span class="wintitle"> Berichtszeit </span> auf Mitternacht der Ausführungsmetrik ( <span class="filepath"> As Of.metric </span>). Aufgrund der unterschiedlichen Definitionen der Metrik Berichtszeit können Sie bei der Abfrage eines Arbeitsbereichs, der eine Dimension Letzte N verwendet, unterschiedliche Ergebnisse in Data Workbench und <span class="keyword"> Report Server </span> für denselben Arbeitsbereich erhalten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Miniatur X </td> 
   <td colname="col2"> <i>Optional</i>. Ganzzahl, die die Größe (in Pixel) der X-Achse der als Ausgabe generierten Miniaturansichten steuert. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Miniatur Y </td> 
   <td colname="col2"> <i>Optional</i>. Ganzzahl, die die Größe (in Pixel) der Y-Achse der als Ausgabe generierten Miniaturansichten steuert. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Top N Metrik </td> 
   <td colname="col2"> <p><i>Optional</i>. Siehe Beschreibung für den Parameter "Top N Value". </p> <p> <p>Hinweis:  Wenn Sie einen Dimension in diesen Parameter eingeben, müssen Sie einen Wert im Parameter "Name der "und im Parameter "Top N Value"eingeben. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Top N Wert </td> 
   <td colname="col2"> <p><i>Optional</i>. Wenn dieser Parameter ausgefüllt ist, wird <span class="keyword"> Berichtsserver </span> im dynamischen Modus ausgeführt und generiert Berichte für die (in diesem Parameter angegebene) oberste Elementanzahl für die im Parameter "Dimension Name"angegebene Dimension, wobei die Metrik nach der im Parameter "Top N Metrik"angegebenen Metrik gezählt wird. </p> <p>Beispiel: Wenn Sie Seite im Parameter Seitenname , Sitzungen im Parameter Top N Metrik und 5 in diesem Dimension eingeben, werden im generierten Bericht die fünf obersten Seiten mit der höchsten Sitzungsanzahl aufgelistet. </p> <p> <p>Hinweis:  Wenn Sie einen Dimension in diesen Parameter eingeben, müssen Sie einen Wert im Parameter "Name der "und im Parameter "Top N Metrik"eingeben. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nur lokales Beispiel verwenden </td> 
   <td colname="col2"> <i>Optional</i>. Gibt an, ob <span class="keyword"> Report Server </span> Berichte erstellen soll, die nur die lokale Stichprobe des Datensatzes verwenden. Wenn Sie diesen Parameter auf "true"setzen, können Sie ein Beispiel des Berichtssatzes anzeigen (ohne einen Data Workbench-Server zu laden), um zu sehen, wie die Ausgabe aussieht, ohne die gesamte für die vollständige Verarbeitung der Daten erforderliche Zeit in Anspruch zu nehmen. Dies dient als Testfunktion. Die Optionen sind "true"oder "false". Der Standardwert ist "false". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Workspace-Pfad </td> 
   <td colname="col2"> <p><i>Optional</i>. Speicherort einer Sammlung von Arbeitsbereichen für einen bestimmten Berichtssatz. Dies ist nützlich, um eine einzelne Kopie von Arbeitsbereichen zu verwalten, die auf unterschiedliche Weise generiert und verteilt werden müssen, indem <span class="filepath"> Report.cfg </span>-Dateien für mehrere Berichtssätze verwendet werden. Der Stammordner für diesen Pfad kann ein beliebiger Profilordner sein. Geben Sie am Anfang der Pfadzeichenfolge keinen Schrägstrich (\) ein. </p> <p>Beispiel: Sie können die gemeinsamen Arbeitsbereiche für Satz A und Satz B im Ordner <span class="filepath"> Berichte\Allgemein </span> speichern und dann die <span class="filepath"> Report.cfg </span>-Dateien für zwei verschiedene Berichtssätze mit jeweils unterschiedlichen Generierungs- und Verteilungseinstellungen definieren. In beiden <span class="filepath"> Report.cfg </span>-Dateien würden Sie den Workspace-Pfadparameter auf <i>Profilname</i>\Reports\Common setzen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> XSL-Ausgabedatei </td> 
   <td colname="col2"> <i>Optional</i>. Pfad der Ausgabedatei, die erstellt wird, wenn die <span class="wintitle"> XSL-Vorlage </span> auf den Berichtsindex angewendet wird. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> XSL-Vorlage </td> 
   <td colname="col2"> <p><i>Optional</i>. Pfad der XSL-Vorlagendatei, die auf den Berichtindex angewendet werden soll. Die resultierende umgewandelte <span class="filepath"> .xml </span>-Datei wird in die angegebene <span class="wintitle"> XSL-Ausgabedatei </span> geschrieben. Eine Beispieldatei finden Sie unter <a href="../../../home/c-rpt-oview/c-rpt-sample-files/c-rpt-sample-files.md#concept-a06b93f21c5d4888be335fa2281b2a87"> BerichtsBeispieldateien </a> . </p> <p> <p>Hinweis:  Sofern Sie beim Generieren Ihrer Berichte keine <span class="filepath"> .xsl </span>-Vorlage verwenden, werden alle Berichte per E-Mail als Anhänge verteilt. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>
