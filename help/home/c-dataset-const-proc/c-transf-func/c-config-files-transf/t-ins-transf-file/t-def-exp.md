---
description: Exporter geben die Anweisungen zur Ausgabe der Ereignisdaten.
title: Definieren von Exportern
uuid: 565d4482-6c25-407c-bda7-0d116180902a
exl-id: 5de6266a-e959-414c-9512-5e9f4011881b
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1120'
ht-degree: 2%

---

# Definieren von Exportern{#defining-exporters}

{{eol}}

Exporter geben die Anweisungen zur Ausgabe der Ereignisdaten.

Die Umwandlungsfunktion bietet drei Exportarten für den Export [!DNL .vsl] Dateien, Protokolldateien, XML-Dateien und ODBC-Daten als [!DNL .vsl] -Dateien, Textdateien oder Textdateien mit Trennzeichen, die von DataWarehouse-Laderoutinen, Prüfagenturen oder anderen Zielen verwendet werden können.

>[!NOTE]
>
>Damit ein Ausführer ordnungsgemäß funktioniert, muss die Protokollquelle die entsprechenden Anforderungen erfüllen, die im Abschnitt [Protokollquellen](../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-6714c720fac044cbb9af003bf401b2ea) Abschnitt [Konfigurationsdatei für die Protokollverarbeitung](../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md).

**So definieren Sie einen Ausführer**

