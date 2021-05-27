---
description: Um Sensorfehler so schnell wie möglich zu erkennen und zu beheben, bevor sie zu größeren Problemen oder Ausfällen führen, sollten Sie regelmäßig Ihre Ereignisprotokolle überwachen.
title: Überwachen administrativer Ereignisse
uuid: c43d6509-6950-4436-8d6c-be7b00664f05
exl-id: 70894074-b8aa-4f6c-87d1-d0403f4c3319
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1092'
ht-degree: 1%

---

# Überwachen administrativer Ereignisse{#monitoring-administrative-events}

Um Sensorfehler so schnell wie möglich zu erkennen und zu beheben, bevor sie zu größeren Problemen oder Ausfällen führen, sollten Sie regelmäßig Ihre Ereignisprotokolle überwachen.

**Empfohlene Häufigkeit:** Mindestens stündlich

Sie können diese Ereignisse mithilfe der Windows Event Viewer- oder Unix Syslog-Datei und der [!DNL *.sensor-log] -Dateien überwachen, die sich standardmäßig im Ordner [!DNL Logs] im Installationsverzeichnis [!DNL Sensor] befinden. Diese Dateien weisen auf das Vorhandensein von Fehlern während der Datenerfassung hin, insbesondere wenn [!DNL Sensor] keine Verbindung zum Ziel [!DNL data workbench server] herstellen kann und mit der Warteschlange für Daten beginnt.

## Überwachen von Ereignissen unter Windows {#section-7c0443a356af4381bf22259654f5cd17}

Der Sensor protokolliert Fehler im Anwendungsprotokoll des Windows Event Viewers mit der Quelle &quot;Adobe&quot;.

Nachrichten werden je nach Schweregrad als &quot;Informationen&quot;, &quot;Warnung&quot;oder &quot;Fehler&quot;protokolliert.

**So öffnen Sie die Windows Event Viewer**:

* Klicken Sie auf **Start > Systemsteuerung > Verwaltung > Ereignis-Viewer**.

## Überwachung von Ereignissen unter Unix {#section-5de3947891fb47ac88b7c855e545d54a}

Der Sensor protokolliert Fehler beim [!DNL syslog]-Daemon.

Der syslog-Daemon schreibt Fehlermeldungen in Protokolldateien basierend auf den Regeln, die Sie in Ihrer syslog.conf-Datei angegeben haben. Fehler werden mit den Flags &quot;LOG_DAEMON&quot;und entweder &quot;LOG_NOTICE&quot;oder &quot;LOG_ERR&quot;je nach Schweregrad protokolliert.

**Öffnen des Unix-Syslog**

Das Unix-Syslog befindet sich normalerweise in [!DNL /var/adm/messages] oder [!DNL /var/log/messages].

Navigieren Sie zum entsprechenden Verzeichnis und öffnen Sie das syslog.

## Nachrichtenformate {#section-a0899add30fd4b2da58a23b9e3324693}

Alle Sensormeldungen enthalten die Zeichenfolge &quot;Sensor&quot; und sind nummeriert, um die Wichtigkeit der angezeigten Nachricht widerzuspiegeln.

| Nummer der Meldung | Nachrichtenbedeutet | Nachrichtenzeichenfolge |
|---|---|---|
| 1xxx | Informatik | Sensor Info # |
| 2xxx | Warnung | Sensorwarnungsnummer |
| 3xxx | Konfigurationsfehler | Sensor Error # |
| 4xxx | Betriebsfehler | Sensor Error # |
| 5xxx | Interner Fehler | Sensor Error # |

>[!NOTE]
>
>Warnungen (2xxx) werden derzeit nicht verwendet. Diese Zahlen sind für die zukünftige Verwendung reserviert.

Ihr Netzwerk-Management-Tool kann so eingestellt werden, dass Ihre Nachrichten alle 5-10 Minuten auf Fehler mit der Quelle &quot;Sensor&quot;überwacht und geeignete Mitarbeiter auf Probleme aufmerksam gemacht werden, die möglicherweise eine Intervention erfordern. Sie können das System nur auf bestimmte Arten von Ereignismeldungen überwachen, wie z. B. die Zeichenfolge &quot;Sensor Error&quot;. Alternativ können Sie unterschiedliche Regeln auf Ereignisse anwenden, die den Zeichenfolgen &quot;Sensor Info&quot;, &quot;Sensor Warning&quot;und &quot;Sensor Error&quot;vorangestellt sind.

