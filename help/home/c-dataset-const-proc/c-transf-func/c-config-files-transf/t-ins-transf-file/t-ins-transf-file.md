---
description: Die Datei "data workbenchTransform.cfg"enthält die Parameter, die die Protokollquellen, Datentransformationen und Exporteure definieren.
solution: Analytics
title: Die Datei "Transform.cfg"
topic: Data workbench
uuid: eab5bb70-6de7-4f08-85db-a6cb00abd3ed
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Die Datei &quot;Transform.cfg&quot;{#the-transform-cfg-file}

Die Datei &quot;data workbenchTransform.cfg&quot;enthält die Parameter, die die Protokollquellen, Datentransformationen und Exporteure definieren.

Die Transformationen, die Sie definieren, manipulieren Rohdaten, die von Sensoren ( [!DNL .vsl] Dateien) erfasst werden oder in Textdateien, XML-Dateien oder ODBC-kompatiblen Datenbanken enthalten sind, und geben sie entweder in vorhandene Felder aus, überschreiben die aktuellen Daten oder in neu definierte Felder.

Um die Transformationsfunktion zu konfigurieren, bearbeiten Sie die Data Workbench- [!DNL Transform.cfg] Datei im Ordner &quot;DataSet&quot;für das Profil, für das Sie Ereignisdaten exportieren möchten. Normalerweise ist dieses Profil der Transformationsfunktion gewidmet (d. h. Sie führen keine andere Datenverarbeitung durch als die in der Data Workbench- [!DNL Transform.cfg] Datei definierten Daten). Es ist wichtig zu beachten, dass alle Verarbeitungsanweisungen, die in den [!DNL Log Processing Dataset Include] Dateien für geerbte Profile angegeben sind, zusätzlich zu den in der Data Workbench- [!DNL Transform.cfg] Datei angegebenen angewendet werden.

Weitere Informationen zu Datenaset-Include-Dateien finden Sie unter [DataSet Include-Dateien](../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md).

Wenn die Daten, die Sie exportieren möchten, von einem Data Workbench-Servercluster verarbeitet werden, verarbeitet jeder der Verarbeitungsserver (DPUs) im Cluster die Daten, aber nur die erste DPU (Verarbeitungsserver #0 in der [!DNL profile.cfg] Datei) schreibt die Ausgabedaten in sein lokales Dateisystem.

**So bearbeiten Sie die Datei &quot;Data Workbench Transform.cfg&quot;**

1. Öffnen Sie bei der Arbeit mit dem Profil, für das Sie Daten exportieren möchten, die Datei [!DNL Profile Manager] und klicken Sie auf **[!UICONTROL Dataset]** , um den Inhalt des Ordners anzuzeigen.
1. Klicken Sie mit der rechten Maustaste auf das Häkchen neben Data Workbench [!DNL Transform.cfg]und klicken Sie dann auf **[!UICONTROL Make Local]**. Ein Häkchen für diese Datei wird in der [!DNL User] Spalte angezeigt.
1. Klicken Sie mit der rechten Maustaste auf das neu erstellte Häkchen und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Das Data Workbench- [!DNL Transform.cfg] Fenster wird angezeigt.
1. Bearbeiten Sie die Parameter in der Konfigurationsdatei mithilfe der folgenden Tabelle als Anleitung:

<table id="table_91D9C4C1BE2E43158D9D06C6284EE3C7"> 
  <thead> 
    <tr> 
    <th colname="col1" class="entry"> Parameter </th> 
    <th colname="col2" class="entry"> Beschreibung </th> 
    </tr> 
  </thead>
  <tbody> 
    <tr> 
    <td colname="col1"> Endzeit </td> 
    <td colname="col2"> <p>Optional. Filtern Sie Daten, um bis zu diesem Zeitpunkt Protokolleinträge mit Zeitstempeln einzuschließen, die jedoch nicht eingeschlossen sind. Adobe empfiehlt die Verwendung eines der folgenden Formate: 
      <ul id="ul_C8C7F0F631594F7095CB83EF54E7CD0E"> 
       <li id="li_77AB6EEE8EEC4698AA886DE8BB0E2783"> 1. Januar 2013 HH:MM:SS EDT </li> 
       <li id="li_33806070F991476BB986906876CAF7F1"> 1. Januar 2013 HH:MM:SS GMT </li> 
      </ul> </p> <p> Wenn Sie beispielsweise den 29. Juli 2013 um 00:00:00 Uhr EDT als <span class="wintitle"> Endzeit festlegen, </span> werden Daten bis zum 28. Juli 2013 um 23:59:59 PM EDT eingeschlossen. </p> <p> Sie müssen eine Zeitzone angeben. Die Zeitzone wird nicht standardmäßig auf GMT gesetzt, wenn sie nicht angegeben ist. Eine Liste der vom Data Workbench-Server unterstützten Zeitzonenabkürzungen finden Sie unter <a href="../../../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> Zeitzonencodes </a>. </p> <p> Der Parameter "Start-/Endzeit verwenden"für Sensor- und Protokolldateiquellen bezieht sich auf diesen Parameter. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Ausführer </td> 
    <td colname="col2"> <p>Die Unterfelder eines Exporteurs geben an, wie die Ausgabedaten verarbeitet und/oder formatiert werden. Sie können mehrere Exporteure für eine Reihe von Protokollquellen definieren. Jeder Exporttyp erstellt die Ausgabe unabhängig voneinander. </p> <p> Es gibt drei Arten von Ausführern: 
      <ul id="ul_C3C39F6DF3DC4F4CA2161EDB69599642"> 
       <li id="li_635FB271D0544D52B1C31740442D2E08"> ExportTextFile </li> 
       <li id="li_D496194848B44823A58890E03FFDD18E"> ExportDelimitedTextFile </li> 
       <li id="li_AEE9AA87076141FC91330D3FCFAB2101"> ExportVSLFile </li> 
      </ul> </p> <p> Weitere Informationen zu Exporttypen finden Sie unter <a href="../../../../../home/c-dataset-const-proc/c-transf-func/c-config-files-transf/t-ins-transf-file/t-def-exp.md#task-900c40d1914347f288587bf0ca394ff2"> Definieren von Exportern </a>. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Hashschwellenwert </td> 
    <td colname="col2"> Optional. Ein Stichprobenfaktor für eine zufällige Unterstichprobe von Zeilen. Wenn der Wert auf "n"festgelegt ist, wird nur eine von n Tracking-IDs für den Export ausgewählt, wodurch die Gesamtzahl der exportierten Zeilen um den Faktor n verringert wird. Um alle Zeilen zu exportieren, legen Sie den Hash-Schwellenwert auf 1 fest. </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Protokolleinstiegsbedingung </td> 
    <td colname="col2"> Optional. Definiert die Regeln, nach denen Protokolleinträge für den Export berücksichtigt werden. Weitere Informationen zur <span class="wintitle"> Protokolleingabebedingung </span>finden Sie unter Konfigurationsdatei für die <a href="../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md"> Protokollverarbeitung </a>. </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Protokollquellen </td> 
    <td colname="col2"> <p>Die Datenquellen. <span class="wintitle"> Protokollquellen </span> können <span class="filepath"> .vsl- </span> Dateien, Protokolldateien oder XML-Dateien oder Daten aus ODBC-kompatiblen Datenbanken sein. Weitere Informationen zu <span class="wintitle"> Protokollquellen </span>finden Sie unter Konfigurationsdatei für die <a href="../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md"> Protokollverarbeitung </a>. </p> <p> <span class="wintitle"> Transform </span> erwartet, dass alle Quelldaten in chronologischer Reihenfolge innerhalb von lexikografisch geordneten Eingabedateien vorliegen. Wenn diese Anforderung nicht erfüllt ist, sind die As Of-Berechnungen nicht korrekt, und nach dem Schließen der Ausgabedateien können zusätzliche Eingabedaten verarbeitet werden. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Offlinemodus </td> 
    <td colname="col2"> <p>Optional. True oder false. Wenn "true", geht <span class="wintitle"> Transform </span> davon aus, dass alle Eingabedateien vorhanden sind, wenn die Verarbeitung der Daten beginnt. Wenn alle Eingabedaten gelesen wurden, <span class="wintitle"> </span> schließt Transform alle Ausgabedateien, ohne darauf zu warten, dass weitere Daten empfangen werden. Der Standardwert ist „false“. </p> <p> <p>Hinweis:  Wenn der <span class="wintitle"> Offline-Modus auf "true"festgelegt </span> ist, erwartet <span class="wintitle"> </span> Transform, dass alle Quelldaten vorhanden sind, bevor die Verarbeitung beginnt. Eine Warnmeldung wird in der Datei <span class="filepath"> VisualServer.log </span> generiert, wenn nach dem Schließen der Ausgabedateien weitere Daten empfangen werden. </p> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Neu verarbeiten </td> 
    <td colname="col2"> <p>Optional. Alle Zeichen oder Kombinationen von Zeichen können hier eingegeben werden. Wenn Sie diesen Parameter ändern und die Datei auf dem <span class="wintitle"> Transform- </span> Computer speichern, wird die Datenverarbeitung initiiert. </p> <p> Weitere Informationen zur erneuten Verarbeitung Ihrer Daten finden Sie unter <a href="../../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md"> Verarbeitung und Verarbeitung </a>. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Phasen </td> 
    <td colname="col2"> <p>Optional. Die Namen der Verarbeitungsstufen, die in <span class="wintitle"> Protokollverarbeitungsdatensätzen verwendet werden können, umfassen </span> Dateien, die zusätzlich zur Datenbasis- <span class="filepath"> Transform.cfg- </span> Datei ausgeführt werden. Verarbeitungsschritte bieten eine Möglichkeit, die Konvertierungen anzuordnen, die in <span class="wintitle"> "Log Processing DataSet Include"- </span> Dateien definiert sind. Dieser Parameter ist sehr hilfreich, wenn Sie eine oder mehrere Konvertierungen in mehreren <span class="wintitle"> Protokollverarbeitungsdatendateien einschließlich </span> -Dateien definiert haben und Sie möchten, dass bestimmte Transformationen an bestimmten Punkten während des Exportvorgangs durchgeführt werden. </p> <p> Die Reihenfolge, in der Sie die Schritte hier auflisten, bestimmt die Reihenfolge, in der die Konvertierungen im <span class="wintitle"> Datensatz "Log Processing DataSet Include"- </span> Dateien während des Datenexports ausgeführt werden. <span class="wintitle"> Vorverarbeitung </span> und <span class="wintitle"> Nachverarbeitung </span> sind integrierte Phasen; Die <span class="wintitle"> Vorverarbeitung </span> ist immer der erste Schritt und die <span class="wintitle"> Nachbearbeitung </span> ist immer der letzte Schritt. Standardmäßig gibt es eine benannte Phase namens " <span class="wintitle"> Standard" </span>. </p> <p> <b>So fügen Sie eine neue Verarbeitungsphase hinzu</b> </p> 
      <ul id="ul_869C52DD30E443A496DC6363C3FC62B5"> 
       <li id="li_6493B2A335A8497C9A1BC6292C88CA81"> Klicken Sie im Data Workbench <span class="filepath"> Transform.cfg- </span> Fenster mit der rechten Maustaste auf <span class="uicontrol"> Stufen </span>und klicken Sie dann auf <span class="uicontrol"> Neu hinzufügen </span> &gt; <span class="uicontrol"> Phase </span>. </li> 
       <li id="li_EE25E50CEB53450EA6465B08B0AE5442"> Geben Sie einen Namen für die neue Phase ein. </li> 
      </ul> <p> <b>So löschen Sie eine vorhandene Verarbeitungsphase</b> </p> 
      <ul id="ul_4950BC26E0CD4837A4CB377605A52D3C"> 
      <li id="li_A61E2C17966E4F96A1256B8390623B0F"> Klicken Sie mit der rechten Maustaste auf die Nummer, die der zu löschenden Phase entspricht, und klicken Sie auf <span class="uicontrol"> &lt; </span><i>#stage_number <span class="uicontrol"> &gt; </span></i>. </li> 
      </ul> <p> <p>Hinweis:  Wenn Sie eine Phase in einer <span class="wintitle"> Protokollverarbeitungsdatenaset-Include- </span> -Datei angeben, muss der Name der Phase genau mit dem Namen übereinstimmen, den Sie hier eingeben. Weitere Informationen zu Datenaset-Include-Dateien finden Sie unter <a href="../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md"> DataSet Include-Dateien </a>. </p> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Startzeit </td> 
    <td colname="col2"> <p>Optional. Filtern Sie die Daten, um Protokolleinträge mit Zeitstempeln zu dieser Zeit oder danach einzuschließen. Adobe empfiehlt die Verwendung eines der folgenden Formate: </p> 
      <ul id="ul_8F9B82A8AE7F45BE8C7949D2E96C7BEC"> 
       <li id="li_8F7BCFF251CB4F1B87DDA1A259FA9C7B"> 1. Januar 2013 HH:MM:SS EDT </li> 
       <li id="li_4BCE317EE1914074B3642687CFED5FC2"> 1. Januar 2013 HH:MM:SS GMT </li> 
      </ul> <p> Wenn Sie beispielsweise den 29. Juli 2013 um 00:00:00 Uhr EDT als Startzeit festlegen, sind Daten ab dem 29. Juli 2013 um 12:00:00 Uhr EDT enthalten. </p> <p> Sie müssen eine Zeitzone angeben. Die Zeitzone wird nicht standardmäßig auf GMT gesetzt, wenn sie nicht angegeben ist. Eine Liste der vom Data Workbench-Server unterstützten Zeitzonenabkürzungen finden Sie unter <a href="../../../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> Zeitzonencodes </a>. </p> <p> <p>Hinweis:  Der Parameter "Start-/Endzeit verwenden"für Sensor- und Protokolldateiquellen bezieht sich auf diesen Parameter. </p> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Transformationen </td> 
    <td colname="col2"> <p>Optional. Definiert die Transformationen, die auf die Daten angewendet werden sollen. Informationen zu den verfügbaren Transformationstypen finden Sie unter <a href="../../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md"> Datentransformationen </a>. </p> <p> <p>Hinweis:  Die folgenden Transformationstypen funktionieren nicht, wenn sie in der Datei "Data Workbench <span class="filepath"> Transform.cfg"definiert </span> sind: </p> </p> 
      <ul id="ul_B091DFBD1C33471BBC01AEC7E92FC8CC"> 
       <li id="li_660EBECFC407488199CCCC886326806D"> AppendURI </li> 
       <li id="li_56BCEBE4A2D044AE87F5B747C6501817"> CrossRows </li> 
       <li id="li_B23B4E81B37942DCA55FEC1A6239C5FA"> ODBCLookup </li> 
       <li id="li_EF0AFF13C40D4AB49EAB4EF1691F8FA4"> Sessionieren </li> 
      </ul> </td> 
    </tr> 
  </tbody> 
  </table>

>[!NOTE]
>
>Werden nach dem Schließen der Ausgabedateien weitere Daten empfangen (siehe [!DNL Log Sources] und [!DNL Offline Mode] in der obigen Tabelle), werden neue Ausgabedateien mit den zusätzlichen Daten [!DNL Transform] erstellt. Die Namen der neuen Ausgabedateien werden aus dem Namen der ursprünglichen Ausgabedatei mit einer in Klammern gesetzten Versionsnummer direkt vor der Erweiterung generiert. Wenn die ursprüngliche Ausgabedatei beispielsweise [!DNL 20070701-ABC.vsl]lautet, werden nachfolgende Versionen dieser Datei benannt [!DNL 20070701-ABC(1).vsl], [!DNL 20070701-ABC(2).vsl]usw. Beachten Sie, dass die Verwendung der versionierten Dateien als Eingabe für den Data Workbench-Server zu Verarbeitungsfehlern führen kann.
>
>
>Adobe empfiehlt, die Erstellung versionierter Ausgabedateien zu vermeiden, indem sichergestellt wird, dass alle Quelldaten in chronologischer Reihenfolge innerhalb der lexikografisch geordneten Eingabedateien vorliegen und, falls &quot;true&quot;festgelegt [!DNL Offline Mode] ist, dass alle Quelldaten vor dem Beginn der Verarbeitung vorhanden sind. Weitere Informationen finden Sie in den [!DNL Log Sources] und in den [!DNL Offline Mode] Einträgen in der obigen Tabelle.

1. Fügen Sie Transformationen hinzu, indem Sie mit der rechten Maustaste klicken **[!UICONTROL Transformations]** und auf **[!UICONTROL Add new]** > **[!UICONTROL Transformation type]**. Füllen Sie die Transformationsfelder aus.

   Beschreibungen und Beispiele der Transformationen, die Sie mit der Transformationsfunktion verwenden können, finden Sie unter [Datentransformationen](../../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md) .

1. Klicken Sie mit der rechten Maustaste **[!UICONTROL (modified)]** am oberen Rand des Fensters und klicken Sie dann auf **[!UICONTROL Save]**.
1. Damit die lokal vorgenommenen Änderungen wirksam werden, klicken Sie im [!DNL Profile Manager]Kontextmenü mit der rechten Maustaste auf das Häkchen für die Datenbasis [!DNL Transform.cfg] in der [!DNL User] Spalte und klicken Sie dann auf **[!UICONTROL Save to]** > **[!UICONTROL profile name]**. Dabei ist Profilname der Name des Profils, für das Sie Daten exportieren. Die erneute Verarbeitung der Daten beginnt nach der Synchronisierung des Profils.

   >[!NOTE]
   >
   >Informationen zur erneuten Verarbeitung Ihrer Daten für den Export finden Sie unter [Wiederaufbereitung und Konvertierung](../../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).