1. Öffnen [!DNL Transform.cfg] in Data Workbench. Siehe [Bearbeiten der Datei Insight Transform.cfg](../../../../../home/c-dataset-const-proc/c-transf-func/c-config-files-transf/t-ins-transf-file/t-ins-transf-file.md#task-857fc535ccdb4c39b763179efa4b0f13).
1. Rechtsklick **[!UICONTROL Exporters]** Klicken Sie auf **[!UICONTROL Add New]**.
1. Wählen Sie eine der folgenden Optionen aus:

   * **[!UICONTROL ExportTextFile]**
   * **[!UICONTROL ExportDelimitedTextFile]**
   * **[!UICONTROL ExportVSLFile]**

   >[!NOTE]
   >
   >Für [!DNL ExportVSLFile] Option, alle erweiterten Felder in der Eingabedatei und alle benutzerdefinierten Felder des Formulars cs(*header*) werden immer in die VSL Ausgabedatei geschrieben. Wenn Sie ein vorhandenes erweitertes Feld überschreiben, wird der neue Wert in die Ausgabedatei geschrieben, auch wenn das Feld leer ist.

1. Bearbeiten Sie die Exporter-Parameter in der Konfigurationsdatei mithilfe der folgenden Tabelle als Anleitung:

   <table id="table_35C380DB6E4F42448C149D5EC185213C"> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> Parameter </th> 
      <th colname="col2" class="entry"> Beschreibung </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> Datenformat </td> 
      <td colname="col2"> <p>Für <span class="wintitle"> ExportTextFile</span> nur. Das Format jeder Ausgabelinie, bestehend aus Feldnamen Escapes (in % ausgedrückt)<i>fieldname</i>%) und beliebigen anderen gewünschten festen Text. Das Format sollte ein Zeilentrennzeichen enthalten, in der Regel [CR] [LF]. </p> <p> Ein literales Prozentzeichen (%) kann in die Formatzeichenfolge eingebettet werden, indem das Zeichen wie im folgenden Beispiel maskiert wird: %% </p> <p> Ein Beispiel für einen Eintrag für den Parameter "Data Format"ist <span class="filepath"> %x-timestring% %x-trackingid%[CR][LF]</span>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> Felder </td> 
      <td colname="col2">Für <span class="wintitle"> ExportDelimitedTextFile</span> nur. Namen der auszugebenden Felder. </td> 
      </tr> 
      <tr> 
      <td colname="col1"> Trennzeichen </td> 
      <td colname="col2"> <p>Optional. Für <span class="wintitle"> ExportDelimitedTextFile</span> nur. Zeichen, das zum Trennen der Felder in der Ausgabedatei verwendet wird. </p> <p> Die Software kann Trennzeichen, die in den Datenwerten enthalten sind, nicht maskieren. Daher wird von Adobe die Verwendung von Kommas als Trennzeichen nicht empfohlen. </p> <p> Wenn Sie die Strg-Taste gedrückt halten und mit der rechten Maustaste im Trennzeichen-Parameter klicken, wird ein <span class="wintitle"> Einfügen</span> angezeigt. Dieses Menü enthält eine Liste von Sonderzeichen, die häufig als Trennzeichen verwendet werden. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> Trennlinie </td> 
      <td colname="col2">Optional. Für <span class="wintitle"> ExportDelimitedTextFile</span> nur. Die Zeichen, die zur Trennung von Zeilen in den Ausgabedateien verwendet werden. Der Standardwert ist [CR] [LF]. </td> 
      </tr> 
      <tr> 
      <td colname="col1"> Name </td> 
      <td colname="col2"> <p>Optional. Kennung für den Ausführer. Dieser Name wird im <span class="wintitle"> Detaillierter Status</span> -Schnittstelle. </p> <p> Informationen zum <span class="wintitle"> Detaillierter Status</span> -Benutzeroberfläche, siehe <i>Data Workbench-Benutzerhandbuch</i>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> Kommentare </td> 
      <td colname="col2"> Optional. Hinweise zum Ausführer. </td> 
      </tr> 
      <tr> 
      <td colname="col1"> Ausgabepfad </td> 
      <td colname="col2"> <p>Pfad, in dem Ausgabedateien gespeichert werden sollen. Der Pfad ist relativ zum Installationsordner des Data Workbench-Servers. </p> <p> <p>Hinweis: Der Data Workbench-Server, der Ausgabedaten speichert, verarbeitet den Server #0 im <span class="filepath"> profile.cfg</span> -Datei. </p> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> Dateirotierungsperiode </td> 
      <td colname="col2"> <p>Optional. Die Häufigkeit, mit der Daten in die Ausgabedatei exportiert werden. Jede Ausgabedatei enthält Daten zu einem bestimmten Zeitraum, der als Rotationszeitraum bezeichnet wird. Alle Zeitberechnungen sind in GMT: Ein Tag beginnt um Mitternacht GMT und endet am folgenden Tag um Mitternacht GMT, selbst wenn die in die Datei geschriebenen Daten ein Feld enthalten, das in Ortszeit umgewandelt wurde. </p> <p> Folgende Werte sind verfügbar: </p> 
      <ul id="ul_64F56D093E2E4D07ACB7D7921F4E6FA1"> 
       <li id="li_E4985C7F56E443049AFF57B0270032D6"> JAHR. Jede Datei enthält Daten für ein Kalenderjahr. </li> 
       <li id="li_42E59BB7A5704C85A6079ED9715C44BC"> MONAT. Jede Datei enthält Daten für einen Kalendermonat. Die Monate sind 1 (Januar) bis 12 (Dezember). </li> 
       <li id="li_91831283616C48DA8C8086776D181751"> WOCHE. Jede Datei enthält Daten für eine Woche. Eine Woche beginnt am Montag. Die Woche, die an einem der ersten sieben Tage des Jahres beginnt, ist Woche 1 und die vorherige (teilweise) Woche, falls vorhanden, Woche 0. </li> 
       <li id="li_BDB7B4D779434B98935261B8B5C0AABB"> TAG. Jede Datei enthält Daten für einen Kalendertag. </li> 
       <li id="li_018F4133E03C42F29073FED1DB082ED5"> STUNDE. Jede Datei enthält Daten für eine Stunde. </li> 
       <li id="li_EE8CF71BA12149F49D4B7F7108262CD0"> KEINE. Es wird keine Drehung durchgeführt. Alle Daten werden in dieselbe Datei geschrieben (oder in einen Dateisatz, der durch andere Parametereinstellungen bestimmt wird). Siehe <span class="wintitle"> Dateinamenformat</span> -Parameter in dieser Tabelle. </li> 
      </ul> <p>Der standardmäßige Zeitraum für die Dateirotation ist DAY. </p> 
      <ul id="ul_0F3BC98275634F759E5022FF2C19715E"> 
       <li id="li_24DC4D144DA94ED0B7B50E8BB39DB8E3"> Setzen Sie die Dateirotation nur dann auf "NONE", wenn Sie in <span class="wintitle"> Offline-Modus</span>. Siehe <a href="../../../../../home/c-dataset-const-proc/c-transf-func/c-config-files-transf/t-ins-transf-file/t-ins-transf-file.md#task-857fc535ccdb4c39b763179efa4b0f13"> Offline-Modus</a> Parameterbeschreibung. </li> 
      </ul> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> Dateinamenformat </td> 
      <td colname="col2"> <p>Optional. Das Format des Namens der Ausgabedatei. </p> <p> Jeder Protokolleintrag kann in einer Datei gespeichert werden, deren Name von der Startzeit des Drehzeitraums und optional von den Werten der Felder in den darin enthaltenen Zeilen abgeleitet wird. Die im Dateinamen zu verwendenden Felder werden als Escape-Zeichen für Feldnamen eingebettet (in % ausgedrückt)<i>fieldname</i>%). </p> <p>Die Dateinamenkomponenten, die sich auf den Rotationszeitraum beziehen, werden mithilfe der folgenden Escape-Sequenzen in die Formatzeichenfolge eingebettet: 
      <ul id="ul_3C5C8C5DC9104070ABCFDD85F49BE596"> 
       <li id="li_B100AE13FEA84AB6A1138CF58440E29E"> %yyy% (vierstellige Jahreszahl) </li> 
       <li id="li_0583970798494A1795B03866DC717FB9"> %yy% (zweistellige Jahreszahl) </li> 
       <li id="li_10AA96200F294364A5CE9DC3F22C789A"> %mm% (zweistelliger Monat, 01 - 12) </li> 
       <li id="li_E112E367F62147C49751D6894E47607C"> %w% (zweistellige Woche, 01 - 52) </li> 
       <li id="li_C4B30E38C05942BB8CAA92F3C9B98A3C"> %dd% (zweistelliger Tag, 01 - 31) </li> 
       <li id="li_0318CA8C4DC441B48C16B29A615F3293"> %HH% (zweistellige Stunde, 00 - 23) </li> 
      </ul> </p> <p> Das standardmäßige Dateinamenformat lautet <span class="filepath"> %yyy%%mm%%dd%-%x-mask%.txt</span> </p> 
      <ul id="ul_07AE3624E7D74632AD5E5F164048196F"> 
       <li id="li_BA5C2BFBA73D4AAD8D729B30FF812759"> Bei Escape-Sequenzen wird zwischen Groß- und Kleinschreibung unterschieden. </li> 
       <li id="li_32CB9C98190D4B17B4DA84732CFB9E2F"> Wenn der Dateirotationszeitraum auf "KEINE"festgelegt ist, wird eine leere Zeichenfolge für jede der Escape-Sequenzen ersetzt, sofern vorhanden. </li> 
       <li id="li_C64731961ED6402FB92210A42854BA72"> Ein Fehler wird erzeugt, wenn <span class="wintitle"> Dateinamenformat</span> führt nicht zu einem eindeutigen Dateinamen für jeden Drehungszeitraum (siehe Parameter "Dateidrehungszeitraum"in dieser Tabelle). Bei Verwendung des Drehungszeitraums Tag müssen beispielsweise die Escape-Sequenzen %dd%, %mm% und %yy% oder %yyy% im Muster vorhanden sein, um Datenverlust zu vermeiden. </li> 
       <li id="li_15CDA2ABE450418FA8D9C4BC581C4ADD"> Wenn Sie Escape-Sequenzen für Feldnamen innerhalb des Musters verwenden und das angegebene Feld viele unterschiedliche Werte aufweist, werden viele Ausgabedateien für jeden Rotationszeitraum geschrieben. Beachten Sie, dass dieses Szenario zu einer schlechten Leistung führen kann. Daher sollten Sie diese Funktion mit Vorsicht verwenden. </li> 
       <li id="li_D0F75E4FFAFF47C4AA8A8D14A6E1C18A"> Alle Berechnungen liegen in GMT vor. </li> 
      </ul> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> Ausführen bei Rollover </td> 
      <td colname="col2"> <p>Optional. Nach Abschluss jeder Datei kann ein externer Befehl (Windows) ausgeführt werden. Die Befehlszeile wird aus dem endgültigen Dateinamen abgeleitet, indem die folgenden Escape-Sequenzen in diesen Parameter ersetzt werden: </p> 
      <ul id="ul_5E16832BDBEA4757A2C02DE4B019A122"> 
       <li id="li_6A74D069353E4FE781657BF492675220"> %dir%. Der Ordnerteil des endgültigen Dateinamens, einschließlich des nachfolgenden umgekehrten Schrägstrichs. </li> 
       <li id="li_2CF7232553C348089B1395BBB0BBD6AE"> %file%. Der Dateiname der endgültigen Datei (ohne Verzeichnis und Erweiterung). </li> 
       <li id="li_901BAB90E5EA434F9EE37A60477F4591"> %ext%. Die Erweiterung (einschließlich des führenden ".") des endgültigen Dateinamens. </li> 
       <li id="li_AD7269A67A0041438A6951FD1898D458"> %path%. Der vollständige Pfadname der Datei, entsprechend %dir%%file%%ext%. </li> 
      </ul> <p> Standardmäßig ist dieser Parameter leer (es wird kein Befehl ausgeführt). </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> Speicherbegrenzung </td> 
      <td colname="col2"> <p>Optional. Die Menge an Speicher in Byte, die zum Puffern der Exportergebnisse verwendet wird. Der Standardwert ist 10.000.000 Bytes. </p> <p> <p>Hinweis: Wenn Sie viele Ausgabedateien haben, die gleichzeitig geöffnet sind, können Sie diesen Wert erhöhen, Sie können jedoch die Speicherkapazität verringern, die für andere Komponenten des Systems zur Verfügung steht. Eine Verringerung dieses Werts kann jedoch den Exportvorgang verlangsamen. Wenden Sie sich für Unterstützung an die Adobe. </p> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> Open Files Limit </td> 
      <td colname="col2"> <p>Optional. Die maximale Anzahl von Dateien, die gleichzeitig für die Ausgabe vom Exporter geöffnet sein können. Wenn diese Zahl überschritten wird, wird ein Fehler im Ereignisprotokoll aufgezeichnet und der Data Workbench-Server wird nicht mehr ausgeführt. Der Standardwert lautet 1000. </p> </td> 
      </tr> 
    </tbody> 
   </table>

1. Nachdem Sie Ihren Exporter (und Änderungen an anderen Parametern) in der [!DNL Transform.cfg] speichern Sie die Datei lokal und speichern Sie sie im entsprechenden Profil auf dem Data Workbench-Server.
