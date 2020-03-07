---
description: Installieren und konfigurieren Sie Sensor für Microsoft IIS 7.x oder 8.x, das unter Microsoft Windows Server 2008 oder höher ausgeführt wird.
title: Microsoft IIS unter Windows Server 2008 oder höher
uuid: 7fd8da68-1553-4395-b13e-b08a6ee1948e
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Microsoft IIS unter Windows Server 2008 oder höher{#microsoft-iis-on-windows-server-or-later}

Installieren und konfigurieren Sie Sensor für Microsoft IIS 7.x oder 8.x, das unter Microsoft Windows Server 2008 oder höher ausgeführt wird.

Die Programmdateien für Sensor werden in einer Installationsdatei verpackt, die Sie von der Adobe-Downloadseite erhalten. Wenn Sie noch nicht über die Sensor-Installationsdatei für Ihren jeweiligen Webserver verfügen, laden Sie diese herunter (oder rufen Sie sie von Ihrem Adobe-Kundenbetreuer ab), bevor Sie die folgenden Schritte durchführen.

Um Sensor zu installieren und zu konfigurieren, müssen Sie die folgenden Schritte auf hoher Ebene ausführen:

1. [Programmdateien installieren](../../../home/c-snsr-ovrvw/c-inst-snsr/c-install-iis-win8.md#section-cb51e5932a6d40c5b00758a7a51b7578)
1. [Bearbeiten der Konfigurationsdatei für den Sensor](../../../home/c-snsr-ovrvw/c-inst-snsr/c-install-iis-win8.md#section-1e1590a92222430e92066292512ae0df)
1. [Starten Sie den Transmitter und erstellen Sie die Datenträgerwarteschlange](../../../home/c-snsr-ovrvw/c-inst-snsr/c-install-iis-win8.md#section-2b8dfd06996d4ab49998eeb99bd9f5f0)
1. [Hinzufügen des Sammlers zum Webserver](../../../home/c-snsr-ovrvw/c-inst-snsr/c-install-iis-win8.md#section-088960c986cf449cb712152298b3518d)
1. [Zusätzliche Daten erfassen](../../../home/c-snsr-ovrvw/c-inst-snsr/c-install-iis-win8.md#section-98db9625efdc4b60bfd76f7adf4af74d)

## Programmdateien installieren {#section-cb51e5932a6d40c5b00758a7a51b7578}

Beim Ausführen von Sensor unter Windows IIS müssen sich die Programmdateien und die Datei mit der Datenträgerwarteschlange im selben Ordner befinden.

Bevor Sie die Programmdateien installieren, legen Sie zunächst fest, wo Sie die Datenträgerwarteschlange halten möchten, da Sie dort die Programmdateien installieren müssen.

Verwenden Sie das folgende Verfahren, um die Programmdateien für Sensor zu extrahieren und zu installieren.

1. Erstellen Sie auf Ihrem Windows-Computer einen Ordner, in dem die Dateien des Sensor-Programms installiert werden sollen. Denken Sie daran, dass sich Ihre Disk-Warteschlange auch in diesem Verzeichnis befindet. Stellen Sie daher sicher, dass das gewählte Gerät über ausreichend Platz verfügt, um eine Warteschlange von der benötigten Größe zu halten.

   Beispiel: C:\VisualSensor

1. Extrahieren Sie den Inhalt der Installationsdatei in den soeben erstellten Ordner. Während dieses Schritts installiert Sensor die folgenden Dateien:

<table id="table_C9E8803E51D046FD8FCCA38F8DAC04D1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Datei </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> EventMessages.dll </td> 
   <td colname="col2"> Ereignis-Viewer-Nachrichten. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> qlog.dll </td> 
   <td colname="col2"> Das Sammlermodul (ISAPI-Filter). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> TestExperiment.xls </td> 
   <td colname="col2"> <p>Eine Excel-Tabellenkalkulationsdatei, die Architekten zum Konfigurieren eines kontrollierten Experiments verwenden können. </p> <p>Sensor verwendet diese Datei nicht. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trust_ca_cert.pem </td> 
   <td colname="col2"> Das Zertifikat, das zum Überprüfen des digitalen Zertifikats verwendet wird, das Insight Server während des Verbindungsprozesses anzeigt. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> TXLog.exe </td> 
   <td colname="col2"> Das Transmitterprogramm. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> txlogd.conf </td> 
   <td colname="col2"> Die Konfigurationsdatei für den Sensor. </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Das Installationspaket enthält eine Tabellendatei mit dem Namen TestExperiment.xls. Diese Tabelle ist ein Tool, mit dem Architekten ein kontrolliertes Experiment konfigurieren können. Sensor selbst verwendet diese Datei nicht, daher ist es nicht notwendig, die Datei auf dem Computer zu installieren, auf dem Sensor läuft (obwohl Sie dies auch tun können). Sie sollten stattdessen die Datei an einen Speicherort kopieren, an dem Ihre Architekten darauf zugreifen oder die Datei nach Bedarf einfach aus dem Installationspaket extrahieren können. Weitere Informationen zum kontrollierten Experimentieren finden Sie im Insight Controlled Experiments Guide.

## Bearbeiten der Konfigurationsdatei für den Sensor {#section-1e1590a92222430e92066292512ae0df}

Die Datei &quot;txlogd.conf&quot;enthält die Konfigurationsparameter für Sensor.

Sie müssen die Datei bearbeiten, um unter anderem die Größe der Disk-Warteschlange, die Adresse des Insight-Servers und die ID anzugeben, die an die von diesem Sensor erzeugten Daten angehängt wird. Die Konfigurationsdatei enthält die erforderlichen Parameter und optionalen Parameter.

* **Erforderliche Parameter** sind Einstellungen, die Sie bei der Installation von Sensor angeben müssen. Ohne diese Einstellungen wird Sensor nicht erfolgreich ausgeführt.
* **Optionale Parameter** sind Einstellungen, die standardmäßig auf vordefinierte Werte (die Sie ändern können) oder optionale Funktionen angewendet werden.

**So bearbeiten Sie die Konfigurationsdatei des Sensors**

1. Öffnen Sie die `<SensorDirectory>/txlogd.conf` Datei in einem Texteditor und legen Sie die erforderlichen Parameter sowie die gewünschten optionalen Parameter fest.

   Beschreibungen der [!DNL txlogd.conf] Parameter finden Sie unter [Sensor Txlogd.conf-Dateiparameter](../../../home/c-snsr-ovrvw/sensor-txlogd-params/sensor-txlogd-params.md#concept-4bb629f058894b4abc65a31eb02eebed).

1. Speichern und schließen Sie die Datei.

## Starten Sie den Transmitter und erstellen Sie die Datenträgerwarteschlange {#section-2b8dfd06996d4ab49998eeb99bd9f5f0}

Nachdem Sie die [!DNL txlogd.conf]Datei konfiguriert haben, können Sie das Transmitter-Programm starten, sie als Windows-Dienst registrieren und die Disk-Warteschlange erstellen.

1. Wählen Sie unter Windows im Startmenü Zubehör > Eingabeaufforderung.
1. Navigieren Sie im Fenster mit der Eingabeaufforderung zum Ordner, in dem Sie Sensor installiert haben, und führen Sie den folgenden Befehl aus:

   ```
   txlog /regserver
   ```

   Dieser Befehl startet den Transmitter, erstellt die Disk-Warteschlange und registriert Sensor als Windows-Dienst.

1. Um sicherzustellen, dass der Transmitter ordnungsgemäß ausgeführt wird, klicken Sie auf Start > Systemsteuerung > Verwaltung > Dienste.

   >[!NOTE]
   >
   >Diese Befehlssequenz kann je nach verwendeter Windows-Version unterschiedlich sein.

   1. Suchen Sie in der Dienstliste den Eintrag für Sensor und vergewissern Sie sich, dass der Status Started und der Starttyp Automatisch ist.
   1. Schließen Sie das Bedienfeld &quot;Dienste&quot;.

1. Um zu überprüfen, ob Transmitter während des Starts Fehler auftraten, klicken Sie auf Start > Systemsteuerung > Verwaltung > Ereignisanzeige, um die Ereignisanzeige zu öffnen.

   >[!NOTE]
   >
   >Diese Befehlssequenz kann je nach verwendeter Windows-Version unterschiedlich sein.

   1. Wählen Sie im linken Bereich des Fensters &quot;Ereignisanzeige&quot;das Anwendungsprotokoll aus.
   1. Suchen Sie im rechten Bereich nach Ereignissen mit &quot;Adobe&quot;in der Spalte &quot;Quelle&quot;.
   1. Wenn Sie eine Fehlermeldung von &quot;Adobe&quot;erhalten, doppelklicken Sie auf den Fehler, um das Fenster &quot;Ereigniseigenschaften&quot;anzuzeigen. Dieses Fenster enthält detaillierte Informationen zum Fehler.

1. Schließen Sie nach Abschluss der Überprüfung des Anwendungsprotokolls die Ereignisanzeige.
1. Überprüfen Sie, ob der Transmitter die Disk-Warteschlange (Diskq2008.log) in dem Ordner erstellt hat, in dem Sie die Sensor-Programmdateien installiert haben, und ob es die Größe ist, die Sie im Parameter QueueSize in der Datei txlogd.conf angegeben haben.

   Wenn die Warteschlange nicht korrekt erstellt wurde:

   1. Überprüfen Sie die Datei &quot;txtlogd.conf&quot;und stellen Sie sicher, dass der Parameter QueueSize korrekt eingestellt ist.
   1. Vergewissern Sie sich, dass auf dem Gerät, auf dem Sie Sensor installiert haben, ausreichend Speicherplatz für eine Datei der im Parameter QueueSize angegebenen Größe zur Verfügung steht.
   1. Beenden Sie den Transmitter über das Bedienfeld &quot;Dienste&quot;in Windows.
   1. Löschen Sie die Warteschlangendatei.
   1. Sensor erneut als Windows-Dienst registrieren: Wählen Sie unter Windows im Startmenü Zubehör > Eingabeaufforderung. Navigieren Sie im Fenster mit der Eingabeaufforderung zum Ordner, in dem Sie Sensor installiert haben, und führen Sie den folgenden Befehl aus:

      ```
      txlog /regserver
      ```

Der Transmitter ist für einen kontinuierlichen Betrieb ausgelegt. Wenn Sie den Computer neu starten, wird der Transmitter automatisch neu gestartet. Wenn Sie den Transmitter manuell starten und anhalten müssen, können Sie dies über das Bedienfeld &quot;Dienste&quot;in Windows tun.

## Hinzufügen des Sammlers zum Webserver {#section-088960c986cf449cb712152298b3518d}

Bei IIS ist der Collector ein ISAPI-Filter, den Sie Ihrem Webserver in IIS hinzufügen.

1. Öffnen Sie den IIS Manager mit **Start > Verwaltung > Internetinformationsdienste (IIS)-Manager**.
1. Erweitern Sie die Knoten **Lokaler Computer** und **Sites** .
1. Wählen Sie die Website aus und doppelklicken Sie im rechten Bereich auf **ISAPI-Filter**.
1. Klicken Sie im Bereich **Aktionen** auf **Hinzufügen**.

1. Geben Sie im Feld **Filtername** einen Anzeigenamen für den Filter ein. Der vorgeschlagene Filtername ist &quot;Sensor&quot;.
1. Klicken Sie auf **Durchsuchen**, wählen Sie die Datei &quot;qlog.dll&quot;(in dem Ordner, in dem Sie Sensor installiert haben) und klicken Sie auf **OK**.

1. Klicken Sie auf **OK** , um den Filter hinzuzufügen.

   Nachdem Sie den Filter hinzugefügt haben, ist der Kollektor sofort einsatzbereit und kann Daten erfassen.

Wenn der grüne Pfeil nach dem Traffic zum Kollektor nicht angezeigt wird, führen Sie die folgenden Schritte aus:

1. Klicken Sie auf Start > Verwaltung > Ereignis-Viewer, um die Ereignisanzeige auf Fehler zu überprüfen.

   >[!NOTE]
   >
   >Diese Befehlssequenz kann je nach verwendeter Windows-Version unterschiedlich sein.

1. Wählen Sie im linken Bereich des Fensters &quot;Ereignisanzeige&quot;das **Anwendungsprotokoll** aus.
1. Suchen Sie im rechten Bereich nach Ereignissen mit &quot;Adobe&quot;in der Spalte **Quelle** .
1. Wenn ein Fehler auftritt, doppelklicken Sie auf den Fehler, um das Fenster **Ereigniseigenschaften** anzuzeigen.

## Zusätzliche Daten erfassen {#section-98db9625efdc4b60bfd76f7adf4af74d}

Webseiten werden häufig mithilfe der Programmiersprache ASP (Active Server Pages) strukturiert.

ASP ist eine Microsoft-Technologie, die innerhalb von IIS ausgeführt wird. Wenn ein Browser eine ASP-Datei anfordert, übergibt IIS die Anforderung an die ASP-Engine. Die ASP-Engine liest die ASP-Datei zeilenweise und führt die Skripten in der Datei aus. Schließlich wird die ASP-Datei als einfaches HTML an den Browser zurückgegeben. ASP stellt RESPOND- oder REQUEST-Objekte bereit, die neben anderen Verwendungen auch die Beantwortung oder Anforderung von Benutzerabfragen oder von HTML-Formularen gesendeten Daten ermöglichen.

In bestimmten Fällen möchten Sie die in Formularen eingegebenen Werte möglicherweise nicht an die URL anhängen, die in der Adressleiste des Browsers des Benutzers angezeigt wird oder die im HTML-Code selbst sichtbar ist. Mit einfachem serverseitigen ASP-Skript können Sie Formularfeldnamen und deren entsprechende Werte an die Protokolldatei anhängen, ohne sie im Browser des Benutzers verfügbar zu machen oder in die HTML-Datei einzubetten. Um die tatsächlichen Formularwerte zu erfassen, die in bestimmte Formulare auf Ihrer Website eingegeben wurden, müssen einige Codezeilen hinzugefügt werden, um die Formularwerte an die Protokollanforderung anzuhängen.

Fügen Sie auf der Verarbeitungsseite eines Formulars den folgenden Code hinzu, um die eingegebenen Formularwerte an die Anforderungsdaten anzuhängen (zusätzlich zum Schreiben der gesendeten Formularwerte in eine externe Datenbank oder an einen anderen Speicherort):

```
var sName= Request.Form("Name"); 
var sCity= Request.Form("City"); 
var sState= Request.Form("State"); 
var sZip= Request.Form("Zip"); 
 
Response.AppendToLog("&v_1=" +  sName); 
Response.AppendToLog("&v_2=" +  sCity); 
Response.AppendToLog("&v_3=" +  sState); 
Response.AppendToLog("&v_4=" +  sZip);
```

Bei diesem Prozess werden die Formularwerte entsprechend der Definition an die Anforderungsdaten für die Formularverarbeitungsseite angehängt. Innerhalb der Protokolldaten stehen die angehängten Werte als Abfragezeichenfolgen der Formularverarbeitungsseite zur Verfügung, wie unten dargestellt. Beispielsweise wären v_1, v_2, v_3 und v_4 nun Abfragezeichenfolgen, die die in die entsprechenden Formularfelder eingegebenen Daten enthalten. Die im vorherigen Beispiel beschriebene Syntax kann für alle zusätzlichen Formularfelder und Werte, die erfasst werden sollen, dupliziert werden:

```
http://www.myserver.com/path/to/formprocessingpage.asp?v_1=John+Smith&v_2=Los+Angeles&v_3=California&v_4=90210
```

Wenn jedes Formularfeld und jeder Wert erfasst und für die Analyse verfügbar sein sollen, können Sie die folgende Syntax verwenden:

```
var formvalues = Response.Form; 
Response.AppendToLog(formvalues);
```

In diesem Beispiel werden alle im HTML vorhandenen Formularfelder zusammen mit ihren jeweiligen Werten als Abfragezeichenfolgen an den Protokolleintrag der Seite &quot;Formularverarbeitung&quot;angehängt. Bitte beachten Sie, dass dies alle ausgeblendeten Felder im Formular einschließen würde.

Die Protokolldaten werden wie in der folgenden Tabelle beschrieben erweitert:

| Erfasste Daten | Erklärung | Beispiel |
|---|---|---|
| v_1 | Mit der Abfragezeichenfolge NAME verknüpfter Wert | v_1=John Smith |
| v_2 | Mit der CITY-Abfragezeichenfolge verknüpfter Wert | v_2=Los Angeles |
| v_3 | Mit der STATE-Abfragezeichenfolge verknüpfter Wert | v_3=Kalifornien |
| v_4 | Mit der ZIP-Abfragezeichenfolge verknüpfter Wert | v_4=90210 |

<!-- <a id="section_55C623AC973246DC9EBECD48DA1EE0F7"></a> -->

