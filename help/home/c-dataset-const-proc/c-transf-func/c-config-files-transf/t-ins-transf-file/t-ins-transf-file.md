---
description: Die Datei "data workbenchTransform.cfg"enthält die Parameter, die die Protokollquellen, Datenumwandlungen und Exporteure definieren.
title: Datei „Transform.cfg“
uuid: eab5bb70-6de7-4f08-85db-a6cb00abd3ed
exl-id: e84f2536-cb22-4c47-a7a8-270b3c37ece6
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1332'
ht-degree: 2%

---

# Datei „Transform.cfg“{#the-transform-cfg-file}

{{eol}}

Die Datei &quot;data workbenchTransform.cfg&quot;enthält die Parameter, die die Protokollquellen, Datenumwandlungen und Exporteure definieren.

Die von Ihnen definierten Umwandlungen manipulieren die von Sensoren erfassten Rohdaten ( [!DNL .vsl] -Dateien) oder in Textdateien, XML-Dateien oder ODBC-kompatiblen Datenbanken enthalten sind, und geben sie entweder in vorhandene Felder aus, überschreiben die aktuellen Daten oder in neu definierte Felder.

Um die Umwandlungsfunktion zu konfigurieren, bearbeiten Sie die Data Workbench [!DNL Transform.cfg] -Datei im Ordner Datensatz für das Profil, für das Sie Ereignisdaten exportieren möchten. In der Regel ist dieses Profil der Umwandlungsfunktion gewidmet (d. h. Sie führen keine andere Datenverarbeitung durch als die in der Data Workbench definierte Datenverarbeitung. [!DNL Transform.cfg] -Datei). Beachten Sie, dass alle Verarbeitungsanweisungen, die im Abschnitt [!DNL Log Processing Dataset Include] -Dateien für alle geerbten Profile werden zusätzlich zu den in Data Workbench angegebenen angewendet. [!DNL Transform.cfg] -Datei.

Informationen zu Datensatzaufnahme-Dateien finden Sie unter [Datensatzaufnahme-Dateien](../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md).

Wenn die Daten, die Sie exportieren möchten, von einem Data Workbench-Servercluster verarbeitet werden, verarbeitet jeder der Verarbeitungsserver (DPUs) im Cluster die Daten, jedoch nur die erste DPU (Verarbeitungsserver Nr. 0 im [!DNL profile.cfg] -Datei) die Ausgabedaten in das lokale Dateisystem schreiben.

**Bearbeiten der Datei &quot;Transform.cfg&quot;in Data Workbench**

