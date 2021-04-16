---
description: Schritte zum Bearbeiten der Datei "Log Processing.cfg"für ein DataSet-Profil.
title: Bearbeiten der Konfigurationsdatei für die Protokollverarbeitung
uuid: 2ffae53a-ef2f-4933-821d-13f29dcdb68d
exl-id: 294063ef-6771-4310-8198-df57fab1e2b4
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1288'
ht-degree: 2%

---

# Bearbeiten der Konfigurationsdatei für die Protokollverarbeitung{#editing-the-log-processing-configuration-file}

Schritte zum Bearbeiten der Datei &quot;Log Processing.cfg&quot;für ein DataSet-Profil.

1. Öffnen Sie beim Arbeiten im DataSet-Profil das [!DNL Profile Manager] und klicken Sie auf **[!UICONTROL Dataset]**, um den Inhalt anzuzeigen.

   Informationen zum Öffnen und Arbeiten mit [!DNL Profile Manager] finden Sie im *Data Workbench Benutzerhandbuch*.

   >[!NOTE]
   >
   >Ein Unterordner für die Protokollverarbeitung kann im Datenaset-Ordner vorhanden sein. Dieser Unterordner enthält die [!DNL Log Processing Dataset Include]-Dateien, die für ein oder mehrere geerbte Profil erstellt wurden. Siehe [Datensatz einschließlich Dateien](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md).

