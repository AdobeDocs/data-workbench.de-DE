---
description: Um Sensorfehler so schnell wie möglich zu erkennen und zu beheben, bevor sie zu größeren Problemen oder Ausfällen führen, sollten Sie Ihre Ereignisprotokolle regelmäßig überwachen.
solution: Insight
title: Überwachen von Verwaltungsereignissen
uuid: c43d6509-6950-4436-8d6c-be7b00664f05
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Überwachen von Verwaltungsereignissen{#monitoring-administrative-events}

Um Sensorfehler so schnell wie möglich zu erkennen und zu beheben, bevor sie zu größeren Problemen oder Ausfällen führen, sollten Sie Ihre Ereignisprotokolle regelmäßig überwachen.

**Empfohlene Häufigkeit:** Mindestens stündlich

Sie können diese Ereignisse mithilfe der Windows Event Viewer- oder Unix-Syslog-Datei und der [!DNL *.sensor-log] Dateien überwachen, die sich standardmäßig im [!DNL Logs] Ordner im [!DNL Sensor] Installationsordner befinden. Diese Dateien weisen auf Fehler bei der Datenerfassung hin, insbesondere wenn eine [!DNL Sensor] Verbindung zum Ziel nicht hergestellt werden kann [!DNL data workbench server] und die Datenwarteschlange beginnt.

## Ereignisse unter Windows überwachen {#section-7c0443a356af4381bf22259654f5cd17}

Sensor protokolliert Fehler im Anwendungsprotokoll des Windows Event Viewers mit der Quelle &quot;Adobe&quot;.

Nachrichten werden je nach Schweregrad als &quot;Informationen&quot;, &quot;Warnung&quot;oder &quot;Fehler&quot;protokolliert.

**So öffnen Sie die Windows-Ereignisanzeige**:

* Klicken Sie auf **Start > Systemsteuerung > Verwaltung > Ereignisanzeige**.

## Ereignisse unter Unix überwachen {#section-5de3947891fb47ac88b7c855e545d54a}

Sensor protokolliert Fehler im [!DNL syslog] Daemon.

Der syslog-Daemon schreibt Fehlermeldungen in Protokolldateien, die auf den Regeln basieren, die Sie in der Datei syslog.conf angegeben haben. Fehler werden mit den Flags &quot;LOG_DAEMON&quot;und entweder &quot;LOG_NOTICE&quot;oder &quot;LOG_ERR&quot;je nach Schweregrad protokolliert.

**So öffnen Sie das Unix-Syslog**

Das Unix-Syslog befindet sich normalerweise in [!DNL /var/adm/messages] oder [!DNL /var/log/messages].

Navigieren Sie zum gewünschten Speicherort und öffnen Sie das Syslog.

## Nachrichtenformate {#section-a0899add30fd4b2da58a23b9e3324693}

Alle Sensormeldungen enthalten die Zeichenfolge &quot;Sensor&quot; und werden nummeriert, um die Wichtigkeit der angezeigten Meldung widerzuspiegeln.

| Nummer der Meldung | Nachrichtenbedeutet | Meldungszeichenfolge |
|---|---|---|
| 1xxx | Informativ | Sensor Info Nr. |
| 2xxx | Warnung | Sensorwarnung Nr. |
| 3xxx | Konfigurationsfehler | Sensorfehler Nr. |
| 4xxx | Operationsfehler | Sensorfehler Nr. |
| 5xxx | Interner Fehler | Sensorfehler Nr. |

>[!NOTE]
>
>Warnungen (2xxx) werden derzeit nicht verwendet. Diese Nummern sind für die zukünftige Verwendung reserviert.

Ihr Netzwerk-Management-Tool kann so eingestellt werden, dass Ihre Nachrichten alle 5-10 Minuten auf Fehler mit der &quot;Sensor&quot;-Quelle überwacht werden und entsprechende Mitarbeiter über Probleme warnen, die eine Intervention erfordern könnten. Sie können festlegen, dass das System nur auf bestimmte Arten von Ereignismeldungen wie die Zeichenfolge &quot;Sensorfehler&quot;überwacht wird. Alternativ können Sie unterschiedliche Regeln auf Ereignisse anwenden, denen die Zeichenfolgen &quot;Sensor Info&quot;, &quot;Sensor Warning&quot;und &quot;Sensor Error&quot;vorangestellt sind.

## Identifizieren wichtiger Nachrichten {#section-5a20f5dc18ca4012931d194db855e54e}

In Ihren Ereignisprotokollen sollten Sie besonders auf Meldungen zur Warteschlangengröße achten und diese sofort bearbeiten.

Zum Beispiel brauchen Nachrichten wie &quot; [!DNL Sensor Info 1012: Adobe disk queue is #% full]&quot;Aufmerksamkeit.

## Antwort auf Sensor-Ereignismeldungen {#section-0004c4a169dc4a8882d9bd87dd326ad4}

Tabellen, die Sensor-Ereignisse und empfohlene Aktionen für die unterstützten Webserverplattformen beschreiben.

**Alle Plattformen**

<table id="table_F8835AC0AD8F43E2B4494D8D35EBC0FD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Ereignismeldung </th> 
   <th colname="col2" class="entry"> Vorgeschlagene Aktion </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Sensor Info 1010: Sensor initialisiert. </td> 
   <td colname="col2"> Keine Aktion erforderlich. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensor Info 1011: Sensor beendet. Klicks insgesamt in Warteschlange ## </td> 
   <td colname="col2"> Keine Aktion erforderlich. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensor Info 1012: Adobe Disk Queue ist #% voll </td> 
   <td colname="col2"> Diese Meldung wird jedes Mal protokolliert, wenn die Auslastung der Disk-Warteschlange einen Schwellenwert von 10 % überschreitet. Wenn dieser Prozentsatz weiter zunimmt, sollten Maßnahmen ergriffen werden, bevor die Warteschlange voll ist und Daten verloren gehen. Das wahrscheinlichste Problem ist, dass der Sensor die Kommunikation mit dem Insight Server eingestellt hat. Wenden Sie sich an Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensor Info 1013: Änderung der Sensorkonfiguration </td> 
   <td colname="col2"> Keine Aktion erforderlich. Der Sensor hat eine Änderung in einer seiner Konfigurationsdateien erkannt und wird neu geladen. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensor Info 1014: Problem beim Zuordnen des Zufallszahlengenerators </td> 
   <td colname="col2"> Wenden Sie sich an Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensor Info 1016: Name der Konfigurationsdatei geladen </td> 
   <td colname="col2"> Keine Aktion erforderlich. Der Sensor hat die aufgeführte Konfigurationsdatei erfolgreich geladen. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensor Info 1017: Name der geladenen Experimentdatei </td> 
   <td colname="col2"> Keine Aktion erforderlich. Der Sensor hat die aufgeführte Experimentdatei erfolgreich geladen. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensorfehler 3016: Konfigurationsdatei /mypath/myfile kann nicht geladen werden </td> 
   <td colname="col2"> Vergewissern Sie sich, dass die in der Webserverkonfiguration angegebene Sensor-Konfigurationsdatei vorhanden ist und über die erforderlichen Berechtigungen zum Lesen durch den Webserverprozess verfügt. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Sensor 3017: Die Konfigurationsdatei für gesteuerte Experimente /mypath/myfile kann nicht geladen werden </p> </td> 
   <td colname="col2"> <p>Vergewissern Sie sich, dass die in txlogd.conf angegebene kontrollierte Experimentdatei vorhanden ist und dass der txlogd-Prozess über die erforderlichen Berechtigungen zum Lesen der Datei verfügt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensorfehler 3018: Inhaltsfilterlisten können nicht analysiert werden. Überprüfen der Konfigurationsdatei von txlogd </td> 
   <td colname="col2"> Überprüfen Sie die Syntax der Einträge ContentFilterInclude und ContentFilterExclude in txlogd.conf. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensorfehler 3023: Fehler beim Erstellen der Sperre (g_lockThrottle) </td> 
   <td colname="col2"> Wenden Sie sich an Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensorfehler 3024: Fehler beim Erstellen der Sperre (g_lockConfigCheck) </td> 
   <td colname="col2"> Wenden Sie sich an Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensorfehler 4014: Die Datenträgerwarteschlange konnte nicht geöffnet werden. </td> 
   <td colname="col2"> Überprüfen Sie den Dateinamen der QueueFile-Datei in txlogd.conf und wenden Sie sich, falls dies für richtig gehalten wird, an Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensorfehler 4020: Keine Warteschlangendatei </td> 
   <td colname="col2"> Überprüfen Sie den Dateinamen der QueueFile-Datei in txlogd.conf und wenden Sie sich, falls dies für richtig gehalten wird, an Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensorfehler 4021: Warteschlange ist abgeschlossen </td> 
   <td colname="col2"> Wenden Sie sich an Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensorfehler 4022: Speicherblock der Länge &lt;x&gt; kann nicht mit Offset &lt;y&gt; zugeordnet werden </td> 
   <td colname="col2"> Wenden Sie sich an Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensorfehler 5012: Mutex konnte nicht erstellt werden. </td> 
   <td colname="col2"> Wenden Sie sich an Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensorfehler 5013: Mutex konnte nicht erfasst werden. </td> 
   <td colname="col2"> Wenden Sie sich an Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensorfehler 5030: Spawn Gabel-Fehler. </td> 
   <td colname="col2"> Wenden Sie sich an Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensorfehler 5031: setsid fehlgeschlagen. </td> 
   <td colname="col2"> Wenden Sie sich an Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensorfehler 5032: Spawn Gabel-Fehler. </td> 
   <td colname="col2"> Wenden Sie sich an Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensorfehler 5033: chdir ist fehlgeschlagen. </td> 
   <td colname="col2"> Wenden Sie sich an Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensorfehler 5034: Signal empfangen </td> 
   <td colname="col2"> Das Programm wurde wahrscheinlich durch ein externes Signal beendet. Wenn die Quelle dieses Signals nicht ermittelt werden kann, wenden Sie sich an Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensorfehler 5035: Ausstieg von außen aufgerufen </td> 
   <td colname="col2"> Wenden Sie sich an Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensorfehler 5036: txlogd wird bereits ausgeführt </td> 
   <td colname="col2"> Eine weitere Instanz des txlogd-Daemons wird bereits ausgeführt. Beenden Sie zuerst die andere Instanz, wenn Sie eine neue Instanz ausführen möchten. </td> 
  </tr> 
 </tbody> 
</table>

**Apache/IBM HTTP Server**

| Ereignismeldung | Vorgeschlagene Aktion |
|---|---|
| Sensorfehler 3015: Die VisualSciencesConfig-Direktive fehlt in httpd.conf. | Dies ist ein Konfigurationsfehler. Die VisualSciencesConfig-Direktive muss sich in httpd.conf befinden und einen Parameter enthalten, der den Speicherort von txlogd.conf angibt. |
| Sensorfehler 3019: vys-cookie wurde nicht vor vys-log aufgerufen. Bitte wenden Sie sich an den Support. | Wenden Sie sich an Adobe ClientCare. |
| Sensorfehler 3025: Subrequest verweist auf sich selbst | Wenden Sie sich an Adobe ClientCare. |

**AOL-Server**

| Ereignismeldung | Vorgeschlagene Aktion |
|---|---|
| Sensorfehler 3015: Der Abschnitt &quot;ns/server/[server]/module/[module] &quot;fehlt in der AOLServer-Konfigurationsdatei. | Dies ist ein Konfigurationsfehler. Richtig, wie im Fehler angegeben. |
| Sensorfehler 3019: vys-cookie wurde nicht vor vys-log aufgerufen. Bitte wenden Sie sich an den Support. Wenden Sie sich an Adobe ClientCare. | Bitte wenden Sie sich an den Support. Wenden Sie sich an Adobe ClientCare. |
| Sensorfehler 3020: VisualSciencesConfig fehlt als erster Eintrag im [Abschnittsabschnitt] in der AOLServer-Konfigurationsdatei. | Dies ist ein Konfigurationsfehler. Richtig, wie im Fehler angegeben. |
| Sensorfehler 3021: VisualSciencesConfig fehlt ein Wert im [Abschnittsabschnitt] in der AOLServer-Konfigurationsdatei. | Dies ist ein Konfigurationsfehler. Richtig, wie im Fehler angegeben. |

**iPlanet- und Java-System-Webserver**

| Ereignismeldung | Vorgeschlagene Aktion |
|---|---|
| Sensorfehler 3011: Init-Richtlinie erforderlich. Beispiel: Init fn=vys-init config-file=&quot;/mypath/myfile&quot; | Dies ist ein Konfigurationsfehler. Die iPlanet Init-Richtlinie fehlt. |
| Sensorfehler 3015: config-file ist nicht in der iPlanet Init-Direktive angegeben | Dies ist ein Konfigurationsfehler. Der Pfad zur Konfigurationsdatei wurde in der iPlanet Init-Richtlinie nicht angegeben. |
| Sensorfehler 3019: vys-cookie wurde nicht vor vys-log aufgerufen. Bitte überprüfen Sie die Konfigurationsdatei | vys-cookie muss als First NameTrans-Direktive für jeden virtuellen Software-Server angegeben werden. |

