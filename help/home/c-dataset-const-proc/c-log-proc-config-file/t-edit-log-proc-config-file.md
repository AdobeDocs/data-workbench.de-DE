---
description: Schritte zum Bearbeiten der Datei "Log Processing.cfg"für ein Datensatzprofil.
solution: Analytics
title: Bearbeiten der Konfigurationsdatei für die Protokollverarbeitung
topic: Data workbench
uuid: 2ffae53a-ef2f-4933-821d-13f29dcdb68d
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Bearbeiten der Konfigurationsdatei für die Protokollverarbeitung{#editing-the-log-processing-configuration-file}

Schritte zum Bearbeiten der Datei &quot;Log Processing.cfg&quot;für ein Datensatzprofil.

1. Öffnen Sie bei der Arbeit im DataSet-Profil die Datei [!DNL Profile Manager] und klicken Sie auf **[!UICONTROL Dataset]** , um deren Inhalt anzuzeigen.

   Weitere Informationen zum Öffnen und Arbeiten mit [!DNL Profile Manager]Data Workbench finden Sie im *Data Workbench-Benutzerhandbuch*.

   >[!NOTE]
   >
   >Ein Unterordner für die Protokollverarbeitung kann im Datenaset-Ordner vorhanden sein. Dieser Unterordner enthält die [!DNL Log Processing Dataset Include] Dateien, die für ein oder mehrere geerbte Profile erstellt wurden. Siehe [DataSet Include-Dateien](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md).

1. Klicken Sie mit der rechten Maustaste auf das Häkchen neben [!DNL Log Processing.cfg] und klicken Sie auf **[!UICONTROL Make Local]**. Ein Häkchen für diese Datei wird in der [!DNL User] Spalte angezeigt.
1. Klicken Sie mit der rechten Maustaste auf das neu erstellte Häkchen und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Workstation]**. Das [!DNL Log Processing.cfg] Fenster wird angezeigt.

   Sie können die [!DNL Log Processing.cfg] Datei auch aus einer [!DNL Transformation Dependency Map]Datei öffnen. Weitere Informationen zu Konversionsabhängigkeitskarten finden Sie unter [DataSet-Konfigurationstools](../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md#concept-6e058b7691834cf79dcfd1573f78d4f5).

1. Bearbeiten Sie die Parameter in der Konfigurationsdatei mithilfe der folgenden Tabelle als Anleitung.

   Beim Bearbeiten der [!DNL Log Processing.cfg] Datei in einem Data Workbench-Fenster können Sie Tastenkombinationen für grundlegende Bearbeitungsfunktionen verwenden, z. B. Ausschneiden ( Strg+x ), Kopieren ( Strg+c), Einfügen ( Strg+v ), Rückgängigmachen ( Strg+Z ), Wiederholen ( Strg+Umschalt+Z ), Abschnitt auswählen (Klicken+Ziehen) und Alles auswählen ( Strg+a ). Sie können die Tastaturbefehle auch verwenden, um Text aus einer Konfigurationsdatei ( [!DNL .cfg]) in eine andere einzufügen.

   >[!NOTE]
   >
   >Eine [!DNL Log Processing Dataset Include] Datei für ein geerbtes Profil enthält eine Untergruppe der in der folgenden Tabelle beschriebenen Parameter sowie einige weitere Parameter. Siehe [DataSet Include-Dateien](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md).

   <table id="table_BC7D3635C94049A9B608463AC1DBFA69">
   <thead> 
   <tr> 
      <th colname="col1" class="entry"> Parameter </th> 
      <th colname="col2" class="entry"> Beschreibung </th> 
   </tr> 
   </thead>
   <tbody> 
   <tr> 
      <td colname="col1"> Protokollquellen </td> 
      <td colname="col2"> Die Datenquellen. Siehe <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-6714c720fac044cbb9af003bf401b2ea"> Protokollquellen </a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Endzeit </td> 
      <td colname="col2"> <p>Optional. Filtern Sie die Daten, um Protokolleinträge mit Zeitstempeln bis zu diesem Zeitpunkt einzuschließen, jedoch nicht eingeschlossen. Adobe empfiehlt die Verwendung eines der folgenden Formate: </p> 
      <ul id="ul_42613B1D2F3A4A6C9563BC9B54BE895E"> 
      <li id="li_BC6E5FC5CA204D89936845BE05DFE6E6">1. Januar 2013 HH:MM:SS EDT </li> 
      <li id="li_18FE1B0417AF4207B02497664F47D23F">1. Januar 2013 HH:MM:SS GMT </li> 
      </ul> <p>Wenn Sie beispielsweise den 29. Juli 2013 um 00:00:00 EDT als Endzeit festlegen, werden Daten bis zum 28. Juli 2013 um 23:59:59 PM EDT eingeschlossen. Siehe <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d"> Datenfilter </a>. </p> <p>Sie müssen eine Zeitzone angeben. Die Zeitzone wird nicht standardmäßig auf GMT gesetzt, wenn sie nicht angegeben ist. Eine Liste der vom Data Workbench-Server unterstützten Zeitzonenabkürzungen finden Sie unter <a href="../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> Zeitzonencodes </a>. </p> <p> <p>Hinweis:  Der Parameter "Start-/Endzeit verwenden"für <span class="wintitle"> Sensor-, Protokoll- </span>und XML-Quellen bezieht sich auf diesen Parameter. Siehe die Abschnitte der <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-6714c720fac044cbb9af003bf401b2ea"> Protokollquellen, in denen diese Quelltypen besprochen </a> werden. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Felder </td> 
      <td colname="col2"> Optional. Adobe empfiehlt, <span class="wintitle"> Felder </span> in einer oder mehreren <span class="wintitle"> Protokollverarbeitungsdatenasets einschließlich </span> Dateien zu definieren. Siehe <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab"> Protokollverarbeitungsdataset einschließlich Dateien </a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Gruppen - Maximale Schlüsselbyte </td> 
      <td colname="col2"> <p>Maximale Anzahl von Ereignisdaten, die der Server für eine einzige Tracking-ID verarbeiten kann. Daten, die diesen Grenzwert überschreiten, werden aus dem Dataset-Aufbau gefiltert. Dieser Wert muss auf 2e6 gesetzt werden, wenn die Schlüsselaufteilung aktiv ist, und auf 1e6, wenn die Schlüsselaufteilung nicht aktiv ist. Siehe <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-64b416bbe42f4d689f90df246f7f7caf"> Key Splitting </a>. </p> <p> <p>Hinweis:  Ändern Sie diesen Wert nicht ohne Rücksprache mit Adobe. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Hashschwellenwert </td> 
      <td colname="col2"> <p>Optional. Ein Stichprobenfaktor für eine zufällige Unterstichprobe von Zeilen. Wenn der Wert auf "n"festgelegt ist, wird nur eine von n Tracking-IDs in den Datensatz eingegeben, wodurch die Gesamtzahl der Zeilen im Datensatz um den Faktor n verringert wird. </p> <p>Um einen Datensatz zu erstellen, der eine 100-prozentige Genauigkeit erfordert (d. h. alle Zeilen einzuschließen), setzen Sie den Hash-Schwellenwert auf 1. </p> <p>Werte: </p> <span class="filepath"> Hash-Schwellenwert = 1 </span> (100 Prozent der Daten einschließlich aller Zeilen) <p> <span class="filepath"> Hashschwellenwert = 2 </span> (1/2 der Daten und umfasst die Hälfte der Zeilen) </p> <p> <span class="filepath"> Hashschwellenwert = 3 </span>(1/3 der Daten und umfasst eine von drei Zeilen, wird jedoch bei abgeschlossener Abfrage auf 34 % gerundet) </p> <p> <span class="filepath"> Hash-Schwellenwert = 4 </span>(1/4 der Daten und umfasst eine von vier Zeilen) </p> <p> </p> <p> <p>Hinweis:  Die Verwendung eines <span class="filepath"> Hash-Schwellenwerts = 8 </span> bietet ein Achtstel der Daten, das sind 12,5 %. Der <span class="uicontrol"> Wert </span> für die Abfragebeendigung wird jedoch auf 13 % gerundet. Weitere Beispiele sind ein <span class="filepath"> Hash-Schwellenwert = 6, </span> der eine Abfrageauflösung von 17 % ergibt. Ein <span class="filepath"> Hash-Schwellenwert = 13 </span>ergibt eine 8%ige Abfrageauflösung. </p> </p> <p>Wenn der <span class="wintitle"> Hash-Schwellenwert sowohl in den </span> Protokolldateien "processing.cfg" <span class="filepath"> und " </span> Transformation.cfg"angegeben <span class="filepath"> </span> ist, wird er nicht nacheinander angewendet. der in beiden Konfigurationsdateien festgelegte Maximalwert gilt. Siehe <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d"> Datenfilter </a>. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Protokolleinstiegsbedingung </td> 
      <td colname="col2"> Optional. Definiert die Regeln, nach denen Protokolleinträge in den Datensatz aufgenommen werden sollen. Siehe <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-ecaff95cee4e40bc90f81e099c5fc934"> Protokolleingabebedingung </a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Neu verarbeiten </td> 
      <td colname="col2"> <p>Optional. Alle Zeichen oder Kombinationen von Zeichen können hier eingegeben werden. Wenn Sie diesen Parameter ändern und die Datei auf dem Data Workbench Server-Computer speichern, wird die Datenverarbeitung initiiert. </p> <p>Siehe <a href="../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md"> Wiederaufbereitung und Umgestaltung </a>. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Schlüsselraum teilen </td> 
      <td colname="col2"> <p>Parameter, der bei der Schlüsselaufteilung verwendet wird. Der Wert sollte 6e6 sein, wenn die Schlüsselaufteilung aktiv ist. Siehe <a href="/help/home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#key-split"> Key Splitting </a>. </p> <p> <p>Hinweis:  Ändern Sie diesen Wert nicht ohne Rücksprache mit Adobe. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Schlüsselbyte teilen </td> 
      <td colname="col2"> <p>Parameter, der bei der Schlüsselaufteilung verwendet wird. Der Wert sollte 1e6 lauten, wenn die Schlüsselaufteilung aktiv ist, und 0, wenn die Schlüsselaufteilung nicht aktiv ist. Siehe <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-64b416bbe42f4d689f90df246f7f7caf"> Key Splitting </a>. </p> <p> <p>Hinweis:  Ändern Sie diesen Wert nicht ohne Rücksprache mit Adobe. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Schlüsselabstand teilen </td> 
      <td colname="col2"> <p>Parameter, der bei der Schlüsselaufteilung verwendet wird. Der Wert sollte 10 betragen, wenn die Schlüsselaufteilung aktiv ist. Siehe <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-64b416bbe42f4d689f90df246f7f7caf"> Key Splitting </a>. </p> <p> <p>Hinweis:  Ändern Sie diesen Wert nicht ohne Rücksprache mit Adobe. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Phasen </td> 
      <td colname="col2"> <p>Optional. Die Namen der Verarbeitungsstufen, die in <span class="wintitle"> Protokollverarbeitungsdatensätzen verwendet werden können, schließen </span> Dateien ein. Verarbeitungsschritte bieten eine Möglichkeit, die Konvertierungen anzuordnen, die in <span class="wintitle"> "Log Processing DataSet Include"- </span> Dateien definiert sind. Dieser Parameter ist sehr hilfreich, wenn Sie eine oder mehrere Konvertierungen in mehreren <span class="wintitle"> Protokollverarbeitungsdatendateien einschließlich </span> -Dateien definiert haben und Sie möchten, dass bestimmte Transformationen an bestimmten Punkten während der Protokollverarbeitung durchgeführt werden. </p> <p>Die Reihenfolge, in der Sie die Schritte hier auflisten, bestimmt die Reihenfolge, in der die Konvertierungen im <span class="wintitle"> Datensatz "Log Processing DataSet Include" </span> -Dateien während der Protokollverarbeitung ausgeführt werden. Die Vorverarbeitung und Nachbearbeitung sind integrierte Phasen. Die Vorverarbeitung ist immer der erste Schritt und die Nachbearbeitung ist immer der letzte Schritt. Standardmäßig gibt es eine benannte Phase namens "Standard". </p> <p> <b>So fügen Sie eine neue Verarbeitungsphase hinzu</b> 
      <ul id="ul_3A49BEAD1C134344999FED379B8CE7A3"> 
         <li id="li_AFC9B2529EC64642AFF98E9D5BA88C71">Klicken Sie im Fenster <span class="filepath"> Log Processing.cfg </span> mit der rechten Maustaste auf <span class="uicontrol"> Stages </span> und klicken Sie auf <span class="uicontrol"> Add New </span> &gt; <span class="uicontrol"> Stage </span>. </li> 
         <li id="li_5731B836658D4E1DB721C57C6275369A">Geben Sie einen Namen für die neue Phase ein. </li> 
      </ul> </p> <p> <b>So löschen Sie eine vorhandene Verarbeitungsphase</b> 
      <ul id="ul_BBF4F710A5624C578F1F2A38FE18E9AD"> 
         <li id="li_CF6982C752DE41FFA97759C30CDE6AA0">Klicken Sie mit der rechten Maustaste auf die Nummer, die der zu löschenden Phase entspricht, und klicken Sie auf <span class="uicontrol"> &lt; </span><i>#stage_number <span class="uicontrol"> &gt; </span></i>. </li> 
      </ul> </p> <p> <p>Hinweis:  Wenn Sie eine <span class="wintitle"> Phase </span> in einer <span class="wintitle"> Protokollverarbeitungsdatenset-Include- </span> Datei angeben, muss der Name der Phase genau mit dem Namen übereinstimmen, den Sie hier eingeben. Siehe <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md"> Datensatz einschließlich Dateien </a>. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Startzeit </td> 
      <td colname="col2"> <p>Optional. Filtern Sie die Daten, um Protokolleinträge mit Zeitstempeln zu dieser Zeit oder danach einzuschließen. Adobe empfiehlt die Verwendung eines der folgenden Formate: </p> <p> 
      <ul id="ul_0774889E22C24A6592809D289D1CBEC5"> 
         <li id="li_CE23541D8B584EA1AC432C5098564E46"> 1. Januar 2013 HH:MM:SS EDT </li> 
         <li id="li_2EB0CF60CF12444BB744E52E9C919152"> 1. Januar 2013 HH:MM:SS GMT </li> 
      </ul> </p> <p> Wenn Sie z. B. "29. Juli 2013 00:00:00 EDT"als Startzeit festlegen, sind Daten ab dem 29. Juli 2013 um 12:00:00 Uhr EDT enthalten. Siehe <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d"> Datenfilter </a>. </p> <p> Sie müssen eine Zeitzone angeben. Die Zeitzone wird nicht standardmäßig auf GMT gesetzt, wenn sie nicht angegeben ist. Eine Liste der vom Data Workbench-Server unterstützten Zeitzonenabkürzungen finden Sie unter <a href="../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> Zeitzonencodes </a>. </p> <p> <p>Hinweis:  Der Parameter "Start-/Endzeit verwenden"für <span class="wintitle"> Sensor-, Protokoll- </span>und XML-Quellen bezieht sich auf diesen Parameter. Siehe die Abschnitte der <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-6714c720fac044cbb9af003bf401b2ea"> Protokollquellen, in denen diese Quelltypen besprochen </a> werden. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Zeitzone </td> 
      <td colname="col2"> <p>Optional. Zeitzone des Data Workbench-Servers, der für Zeitkonvertierungen (z. B. die Konvertierung durch das Feld x-local-timestring) während der Protokollverarbeitung verwendet wird. </p> <p> <p>Hinweis:  Sie müssen die Zeitzone angeben, wenn Sie während der Protokollbearbeitung des Datensatzes auf das konvertierte Zeitfeld zugreifen möchten. Andernfalls zeichnet der Data Workbench-Server einen Fehler in den Ereignisprotokollen auf. </p> </p> <p>Siehe <a href="../../../home/c-dataset-const-proc/c-trans-config-file/c-spec-trans-param/c-time-zones.md#concept-9cf16b1cb4874f7d85e1dd950fdb4956"> Zeitzonen </a>. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Transformationen </td> 
      <td colname="col2"> Optional. Adobe empfiehlt, Konvertierungen für die Protokollverarbeitung in einer oder mehreren <span class="wintitle"> Protokollverarbeitungsdatenasets einschließlich </span> -Dateien zu definieren. Siehe <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab"> Protokollverarbeitungsdataset einschließlich Dateien </a>. </td> 
   </tr> 
   </tbody> 
   </table>

1. Klicken Sie mit der rechten Maustaste **[!UICONTROL (modified)]** am oberen Rand des Fensters und klicken Sie auf **[!UICONTROL Save]**.
1. Klicken Sie in der [!DNL Profile Manager]Spalte mit der rechten Maustaste auf das Häkchen [!DNL Log Processing.cfg]in der [!DNL User] Spalte und klicken Sie dann auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL dataset profile name]**>* , damit die lokal vorgenommenen Änderungen wirksam werden. Die Verarbeitung der Daten beginnt nach der Synchronisierung des Datensatzprofils.

   >[!NOTE]
   >
   >Speichern Sie die geänderte Konfigurationsdatei nicht in einem der von Adobe bereitgestellten internen Profile, da Ihre Änderungen bei der Installation von Updates für diese Profile überschrieben werden.

   Weitere Informationen zur erneuten Verarbeitung Ihrer Daten finden Sie unter [Wiederaufbereitung und Wiederherstellung](../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).
