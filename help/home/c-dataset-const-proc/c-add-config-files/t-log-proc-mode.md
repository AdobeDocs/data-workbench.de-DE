---
description: Die Konfigurationsdatei "Log Processing Mode.cfg"ermöglicht es Ihnen, die Verarbeitung von Daten in einem Datensatz anzuhalten, Offlinequellen anzugeben oder anzugeben, wie oft der Data Workbench-Server seine Statusdateien speichert.
title: Log Processing Mode.cfg
uuid: 1f1e5d8b-80e7-4423-bb03-56e706a1b7b4
exl-id: e252b815-e691-490d-9ac9-88bb1fd2c64d
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '956'
ht-degree: 3%

---

# Log Processing Mode.cfg{#log-processing-mode-cfg}

Die Konfigurationsdatei &quot;Log Processing Mode.cfg&quot;ermöglicht es Ihnen, die Verarbeitung von Daten in einem Datensatz anzuhalten, Offlinequellen anzugeben oder anzugeben, wie oft der Data Workbench-Server seine Statusdateien speichert.

Änderungen an der Datei [!DNL Log Processing Mode.cfg], einschließlich des Hinzufügens oder Entfernen von Quellen, führen nicht zur erneuten Verarbeitung der Daten.

**So bearbeiten Sie die Datei &quot;Log Processing Mode.cfg&quot;für ein DataSet-Profil**

1. Öffnen Sie beim Arbeiten im DataSet-Profil das [!DNL Profile Manager] und klicken Sie auf **[!UICONTROL Dataset]**, um den Inhalt anzuzeigen.

   >[!NOTE]
   >
   >Wenn sich die [!DNL Log Processing Mode.cfg]-Datei nicht im Ordner des gewünschten Profils befindet, müssen Sie diese Datei aus dem Basisordner auf dem Datenbasis-Servercomputer in den Ordner des Profils kopieren.

   Informationen zum Öffnen und Arbeiten mit [!DNL Profile Manager,] finden Sie im *Data Workbench Benutzerhandbuch*.

