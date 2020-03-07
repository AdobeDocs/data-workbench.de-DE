---
description: Die Konfigurationsdatei "Log Processing Mode.cfg"ermöglicht es Ihnen, die Verarbeitung von Daten in einem Datensatz anzuhalten, Offlinequellen anzugeben oder anzugeben, wie oft der Data Workbench-Server seine Statusdateien speichert.
solution: Analytics
title: Protokollverarbeitungsmodus.cfg
topic: Data workbench
uuid: 1f1e5d8b-80e7-4423-bb03-56e706a1b7b4
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Protokollverarbeitungsmodus.cfg{#log-processing-mode-cfg}

Die Konfigurationsdatei &quot;Log Processing Mode.cfg&quot;ermöglicht es Ihnen, die Verarbeitung von Daten in einem Datensatz anzuhalten, Offlinequellen anzugeben oder anzugeben, wie oft der Data Workbench-Server seine Statusdateien speichert.

Änderungen an der [!DNL Log Processing Mode.cfg] Datei, einschließlich des Hinzufügens oder Entfernen von Quellen, führen nicht zur erneuten Verarbeitung der Daten.

**So bearbeiten Sie die Datei &quot;Log Processing Mode.cfg&quot;für ein Datensatzprofil**

1. Öffnen Sie bei der Arbeit im DataSet-Profil die Datei [!DNL Profile Manager] und klicken Sie auf **[!UICONTROL Dataset]** , um deren Inhalt anzuzeigen.

   >[!NOTE]
   >
   >Wenn sich die [!DNL Log Processing Mode.cfg] Datei nicht im Ordner des gewünschten Profils befindet, müssen Sie diese Datei aus dem Basisordner auf dem Datenbasis-Servercomputer in den Ordner des Profils kopieren.

   Informationen zum Öffnen und Arbeiten mit dem [!DNL Profile Manager,] Handbuch *Data Workbench finden Sie im Benutzerhandbuch*.

1. Klicken Sie mit der rechten Maustaste auf das Häkchen neben dem Namen der Konfigurationsdatei und klicken Sie auf **[!UICONTROL Make Local]**. Ein Häkchen für diese Datei wird in der [!DNL User] Spalte angezeigt.
1. Klicken Sie mit der rechten Maustaste auf das neu erstellte Häkchen und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Das Konfigurationsfenster wird angezeigt.
1. Bearbeiten Sie die Parameter in der Konfigurationsdatei mithilfe der folgenden Tabelle als Anleitung.

   >[!NOTE]
   >
   >Einige der Parameter in der [!DNL Log Processing Mode.cfg] Datei haben Namen, die einschließen [!DNL Fast Input] oder [!DNL Fast Merge]. [!DNL Fast Input]bezieht sich auf die Phase der Protokollverarbeitung der Dataset-Konstruktion und ist für etwa die Hälfte der gesamten Datenmenge-Verarbeitungszeit verantwortlich. [!DNL Fast Merge] bezieht sich nur auf die Umwandlungsphase der Datensatzerstellung, wenn der Protokollverarbeitung vorausgeht. [!DNL Fast Merge] nicht während der Umgestaltung erfolgt, die durch das Ändern einer [!DNL Transformation Dataset Configuration] Datei resultiert. Wie [!DNL Fast Input]ist [!DNL Fast Merge] auch für etwa die Hälfte der Verarbeitungszeit des Datensatzes verantwortlich.

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
      <td colname="col2"> <p>Ein Abstimmungsparameter, der die Effizienz der Datenumwandlung beeinflusst. Der Standardwert lautet 128000000. </p> <p> <p>Hinweis:  Sie sollten diesen Wert nicht ohne Rücksprache mit Adobe ändern. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Fast Input Decision Ratio </td> 
      <td colname="col2"> <p>Ein Tuning-Parameter, der das Verhältnis zwischen insgesamt ungelesenen und ungelesenen Protokollbyte angibt, bei dem das System in den <span class="wintitle"> schnellen Eingabemodus</span> (und anschließend in der <span class="wintitle"> Schnellzusammenführung</span>) wechselt, anstatt Daten in Echtzeit zu verarbeiten. </p> <p> Der Standardwert ist 200, d. h., das System ruft den <span class="wintitle"> schnellen Eingabemodus</span> aus dem Echtzeitmodus auf, wenn die ungelesenen Protokolldaten das 1/200. der Gesamtdaten betragen. Ein höheres Entscheidungsverhältnis sorgt dafür, dass das System schneller in den <span class="wintitle"> Fast-Input</span> -Modus wechselt, während ein niedrigeres Verhältnis die Wahrscheinlichkeit verringert, dass es in den <span class="wintitle"> Fast-Input</span> -Modus wechselt. </p> <p> <p>Hinweis: Wenn Sie den Parameter auf 0 einstellen, wird verhindert, dass das System überhaupt in den <span class="wintitle"> schnellen Eingabemodus</span> wechselt, auch bei der Erstverarbeitung. Wenn Sie den Parameter auf 1.1 setzen, kann das System während der ersten Verarbeitung, nicht aber bei der anschließenden Verarbeitung, <span class="wintitle"> schnell Input</span> eingeben. Adobe empfiehlt die Verwendung von Werten zwischen 0 und 1.1 nicht. Weitere Informationen zum Festlegen dieses Parameters erhalten Sie bei Adobe. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Schnelle Eingabe-FIFO-Byte </td> 
      <td colname="col2"> <p>Ein Tuning-Parameter, der die Speichernutzung und die Systemleistung während der Datenverarbeitung ausgleicht. Der Standardwert lautet 120000000. </p> <p> <p>Hinweis:  Sie sollten diesen Wert nicht ohne Rücksprache mit Adobe ändern. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Schnellzusammenführungs-Pufferbyte </td> 
      <td colname="col2"> <p>Ein Tuning-Parameter, der die Speichernutzung und die Systemleistung während der Datenverarbeitung ausgleicht. Der Standardwert lautet 128000000. </p> <p> <p>Hinweis:  Sie sollten diesen Wert nicht ohne Rücksprache mit Adobe ändern. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Offline-Quellen </td> 
      <td colname="col2"> <p>Maske der Offline-Protokollquelle. </p> <p> <b> So legen Sie eine Offline-Quelle fest</b> 
      <ul id="ul_569B90E9A85246F88906FA5444F8A93E"> 
       <li id="li_3EF182CEF4A44106B5267175EC62B9AB"> Klicken Sie mit der rechten Maustaste auf <span class="uicontrol"> Offline-Quellen</span>und dann auf <span class="uicontrol"> Neue</span> hinzufügen &gt; <span class="uicontrol"> Quelle</span>. </li> 
       <li id="li_E8FBA212F4784B1A830745A90BB3AF90"> Geben Sie im Parameter für die neue Quelle die Maske der Protokollsequenz ein. Bei Sensor-Protokollquellen mit Dateinamen des Formats JJJJMMTT-<i>SENSORID</i>.vsl ist die Maske <i>SENSORID.SENSORID</i> Groß-/Kleinschreibung zu beachten. Bei Protokollquellen für Protokolldateien ist die Maske die vom <span class="wintitle"> Maskenmuster</span>extrahierte Zeichenfolge. See <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e"> Log Files</a>. </li> 
      </ul> </p> <p> Das Hinzufügen oder Entfernen von Quellen aus Offline-Quellen führt nicht zur erneuten Verarbeitung des Datensatzes. </p> <p> Mit der Zeit werden Messungen zur Verarbeitung der Online-Quellen des Profils durchgeführt. Wenn die Offline-Quelle erneut online ist, wird die Verarbeitung eingehender Protokolldateien für diese Quelle fortgesetzt. </p> <p> Wenn eine Quelle wieder online ist, sollten Sie sie aus Offline-Quellen entfernen. Andernfalls behandelt der Data Workbench-Server die Quelle als Online-Quelle und aktualisiert die Ausführungszeit, solange die Quelle Daten sendet. Wenn die Quelle wieder offline ist, werden die Zeitüberschreitungsmessungen beendet. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> angehalten </td> 
      <td colname="col2"> True oder false. Wenn "true", werden neue Daten nicht in den Datensatz verarbeitet. Der Standardwert ist „false“. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Echtzeitverzögerung </td> 
      <td colname="col2"> Die Zeitspanne in Sekunden, die Data Workbench Server zwischen den Zeitabständen der Verarbeitung der Daten in den Datensatz wartet. Wenn dieser Wert auf null gesetzt ist, versucht das System, mit den eingehenden Daten in Echtzeit Schritt zu halten. Der Standardwert ist null (0), Sie können diesen Wert jedoch erhöhen, um die CPU-Auslastung zu verringern. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> FIFO-Byte in Echtzeit </td> 
      <td colname="col2"> <p>Die Menge des Speichers in Bytes, der zum Speichern von Daten verwendet wird, die darauf warten, in den Datensatz verarbeitet zu werden. Möglicherweise müssen Sie diesen Wert anhand der Anzahl der Sekunden ändern, die Sie für die Echtzeitverzögerung angeben. Der Standardwert lautet 16000000. </p> <p> <p>Hinweis:  Sie sollten diesen Wert nicht ohne Rücksprache mit Adobe ändern. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Speicherintervall (s) </td> 
      <td colname="col2"> <p>Häufigkeit, mit der der Data Workbench-Server seine Statusdateien speichert. Der Standardwert lautet 3600. </p> <p> <p>Hinweis:  Sie sollten diesen Wert nicht ohne Rücksprache mit Adobe ändern. </p> </p> </td> 
   </tr> 
   </tbody> 
   </table>

   Beim Bearbeiten der [!DNL Log Processing Mode.cfg] Datei in einem Data Workbench-Fenster können Sie Tastenkombinationen für grundlegende Bearbeitungsfunktionen verwenden, z. B. Ausschneiden (Strg+x), Kopieren (Strg+c), Einfügen (Strg+v), Rückgängigmachen (Strg+Z), Wiederholen (Strg+Umschalt+Z), Abschnitt auswählen (Klicken+Ziehen) und alle auswählen (Strg+a). Darüber hinaus können Sie mithilfe der Tastaturbefehle Text aus einer Konfigurationsdatei ( [!DNL .cfg]) in eine andere kopieren und einfügen.

1. Klicken Sie mit der rechten Maustaste **[!UICONTROL (modified)]** am oberen Rand des Fensters und klicken Sie auf **[!UICONTROL Save]**.
1. Klicken Sie in der [!DNL Profile Manager]Spalte mit der rechten Maustaste auf das Häkchen für die Datei in der [!DNL User] Spalte und klicken Sie dann auf **[!UICONTROL Save to]** > **[!UICONTROL datasetprofile name]**.

   >[!NOTE]
   >
   >Speichern Sie die geänderte Konfigurationsdatei nicht in einem der von Adobe bereitgestellten internen Profile, da Ihre Änderungen bei der Installation von Updates für diese Profile überschrieben werden.
