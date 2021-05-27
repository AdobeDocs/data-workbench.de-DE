---
description: Die Datei "data workbenchTransform.cfg"enthält die Parameter, die die Protokollquellen, Datenumwandlungen und Exporteure definieren.
title: Datei „Transform.cfg“
uuid: eab5bb70-6de7-4f08-85db-a6cb00abd3ed
exl-id: e84f2536-cb22-4c47-a7a8-270b3c37ece6
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1336'
ht-degree: 2%

---

# Datei „Transform.cfg“{#the-transform-cfg-file}

Die Datei &quot;data workbenchTransform.cfg&quot;enthält die Parameter, die die Protokollquellen, Datenumwandlungen und Exporteure definieren.

Die von Ihnen definierten Umwandlungen manipulieren Rohdaten, die von Sensoren ( [!DNL .vsl]-Dateien) erfasst oder in Textdateien, XML-Dateien oder ODBC-kompatiblen Datenbanken enthalten sind, und geben sie entweder in vorhandene Felder aus, überschreiben die aktuellen Daten oder in neu definierte Felder.

Um die Umwandlungsfunktion zu konfigurieren, bearbeiten Sie die Data Workbench-Datei [!DNL Transform.cfg] im Ordner Datensatz für das Profil, für das Sie Ereignisdaten exportieren möchten. In der Regel bezieht sich dieses Profil auf die Umwandlungsfunktion (d. h. Sie führen keine andere Datenverarbeitung durch als die in der Datei [!DNL Transform.cfg] der Data Workbench definierte Datenverarbeitung). Beachten Sie, dass alle in den [!DNL Log Processing Dataset Include]-Dateien für geerbte Profile angegebenen Verarbeitungsanweisungen zusätzlich zu den in der Datei [!DNL Transform.cfg] von Data Workbench angegebenen angewendet werden.

Informationen zu Datensatzaufnahme-Dateien finden Sie unter [Datensatzaufnahme-Dateien](../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md).

Wenn die Daten, die Sie exportieren möchten, von einem Data Workbench-Servercluster verarbeitet werden, verarbeitet jeder der Verarbeitungsserver (DPUs) im Cluster die Daten, aber nur die erste DPU (Verarbeitungsserver Nr. 0 in der Datei [!DNL profile.cfg]) schreibt die Ausgabedaten in sein lokales Dateisystem.

**Bearbeiten der Datei &quot;Transform.cfg&quot;in Data Workbench**