1. Wenn Sie in dem Profil arbeiten, für das Sie Daten exportieren möchten, öffnen Sie die [!DNL Profile Manager] und klicken Sie auf **[!UICONTROL Dataset]** um den Inhalt des Ordners anzuzeigen.
1. Klicken Sie mit der rechten Maustaste auf das Häkchen neben Data Workbench. [!DNL Transform.cfg]Klicken Sie auf **[!UICONTROL Make Local]**. Ein Häkchen für diese Datei wird im [!DNL User] Spalte.
1. Klicken Sie mit der rechten Maustaste auf das neu erstellte Häkchen und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Die Data Workbench [!DNL Transform.cfg] angezeigt.
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
      </ul> </p> <p> Beispiel: 29. Juli 2013 00:00:00 EDT als <span class="wintitle"> Endzeit </span> enthält Daten bis zum 28. Juli 2013, 11.:59:17:00 UHR EDT. </p> <p> Sie müssen eine Zeitzone angeben. Wenn nicht anders angegeben, wird in der Zeitzone nicht standardmäßig GMT verwendet. Eine Liste der vom Data Workbench-Server unterstützten Zeitzonen-Abkürzungen finden Sie unter <a href="../../../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> Zeitzonencodes </a>. </p> <p> Der Parameter Start-/Endzeiten für Sensor- und Protokolldateiquellen bezieht sich auf diesen Parameter. </p> </td> 
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
    <td colname="col2"> Optional. Definiert die Regeln, nach denen Protokolleinträge für den Export berücksichtigt werden. Weitere Informationen zum <span class="wintitle"> Protokolleintragsbedingung </span>, siehe <a href="../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md"> Konfigurationsdatei für die Protokollverarbeitung </a>. </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Quellen für die Protokollierung </td> 
    <td colname="col2"> <p>Die Datenquellen. <span class="wintitle"> Protokollquellen </span> kann <span class="filepath"> .vsl </span> Dateien, Protokolldateien, XML-Dateien oder Daten aus ODBC-konformen Datenbanken. Informationen zu <span class="wintitle"> Protokollquellen </span>, siehe <a href="../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md"> Konfigurationsdatei für die Protokollverarbeitung </a>. </p> <p> <span class="wintitle"> Transform </span> erwartet, dass alle Quelldaten in chronologischer Reihenfolge innerhalb von lexikografisch geordneten Eingabedateien gespeichert werden. Wenn diese Anforderung nicht erfüllt ist, sind die As Of-Berechnungen falsch und zusätzliche Eingabedaten können verarbeitet werden, nachdem die Ausgabedateien geschlossen wurden. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Offline-Modus </td> 
    <td colname="col2"> <p>Optional. True oder false. Wenn "true", <span class="wintitle"> Transform </span> geht davon aus, dass alle Eingabedateien vorhanden sind, wenn mit der Verarbeitung der Daten begonnen wird. Wenn alle Eingabedaten gelesen wurden, <span class="wintitle"> Transform </span> schließt alle Ausgabedateien, ohne auf den Empfang zusätzlicher Daten zu warten. Der Standardwert ist „false“. </p> <p> <p>Hinweis: Wenn <span class="wintitle"> Offline-Modus </span> auf "true"festgelegt ist, <span class="wintitle"> Transform </span> erwartet, dass alle Quelldaten vorhanden sind, bevor die Verarbeitung beginnt. Eine Warnmeldung wird im <span class="filepath"> VisualServer.log </span> Datei, wenn nach dem Schließen der Ausgabedateien zusätzliche Daten empfangen werden. </p> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Neuverarbeitung </td> 
    <td colname="col2"> <p>Optional. Hier können beliebige Zeichen oder Kombinationen von Zeichen eingegeben werden. Ändern Sie diesen Parameter und speichern Sie die Datei im <span class="wintitle"> Transform </span> -Maschine initiiert eine erneute Datenverarbeitung. </p> <p> Informationen zur erneuten Verarbeitung Ihrer Daten finden Sie unter <a href="../../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md"> Wiederaufbereitung und erneute Umwandlung </a>. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Phasen </td> 
    <td colname="col2"> <p>Optional. Die Namen der Verarbeitungsschritte, die in <span class="wintitle"> Datensatz für die Protokollverarbeitung einschließen </span> -Dateien, die zusätzlich zur Data Workbench ausgeführt werden <span class="filepath"> Transform.cfg </span> -Datei. Verarbeitungsschritte bieten eine Möglichkeit, die in <span class="wintitle"> Datensatz für die Protokollverarbeitung einschließen </span> Dateien. Dieser Parameter ist sehr hilfreich, wenn Sie eine oder mehrere Umwandlungen innerhalb mehrerer <span class="wintitle"> Datensatz für die Protokollverarbeitung einschließen </span> -Dateien und Sie möchten, dass bestimmte Umwandlungen während des Exportvorgangs an bestimmten Punkten vorgenommen werden. </p> <p> Die Reihenfolge, in der Sie die Phasen hier auflisten, bestimmt die Reihenfolge, in der die Umwandlungen in der <span class="wintitle"> Datensatz für die Protokollverarbeitung einschließen </span> -Dateien werden während des Datenexports ausgeführt. <span class="wintitle"> Vorverarbeitung </span> und <span class="wintitle"> Nachbearbeitung </span> sind eingebaute Phasen; <span class="wintitle"> Vorverarbeitung </span> ist immer der erste Schritt und <span class="wintitle"> Nachbearbeitung </span> ist immer der letzte Schritt. Standardmäßig gibt es eine benannte Phase namens <span class="wintitle"> Standard </span>. </p> <p> <b>So fügen Sie eine neue Verarbeitungsphase hinzu</b> </p> 
      <ul id="ul_869C52DD30E443A496DC6363C3FC62B5"> 
       <li id="li_6493B2A335A8497C9A1BC6292C88CA81"> In der Data Workbench <span class="filepath"> Transform.cfg </span> Fenster, Rechtsklick <span class="uicontrol"> Phasen </span>Klicken Sie auf <span class="uicontrol"> Neu hinzufügen </span> &gt; <span class="uicontrol"> Staging </span>. </li> 
       <li id="li_EE25E50CEB53450EA6465B08B0AE5442"> Geben Sie einen Namen für die neue Phase ein. </li> 
      </ul> <p> <b>So löschen Sie eine vorhandene Verarbeitungsphase</b> </p> 
      <ul id="ul_4950BC26E0CD4837A4CB377605A52D3C"> 
      <li id="li_A61E2C17966E4F96A1256B8390623B0F"> Klicken Sie mit der rechten Maustaste auf die Nummer der Phase, die Sie löschen möchten, und klicken Sie auf <span class="uicontrol"> Entfernen </span><i>&lt; <span class="uicontrol"> #stage_number </span>&gt;</i>. </li> 
      </ul> <p> <p>Hinweis: Wenn Sie eine Bühne in einem <span class="wintitle"> Datensatz für die Protokollverarbeitung einschließen </span> -Datei muss der Name der Bühne genau mit dem Namen übereinstimmen, den Sie hier eingeben. Weitere Informationen zu Datensatzaufnahme-Dateien finden Sie unter <a href="../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md"> Datensatzaufnahme-Dateien </a>. </p> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Startzeit </td> 
    <td colname="col2"> <p>Optional. Filtern Sie Daten, um Protokolleinträge mit Zeitstempeln zu dieser Zeit oder danach einzuschließen. Adobe empfiehlt die Verwendung eines der folgenden Zeitformate: </p> 
      <ul id="ul_8F9B82A8AE7F45BE8C7949D2E96C7BEC"> 
       <li id="li_8F7BCFF251CB4F1B87DDA1A259FA9C7B"> 1. Januar 2013 HH:MM:SS EDT </li> 
       <li id="li_4BCE317EE1914074B3642687CFED5FC2"> 1. Januar 2013 HH:MM:SS GMT </li> 
      </ul> <p> Beispiel: 29. Juli 2013 00:00:00 EDT als Startzeit umfasst Daten ab dem 29. Juli 2013, 12:00:00 UHR EDT. </p> <p> Sie müssen eine Zeitzone angeben. Wenn nicht anders angegeben, wird in der Zeitzone nicht standardmäßig GMT verwendet. Eine Liste der vom Data Workbench-Server unterstützten Zeitzonen-Abkürzungen finden Sie unter <a href="../../../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> Zeitzonencodes </a>. </p> <p> <p>Hinweis: Der Parameter Start-/Endzeiten für Sensor- und Protokolldateiquellen bezieht sich auf diesen Parameter. </p> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Umwandlungen </td> 
    <td colname="col2"> <p>Optional. Definiert die Transformationen, die auf die Daten angewendet werden sollen. Informationen zu den verfügbaren Transformationstypen finden Sie unter <a href="../../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md"> Datenumwandlungen </a>. </p> <p> <p>Hinweis: Die folgenden Transformationstypen funktionieren nicht, wenn sie in Data Workbench definiert sind <span class="filepath"> Transform.cfg </span> Datei: </p> </p> 
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
>Wenn zusätzliche Daten empfangen werden, nachdem die Ausgabedateien geschlossen wurden (siehe [!DNL Log Sources] und [!DNL Offline Mode] in der obigen Tabelle), [!DNL Transform] erstellt neue Ausgabedateien mit den Zusatzdaten. Die Namen der neuen Ausgabedateien werden aus dem Namen der ursprünglichen Ausgabedatei generiert, wobei eine in Klammern eingeschlossene Versionsnummer direkt vor der Erweiterung hinzugefügt wird. Wenn die ursprüngliche Ausgabedatei beispielsweise [!DNL 20070701-ABC.vsl], werden nachfolgende Versionen dieser Datei [!DNL 20070701-ABC(1).vsl], [!DNL 20070701-ABC(2).vsl]usw. Beachten Sie, dass die Verwendung der versionierten Dateien als Eingabe für den Data Workbench-Server zu Verarbeitungsfehlern führen kann.
>
>
>Adobe empfiehlt, die Erstellung versionierter Ausgabedateien zu vermeiden, indem sichergestellt wird, dass alle Quelldaten in chronologischer Reihenfolge innerhalb von lexikografisch geordneten Eingabedateien und, falls [!DNL Offline Mode] auf &quot;true&quot;gesetzt ist, dass alle Quelldaten vorhanden sind, bevor die Verarbeitung beginnt. Weitere Informationen finden Sie unter [!DNL Log Sources] und [!DNL Offline Mode] Einträge in der obigen Tabelle.

1. Hinzufügen von Umwandlungen durch Rechtsklick **[!UICONTROL Transformations]** und klicken **[!UICONTROL Add new]** > **[!UICONTROL Transformation type]**. Füllen Sie die Umwandlungsfelder aus.

   Siehe [Datenumwandlungen](../../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md) für Beschreibungen und Beispiele der Umwandlungsfunktionen.

1. Rechtsklick **[!UICONTROL (modified)]** Klicken Sie oben im Fenster auf **[!UICONTROL Save]**.
1. Damit die lokal vorgenommenen Änderungen wirksam werden, finden Sie im [!DNL Profile Manager]klicken Sie mit der rechten Maustaste auf das Häkchen für Data Workbench [!DNL Transform.cfg] im [!DNL User] und klicken Sie auf **[!UICONTROL Save to]** >  **[!UICONTROL profile name]**, wobei der Profilname der Name des Profils ist, für das Sie Daten exportieren. Die erneute Verarbeitung der Daten beginnt nach der Synchronisierung des Profils.

   >[!NOTE]
   >
   >Informationen zur erneuten Verarbeitung Ihrer Daten für den Export finden Sie unter [Wiederaufbereitung und erneute Umwandlung](../../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).