## Identifizieren wichtiger Nachrichten {#section-5a20f5dc18ca4012931d194db855e54e}

In Ihren Ereignisprotokollen sollten Sie auf alle Nachrichten bezüglich der Warteschlangengröße achten und diese sofort bearbeiten.

Beispielsweise müssen Nachrichten wie &quot;[!DNL Sensor Info 1012: Adobe disk queue is #% full]&quot;aufmerksam verfolgt werden.

## Antwort auf Sensor-Ereignismeldungen {#section-0004c4a169dc4a8882d9bd87dd326ad4}

Tabellen, die Sensor-Ereignisse und empfohlene Aktionen für die unterstützten Webserverplattformen beschreiben.

**Alle Plattformen**

<table id="table_F8835AC0AD8F43E2B4494D8D35EBC0FD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Ereignisnachricht </th> 
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
   <td colname="col1"> Sensor Info 1012: Adobe-Festplattenwarteschlange ist #% voll </td> 
   <td colname="col2"> Diese Meldung wird jedes Mal protokolliert, wenn die Auslastung der Festplattenwarteschlange einen Schwellenwert von 10 % überschreitet. Wenn dieser Prozentsatz weiter zunimmt, sollten Maßnahmen ergriffen werden, bevor die Warteschlange voll ist und Daten verloren gehen. Das wahrscheinlichste Problem ist, dass der Sensor die Kommunikation mit dem Insight Server eingestellt hat. Wenden Sie sich an Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensor Info 1013: Sensorkonfiguration geändert </td> 
   <td colname="col2"> Keine Aktion erforderlich. Der Sensor hat eine Änderung in einer seiner Konfigurationsdateien erkannt und wird neu geladen. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensor Info 1014: Problem beim Zuweisen eines Zufallszahlengenerators </td> 
   <td colname="col2"> Wenden Sie sich an Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensor Info 1016: Konfigurationsdateiname geladen </td> 
   <td colname="col2"> Keine Aktion erforderlich. Der Sensor hat die aufgelistete Konfigurationsdatei erfolgreich geladen. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensor Info 1017: Name der geladenen Experimentdatei </td> 
   <td colname="col2"> Keine Aktion erforderlich. Der Sensor hat die aufgelistete Experimentdatei erfolgreich geladen. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensor-Fehler 3016: Konfigurationsdatei /mypath/myfile kann nicht geladen werden </td> 
   <td colname="col2"> Vergewissern Sie sich, dass die in der Webserverkonfiguration angegebene Konfigurationsdatei Sensor vorhanden ist und über die erforderlichen Berechtigungen zum Lesen durch den Webserverprozess verfügt. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Sensor 3017: Die kontrollierte Experimentkonfigurationsdatei /mypath/myfile kann nicht geladen werden </p> </td> 
   <td colname="col2"> <p>Vergewissern Sie sich, dass die in txlogd.conf angegebene kontrollierte Experimentdatei vorhanden ist und dass der txlogd-Prozess über die erforderlichen Berechtigungen zum Lesen der Datei verfügt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensor-Fehler 3018: Inhaltsfilterlisten können nicht analysiert werden. Überprüfen der txlogd-Konfigurationsdatei </td> 
   <td colname="col2"> Überprüfen Sie die Syntax der Einträge ContentFilterInclude und ContentFilterExclude in txlogd.conf. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensor-Fehler 3023: Fehler beim Erstellen der Sperre (g_lockThrottle) </td> 
   <td colname="col2"> Wenden Sie sich an Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensor-Fehler 3024: Fehler beim Erstellen der Sperre (g_lockConfigCheck) </td> 
   <td colname="col2"> Wenden Sie sich an Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensor-Fehler 4014: Die Festplattenwarteschlange konnte nicht geöffnet werden. </td> 
   <td colname="col2"> Überprüfen Sie den Dateinamen der QueueFile-Datei in txlogd.conf. Wenn angenommen wird, dass er korrekt ist, wenden Sie sich an Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensor-Fehler 4020: Keine Warteschlangendatei </td> 
   <td colname="col2"> Überprüfen Sie den Dateinamen der QueueFile-Datei in txlogd.conf. Wenn angenommen wird, dass er korrekt ist, wenden Sie sich an Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensor-Fehler 4021: Warteschlange ist voll </td> 
   <td colname="col2"> Wenden Sie sich an Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensor-Fehler 4022: Arbeitsspeicherblock der Länge &lt;x&gt; kann nicht mit Versatz &lt;y&gt; zugeordnet werden </td> 
   <td colname="col2"> Wenden Sie sich an Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensor-Fehler 5012: Es konnte kein Mutex erstellt werden. </td> 
   <td colname="col2"> Wenden Sie sich an Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensor-Fehler 5013: Ich konnte keinen Mutex erwerben. </td> 
   <td colname="col2"> Wenden Sie sich an Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensor-Fehler 5030: Fehler bei Spawn Gabelung. </td> 
   <td colname="col2"> Wenden Sie sich an Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensor-Fehler 5031: setsid fehlgeschlagen. </td> 
   <td colname="col2"> Wenden Sie sich an Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensor-Fehler 5032: Fehler bei Spawn Gabelung. </td> 
   <td colname="col2"> Wenden Sie sich an Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensor-Fehler 5033: chdir ist fehlgeschlagen. </td> 
   <td colname="col2"> Wenden Sie sich an Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensor-Fehler 5034: Signal empfangen </td> 
   <td colname="col2"> Das Programm wurde wahrscheinlich durch ein externes Signal beendet. Wenn die Signalquelle nicht ermittelt werden kann, wenden Sie sich an Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensor-Fehler 5035: Ausstieg von außerhalb Haupt aufgerufen </td> 
   <td colname="col2"> Wenden Sie sich an Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensor-Fehler 5036: txlogd wird bereits ausgeführt </td> 
   <td colname="col2"> Eine weitere Instanz des txlogd-Daemons wird bereits ausgeführt. Beenden Sie die andere Instanz zuerst, wenn Sie eine neue ausführen möchten. </td> 
  </tr> 
 </tbody> 
</table>

**Apache/IBM HTTP Server**

| Ereignisnachricht | Vorgeschlagene Aktion |
|---|---|
| Sensor-Fehler 3015: Die VisualSciencesConfig -Direktive fehlt in httpd.conf. | Dies ist ein Konfigurationsfehler. Die VisualSciencesConfig-Direktive muss sich in httpd.conf befinden und einen Parameter enthalten, der den Speicherort von txlogd.conf angibt. |
| Sensor-Fehler 3019: vys-cookie wurde nicht vor vys-log aufgerufen. Wenden Sie sich an den Support. | Wenden Sie sich an Adobe ClientCare. |
| Sensor-Fehler 3025: Unteranfrage verweist auf sich selbst zurück | Wenden Sie sich an Adobe ClientCare. |

**AOL-Server**

| Ereignisnachricht | Vorgeschlagene Aktion |
|---|---|
| Sensor-Fehler 3015: ns/server/[server]/module/[module] -Abschnitt fehlt in der AOLServer-Konfigurationsdatei. | Dies ist ein Konfigurationsfehler. Richtig, wie im Fehler angegeben. |
| Sensor-Fehler 3019: vys-cookie wurde nicht vor vys-log aufgerufen. Wenden Sie sich an den Support. Wenden Sie sich an Adobe ClientCare. | Wenden Sie sich an den Support. Wenden Sie sich an Adobe ClientCare. |
| Sensor-Fehler 3020: VisualSciencesConfig fehlt als erster Eintrag im Abschnitt [Abschnitt] in der AOLServer-Konfigurationsdatei. | Dies ist ein Konfigurationsfehler. Richtig, wie im Fehler angegeben. |
| Sensor-Fehler 3021: In VisualSciencesConfig fehlt ein Wert im Abschnitt [Abschnitt] in der AOLServer-Konfigurationsdatei. | Dies ist ein Konfigurationsfehler. Richtig, wie im Fehler angegeben. |

**iPlanet- und Java-System-Webserver**

| Ereignisnachricht | Vorgeschlagene Aktion |
|---|---|
| Sensor-Fehler 3011: Init-Richtlinie erforderlich. Beispiel: Init fn=vys-init config-file=&quot;/mypath/myfile&quot; | Dies ist ein Konfigurationsfehler. Die iPlanet-Init-Richtlinie fehlt. |
| Sensor-Fehler 3015: config-file ist nicht in der iPlanet Init-Direktive angegeben. | Dies ist ein Konfigurationsfehler. Der Pfad zur Konfigurationsdatei wurde nicht in der iPlanet Init-Richtlinie angegeben. |
| Sensor-Fehler 3019: vys-cookie wurde nicht vor vys-log aufgerufen. Überprüfen Sie die Konfigurationsdatei. | vys-cookie muss für jeden virtuellen Software-Server als VornameTrans-Direktive angegeben werden. |
