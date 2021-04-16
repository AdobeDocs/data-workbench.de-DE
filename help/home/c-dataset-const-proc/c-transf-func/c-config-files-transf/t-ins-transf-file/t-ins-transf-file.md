---
description: Die Datei "data workbenchTransform.cfg"enthält die Parameter, die die Protokollquellen, Datentransformationen und Exporteure definieren.
title: Datei „Transform.cfg“
uuid: eab5bb70-6de7-4f08-85db-a6cb00abd3ed
exl-id: e84f2536-cb22-4c47-a7a8-270b3c37ece6
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1336'
ht-degree: 2%

---

# Datei „Transform.cfg“{#the-transform-cfg-file}

Die Datei &quot;data workbenchTransform.cfg&quot;enthält die Parameter, die die Protokollquellen, Datentransformationen und Exporteure definieren.

Die Transformationen, die Sie definieren, manipulieren Rohdaten, die von Sensoren ( [!DNL .vsl]-Dateien) oder in Textdateien, XML-Dateien oder ODBC-kompatiblen Datenbanken erfasst werden, und geben sie entweder in vorhandene Felder aus, überschreiben die aktuellen Daten oder in neu definierte Felder.

Um die Transformationsfunktion zu konfigurieren, bearbeiten Sie die Datei &quot;data workbench [!DNL Transform.cfg]&quot;im Ordner &quot;DataSet&quot;für das Profil, für das Sie Ereignis-Daten exportieren möchten. In der Regel ist dieses Profil der Transformationsfunktion gewidmet (d. h. Sie führen keine andere Datenverarbeitung durch als die in der Datenbasis definierte Datei [!DNL Transform.cfg]). Beachten Sie, dass alle Verarbeitungsanweisungen, die in den [!DNL Log Processing Dataset Include]-Dateien für alle geerbten Profil angegeben sind, zusätzlich zu den in der Datenbasis [!DNL Transform.cfg]-Datei angegebenen angewendet werden.

Weitere Informationen zu Datenaset-Include-Dateien finden Sie unter [DataSet Include Files](../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md).