1. Öffnen Sie bei der Arbeit mit dem Profil, für das Sie Daten exportieren möchten, [!DNL Profile Manager] und klicken Sie auf **[!UICONTROL Dataset]** , um den Inhalt des Ordners anzuzeigen.
1. Klicken Sie mit der rechten Maustaste auf das Häkchen neben Data Workbench [!DNL Transform.cfg] und klicken Sie dann auf **[!UICONTROL Make Local]**. Ein Häkchen für diese Datei wird in der Spalte [!DNL User] angezeigt.
1. Klicken Sie mit der rechten Maustaste auf das neu erstellte Häkchen und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Das Fenster [!DNL Transform.cfg] von Data Workbench wird angezeigt.
1. Bearbeiten Sie die Parameter in der Konfigurationsdatei mithilfe der unten stehenden Tabelle als Anleitung:

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
    <td colname="col2"> <p>Optional. Filtern Sie Daten, um Protokolleinträge mit Zeitstempeln bis zu diesem Zeitpunkt einzuschließen, jedoch nicht eingeschlossen. Adobe empfiehlt die Verwendung eines der folgenden Zeitformate: 
      <ul id="ul_C8C7F0F631594F7095CB83EF54E7CD0E"> 
       <li id="li_77AB6EEE8EEC4698AA886DE8BB0E2783"> 1. Januar 2013 HH:MM:SS EDT </li> 
       <li id="li_33806070F991476BB986906876CAF7F1"> 1. Januar 2013 HH:MM:SS GMT </li> 
      </ul> </p> <p> Wenn Sie beispielsweise den 29. Juli 2013 um 00:00:00 EDT als <span class="wintitle"> Endzeit </span> angeben, werden Daten bis zum 28. Juli 2013, 23:59:59 PM EDT eingeschlossen. </p> <p> Sie müssen eine Zeitzone angeben. Wenn nicht anders angegeben, wird in der Zeitzone nicht standardmäßig GMT verwendet. Eine Liste der vom Data Workbench-Server unterstützten Zeitzonen-Abkürzungen finden Sie unter <a href="../../../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> Zeitzonencodes </a>. </p> <p> Der Parameter Start-/Endzeiten für Sensor- und Protokolldateiquellen bezieht sich auf diesen Parameter. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Ausführer </td> 
    <td colname="col2"> <p>Die Unterfelder eines Exporteurs geben an, wie die Ausgabedaten verarbeitet und/oder formatiert werden. Sie können mehrere Exporteure für eine Reihe von Protokollquellen definieren. Jeder Exporteryp erstellt die Ausgabe unabhängig voneinander. </p> <p> Es gibt drei Arten von Ausführern: 
      <ul id="ul_C3C39F6DF3DC4F4CA2161EDB69599642"> 
       <li id="li_635FB271D0544D52B1C31740442D2E08"> ExportTextFile </li> 
       <li id="li_D496194848B44823A58890E03FFDD18E"> ExportDelimitedTextFile </li> 
       <li id="li_AEE9AA87076141FC91330D3FCFAB2101"> ExportVSLFile </li> 
      </ul> </p> <p> Weitere Informationen zu Exporttypen finden Sie unter <a href="../../../../../home/c-dataset-const-proc/c-transf-func/c-config-files-transf/t-ins-transf-file/t-def-exp.md#task-900c40d1914347f288587bf0ca394ff2"> Definieren von Exportern </a>. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Hash-Schwellenwert </td> 
    <td colname="col2"> Optional. Ein Stichprobenfaktor für eine Stichprobe von Zeilen. Wenn der Wert auf eine Zahl n festgelegt ist, wird nur eine von n Tracking-IDs für den Export ausgewählt, wodurch die Gesamtzahl der exportierten Zeilen um den Faktor n verringert wird. Um alle Zeilen zu exportieren, setzen Sie den Hash-Schwellenwert auf 1. </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Protokolleintragsbedingung </td> 
    <td colname="col2"> Optional. Definiert die Regeln, nach denen Protokolleinträge für den Export berücksichtigt werden. Weitere Informationen zur <span class="wintitle"> Protokolleintragsbedingung </span> finden Sie unter <a href="../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md"> Konfigurationsdatei für die Protokollverarbeitung </a>. </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Quellen für die Protokollierung </td> 
    <td colname="col2"> <p>Die Datenquellen. <span class="wintitle"> Protokollquellen  </span> können  <span class="filepath"> .vsl- </span> Dateien, Protokolldateien, XML-Dateien oder Daten aus ODBC-kompatiblen Datenbanken sein. Weitere Informationen zu <span class="wintitle"> Protokollquellen </span> finden Sie unter <a href="../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md"> Konfigurationsdatei für die Protokollverarbeitung </a>. </p> <p> <span class="wintitle"> Transform  </span> erwartet, dass alle Quelldaten in chronologischer Reihenfolge innerhalb von lexikografisch geordneten Eingabedateien vorliegen. Wenn diese Anforderung nicht erfüllt ist, sind die As Of-Berechnungen falsch und zusätzliche Eingabedaten können verarbeitet werden, nachdem die Ausgabedateien geschlossen wurden. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Offline-Modus </td> 
    <td colname="col2"> <p>Optional. Wahr oder falsch. Wenn "true", geht <span class="wintitle"> Transformieren Sie </span> davon aus, dass alle Eingabedateien vorhanden sind, wenn die Datenverarbeitung beginnt. Wenn alle Eingabedaten gelesen wurden, schließt <span class="wintitle"> Transform </span> alle Ausgabedateien, ohne auf den Empfang zusätzlicher Daten zu warten. Der Standardwert ist „false“. </p> <p> <p>Hinweis:  Wenn <span class="wintitle"> Offline-Modus </span> auf "true"gesetzt ist, erwartet <span class="wintitle"> Transform </span>, dass alle Quelldaten vorhanden sind, bevor die Verarbeitung beginnt. In der Datei <span class="filepath"> VisualServer.log </span> wird eine Warnmeldung erzeugt, wenn nach dem Schließen der Ausgabedateien zusätzliche Daten empfangen werden. </p> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Neuverarbeitung </td> 
    <td colname="col2"> <p>Optional. Hier können beliebige Zeichen oder Kombinationen von Zeichen eingegeben werden. Wenn Sie diesen Parameter ändern und die Datei auf dem Computer <span class="wintitle"> Transformieren </span> speichern, wird die erneute Verarbeitung der Daten initiiert. </p> <p> Weitere Informationen zur erneuten Verarbeitung Ihrer Daten finden Sie unter <a href="../../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md"> Wiederaufbereitung und erneute Umwandlung </a>. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Phasen </td> 
    <td colname="col2"> <p>Optional. Die Namen der Verarbeitungsphasen, die in <span class="wintitle"> Protokollverarbeitungsdatensatz verwendet werden können, umfassen </span> -Dateien, die zusätzlich zur Data Workbench-Datei <span class="filepath"> Transform.cfg </span> ausgeführt werden. Verarbeitungsphasen bieten eine Möglichkeit, die in <span class="wintitle"> Protokollverarbeitungsdatensatz </span> -Dateien definierten Umwandlungen zu sortieren. Dieser Parameter ist sehr hilfreich, wenn Sie eine oder mehrere Umwandlungen in mehreren <span class="wintitle"> Protokollverarbeitungs-Datensatzaufnahme </span>-Dateien definiert haben und Sie möchten, dass bestimmte Umwandlungen an bestimmten Punkten während des Exportvorgangs durchgeführt werden. </p> <p> Die Reihenfolge, in der Sie die Phasen hier auflisten, bestimmt die Reihenfolge, in der die Umwandlungen in den <span class="wintitle"> Protokollverarbeitungsdatensatz einschließlich </span>-Dateien während des Datenexports ausgeführt werden. <span class="wintitle"> Die Vorverarbeitung  </span> und  <span class="wintitle"> Nachbearbeitung  </span> sind integrierte Phasen.  <span class="wintitle"> Die Vorverarbeitung  </span> ist immer der erste Schritt und die  <span class="wintitle"> Nachbearbeitung  </span> ist immer der letzte Schritt. Standardmäßig gibt es eine benannte Phase namens <span class="wintitle"> Default </span>. </p> <p> <b>So fügen Sie eine neue Verarbeitungsphase hinzu</b> </p> 
      <ul id="ul_869C52DD30E443A496DC6363C3FC62B5"> 
       <li id="li_6493B2A335A8497C9A1BC6292C88CA81"> Klicken Sie im Data Workbench-Fenster <span class="filepath"> Transform.cfg </span> mit der rechten Maustaste auf <span class="uicontrol"> Stages </span> und klicken Sie dann auf <span class="uicontrol"> Neue hinzufügen </span> &gt; <span class="uicontrol"> Staging </span>. </li> 
       <li id="li_EE25E50CEB53450EA6465B08B0AE5442"> Geben Sie einen Namen für die neue Phase ein. </li> 
      </ul> <p> <b>So löschen Sie eine vorhandene Verarbeitungsphase</b> </p> 
      <ul id="ul_4950BC26E0CD4837A4CB377605A52D3C"> 
      <li id="li_A61E2C17966E4F96A1256B8390623B0F"> Klicken Sie mit der rechten Maustaste auf die Nummer der zu löschenden Phase und klicken Sie auf <span class="uicontrol"> </span><i>&lt; <span class="uicontrol"> #stage_number </span></i>. </li> 
      </ul> <p> <p>Hinweis:  Wenn Sie eine Phase in einer <span class="wintitle"> Protokollverarbeitungs-Datensatz-Include </span>-Datei angeben, muss der Name der Phase genau mit dem Namen übereinstimmen, den Sie hier eingeben. Weitere Informationen zu Datensatzaufnahme-Dateien finden Sie unter <a href="../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md"> Datensatzaufnahme-Dateien </a>. </p> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Startzeit </td> 
    <td colname="col2"> <p>Optional. Filtern Sie Daten, um Protokolleinträge mit Zeitstempeln zu dieser Zeit oder danach einzuschließen. Adobe empfiehlt die Verwendung eines der folgenden Zeitformate: </p> 
      <ul id="ul_8F9B82A8AE7F45BE8C7949D2E96C7BEC"> 
       <li id="li_8F7BCFF251CB4F1B87DDA1A259FA9C7B"> 1. Januar 2013 HH:MM:SS EDT </li> 
       <li id="li_4BCE317EE1914074B3642687CFED5FC2"> 1. Januar 2013 HH:MM:SS GMT </li> 
      </ul> <p> Wenn Sie beispielsweise den 29. Juli 2013 um 00:00:00 EDT als Startzeit angeben, werden Daten ab dem 29. Juli 2013 um 12:00:00 Uhr EDT einbezogen. </p> <p> Sie müssen eine Zeitzone angeben. Wenn nicht anders angegeben, wird in der Zeitzone nicht standardmäßig GMT verwendet. Eine Liste der vom Data Workbench-Server unterstützten Zeitzonen-Abkürzungen finden Sie unter <a href="../../../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> Zeitzonencodes </a>. </p> <p> <p>Hinweis:  Der Parameter Start-/Endzeiten für Sensor- und Protokolldateiquellen bezieht sich auf diesen Parameter. </p> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Umwandlungen </td> 
    <td colname="col2"> <p>Optional. Definiert die Transformationen, die auf die Daten angewendet werden sollen. Informationen zu den verfügbaren Transformationstypen finden Sie unter <a href="../../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md"> Datenumwandlungen </a>. </p> <p> <p>Hinweis:  Die folgenden Transformationstypen funktionieren nicht, wenn sie in der Data Workbench-Datei <span class="filepath"> Transform.cfg </span> definiert sind: </p> </p> 
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
>Wenn zusätzliche Daten empfangen werden, nachdem die Ausgabedateien geschlossen wurden (siehe [!DNL Log Sources] und [!DNL Offline Mode] in der obigen Tabelle), erstellt [!DNL Transform] neue Ausgabedateien mit den zusätzlichen Daten. Die Namen der neuen Ausgabedateien werden aus dem Namen der ursprünglichen Ausgabedatei generiert, wobei eine in Klammern eingeschlossene Versionsnummer direkt vor der Erweiterung hinzugefügt wird. Wenn die ursprüngliche Ausgabedatei beispielsweise [!DNL 20070701-ABC.vsl] lautet, werden nachfolgende Versionen dieser Datei [!DNL 20070701-ABC(1).vsl], [!DNL 20070701-ABC(2).vsl] usw. benannt. Beachten Sie, dass die Verwendung der versionierten Dateien als Eingabe für den Data Workbench-Server zu Verarbeitungsfehlern führen kann.
>
>
>Adobe empfiehlt, die Erstellung versionierter Ausgabedateien zu vermeiden, indem sichergestellt wird, dass alle Quelldaten in chronologischer Reihenfolge innerhalb der lexikografisch sortierten Eingabedateien vorliegen und, falls [!DNL Offline Mode] auf &quot;true&quot;gesetzt ist, alle Quelldaten vor Beginn der Verarbeitung vorhanden sind. Weitere Informationen finden Sie in den Einträgen [!DNL Log Sources] und [!DNL Offline Mode] in der obigen Tabelle.

