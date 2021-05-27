---
description: Die Konfigurationsdatei "Log Processing Mode.cfg"ermöglicht es Ihnen, die Verarbeitung von Daten in einem Datensatz anzuhalten, Offline-Quellen anzugeben oder anzugeben, wie häufig der Data Workbench-Server seine Statusdateien speichert.
title: Log Processing Mode.cfg
uuid: 1f1e5d8b-80e7-4423-bb03-56e706a1b7b4
exl-id: e252b815-e691-490d-9ac9-88bb1fd2c64d
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '956'
ht-degree: 3%

---

# Log Processing Mode.cfg{#log-processing-mode-cfg}

Die Konfigurationsdatei &quot;Log Processing Mode.cfg&quot;ermöglicht es Ihnen, die Verarbeitung von Daten in einem Datensatz anzuhalten, Offline-Quellen anzugeben oder anzugeben, wie häufig der Data Workbench-Server seine Statusdateien speichert.

Änderungen an der [!DNL Log Processing Mode.cfg]-Datei, einschließlich Hinzufügen oder Entfernen von Quellen, führen nicht zur erneuten Verarbeitung der Daten.

**So bearbeiten Sie die Datei &quot;Log Processing Mode.cfg&quot;für ein Datensatzprofil**

1. Wenn Sie in Ihrem Datensatzprofil arbeiten, öffnen Sie [!DNL Profile Manager] und klicken Sie auf **[!UICONTROL Dataset]** , um dessen Inhalt anzuzeigen.

   >[!NOTE]
   >
   >Wenn sich die Datei [!DNL Log Processing Mode.cfg] nicht im Verzeichnis für das gewünschte Profil befindet, müssen Sie diese Datei aus dem Basisverzeichnis auf dem Computer des Data Workbench-Servers in das Verzeichnis des Profils kopieren.

   Informationen zum Öffnen und Verwenden von [!DNL Profile Manager,] finden Sie im *Data Workbench-Benutzerhandbuch*.