Wenn die Daten, die Sie exportieren möchten, von einem Data Workbench-Servercluster verarbeitet werden, verarbeitet jeder der Verarbeitungsserver (DPUs) im Cluster die Daten, aber nur die erste DPU (Verarbeitungsserver #0 in der [!DNL profile.cfg]-Datei) schreibt die Ausgabedaten in sein lokales Dateisystem.

**So bearbeiten Sie die Datei &quot;Data Workbench Transform.cfg&quot;**

1. Wenn Sie in dem Profil arbeiten, für das Sie Daten exportieren möchten, öffnen Sie das [!DNL Profile Manager] und klicken Sie auf **[!UICONTROL Dataset]**, um den Ordnerinhalt anzuzeigen.
1. Klicken Sie mit der rechten Maustaste auf das Häkchen neben Data Workbench [!DNL Transform.cfg] und klicken Sie dann auf **[!UICONTROL Make Local]**. In der Spalte [!DNL User] wird ein Häkchen für diese Datei angezeigt.
1. Klicken Sie mit der rechten Maustaste auf das neu erstellte Häkchen und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Das Fenster Data Workbench [!DNL Transform.cfg] wird angezeigt.
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
    <td colname="col2"> <p>Optional. Filtern Sie Daten, um bis zu diesem Zeitpunkt Protokolleinträge mit Zeitstempeln einzuschließen, die jedoch nicht eingeschlossen sind. Adobe empfiehlt die Verwendung eines der folgenden Zeitformate: 
      <ul id="ul_C8C7F0F631594F7095CB83EF54E7CD0E"> 
       <li id="li_77AB6EEE8EEC4698AA886DE8BB0E2783"> 1. Januar 2013 HH:MM:SS EDT </li> 
       <li id="li_33806070F991476BB986906876CAF7F1"> 1. Januar 2013 HH:MM:SS GMT </li> 
      </ul> </p> <p> Wenn Sie beispielsweise den 29. Juli 2013 um 00:00:00 EDT als <span class="wintitle"> Endzeit </span> festlegen, werden Daten bis zum 28. Juli 2013 um 23:59:59 PM EDT erfasst. </p> <p> Sie müssen eine Zeitzone angeben. Die Zeitzone wird nicht standardmäßig auf GMT gesetzt, wenn sie nicht angegeben ist. Eine Liste der vom Data Workbench-Server unterstützten Zeitzonenabkürzungen finden Sie unter <a href="../../../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> Zeitzonencodes </a>. </p> <p> Der Parameter Use Beginn/End Times für Sensor- und Protokolldateiquellen bezieht sich auf diesen Parameter. </p> </td> 
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
    <td colname="col1"> Protokolleintragsbedingung </td> 
    <td colname="col2"> Optional. Definiert die Regeln, nach denen Protokolleinträge für den Export berücksichtigt werden. Weitere Informationen zur Protokolleingabebedingung </span> finden Sie unter <a href="../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md"> Konfigurationsdatei für die Protokollverarbeitung </a>.<span class="wintitle"> </span></td> 
    </tr> 
    <tr> 
    <td colname="col1"> Quellen für die Protokollierung </td> 
    <td colname="col2"> <p>Die Datenquellen. <span class="wintitle"> Protokollquellen  </span> können  <span class="filepath"> .vsl- </span> Dateien, Protokolldateien, XML-Dateien oder Daten aus ODBC-kompatiblen Datenbanken sein. Weitere Informationen zu <span class="wintitle"> Protokollquellen </span> finden Sie unter <a href="../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md"> Protokollverarbeitungskonfigurationsdatei </a>. </p> <p> <span class="wintitle"> Transform  </span> erwartet, dass alle Quelldaten in chronologischer Reihenfolge innerhalb der lexikografisch geordneten Eingabedateien vorliegen. Wenn diese Anforderung nicht erfüllt ist, sind die As Of-Berechnungen nicht korrekt, und nach dem Schließen der Ausgabedateien können zusätzliche Eingabedaten verarbeitet werden. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Offlinemodus </td> 
    <td colname="col2"> <p>Optional. Wahr oder falsch. Bei "true"geht <span class="wintitle"> Transform </span> davon aus, dass alle Eingabedateien vorhanden sind, wenn der Beginn die Daten verarbeitet. Wenn alle Eingabedaten gelesen wurden, schließt <span class="wintitle"> Transform </span> alle Ausgabedateien, ohne darauf zu warten, dass zusätzliche Daten empfangen werden. Der Standardwert ist „false“. </p> <p> <p>Hinweis:  Wenn <span class="wintitle"> Offlinemodus </span> auf "true"eingestellt ist, erwartet <span class="wintitle"> Transform </span>, dass alle Quelldaten vor der Verarbeitung von Beginn vorhanden sind. In der Datei <span class="filepath"> VisualServer.log </span> wird eine Warnmeldung generiert, wenn nach dem Schließen der Ausgabedateien weitere Daten empfangen werden. </p> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Neu verarbeiten </td> 
    <td colname="col2"> <p>Optional. Alle Zeichen oder Kombinationen von Zeichen können hier eingegeben werden. Durch Ändern dieses Parameters und Speichern der Datei auf dem Computer <span class="wintitle"> Transform </span> wird die Datenverarbeitung initiiert. </p> <p> Weitere Informationen zur erneuten Verarbeitung Ihrer Daten finden Sie unter <a href="../../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md"> Wiederaufbereitung und Verarbeitung </a>. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Phasen </td> 
    <td colname="col2"> <p>Optional. Die Namen der Verarbeitungsstufen, die in <span class="wintitle"> Protokollverarbeitungsdataset verwendet werden können, umfassen </span>-Dateien, die zusätzlich zur Datei <span class="filepath"> Transform.cfg </span> ausgeführt werden. Verarbeitungsschritte bieten eine Möglichkeit, die in <span class="wintitle"> Protokollverarbeitungsdataset definierten Transformationen anzuordnen. Schließen Sie </span>-Dateien ein. Dieser Parameter ist sehr hilfreich, wenn Sie eine oder mehrere Konvertierungen innerhalb mehrerer <span class="wintitle">-Protokollverarbeitungsdaten einschließen </span>-Dateien definiert haben und Sie möchten, dass bestimmte Konvertierungen an bestimmten Punkten während des Exportvorgangs durchgeführt werden. </p> <p> Die Reihenfolge, in der die Schritte hier Liste werden, bestimmt die Reihenfolge, in der die Transformationen in den Protokollverarbeitungsdatenasets <span class="wintitle">-Dateien einschließlich </span> während des Datenexports ausgeführt werden. <span class="wintitle"> Vorverarbeitung  </span> und  <span class="wintitle"> Nachverarbeitung  </span> sind integrierte Phasen;  <span class="wintitle"> Die Vorverarbeitung  </span> ist immer der erste Schritt und die  <span class="wintitle"> Nachbearbeitung  </span> ist immer der letzte Schritt. Standardmäßig gibt es eine benannte Phase mit dem Namen <span class="wintitle"> Default </span>. </p> <p> <b>So fügen Sie eine neue Verarbeitungsphase hinzu</b> </p> 
      <ul id="ul_869C52DD30E443A496DC6363C3FC62B5"> 
       <li id="li_6493B2A335A8497C9A1BC6292C88CA81"> Klicken Sie im Fenster Data Workbench <span class="filepath"> Transform.cfg </span> mit der rechten Maustaste auf <span class="uicontrol"> Stages </span> und dann auf <span class="uicontrol"> Hinzufügen New </span> &gt; <span class="uicontrol"> Stage </span>. </li> 
       <li id="li_EE25E50CEB53450EA6465B08B0AE5442"> Geben Sie einen Namen für die neue Phase ein. </li> 
      </ul> <p> <b>So löschen Sie eine vorhandene Verarbeitungsphase</b> </p> 
      <ul id="ul_4950BC26E0CD4837A4CB377605A52D3C"> 
      <li id="li_A61E2C17966E4F96A1256B8390623B0F"> Klicken Sie mit der rechten Maustaste auf die Zahl, die der zu löschenden Phase entspricht, und klicken Sie auf <span class="uicontrol"> </span><i>&lt; <span class="uicontrol"> #stage_number </span></i>. </li> 
      </ul> <p> <p>Hinweis:  Wenn Sie eine Phase in einer <span class="wintitle">-Protokollverarbeitungsdataset Einschließen </span>-Datei angeben, muss der Name der Bühne exakt mit dem Namen übereinstimmen, den Sie hier eingeben. Weitere Informationen zu Datenaset-Include-Dateien finden Sie unter <a href="../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md"> DataSet Include-Dateien </a>. </p> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Startzeit </td> 
    <td colname="col2"> <p>Optional. Filtern Sie die Daten, um Protokolleinträge mit Zeitstempeln zu dieser Zeit oder danach einzuschließen. Adobe empfiehlt die Verwendung eines der folgenden Zeitformate: </p> 
      <ul id="ul_8F9B82A8AE7F45BE8C7949D2E96C7BEC"> 
       <li id="li_8F7BCFF251CB4F1B87DDA1A259FA9C7B"> 1. Januar 2013 HH:MM:SS EDT </li> 
       <li id="li_4BCE317EE1914074B3642687CFED5FC2"> 1. Januar 2013 HH:MM:SS GMT </li> 
      </ul> <p> Wenn Sie beispielsweise den 29. Juli 2013 um 00:00:00 Uhr EDT als "Beginn Time"festlegen, werden Daten ab dem 29. Juli 2013 um 12:00:00 Uhr EDT eingeschlossen. </p> <p> Sie müssen eine Zeitzone angeben. Die Zeitzone wird nicht standardmäßig auf GMT gesetzt, wenn sie nicht angegeben ist. Eine Liste der vom Data Workbench-Server unterstützten Zeitzonenabkürzungen finden Sie unter <a href="../../../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> Zeitzonencodes </a>. </p> <p> <p>Hinweis:  Der Parameter Use Beginn/End Times für Sensor- und Protokolldateiquellen bezieht sich auf diesen Parameter. </p> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Transformationen </td> 
    <td colname="col2"> <p>Optional. Definiert die Transformationen, die auf die Daten angewendet werden sollen. Informationen zu den verfügbaren Transformationstypen finden Sie unter <a href="../../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md"> Datentransformationen </a>. </p> <p> <p>Hinweis:  Die folgenden Transformationstypen funktionieren nicht, wenn sie in der Datei data workbench <span class="filepath"> Transform.cfg </span> definiert werden: </p> </p> 
      <ul id="ul_B091DFBD1C33471BBC01AEC7E92FC8CC"> 
       <li id="li_660EBECFC407488199CCCC886326806D"> AppendURI </li> 
       <li id="li_56BCEBE4A2D044AE87F5B747C6501817"> CrossRows </li> 
       <li id="li_B23B4E81B37942DCA55FEC1A6239C5FA"> ODBCLookup </li> 
       <li id="li_EF0AFF13C40D4AB49EAB4EF1691F8FA4"> Sessionize </li> 
      </ul> </td> 
    </tr> 
  </tbody> 
  </table>

>[!NOTE]
>
>Wenn nach dem Schließen der Ausgabedateien weitere Daten empfangen werden (siehe [!DNL Log Sources] und [!DNL Offline Mode] in der obigen Tabelle), erstellt [!DNL Transform] neue Ausgabedateien mit den zusätzlichen Daten. Die Namen der neuen Ausgabedateien werden aus dem Namen der ursprünglichen Ausgabedatei mit einer in Klammern gesetzten Versionsnummer direkt vor der Erweiterung generiert. Wenn die ursprüngliche Ausgabedatei beispielsweise [!DNL 20070701-ABC.vsl] lautet, werden nachfolgende Versionen dieser Datei [!DNL 20070701-ABC(1).vsl], [!DNL 20070701-ABC(2).vsl] usw. benannt. Beachten Sie, dass die Verwendung der versionierten Dateien als Eingabe für den Data Workbench-Server zu Verarbeitungsfehlern führen kann.
>
>
>Adobe empfiehlt, die Erstellung versionierter Ausgabedateien zu vermeiden, indem sichergestellt wird, dass alle Quelldaten in chronologischer Reihenfolge innerhalb von lexikografisch geordneten Eingabedateien vorliegen und, wenn [!DNL Offline Mode] auf true gesetzt ist, alle Quelldaten vor der Verarbeitung von Beginn vorhanden sind. Weitere Informationen finden Sie in den Einträgen [!DNL Log Sources] und [!DNL Offline Mode] in der obigen Tabelle.

1. hinzufügen Sie die Transformationen, indem Sie mit der rechten Maustaste auf **[!UICONTROL Transformations]** klicken und **[!UICONTROL Add new]** > **[!UICONTROL Transformation type]** klicken. Füllen Sie die Transformationsfelder aus.

   Beschreibungen und Beispiele der Transformationen, die Sie mit der Transformationsfunktion verwenden können, finden Sie unter [Datentransformationen](../../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md).

1. Klicken Sie mit der rechten Maustaste auf **[!UICONTROL (modified)]** oben im Fenster und dann auf **[!UICONTROL Save]**.
1. Um die lokal vorgenommenen Änderungen in Kraft zu setzen, klicken Sie in der Spalte [!DNL Profile Manager] mit der rechten Maustaste auf das Häkchen für Data Workbench [!DNL Transform.cfg] und klicken Sie dann auf [!DNL User] und dann auf **[!UICONTROL Save to]** > **[!UICONTROL profile name]**. Dabei ist der Profil der Name des Profils, für das Sie Daten exportieren. Die erneute Verarbeitung der Daten beginnt nach der Synchronisierung des Profils.

   >[!NOTE]
   >
   >Weitere Informationen zur erneuten Verarbeitung Ihrer Daten für den Export finden Sie unter [Wiederaufbereitung und Verarbeitung](../../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).
