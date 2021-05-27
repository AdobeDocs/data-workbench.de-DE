---
description: Schritte zum Bearbeiten der Datei "Log Processing.cfg"für ein Datensatzprofil.
title: Bearbeiten der Konfigurationsdatei für die Protokollverarbeitung
uuid: 2ffae53a-ef2f-4933-821d-13f29dcdb68d
exl-id: 294063ef-6771-4310-8198-df57fab1e2b4
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1288'
ht-degree: 2%

---

# Bearbeiten der Konfigurationsdatei für die Protokollverarbeitung{#editing-the-log-processing-configuration-file}

Schritte zum Bearbeiten der Datei &quot;Log Processing.cfg&quot;für ein Datensatzprofil.

1. Wenn Sie in Ihrem Datensatzprofil arbeiten, öffnen Sie [!DNL Profile Manager] und klicken Sie auf **[!UICONTROL Dataset]** , um dessen Inhalt anzuzeigen.

   Informationen zum Öffnen und Verwenden von [!DNL Profile Manager] finden Sie im *Data Workbench-Benutzerhandbuch*.

   >[!NOTE]
   >
   >Ein Unterordner für die Protokollverarbeitung kann im Datensatzverzeichnis vorhanden sein. Dieses Unterverzeichnis enthält die [!DNL Log Processing Dataset Include]-Dateien, die für ein oder mehrere geerbte Profile erstellt wurden. Siehe [Datensatzaufnahme-Dateien](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md).