1. Klicken Sie mit der rechten Maustaste auf das Häkchen neben [!DNL Log Processing.cfg] und klicken Sie auf **[!UICONTROL Make Local]**. In der Spalte [!DNL User] wird ein Häkchen für diese Datei angezeigt.
1. Klicken Sie mit der rechten Maustaste auf das neu erstellte Häkchen und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Workstation]**. Das Fenster [!DNL Log Processing.cfg] wird angezeigt.

   Sie können auch die Datei [!DNL Log Processing.cfg] von einem [!DNL Transformation Dependency Map] öffnen. Weitere Informationen zu Konversionsabhängigkeitskarten finden Sie unter [Dataset-Konfigurationstools](../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md#concept-6e058b7691834cf79dcfd1573f78d4f5).

1. Bearbeiten Sie die Parameter in der Konfigurationsdatei mithilfe der folgenden Tabelle als Anleitung.

   Beim Bearbeiten der Datei [!DNL Log Processing.cfg] in einem Data Workbench-Fenster können Sie Tastenkombinationen für grundlegende Bearbeitungsfunktionen verwenden, z. B. Ausschneiden ( Strg+x ), Kopieren ( Strg+c), Einfügen ( Strg+v ), Rückgängigmachen ( Strg+Z ), Wiederholen ( Strg+Umschalt+Z ), Abschnitt (Klicken+Ziehen) und Alles auswählen ( Strg+a ). Sie können die Tastaturbefehle auch verwenden, um Text aus einer Konfigurationsdatei ( [!DNL .cfg]) in eine andere zu kopieren und einzufügen.

   >[!NOTE]
   >
   >Eine [!DNL Log Processing Dataset Include]-Datei für ein geerbtes Profil enthält eine Untergruppe der in der folgenden Tabelle beschriebenen Parameter sowie einige weitere Parameter. Siehe [Datensatz einschließlich Dateien](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md).

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
      <td colname="col2"> <p>Optional. Filtern Sie die Daten, um Protokolleinträge mit Zeitstempeln bis zu diesem Zeitpunkt einzuschließen, jedoch nicht eingeschlossen. Adobe empfiehlt die Verwendung eines der folgenden Zeitformate: </p> 
      <ul id="ul_42613B1D2F3A4A6C9563BC9B54BE895E"> 
      <li id="li_BC6E5FC5CA204D89936845BE05DFE6E6">1. Januar 2013 HH:MM:SS EDT </li> 
      <li id="li_18FE1B0417AF4207B02497664F47D23F">1. Januar 2013 HH:MM:SS GMT </li> 
      </ul> <p>Wenn Sie beispielsweise den 29. Juli 2013 um 00:00:00 EDT als Endzeit festlegen, werden Daten bis zum 28. Juli 2013 um 23:59:59 PM EDT eingeschlossen. Siehe <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d"> Data Filters </a>. </p> <p>Sie müssen eine Zeitzone angeben. Die Zeitzone wird nicht standardmäßig auf GMT gesetzt, wenn sie nicht angegeben ist. Eine Liste der vom Data Workbench-Server unterstützten Zeitzonenabkürzungen finden Sie unter <a href="../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> Zeitzonencodes </a>. </p> <p> <p>Hinweis:  Der Parameter "Beginn-/Endzeit verwenden"für die Sensor-<span class="wintitle">-, Protokolldatei- und XML-Quellen ist mit diesem Parameter verknüpft. </span> In den Abschnitten zu <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-6714c720fac044cbb9af003bf401b2ea"> Protokollquellen </a> finden Sie Informationen zu diesen Quelltypen. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Felder </td> 
      <td colname="col2"> Optional. Adobe empfiehlt, die Felder <span class="wintitle"> in einer oder mehreren <span class="wintitle">-Protokollverarbeitungsdataset einzuschließen </span>-Dateien. </span> Siehe <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab"> Protokollverarbeitungsdataset Include-Dateien </a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Gruppen - Maximale Schlüsselbyte </td> 
      <td colname="col2"> <p>Maximale Anzahl von Ereignis-Daten, die der Server für eine einzige Tracking-ID verarbeiten kann. Daten, die diesen Grenzwert überschreiten, werden aus dem Dataset-Aufbau gefiltert. Dieser Wert muss auf 2e6 gesetzt werden, wenn die Schlüsselaufteilung aktiv ist, und auf 1e6, wenn die Schlüsselaufteilung nicht aktiv ist. Siehe <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-64b416bbe42f4d689f90df246f7f7caf"> Schlüsselaufteilung </a>. </p> <p> <p>Hinweis:  Ändern Sie diesen Wert nicht ohne vorherige Adobe. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Hashschwellenwert </td> 
      <td colname="col2"> <p>Optional. Ein Stichprobenfaktor für eine zufällige Unterstichprobe von Zeilen. Wenn der Wert auf "n"festgelegt ist, wird nur eine von n Tracking-IDs in den Datensatz eingegeben, wodurch die Gesamtzahl der Zeilen im Datensatz um den Faktor n verringert wird. </p> <p>Um einen Datensatz zu erstellen, der eine 100-prozentige Genauigkeit erfordert (d. h. alle Zeilen einzuschließen), setzen Sie den Hash-Schwellenwert auf 1. </p> <p>Werte: </p> <span class="filepath"> Hash-Schwellenwert = 1  </span> (100 Prozent der Daten einschließlich aller Zeilen) <p> <span class="filepath"> Hash-Schwellenwert = 2  </span> (1/2 der Daten und umfasst die Hälfte der Zeilen) </p> <p> <span class="filepath"> Hash-Schwellenwert = 3  </span>(1/3 der Daten und umfasst eine von drei Zeilen, bei Abschluss der Abfrage jedoch bis zu 34 %) </p> <p> <span class="filepath"> Hash-Schwellenwert = 4  </span>(1/4 der Daten und umfasst eine von vier Zeilen) </p> <p> </p> <p> <p>Hinweis:  Bei Verwendung eines Hash-Schwellenwerts = 8 </span> wird 1/8 der Daten bereitgestellt, was 12,5 % entspricht. <span class="filepath"> Der Wert <span class="uicontrol"> Abfrage Complete </span> wird jedoch in den Runden auf 13 % für diesen Wert gerundet. Weitere Beispiele sind ein <span class="filepath"> Hash-Schwellenwert = 6 </span>, der eine Auflösung von 17 % der Abfrage ergibt. Ein <span class="filepath"> Hash-Schwellenwert = 13 </span>ergibt eine Auflösung von 8 % der Abfrage. </span></p> </p> <p>Wenn <span class="wintitle"> Hash-Schwellenwert </span> sowohl in den Dateien <span class="filepath"> Log Processing.cfg </span> als auch <span class="filepath"> Transformation.cfg </span> angegeben ist, wird er nicht nacheinander angewendet. der in beiden Konfigurationsdateien festgelegte Maximalwert gilt. Siehe <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d"> Data Filters </a>. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Protokolleintragsbedingung </td> 
      <td colname="col2"> Optional. Definiert die Regeln, nach denen Protokolleinträge in den Datensatz aufgenommen werden sollen. Siehe <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-ecaff95cee4e40bc90f81e099c5fc934"> Protokolleinstiegsbedingung </a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Neu verarbeiten </td> 
      <td colname="col2"> <p>Optional. Alle Zeichen oder Kombinationen von Zeichen können hier eingegeben werden. Wenn Sie diesen Parameter ändern und die Datei auf dem Data Workbench Server-Computer speichern, wird die Datenverarbeitung initiiert. </p> <p>Siehe <a href="../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md"> Reprocessing and Retransformation </a>. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Schlüsselraum teilen </td> 
      <td colname="col2"> <p>Parameter, der bei der Schlüsselaufteilung verwendet wird. Der Wert sollte 6e6 sein, wenn die Schlüsselaufteilung aktiv ist. Siehe <a href="/help/home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#key-split"> Schlüsselaufteilung </a>. </p> <p> <p>Hinweis:  Ändern Sie diesen Wert nicht ohne vorherige Adobe. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Schlüsselbyte teilen </td> 
      <td colname="col2"> <p>Parameter, der bei der Schlüsselaufteilung verwendet wird. Der Wert sollte 1e6 lauten, wenn die Schlüsselaufteilung aktiv ist, und 0, wenn die Schlüsselaufteilung nicht aktiv ist. Siehe <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-64b416bbe42f4d689f90df246f7f7caf"> Schlüsselaufteilung </a>. </p> <p> <p>Hinweis:  Ändern Sie diesen Wert nicht ohne vorherige Adobe. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Schlüsselabstand teilen </td> 
      <td colname="col2"> <p>Parameter, der bei der Schlüsselaufteilung verwendet wird. Der Wert sollte 10 betragen, wenn die Schlüsselaufteilung aktiv ist. Siehe <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-64b416bbe42f4d689f90df246f7f7caf"> Schlüsselaufteilung </a>. </p> <p> <p>Hinweis:  Ändern Sie diesen Wert nicht ohne vorherige Adobe. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Phasen </td> 
      <td colname="col2"> <p>Optional. Die Namen der Verarbeitungsstufen, die in den Dateien <span class="wintitle"> "Protokollverarbeitungsdataset"verwendet werden können, umfassen </span>. Verarbeitungsschritte bieten eine Möglichkeit, die in <span class="wintitle"> Protokollverarbeitungsdataset definierten Transformationen anzuordnen. Schließen Sie </span>-Dateien ein. Dieser Parameter ist sehr hilfreich, wenn Sie eine oder mehrere Konvertierungen innerhalb mehrerer <span class="wintitle">-Protokollverarbeitungsdaten einschließen </span>-Dateien definiert haben und Sie möchten, dass bestimmte Transformationen an bestimmten Punkten während der Protokollverarbeitung durchgeführt werden. </p> <p>Die Reihenfolge, in der die Schritte hier Liste werden, bestimmt die Reihenfolge, in der die Transformationen in den Protokollverarbeitungsdatenasets <span class="wintitle"> einschließlich </span>-Dateien während der Protokollverarbeitung ausgeführt werden. Die Vorverarbeitung und Nachbearbeitung sind integrierte Phasen. Die Vorverarbeitung ist immer der erste Schritt und die Nachbearbeitung ist immer der letzte Schritt. Standardmäßig gibt es eine benannte Phase namens "Standard". </p> <p> <b>So fügen Sie eine neue Verarbeitungsphase hinzu</b> 
      <ul id="ul_3A49BEAD1C134344999FED379B8CE7A3"> 
         <li id="li_AFC9B2529EC64642AFF98E9D5BA88C71">Klicken Sie im Fenster <span class="filepath"> Log Processing.cfg </span> mit der rechten Maustaste auf <span class="uicontrol"> Stages </span> und klicken Sie auf <span class="uicontrol"> Hinzufügen New </span> &gt; <span class="uicontrol"> Stage </span>. </li> 
         <li id="li_5731B836658D4E1DB721C57C6275369A">Geben Sie einen Namen für die neue Phase ein. </li> 
      </ul> </p> <p> <b>So löschen Sie eine vorhandene Verarbeitungsphase</b> 
      <ul id="ul_BBF4F710A5624C578F1F2A38FE18E9AD"> 
         <li id="li_CF6982C752DE41FFA97759C30CDE6AA0">Klicken Sie mit der rechten Maustaste auf die Zahl, die der zu löschenden Phase entspricht, und klicken Sie auf <span class="uicontrol"> </span><i>&lt; <span class="uicontrol"> #stage_number </span></i>. </li> 
      </ul> </p> <p> <p>Hinweis:  Wenn Sie eine <span class="wintitle">-Stufe </span> in einer <span class="wintitle">-Protokollverarbeitungsdataset Einschließen </span>-Datei angeben, muss der Name der Bühne exakt mit dem Namen übereinstimmen, den Sie hier eingeben. Siehe <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md"> DataSet Include Files </a>. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Startzeit </td> 
      <td colname="col2"> <p>Optional. Filtern Sie die Daten, um Protokolleinträge mit Zeitstempeln zu dieser Zeit oder danach einzuschließen. Adobe empfiehlt die Verwendung eines der folgenden Zeitformate: </p> <p> 
      <ul id="ul_0774889E22C24A6592809D289D1CBEC5"> 
         <li id="li_CE23541D8B584EA1AC432C5098564E46"> 1. Januar 2013 HH:MM:SS EDT </li> 
         <li id="li_2EB0CF60CF12444BB744E52E9C919152"> 1. Januar 2013 HH:MM:SS GMT </li> 
      </ul> </p> <p> Wenn Sie z. B. "29. Juli 2013 00:00:00 EDT"als "Beginn Time"festlegen, werden Daten ab dem 29. Juli 2013 um 12:00:00 Uhr EDT eingeschlossen. Siehe <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d"> Data Filters </a>. </p> <p> Sie müssen eine Zeitzone angeben. Die Zeitzone wird nicht standardmäßig auf GMT gesetzt, wenn sie nicht angegeben ist. Eine Liste der vom Data Workbench-Server unterstützten Zeitzonenabkürzungen finden Sie unter <a href="../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> Zeitzonencodes </a>. </p> <p> <p>Hinweis:  Der Parameter "Beginn-/Endzeit verwenden"für die Sensor-<span class="wintitle">-, Protokolldatei- und XML-Quellen ist mit diesem Parameter verknüpft. </span> In den Abschnitten zu <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-6714c720fac044cbb9af003bf401b2ea"> Protokollquellen </a> finden Sie Informationen zu diesen Quelltypen. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Zeitzone </td> 
      <td colname="col2"> <p>Optional. Zeitzone des Data Workbench-Servers, der für Zeitkonvertierungen (z. B. die Konvertierung durch das Feld x-local-timestring) während der Protokollverarbeitung verwendet wird. </p> <p> <p>Hinweis:  Sie müssen die Zeitzone angeben, wenn Sie während der Protokollbearbeitung des Datensatzes auf das konvertierte Zeitfeld zugreifen möchten. Andernfalls zeichnet der Data Workbench-Server einen Fehler in den Ereignis-Protokollen auf. </p> </p> <p>Siehe <a href="../../../home/c-dataset-const-proc/c-trans-config-file/c-spec-trans-param/c-time-zones.md#concept-9cf16b1cb4874f7d85e1dd950fdb4956"> Zeitzonen </a>. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Transformationen </td> 
      <td colname="col2"> Optional. Adobe empfiehlt das Definieren von Transformationen für die Protokollverarbeitung in einer oder mehreren <span class="wintitle"> Protokollverarbeitungsdataset Include </span>-Dateien. Siehe <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab"> Protokollverarbeitungsdataset Include-Dateien </a>. </td> 
   </tr> 
   </tbody> 
   </table>

1. Klicken Sie mit der rechten Maustaste auf **[!UICONTROL (modified)]** oben im Fenster und klicken Sie auf **[!UICONTROL Save]**.
1. Klicken Sie in der Spalte [!DNL Profile Manager] mit der rechten Maustaste auf das Häkchen für [!DNL Log Processing.cfg]in der Spalte [!DNL User] und dann auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL dataset profile name]***, um die lokal vorgenommenen Änderungen zu übernehmen. Die Neuverarbeitung der Daten beginnt nach der Synchronisierung des DataSet-Profils.

   >[!NOTE]
   >
   >Speichern Sie die geänderte Konfigurationsdatei nicht in einem der von der Adobe bereitgestellten internen Profil, da Ihre Änderungen bei der Installation von Updates auf diesen Profilen überschrieben werden.

   Weitere Informationen zur erneuten Verarbeitung Ihrer Daten finden Sie unter [Wiederaufbereitung und Umrechnung](../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).