1. Fügen Sie Umwandlungen hinzu, indem Sie mit der rechten Maustaste auf **[!UICONTROL Transformations]** klicken und **[!UICONTROL Add new]** > **[!UICONTROL Transformation type]** klicken. Füllen Sie die Umwandlungsfelder aus.

   Beschreibungen und Beispiele für die Umwandlungsfunktionen finden Sie unter [Datenumwandlungen](../../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md) .

1. Klicken Sie oben im Fenster mit der rechten Maustaste auf **[!UICONTROL (modified)]** und klicken Sie dann auf **[!UICONTROL Save]**.
1. Damit die lokal vorgenommenen Änderungen wirksam werden, klicken Sie in der Spalte [!DNL Profile Manager] mit der rechten Maustaste auf das Häkchen für Data Workbench [!DNL Transform.cfg] in der Spalte [!DNL User] und klicken Sie dann auf **[!UICONTROL Save to]** > **[!UICONTROL profile name]**, wobei der Profilname der Name des Profils ist, für das Sie Daten exportieren. Die erneute Verarbeitung der Daten beginnt nach der Synchronisierung des Profils.

   >[!NOTE]
   >
   >Informationen zur erneuten Verarbeitung Ihrer Daten für den Export finden Sie unter [Wiederaufbereitung und erneute Umwandlung](../../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).
