---
description: Installieren und konfigurieren Sie Sensor für Microsoft IIS 7.x oder 8.x, der unter Microsoft Windows Server 2008 oder höher ausgeführt wird.
title: Microsoft IIS unter Windows Server 2008 oder höher
uuid: 7fd8da68-1553-4395-b13e-b08a6ee1948e
exl-id: cc909daa-60c0-4188-8e90-035c41bf3105
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1589'
ht-degree: 1%

---

# Microsoft IIS unter Windows Server 2008 oder höher{#microsoft-iis-on-windows-server-or-later}

{{eol}}

Installieren und konfigurieren Sie Sensor für Microsoft IIS 7.x oder 8.x, der unter Microsoft Windows Server 2008 oder höher ausgeführt wird.

Die Programmdateien für Sensor werden in einer Installationsdatei zusammengefasst, die Sie von der Adobe-Download-Site erhalten. Wenn Sie noch nicht über die Installationsdatei für den Sensor für Ihren Webserver verfügen, laden Sie sie herunter (oder rufen Sie sie von Ihrem Kundenbetreuer ab), bevor Sie mit den folgenden Verfahren beginnen.

Um Sensor zu installieren und zu konfigurieren, müssen Sie die folgenden allgemeinen Schritte ausführen:

1. [Programmdateien installieren](../../../home/c-snsr-ovrvw/c-inst-snsr/c-install-iis-win8.md#section-cb51e5932a6d40c5b00758a7a51b7578)
1. [Bearbeiten Sie die Konfigurationsdatei für den Sensor](../../../home/c-snsr-ovrvw/c-inst-snsr/c-install-iis-win8.md#section-1e1590a92222430e92066292512ae0df)
1. [Starten Sie den Transmitter und erstellen Sie die Festplattenwarteschlange.](../../../home/c-snsr-ovrvw/c-inst-snsr/c-install-iis-win8.md#section-2b8dfd06996d4ab49998eeb99bd9f5f0)
1. [Hinzufügen des Sammlers zum Webserver](../../../home/c-snsr-ovrvw/c-inst-snsr/c-install-iis-win8.md#section-088960c986cf449cb712152298b3518d)
1. [Zusätzliche Daten erfassen](../../../home/c-snsr-ovrvw/c-inst-snsr/c-install-iis-win8.md#section-98db9625efdc4b60bfd76f7adf4af74d)

## Programmdateien installieren {#section-cb51e5932a6d40c5b00758a7a51b7578}

Beim Ausführen von Sensor unter Windows IIS müssen sich die Programmdateien und die Datei mit der Festplattenwarteschlange im selben Ordner befinden.

Bestimmen Sie vor der Installation der Programmdateien zunächst, wo Sie die Festplattenwarteschlange warten möchten, da Sie dort die Programmdateien installieren müssen.

Gehen Sie wie folgt vor, um die Programmdateien für Sensor zu extrahieren und zu installieren.

1. Erstellen Sie auf Ihrem Windows-Computer einen Ordner, in dem Sie die Programmdateien des Sensor installieren können. Beachten Sie, dass sich Ihre Datenträgerwarteschlange auch in diesem Verzeichnis befindet. Stellen Sie daher sicher, dass das gewählte Gerät über ausreichend Speicherplatz verfügt, um eine Warteschlange mit der benötigten Größe zu speichern.

   Beispiel: C:\VisualSensor

1. Extrahieren Sie den Inhalt der Installationsdatei in das soeben erstellte Verzeichnis. Während dieses Schritts installiert Sensor die folgenden Dateien:

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
   <td colname="col2"> Das Sammlermodul (ein ISAPI-Filter). </td>
  </tr>
  <tr>
   <td colname="col1"> TestExperiment.xls </td>
   <td colname="col2"> <p>Eine Excel-Tabellenkalkulationsdatei, mit der Architekten ein gesteuertes Experiment konfigurieren können. </p> <p>Sensor verwendet diese Datei nicht. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> trust_ca_cert.pem </td>
   <td colname="col2"> Das Zertifikat, das zum Überprüfen des digitalen Zertifikats verwendet wird, das Insight Server während des Verbindungsprozesses präsentiert. </td>
  </tr>
  <tr>
   <td colname="col1"> TXLog.exe </td>
   <td colname="col2"> Das Transmitter-Programm. </td>
  </tr>
  <tr>
   <td colname="col1"> txlogd.conf </td>
   <td colname="col2"> Die Konfigurationsdatei für Sensor. </td>
  </tr>
 </tbody>
</table>

>[!NOTE]
>
>Das Installationspaket enthält eine Tabellendatei mit dem Namen TestExperiment.xls. Diese Tabelle ist ein Tool, mit dem Architekten ein gesteuertes Experiment konfigurieren. Sensor selbst verwendet diese Datei nicht, daher ist es nicht notwendig, die Datei auf dem Computer zu installieren, auf dem Sensor ausgeführt wird (obwohl Sie dies tun können). Sie können die Datei stattdessen an einen Speicherort kopieren, an dem Ihre Architekten darauf zugreifen können, oder einfach die Datei aus dem Installationspaket extrahieren. Weitere Informationen zu kontrollierten Experimenten finden Sie im Leitfaden zu kontrollierten Experimenten mit Insight.

## Bearbeiten Sie die Konfigurationsdatei für den Sensor {#section-1e1590a92222430e92066292512ae0df}

Die Datei txlogd.conf enthält die Konfigurationsparameter für Sensor.

Sie müssen die Datei bearbeiten, um unter anderem die Größe der Festplattenwarteschlange, die Adresse des Insight Servers und die Kennung anzugeben, die an die von diesem Sensor erzeugten Daten angehängt werden soll. Die Konfigurationsdatei enthält die erforderlichen Parameter und optionalen Parameter.

* **Erforderliche Parameter** sind Einstellungen, die Sie bei der Installation von Sensor angeben müssen. Ohne diese Einstellungen wird Sensor nicht erfolgreich ausgeführt.
* **Optionale Parameter** sind Einstellungen, die standardmäßig vordefinierte Werte enthalten (die Sie ändern können) oder optionale Funktionen aktivieren.

**Bearbeiten der Sensorkonfigurationsdatei**

1. Öffnen Sie die `<SensorDirectory>/txlogd.conf` in einem Texteditor speichern und die erforderlichen Parameter sowie die gewünschten optionalen Parameter festlegen.

   Beschreibungen der [!DNL txlogd.conf] Parameter, siehe [Parameter der Datei &quot;Sensor Txlogd.conf&quot;](../../../home/c-snsr-ovrvw/sensor-txlogd-params/sensor-txlogd-params.md#concept-4bb629f058894b4abc65a31eb02eebed).

1. Speichern und schließen Sie die Datei.

## Starten Sie den Transmitter und erstellen Sie die Festplattenwarteschlange. {#section-2b8dfd06996d4ab49998eeb99bd9f5f0}

Nachdem Sie die [!DNL txlogd.conf]-Datei, können Sie das Transmitter-Programm starten, es als Windows-Dienst registrieren und die Festplattenwarteschlange erstellen.

1. Wählen Sie unter Windows im Menü Start die Option Zubehör > Eingabeaufforderung aus.
1. Navigieren Sie im Eingabeaufforderungsfenster zum Ordner, in dem Sie Sensor installiert haben, und führen Sie den folgenden Befehl aus:

   ```
   txlog /regserver
   ```

   Dieser Befehl startet den Transmitter, erstellt die Festplattenwarteschlange und registriert Sensor als Windows-Dienst.

1. Um sicherzustellen, dass der Transmitter ordnungsgemäß ausgeführt wird, klicken Sie auf Start > Systemsteuerung > Verwaltung > Dienste.

   >[!NOTE]
   >
   >Diese Befehlssequenz variiert je nach verwendeter Windows-Version.

   1. Suchen Sie in der Dienstliste den Eintrag für Sensor und bestätigen Sie, dass sein Status Gestartet und sein Starttyp Automatisch lautet.
   1. Schließen Sie die Systemsteuerung &quot;Dienste&quot;.

1. Um zu überprüfen, ob Transmitter beim Start Fehler erhalten hat, klicken Sie auf Start > Systemsteuerung > Verwaltung > Ereignis-Viewer , um die Ereignisanzeige zu öffnen.

   >[!NOTE]
   >
   >Diese Befehlssequenz variiert je nach verwendeter Windows-Version.

   1. Wählen Sie im linken Bereich des Fensters Ereignis-Viewer das Protokoll Anwendungen aus.
   1. Suchen Sie im rechten Bereich nach Ereignissen mit &quot;Adobe&quot;in der Quellspalte.
   1. Doppelklicken Sie auf die Fehlermeldung &quot;Adobe&quot;, um das Fenster Ereigniseigenschaften anzuzeigen. In diesem Fenster erhalten Sie detaillierte Informationen zum Fehler.

1. Wenn Sie die Prüfung des Anwendungsprotokolls abgeschlossen haben, schließen Sie die Ereignisanzeige.
1. Stellen Sie sicher, dass der Transmitter die Festplattenwarteschlange (Diskq2008.log) in dem Ordner erstellt hat, in dem Sie die Dateien des Sensor-Programms installiert haben, und dass es sich um die Größe handelt, die Sie im Parameter QueueSize in der Datei txlogd.conf angegeben haben.

   Wenn die Warteschlange nicht korrekt erstellt wurde:

   1. Überprüfen Sie die Datei txtlogd.conf und überprüfen Sie, ob der Parameter QueueSize richtig eingestellt ist.
   1. Vergewissern Sie sich, dass auf dem Gerät, auf dem Sie Sensor installiert haben, ausreichend Speicherplatz für eine Datei zur Verfügung steht, die der im Parameter QueueSize angegebenen Größe entspricht.
   1. Beenden Sie den Transmitter über das Bedienfeld Dienste in Windows.
   1. Löschen Sie die Warteschlangendatei.
   1. Registrieren Sie Sensor als Windows-Dienst erneut: Wählen Sie unter Windows im Menü Start die Option Zubehör > Eingabeaufforderung aus. Navigieren Sie im Eingabeaufforderungsfenster zum Ordner, in dem Sie Sensor installiert haben, und führen Sie den folgenden Befehl aus:

      ```
      txlog /regserver
      ```

Der Transmitter ist für eine kontinuierliche Ausführung ausgelegt. Wenn Sie den Computer neu starten, wird der Transmitter automatisch neu gestartet. Wenn Sie den Transmitter manuell starten und anhalten müssen, können Sie dies über die Systemsteuerung Dienste in Windows tun.

## Hinzufügen des Sammlers zum Webserver {#section-088960c986cf449cb712152298b3518d}

Bei IIS ist der Wächter ein ISAPI-Filter, den Sie Ihrem Webserver in IIS hinzufügen.

1. Öffnen Sie den IIS-Manager mit **Start > Verwaltung > Internet Information Services (IIS) Manager**.
1. Erweitern Sie die **Lokaler Computer** und **Sites** Knoten.
1. Wählen Sie die Website aus und doppelklicken Sie im rechten Bereich auf **ISAPI-Filter**.
1. Unter dem **Aktionen** Bereich, klicken Sie auf **Hinzufügen**.

1. Im **Filtername** ein, geben Sie einen Anzeigenamen für den Filter ein. Der vorgeschlagene Filtername lautet &quot;Sensor&quot;.
1. Klicken **Durchsuchen**, wählen Sie die Datei &quot;qlog.dll&quot;aus (die sich in dem Ordner befindet, in dem Sie Sensor installiert haben) und klicken Sie auf **OK**.

1. Klicken **OK** , um den Filter hinzuzufügen.

   Nach dem Hinzufügen des Filters ist der Kollektor sofort einsatzbereit und kann Daten erfassen.

Wenn der grüne Pfeil nach dem Traffic zum Kollektor nicht angezeigt wird, führen Sie die folgenden Schritte aus:

1. Klicken Sie auf Start > Verwaltung > Ereignis-Viewer , um die Ereignisanzeige auf Fehler zu überprüfen.

   >[!NOTE]
   >
   >Diese Befehlssequenz variiert je nach verwendeter Windows-Version.

1. Wählen Sie im linken Bereich des Fensters Ereignis-Viewer die Option **Anwendung** log.
1. Suchen Sie im rechten Bereich nach Ereignissen mit &quot;Adobe&quot;im **Quelle** Spalte.
1. Wenn Sie einen Fehler finden, doppelklicken Sie auf den Fehler, um die **Ereigniseigenschaften** Fenster.

## Zusätzliche Daten erfassen {#section-98db9625efdc4b60bfd76f7adf4af74d}

Webseiten werden häufig mithilfe der Programmiersprache ASP (Active Server Pages) strukturiert.

ASP ist eine Microsoft-Technologie, die innerhalb von IIS ausgeführt wird. Wenn ein Browser eine ASP-Datei anfordert, übergibt IIS die Anforderung an die ASP-Engine. Die ASP-Engine liest die ASP-Datei zeilenweise und führt die Skripte in der Datei aus. Schließlich wird die ASP-Datei als einfache HTML an den Browser zurückgegeben. ASP stellt RESPOND- oder REQUEST-Objekte bereit, die zusätzlich zu anderen Verwendungen die Antwort oder Anforderung von Benutzerabfragen oder Daten erlauben, die von HTML-Formularen gesendet werden.

In bestimmten Fällen möchten Sie die in Formularen eingegebenen Werte nicht an die URL anhängen, die in der Adressleiste des Browsers eines Benutzers angezeigt wird oder die im HTML-Code selbst sichtbar ist. Mit einfachem serverseitigem ASP-Skript können Sie Formularfeldnamen und die entsprechenden Werte an die Protokolldatei anhängen, ohne sie im Browser des Benutzers verfügbar zu machen oder in die HTML-Datei einzubetten. Um die tatsächlichen Formularwerte zu erfassen, die in bestimmte Formulare auf Ihrer Website eingegeben wurden, müssen einige Codezeilen hinzugefügt werden, um die Formularwerte an die Protokollanforderung anzuhängen.

Fügen Sie auf der Verarbeitungsseite eines Formulars den folgenden Code hinzu, um die eingegebenen Formularwerte an die Anfragedaten anzuhängen (zusätzlich zum Schreiben der gesendeten Formularwerte in eine externe Datenbank oder an einen anderen Speicherort):

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

Durch diesen Prozess werden die Formularwerte, wie sie definiert sind, an die Anforderungsdaten für die Formularverarbeitungsseite angehängt. Innerhalb der Protokolldaten sind die angehängten Werte als Abfragezeichenfolgen der Formularverarbeitungsseite verfügbar, wie unten dargestellt. Beispielsweise wären v_1, v_2, v_3 und v_4 jetzt Abfragezeichenfolgen, die die in die entsprechenden Formularfelder eingegebenen Daten enthalten. Die im vorherigen Beispiel beschriebene Syntax kann für alle zusätzlichen Formularfelder und Werte dupliziert werden, die erfasst werden sollen:

```
https://www.myserver.com/path/to/formprocessingpage.asp?v_1=John+Smith&v_2=Los+Angeles&v_3=California&v_4=90210
```

Wenn Sie möchten, dass jedes Formularfeld und jeder Wert erfasst und für die Analyse verfügbar ist, können Sie die folgende Syntax verwenden:

```
var formvalues = Response.Form;
Response.AppendToLog(formvalues);
```

In diesem Beispiel werden alle in der HTML vorhandenen Formularfelder zusammen mit den entsprechenden Werten als Abfragezeichenfolgen an den Protokolleintrag für die Formularverarbeitungsseite angehängt. Bitte beachten Sie, dass dies alle verborgenen Felder im Formular einschließen würde.

Die Protokolldaten werden wie in der folgenden Tabelle beschrieben erweitert:

| Erfasste Daten | Erklärung | Beispiel |
|---|---|---|
| v_1 | Wert, der mit der Abfragezeichenfolge NAME verknüpft ist | v_1=John Smith |
| v_2 | Der CITY-Abfragezeichenfolge zugeordnete Wert | v_2=Los Angeles |
| v_3 | Wert, der mit der STATE-Abfragezeichenfolge verknüpft ist | v_3=California |
| v_4 | Der ZIP-Abfragezeichenfolge zugeordnete Wert | v_4=90210 |

<!-- <a id="section_55C623AC973246DC9EBECD48DA1EE0F7"></a> -->