1. Klicken Sie mit der rechten Maustaste auf das Häkchen neben [!DNL Log Processing.cfg] und klicken Sie auf **[!UICONTROL Make Local]**. Ein Häkchen für diese Datei wird in der Spalte [!DNL User] angezeigt.
1. Klicken Sie mit der rechten Maustaste auf das neu erstellte Häkchen und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Workstation]**. Das Fenster [!DNL Log Processing.cfg] wird angezeigt.

   Sie können die [!DNL Log Processing.cfg]-Datei auch von einem [!DNL Transformation Dependency Map] aus öffnen. Informationen zu Transformationsabhängigkeitskarten finden Sie unter [Tools für die Datensatzkonfiguration](../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md#concept-6e058b7691834cf79dcfd1573f78d4f5).

1. Bearbeiten Sie die Parameter in der Konfigurationsdatei mithilfe der folgenden Tabelle als Anleitung.

   Beim Bearbeiten der Datei [!DNL Log Processing.cfg] in einem Data Workbench-Fenster können Sie Tastaturbefehle für grundlegende Bearbeitungsfunktionen verwenden, z. B. zum Ausschneiden ( Strg+x ), Kopieren ( Strg+C), Einfügen ( Strg+V ), Rückgängigmachen ( Strg+Z ), Wiederholen ( Strg+Umschalt+Z ), Auswählen des Bereichs (Klicken+Ziehen) und Auswählen aller Elemente ( Strg+A ). Sie können auch die Verknüpfungen verwenden, um Text aus einer Konfigurationsdatei ( [!DNL .cfg]) in eine andere einzufügen.

   >[!NOTE]
   >
   >Eine [!DNL Log Processing Dataset Include]-Datei für ein geerbtes Profil enthält eine Teilmenge der in der folgenden Tabelle beschriebenen Parameter sowie einige zusätzliche Parameter. Siehe [Datensatzaufnahme-Dateien](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md).

   <table id="table_BC7D3635C94049A9B608463AC1DBFA69">
   <thead> 
   <tr> 
      <th colname="col1" class="entry"> Parameter </th> 
      <th colname="col2" class="entry"> Beschreibung </th> 
   </tr> 
   </thead>
   <tbody> 
   <tr> 
      <td colname="col1"> Quellen für die Protokollierung </td> 
      <td colname="col2"> Die Datenquellen. Siehe <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-6714c720fac044cbb9af003bf401b2ea"> Protokollquellen </a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Endzeit </td> 
      <td colname="col2"> <p>Optional. Filtern Sie die Daten, um Protokolleinträge mit Zeitstempeln bis zu diesem Zeitpunkt einzuschließen, jedoch nicht. Adobe empfiehlt die Verwendung eines der folgenden Zeitformate: </p> 
      <ul id="ul_42613B1D2F3A4A6C9563BC9B54BE895E"> 
      <li id="li_BC6E5FC5CA204D89936845BE05DFE6E6">1. Januar 2013 HH:MM:SS EDT </li> 
      <li id="li_18FE1B0417AF4207B02497664F47D23F">1. Januar 2013 HH:MM:SS GMT </li> 
      </ul> <p>Wenn Sie beispielsweise den 29. Juli 2013 um 00:00:00 EDT als Endzeit angeben, werden Daten bis zum 28. Juli 2013, 11:59:59 PM EDT einbezogen. Siehe <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d"> Datenfilter </a>. </p> <p>Sie müssen eine Zeitzone angeben. Wenn nicht anders angegeben, wird in der Zeitzone nicht standardmäßig GMT verwendet. Eine Liste der vom Data Workbench-Server unterstützten Zeitzonen-Abkürzungen finden Sie unter <a href="../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> Zeitzonencodes </a>. </p> <p> <p>Hinweis:  Der Parameter Start-/Endzeiten verwenden für <span class="wintitle"> Sensor </span>, Protokolldatei und XML-Quellen ist mit diesem Parameter verknüpft. Weitere Informationen zu diesen Quelltypen finden Sie in den Abschnitten <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-6714c720fac044cbb9af003bf401b2ea"> Protokollquellen </a> . </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Felder </td> 
      <td colname="col2"> Optional. Adobe empfiehlt, <span class="wintitle"> Felder </span> in einer oder mehreren <span class="wintitle"> Protokollverarbeitungsdatensätzen zu definieren </span>. Siehe <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab"> Datensatzaufnahme-Dateien zur Protokollverarbeitung </a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Group Maximum Key Bytes </td> 
      <td colname="col2"> <p>Maximale Anzahl von Ereignisdaten, die der Server für eine einzelne Tracking-ID verarbeiten kann. Daten, die diesen Grenzwert überschreiten, werden aus dem Prozess der Datensatzerstellung gefiltert. Dieser Wert muss bei aktiver Schlüsselaufteilung auf 2e6 und bei nicht aktiver Schlüsselaufteilung auf 1e6 gesetzt werden. Siehe <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-64b416bbe42f4d689f90df246f7f7caf"> Schlüsselaufteilung </a>. </p> <p> <p>Hinweis:  Ändern Sie diesen Wert nicht, ohne die Adobe zu konsultieren. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Hash-Schwellenwert </td> 
      <td colname="col2"> <p>Optional. Ein Stichprobenfaktor für eine Stichprobe von Zeilen. Wenn der Wert auf eine Zahl n festgelegt ist, wird nur eine von n Tracking-IDs in den Datensatz aufgenommen, wodurch die Gesamtzahl der Zeilen im Datensatz um den Faktor n verringert wird. </p> <p>Um einen Datensatz zu erstellen, der eine 100-prozentige Genauigkeit erfordert (d. h., um alle Zeilen einzuschließen), setzen Sie den Hash-Schwellenwert auf 1. </p> <p>Werte: </p> <span class="filepath"> Hash-Schwellenwert = 1  </span> (100 Prozent der Daten einschließlich aller Zeilen) <p> <span class="filepath"> Hash-Schwellenwert = 2  </span> (1/2 von Daten und umfasst die Hälfte der Zeilen.) </p> <p> <span class="filepath"> Hash-Schwellenwert = 3  </span>(1/3 der Daten und umfasst eine von drei Zeilen, wird jedoch in Query Complete auf 34 % gerundet) </p> <p> <span class="filepath"> Hash-Schwellenwert = 4  </span>(1/4 der Daten und umfasst eine von vier Zeilen.) </p> <p> </p> <p> <p>Hinweis:  Durch Verwendung eines <span class="filepath"> Hash-Schwellenwerts = 8 </span> erhalten Sie einen 1/8. der Daten, der 12,5 % beträgt. Der Wert <span class="uicontrol"> Query Completion </span> wird jedoch in den Runden auf 13 % für diesen Wert gerundet. Weitere Beispiele sind ein <span class="filepath"> Hash-Schwellenwert = 6 </span> , der zu einer 17 %-igen Abfrageauflösung führt. Ein <span class="filepath"> Hash-Schwellenwert = 13 </span>führt zur 8 %-Abfragelösung. </p> </p> <p>Wenn <span class="wintitle"> Hash-Schwellenwert </span> sowohl in den Dateien <span class="filepath"> Protokollverarbeitung.cfg </span> als auch in den Dateien <span class="filepath"> Transformation.cfg </span> angegeben ist, wird er nicht nacheinander angewendet. gilt der in beiden Konfigurationsdateien festgelegte Maximalwert. Siehe <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d"> Datenfilter </a>. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Protokolleintragsbedingung </td> 
      <td colname="col2"> Optional. Definiert die Regeln, nach denen Protokolleinträge zur Aufnahme in den Datensatz berücksichtigt werden. Siehe <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-ecaff95cee4e40bc90f81e099c5fc934"> Protokolleintragsbedingung </a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Neuverarbeitung </td> 
      <td colname="col2"> <p>Optional. Hier können beliebige Zeichen oder Kombinationen von Zeichen eingegeben werden. Wenn Sie diesen Parameter ändern und die Datei auf dem Data Workbench Server-Computer speichern, wird die erneute Datenverarbeitung initiiert. </p> <p>Siehe <a href="../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md"> Wiederaufbereitung und erneute Umwandlung </a>. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Aufteilen des Schlüsselspeicherplatzes </td> 
      <td colname="col2"> <p>Parameter, die an der Schlüsselaufteilung beteiligt sind. Der Wert sollte 6e6 lauten, wenn die Schlüsselaufteilung aktiv ist. Siehe <a href="/help/home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#key-split"> Schlüsselaufteilung </a>. </p> <p> <p>Hinweis:  Ändern Sie diesen Wert nicht, ohne die Adobe zu konsultieren. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Geteilte Schlüsselbyte </td> 
      <td colname="col2"> <p>Parameter, die an der Schlüsselaufteilung beteiligt sind. Der Wert sollte 1e6 lauten, wenn die Schlüsselaufteilung aktiv ist, und 0, wenn die Schlüsselaufteilung nicht aktiv ist. Siehe <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-64b416bbe42f4d689f90df246f7f7caf"> Schlüsselaufteilung </a>. </p> <p> <p>Hinweis:  Ändern Sie diesen Wert nicht, ohne die Adobe zu konsultieren. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Split Key Space Ratio </td> 
      <td colname="col2"> <p>Parameter, die an der Schlüsselaufteilung beteiligt sind. Der Wert sollte 10 betragen, wenn die Schlüsselaufteilung aktiv ist. Siehe <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-64b416bbe42f4d689f90df246f7f7caf"> Schlüsselaufteilung </a>. </p> <p> <p>Hinweis:  Ändern Sie diesen Wert nicht, ohne die Adobe zu konsultieren. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Phasen </td> 
      <td colname="col2"> <p>Optional. Die Namen der Verarbeitungsphasen, die in <span class="wintitle"> Protokollverarbeitungsdatensätzen verwendet werden können, umfassen </span> -Dateien. Verarbeitungsphasen bieten eine Möglichkeit, die in <span class="wintitle"> Protokollverarbeitungsdatensatz </span> -Dateien definierten Umwandlungen zu sortieren. Dieser Parameter ist sehr hilfreich, wenn Sie eine oder mehrere Umwandlungen in mehreren <span class="wintitle"> Protokollverarbeitungs-Datensatz Include </span>-Dateien definiert haben und Sie möchten, dass bestimmte Umwandlungen an bestimmten Punkten während der Protokollverarbeitung durchgeführt werden. </p> <p>Die Reihenfolge, in der Sie die Phasen hier auflisten, bestimmt die Reihenfolge, in der die Umwandlungen in den <span class="wintitle"> Protokollverarbeitungs-Datensatz-Include </span>-Dateien während der Protokollverarbeitung ausgeführt werden. Die Vorverarbeitung und die Nachbearbeitung sind integrierte Phasen. Die Vorverarbeitung ist immer der erste Schritt und die Nachbearbeitung ist immer der letzte Schritt. Standardmäßig gibt es eine benannte Phase namens "Standard". </p> <p> <b>So fügen Sie eine neue Verarbeitungsphase hinzu</b> 
      <ul id="ul_3A49BEAD1C134344999FED379B8CE7A3"> 
         <li id="li_AFC9B2529EC64642AFF98E9D5BA88C71">Klicken Sie im Fenster <span class="filepath"> Log Processing.cfg </span> mit der rechten Maustaste auf <span class="uicontrol"> Stages </span> und klicken Sie auf <span class="uicontrol"> Add New </span> &gt; <span class="uicontrol"> Stage </span>. </li> 
         <li id="li_5731B836658D4E1DB721C57C6275369A">Geben Sie einen Namen für die neue Phase ein. </li> 
      </ul> </p> <p> <b>So löschen Sie eine vorhandene Verarbeitungsphase</b> 
      <ul id="ul_BBF4F710A5624C578F1F2A38FE18E9AD"> 
         <li id="li_CF6982C752DE41FFA97759C30CDE6AA0">Klicken Sie mit der rechten Maustaste auf die Nummer der zu löschenden Phase und klicken Sie auf <span class="uicontrol"> </span><i>&lt; <span class="uicontrol"> #stage_number </span></i>. </li> 
      </ul> </p> <p> <p>Hinweis:  Wenn Sie eine <span class="wintitle"> Stage </span> in einer <span class="wintitle"> Protokollverarbeitungsdatensatz - Include </span> -Datei angeben, muss der Name der Bühne genau mit dem Namen übereinstimmen, den Sie hier eingeben. Siehe <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md"> Datensatzaufnahme-Dateien </a>. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Startzeit </td> 
      <td colname="col2"> <p>Optional. Filtern Sie Daten, um Protokolleinträge mit Zeitstempeln zu dieser Zeit oder danach einzuschließen. Adobe empfiehlt die Verwendung eines der folgenden Zeitformate: </p> <p> 
      <ul id="ul_0774889E22C24A6592809D289D1CBEC5"> 
         <li id="li_CE23541D8B584EA1AC432C5098564E46"> 1. Januar 2013 HH:MM:SS EDT </li> 
         <li id="li_2EB0CF60CF12444BB744E52E9C919152"> 1. Januar 2013 HH:MM:SS GMT </li> 
      </ul> </p> <p> Wenn Sie beispielsweise "29. Juli 2013 00:00:00 EDT"als Startzeit angeben, werden Daten ab dem 29. Juli 2013, um 12:00:00 Uhr EDT einbezogen. Siehe <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d"> Datenfilter </a>. </p> <p> Sie müssen eine Zeitzone angeben. Wenn nicht anders angegeben, wird in der Zeitzone nicht standardmäßig GMT verwendet. Eine Liste der vom Data Workbench-Server unterstützten Zeitzonen-Abkürzungen finden Sie unter <a href="../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> Zeitzonencodes </a>. </p> <p> <p>Hinweis:  Der Parameter Start-/Endzeiten verwenden für <span class="wintitle"> Sensor </span>, Protokolldatei und XML-Quellen ist mit diesem Parameter verknüpft. Weitere Informationen zu diesen Quelltypen finden Sie in den Abschnitten <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-6714c720fac044cbb9af003bf401b2ea"> Protokollquellen </a> . </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Zeitzone </td> 
      <td colname="col2"> <p>Optional. Zeitzone des Data Workbench-Servers, der bei der Protokollverarbeitung für Zeitkonvertierungen (z. B. die Konvertierung, die durch das Feld x-local-timestring dargestellt wird) verwendet wird. </p> <p> <p>Hinweis:  Sie müssen die Zeitzone angeben, wenn Sie während der Protokollverarbeitungsphase der Datensatzerstellung auf das konvertierte Zeitfeld zugreifen möchten. Andernfalls zeichnet der Data Workbench-Server einen Fehler in den Ereignisprotokollen auf. </p> </p> <p>Siehe <a href="../../../home/c-dataset-const-proc/c-trans-config-file/c-spec-trans-param/c-time-zones.md#concept-9cf16b1cb4874f7d85e1dd950fdb4956"> Zeitzonen </a>. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Umwandlungen </td> 
      <td colname="col2"> Optional. Adobe empfiehlt, Transformationen für die Protokollverarbeitung in einer oder mehreren <span class="wintitle"> Protokollverarbeitungsdatensätzen zu definieren, die </span> -Dateien enthalten. Siehe <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab"> Datensatzaufnahme-Dateien zur Protokollverarbeitung </a>. </td> 
   </tr> 
   </tbody> 
   </table>

1. Klicken Sie oben im Fenster mit der rechten Maustaste auf **[!UICONTROL (modified)]** und klicken Sie auf **[!UICONTROL Save]**.
1. Klicken Sie in der Spalte [!DNL Profile Manager] mit der rechten Maustaste auf das Häkchen für [!DNL Log Processing.cfg]in der Spalte [!DNL User] und klicken Sie dann auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL dataset profile name]*** , damit die lokal vorgenommenen Änderungen wirksam werden. Die erneute Verarbeitung der Daten beginnt nach der Synchronisierung des Datensatzprofils.

   >[!NOTE]
   >
   >Speichern Sie die geänderte Konfigurationsdatei nicht in einem der von Adobe bereitgestellten internen Profile, da Ihre Änderungen bei der Installation von Updates für diese Profile überschrieben werden.

   Weitere Informationen zur erneuten Verarbeitung Ihrer Daten finden Sie unter [Wiederaufbereitung und erneute Umwandlung](../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).