1. Klicken Sie mit der rechten Maustaste auf das Häkchen neben dem Namen der Konfigurationsdatei und klicken Sie auf **[!UICONTROL Make Local]**. Ein Häkchen für diese Datei wird in der Spalte [!DNL User] angezeigt.
1. Klicken Sie mit der rechten Maustaste auf das neu erstellte Häkchen und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Das Konfigurationsfenster wird angezeigt.
1. Bearbeiten Sie die Parameter in der Konfigurationsdatei mithilfe der folgenden Tabelle als Anleitung.

   >[!NOTE]
   >
   >Einige der Parameter in der Datei [!DNL Log Processing Mode.cfg] haben Namen, die [!DNL Fast Input] oder [!DNL Fast Merge] enthalten. [!DNL Fast Input]bezieht sich auf die Protokollverarbeitungsphase der Datensatzerstellung und ist für ungefähr die Hälfte der gesamten Datensatzverarbeitungszeit verantwortlich. [!DNL Fast Merge] bezieht sich auf die Umwandlungsphase der Datensatzerstellung nur, wenn vor der Protokollverarbeitung eine Protokollverarbeitung erfolgt. [!DNL Fast Merge] nicht während der Umformatierung erfolgt, die durch die Änderung einer  [!DNL Transformation Dataset Configuration] Datei entsteht. Wie [!DNL Fast Input] ist [!DNL Fast Merge] auch für ungefähr die Hälfte der Datensatzverarbeitungszeit verantwortlich.

   <table id="table_1BF356E21C0E4119A277F40CEC5D7A21"> 
   <thead> 
   <tr> 
      <th colname="col1" class="entry"> Parameter </th> 
      <th colname="col2" class="entry"> Beschreibung </th> 
   </tr> 
   </thead>
   <tbody> 
   <tr> 
      <td colname="col1"> Cloud Bytes </td> 
      <td colname="col2"> <p>Ein Tuning-Parameter, der die Effizienz der Datenumwandlung beeinflusst. Der Standardwert lautet 128000000. </p> <p> <p>Hinweis:  Sie sollten diesen Wert nicht ändern, ohne die Adobe zu konsultieren. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Fast Input Decisioning Ratio </td> 
      <td colname="col2"> <p>Ein Tuning-Parameter, der das Verhältnis zwischen Gesamtanzahl und ungelesenen Log-Bytes angibt, in dem das System den Modus <span class="wintitle"> Fast Input</span> (und anschließend <span class="wintitle"> Fast Merge</span>) betritt, anstatt Daten in Echtzeit zu verarbeiten. </p> <p> Der Standardwert ist 200, was bedeutet, dass das System den Modus <span class="wintitle"> Schnelle Eingabe</span> aus dem Echtzeitmodus aufruft, wenn die ungelesenen Protokolldaten das 1/200. der Gesamtdaten betragen. Ein höheres Entscheidungsverhältnis sorgt dafür, dass das System den Modus <span class="wintitle"> Fast Input</span> leichter aufruft, während ein niedrigeres Verhältnis die Wahrscheinlichkeit verringert, in den Modus <span class="wintitle"> Fast Input</span> zu wechseln. </p> <p> <p>Hinweis: Wenn Sie den Parameter auf 0 setzen, wird verhindert, dass das System überhaupt in den Modus <span class="wintitle"> Fast Input</span> wechselt, auch bei der Erstverarbeitung. Wenn Sie den Parameter auf 1.1 setzen, kann das System während der anfänglichen Verarbeitung <span class="wintitle"> Fast Input</span> eingeben, jedoch nicht für die nachfolgende Verarbeitung. Adobe rät von der Verwendung von Werten zwischen 0 und 1.1 ab. Weiterführende Informationen zur Festlegung dieses Parameters erhalten Sie von der Adobe. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Fast Input FIFO Bytes </td> 
      <td colname="col2"> <p>Ein Tuning-Parameter, der die Speichernutzung und die Systemleistung während der Datenverarbeitung gleicht. Der Standardwert lautet 120000000. </p> <p> <p>Hinweis:  Sie sollten diesen Wert nicht ändern, ohne die Adobe zu konsultieren. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Schnelles Zusammenführen von Pufferbyte </td> 
      <td colname="col2"> <p>Ein Tuning-Parameter, der die Speichernutzung und die Systemleistung während der Datenverarbeitung gleicht. Der Standardwert lautet 128000000. </p> <p> <p>Hinweis:  Sie sollten diesen Wert nicht ändern, ohne die Adobe zu konsultieren. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Offline-Quellen </td> 
      <td colname="col2"> <p>Maske der Offline-Protokollquelle. </p> <p> <b> So legen Sie eine Offline-Quelle fest</b> 
      <ul id="ul_569B90E9A85246F88906FA5444F8A93E"> 
       <li id="li_3EF182CEF4A44106B5267175EC62B9AB"> Klicken Sie mit der rechten Maustaste auf <span class="uicontrol"> Offline-Quellen</span> und klicken Sie dann auf <span class="uicontrol"> Hinzufügen neuer</span> &gt; <span class="uicontrol"> Quelle</span>. </li> 
       <li id="li_E8FBA212F4784B1A830745A90BB3AF90"> Geben Sie im Parameter für die neue Quelle die Maske der Protokollsequenz ein. Bei Sensor-Protokollquellen mit Dateinamen im Format JJJMMTT-<i>SENSORID</i>.vsl wird bei der Maske <i>SENSORID.SENSORID</i> zwischen Groß- und Kleinschreibung unterschieden. Bei Protokollquellen für Protokolldateien ist die Maske die Zeichenfolge, die vom <span class="wintitle"> Maskenmuster</span> extrahiert wird. Siehe <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e"> Protokolldateien</a>. </li> 
      </ul> </p> <p> Das Hinzufügen oder Entfernen von Quellen aus Offline-Quellen führt nicht zur erneuten Verarbeitung des Datensatzes. </p> <p> Ab der Zeit werden Messungen für die Verarbeitung der Online-Quellen des Profils durchgeführt. Wenn die Offline-Quelle wieder online ist, wird die Verarbeitung der eingehenden Protokolldateien für diese Quelle fortgesetzt. </p> <p> Immer wenn eine Quelle wieder online geht, sollten Sie sie aus Offline-Quellen entfernen. Andernfalls behandelt der Data Workbench-Server die Quelle als Online-Quelle und aktualisiert die Ausführungsdauer, solange die Quelle Daten sendet. Wenn die Quelle wieder offline geht, werden die Ausführungszeitmessungen angehalten. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> angehalten </td> 
      <td colname="col2"> Wahr oder falsch. Wenn "true", werden neue Daten nicht in den Datensatz verarbeitet. Der Standardwert ist „false“. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Echtzeit-Verzögerung </td> 
      <td colname="col2"> Die Zeit in Sekunden, die der Data Workbench-Server zwischen den Zeitintervallen der Datenverarbeitung in den Datensatz wartet. Wenn dieser Wert auf null gesetzt ist, versucht das System, mit den eingehenden Daten in Echtzeit Schritt zu halten. Der Standardwert ist null (0), Sie können diesen Wert jedoch erhöhen, um die CPU-Last zu reduzieren. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> FIFO-Byte in Echtzeit </td> 
      <td colname="col2"> <p>Die Menge an Speicher in Bytes, die zum Speichern von Daten verwendet wird, die auf die Verarbeitung in dem Datensatz warten. Möglicherweise müssen Sie diesen Wert anhand der Anzahl der Sekunden ändern, die Sie für die Echtzeit-Verzögerung angeben. Der Standardwert lautet 16000000. </p> <p> <p>Hinweis:  Sie sollten diesen Wert nicht ändern, ohne die Adobe zu konsultieren. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Speicherintervall (Sek.) </td> 
      <td colname="col2"> <p>Häufigkeit, mit der der Data Workbench-Server seine Statusdateien speichert. Der Standardwert lautet 3600. </p> <p> <p>Hinweis:  Sie sollten diesen Wert nicht ändern, ohne die Adobe zu konsultieren. </p> </p> </td> 
   </tr> 
   </tbody> 
   </table>

   Beim Bearbeiten der Datei [!DNL Log Processing Mode.cfg] in einem Data Workbench-Fenster können Sie Tastaturbefehle für grundlegende Bearbeitungsfunktionen verwenden, z. B. Ausschneiden (Strg+x ), Kopieren (Strg+C), Einfügen (Strg+V ), Rückgängigmachen (Strg+Z ), Wiederholen (Strg+Umschalt+Z ), Auswahl des Bereichs (Klicken+Ziehen) und Auswahl aller Elemente (Strg+A ). Darüber hinaus können Sie die Verknüpfungen verwenden, um Text aus einer Konfigurationsdatei ( [!DNL .cfg]) in eine andere einzufügen.

1. Klicken Sie oben im Fenster mit der rechten Maustaste auf **[!UICONTROL (modified)]** und klicken Sie auf **[!UICONTROL Save]**.
1. Klicken Sie in der Spalte [!DNL Profile Manager] mit der rechten Maustaste auf das Häkchen für die Datei in der Spalte [!DNL User] und klicken Sie dann auf **[!UICONTROL Save to]** > **[!UICONTROL datasetprofile name]**.

   >[!NOTE]
   >
   >Speichern Sie die geänderte Konfigurationsdatei nicht in einem der von Adobe bereitgestellten internen Profile, da Ihre Änderungen bei der Installation von Updates für diese Profile überschrieben werden.