1. Klicken Sie mit der rechten Maustaste auf das Häkchen neben dem Namen der Konfigurationsdatei und klicken Sie auf **[!UICONTROL Make Local]**. In der Spalte [!DNL User] wird ein Häkchen für diese Datei angezeigt.
1. Klicken Sie mit der rechten Maustaste auf das neu erstellte Häkchen und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Das Konfigurationsfenster wird angezeigt.
1. Bearbeiten Sie die Parameter in der Konfigurationsdatei mithilfe der folgenden Tabelle als Anleitung.

   >[!NOTE]
   >
   >Einige der Parameter in der Datei [!DNL Log Processing Mode.cfg] haben Namen, die [!DNL Fast Input] oder [!DNL Fast Merge] enthalten. [!DNL Fast Input]bezieht sich auf die Phase der Protokollverarbeitung der Dataset-Konstruktion und ist für etwa die Hälfte der gesamten Datenmenge-Verarbeitungszeit verantwortlich. [!DNL Fast Merge] bezieht sich nur auf die Umwandlungsphase der Datensatzerstellung, wenn der Protokollverarbeitung vorausgeht. [!DNL Fast Merge] nicht während der Umgestaltung erfolgt, die durch das Ändern einer  [!DNL Transformation Dataset Configuration] Datei resultiert. Wie [!DNL Fast Input] ist [!DNL Fast Merge] auch für etwa die Hälfte der Verarbeitungszeit des Datensatzes verantwortlich.

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
      <td colname="col2"> <p>Ein Abstimmungsparameter, der die Effizienz der Datenumwandlung beeinflusst. Der Standardwert lautet 128000000. </p> <p> <p>Hinweis:  Sie sollten diesen Wert nicht ändern, ohne die Adobe zu konsultieren. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Fast Input Decision Ratio </td> 
      <td colname="col2"> <p>Ein Tuning-Parameter, der das Verhältnis zwischen insgesamt ungelesenen und ungelesenen Protokollbyte angibt, bei dem das System in den Modus <span class="wintitle"> Fast Input</span> (und danach <span class="wintitle"> Fast Merge</span>) wechselt, anstatt Daten in Echtzeit zu verarbeiten. </p> <p> Der Standardwert ist 200, d. h., das System ruft den Modus <span class="wintitle"> Fast Input</span> aus dem Echtzeitmodus auf, wenn die ungelesenen Protokolldaten das 1/200. der Gesamtdaten betragen. Bei einem höheren Entscheidungsverhältnis wird das System einfacher in den Modus <span class="wintitle"> Fast Input</span> einsteigen, während bei einem niedrigeren Verhältnis die Wahrscheinlichkeit, in den Modus <span class="wintitle"> Fast Input</span> einzusteigen, geringer ist. </p> <p> <p>Hinweis: Wenn Sie den Parameter auf 0 setzen, wird verhindert, dass das System überhaupt in den Modus <span class="wintitle"> Fast Input</span> wechselt, auch bei der Erstverarbeitung. Wenn Sie den Parameter auf 1.1 setzen, kann das System während der ersten Verarbeitung, jedoch nicht für die anschließende Verarbeitung, <span class="wintitle"> Fast Input</span> eingeben. Adobe empfiehlt die Verwendung von Werten zwischen 0 und 1.1 nicht. Weitere Informationen zum Festlegen dieses Parameters erhalten Sie bei der Adobe. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Schnelle Eingabe-FIFO-Byte </td> 
      <td colname="col2"> <p>Ein Tuning-Parameter, der die Speichernutzung und die Systemleistung während der Datenverarbeitung ausgleicht. Der Standardwert lautet 120000000. </p> <p> <p>Hinweis:  Sie sollten diesen Wert nicht ändern, ohne die Adobe zu konsultieren. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Schnellzusammenführungs-Pufferbyte </td> 
      <td colname="col2"> <p>Ein Tuning-Parameter, der die Speichernutzung und die Systemleistung während der Datenverarbeitung ausgleicht. Der Standardwert lautet 128000000. </p> <p> <p>Hinweis:  Sie sollten diesen Wert nicht ändern, ohne die Adobe zu konsultieren. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Offline-Quellen </td> 
      <td colname="col2"> <p>Maske der Offline-Protokollquelle. </p> <p> <b> So legen Sie eine Offline-Quelle fest</b> 
      <ul id="ul_569B90E9A85246F88906FA5444F8A93E"> 
       <li id="li_3EF182CEF4A44106B5267175EC62B9AB"> Klicken Sie mit der rechten Maustaste auf <span class="uicontrol"> Offline-Quellen</span> und klicken Sie dann auf <span class="uicontrol"> Hinzufügen neuen </span> &gt; <span class="uicontrol"> Quelle</span>. </li> 
       <li id="li_E8FBA212F4784B1A830745A90BB3AF90"> Geben Sie im Parameter für die neue Quelle die Maske der Protokollsequenz ein. Bei Sensor-Protokollquellen mit Dateinamen im Format JJJMMTT-<i>SENSORID</i>.vsl wird bei der Maske die Groß-/Kleinschreibung beachtet. <i></i> Bei Protokollquellen für Protokolldateien ist die Maske die vom <span class="wintitle"> Maskenmuster</span> extrahierte Zeichenfolge. Siehe <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e"> Protokolldateien</a>. </li> 
      </ul> </p> <p> Das Hinzufügen oder Entfernen von Quellen aus Offline-Quellen führt nicht zur erneuten Verarbeitung des Datensatzes. </p> <p> Die Zeitmessungen werden für die Verarbeitung der Online-Quellen des Profils beibehalten. Wenn die Offline-Quelle erneut online ist, wird die Verarbeitung eingehender Protokolldateien für diese Quelle fortgesetzt. </p> <p> Wenn eine Quelle wieder online ist, sollten Sie sie aus Offline-Quellen entfernen. Andernfalls behandelt der Data Workbench-Server die Quelle als Online-Quelle und aktualisiert die Ausführungszeit, solange die Quelle Daten sendet. Wenn die Quelle wieder offline ist, werden die Zeitüberschreitungsmessungen beendet. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> angehalten </td> 
      <td colname="col2"> Wahr oder falsch. Wenn "true", werden neue Daten nicht in den Datensatz verarbeitet. Der Standardwert ist „false“. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Echte Verzögerung </td> 
      <td colname="col2"> Die Zeitspanne in Sekunden, die Data Workbench Server zwischen den Zeitabständen der Verarbeitung der Daten in den Datensatz wartet. Wenn dieser Wert auf null gesetzt ist, versucht das System, mit den eingehenden Daten in Echtzeit Schritt zu halten. Der Standardwert ist null (0), Sie können diesen Wert jedoch erhöhen, um die CPU-Auslastung zu verringern. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> FIFO-Byte in Echtzeit </td> 
      <td colname="col2"> <p>Die Menge des Speichers in Bytes, der zum Speichern von Daten verwendet wird, die darauf warten, in den Datensatz verarbeitet zu werden. Möglicherweise müssen Sie diesen Wert entsprechend der Anzahl der Sekunden ändern, die Sie für "Echte Verzögerung"angeben. Der Standardwert lautet 16000000. </p> <p> <p>Hinweis:  Sie sollten diesen Wert nicht ändern, ohne die Adobe zu konsultieren. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Speicherintervall (s) </td> 
      <td colname="col2"> <p>Häufigkeit, mit der der Data Workbench-Server seine Statusdateien speichert. Der Standardwert lautet 3600. </p> <p> <p>Hinweis:  Sie sollten diesen Wert nicht ändern, ohne die Adobe zu konsultieren. </p> </p> </td> 
   </tr> 
   </tbody> 
   </table>

   Beim Bearbeiten der Datei [!DNL Log Processing Mode.cfg] in einem Data Workbench-Fenster können Sie Tastenkombinationen für grundlegende Bearbeitungsfunktionen verwenden, z. B. Ausschneiden (Strg+x), Kopieren (Strg+c), Einfügen (Strg+v), Rückgängigmachen (Strg+Z), Wiederholen (Strg+Umschalt+Z), Abschnitt (Klicken+Ziehen) und Alles auswählen (Strg+a). Darüber hinaus können Sie mithilfe der Tastaturbefehle Text aus einer Konfigurationsdatei ( [!DNL .cfg]) in eine andere kopieren und einfügen.

1. Klicken Sie mit der rechten Maustaste auf **[!UICONTROL (modified)]** oben im Fenster und klicken Sie auf **[!UICONTROL Save]**.
1. Klicken Sie in der Spalte [!DNL Profile Manager] mit der rechten Maustaste auf das Häkchen für die Datei in der Spalte [!DNL User] und klicken Sie dann auf **[!UICONTROL Save to]** > **[!UICONTROL datasetprofile name]**.

   >[!NOTE]
   >
   >Speichern Sie die geänderte Konfigurationsdatei nicht in einem der von der Adobe bereitgestellten internen Profil, da Ihre Änderungen bei der Installation von Updates auf diesen Profilen überschrieben werden.
