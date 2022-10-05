---
description: Schritte zum Bearbeiten der Datei "Transformation.cfg"für ein Datensatzprofil.
title: Bearbeiten der Konfigurationsdatei für Umwandlungen
uuid: 77b9e566-4a9a-4ea1-b5ab-63a4574c0fdb
exl-id: 3fab17a4-d356-4548-b977-f5d409870753
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1131'
ht-degree: 2%

---

# Bearbeiten der Konfigurationsdatei für Umwandlungen{#editing-the-transformation-configuration-file}

{{eol}}

Schritte zum Bearbeiten der Datei &quot;Transformation.cfg&quot;für ein Datensatzprofil.

1. Wenn Sie in Ihrem Datensatzprofil arbeiten, öffnen Sie die [!DNL Profile Manager] und klicken Sie auf **[!UICONTROL Dataset]** um den Inhalt anzuzeigen.

   Informationen zum Öffnen und Arbeiten mit der [!DNL Profile Manager], siehe *Data Workbench-Benutzerhandbuch*.

   >[!NOTE]
   >
   >Ein Unterverzeichnis für Umwandlungen kann im Datensatzverzeichnis vorhanden sein. Dieses Unterverzeichnis enthält [!DNL Transformation Dataset Include] -Dateien, die für ein oder mehrere geerbte Profile erstellt wurden. Informationen zu [!DNL Transformation Dataset Include] -Dateien, siehe [Datensatzaufnahme-Dateien](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md).

1. Klicken Sie mit der rechten Maustaste auf das Häkchen neben [!DNL Transformation.cfg] und klicken Sie auf **[!UICONTROL Make Local]**. Ein Häkchen für diese Datei wird im [!DNL User] Spalte.
1. Klicken Sie mit der rechten Maustaste auf das neu erstellte Häkchen und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Workstation]**. Die [!DNL Transformation.cfg] angezeigt.

   Sie können auch die [!DNL Transformation.cfg] -Datei [!DNL Transformation Dependency Map]. Informationen zu [!DNL transformation dependency maps], siehe [Tools zur Datensatzkonfiguration](../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md#concept-6e058b7691834cf79dcfd1573f78d4f5).

1. Bearbeiten Sie die Parameter in der Konfigurationsdatei mithilfe der folgenden Tabelle als Anleitung.

   Beim Bearbeiten der [!DNL Transformation.cfg] -Datei in einem Data Workbench-Fenster verwenden, können Sie Tastaturbefehle für grundlegende Bearbeitungsfunktionen verwenden, z. B. Ausschneiden (Strg+x ), Kopieren (Strg+c) , Einfügen (Strg+V ), Rückgängigmachen (Strg+Z ), Wiederholen (Strg+Umschalt+Z ), Auswählen des Bereichs (Klicken+Ziehen) und Alle auswählen (Strg+A ). Darüber hinaus können Sie die Verknüpfungen verwenden, um Text aus einer Konfigurationsdatei zu kopieren und einzufügen ( [!DNL .cfg]) in eine andere.

   >[!NOTE]
   >
   >A [!DNL Transformation Dataset Include] -Dateien für ein geerbtes Profil enthält eine Teilmenge der in der folgenden Tabelle beschriebenen Parameter sowie einige zusätzliche Parameter. Informationen zu [!DNL Transformation Dataset Include] -Dateien, siehe [Datensatzaufnahme-Dateien](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md)

   <table id="table_5E184F67CCEC4421B2BBD4261711A6FE"> 
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
      <ul id="ul_1EC55DA4936946C98E447E1476E8280F"> 
       <li id="li_F2D862833F4B451C965E1ED6C05DCE1B"> 1. Januar 2013 HH:MM:SS EDT </li> 
       <li id="li_EB7FFEB2E2C24EAFB8E4B14F2479DA3D"> 1. Januar 2013 HH:MM:SS GMT </li> 
      </ul> </p> <p> Beispielsweise durch Angabe von "29. Juli 2013 00:00:00 EDT", da die Endzeit Daten bis zum 28. Juli 2013, 11 umfasst:59:17:00 UHR EDT. </p> <p> Sie müssen eine Zeitzone angeben. Wenn nicht anders angegeben, wird in der Zeitzone nicht standardmäßig GMT verwendet. Eine Liste der vom Data Workbench-Server unterstützten Zeitzonen-Abkürzungen finden Sie unter <a href="../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> Zeitzonencodes </a>. </p> <p> <p>Hinweis: Wenn Sie einen Wert für "Endzeit"angeben, wird ein Parameter mit dem Namen "Endzeit"festgelegt und während der gesamten Transformationsphase der Datensatzerstellung angewendet. Informationen zu Parametern finden Sie unter <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-def-param-dataset-inc-files.md#concept-5ad06acc8dc44bf2a99643fafdd56b50"> Definieren von Parametern in Datensatzaufnahme-Dateien </a>. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Erweiterte Dimensionen </td> 
      <td colname="col2"> Optional. Adobe empfiehlt, erweiterte Dimensionen in einer oder mehreren <span class="wintitle"> Einschließen von Umwandlungsdatensätzen </span> Dateien. Weitere Informationen finden Sie unter <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace"> Datensatzaufnahme-Dateien zur Transformation </a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Hash-Schwellenwert </td> 
      <td colname="col2"> <p>Optional. Ein Stichprobenfaktor für eine Stichprobe von Zeilen. Wenn der Wert auf eine Zahl n festgelegt ist, wird nur eine von n Tracking-IDs in den Datensatz aufgenommen, wodurch die Gesamtzahl der Zeilen im Datensatz um den Faktor n verringert wird. Um einen Datensatz zu erstellen, der eine 100-prozentige Genauigkeit erfordert (d. h., um alle Zeilen einzuschließen), setzen Sie den Hash-Schwellenwert auf 1. </p> <p> Wenn der Hash-Schwellenwert in beiden <span class="filepath"> Log Processing.cfg </span> und <span class="filepath"> Transformation.cfg </span> Dateien, wird sie nicht nacheinander angewendet; gilt das Maximum der Werte, die in beiden Konfigurationsdateien festgelegt wurden. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Protokolleintragsbedingung </td> 
      <td colname="col2"> Optional. Definiert die Regeln, nach denen Protokolleinträge, die aus der Protokollverarbeitung ausgegeben werden, zur Aufnahme in das Datensatzprofil berücksichtigt werden. Siehe <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-ecaff95cee4e40bc90f81e099c5fc934"> Protokolleintragsbedingung </a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Bedingung für neuen Besucher </td> 
      <td colname="col2"> Optional. Zur Verwendung mit Webdaten. Definiert die Regeln, nach denen Besucher zur Aufnahme in die Daten berücksichtigt werden. Die <span class="wintitle"> Bedingung für neuen Besucher </span> definiert den ersten Protokolleintrag für einen Besucher (geordnet nach Uhrzeit), der im Datensatz verwendet werden soll. Alle nachfolgenden Protokolleinträge für diesen Besucher werden in den Datensatz aufgenommen, unabhängig davon, ob sie diese Bedingung erfüllen. Siehe <a href="../../../home/c-dataset-const-proc/c-trans-config-file/c-spec-trans-param/c-new-vstr-con.md#concept-1d0d8e26718447ad9d235e00b33a36f3"> Bedingung für neuen Besucher </a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Neuverarbeitung </td> 
      <td colname="col2"> <p>Optional. Hier können beliebige Zeichen oder Kombinationen von Zeichen eingegeben werden. Wenn Sie diesen Parameter ändern und die Datei speichern, wird die Datenumwandlung initiiert. </p> <p> Informationen zur erneuten Verarbeitung Ihrer Daten finden Sie unter <a href="../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md"> Wiederaufbereitung und erneute Umwandlung </a>. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Schemavalidierung </td> 
      <td colname="col2"> True oder false. Wenn "true", erkennt der Data Workbench-Server Probleme mit Beschädigung von Datensätzen und zeichnet Informationen über die Probleme in Protokolldateien im Trace-Verzeichnis des Data Workbench-Servers auf. Der Standardwert ist "true". Adobe empfiehlt, diesen Parameter immer auf "true"zu setzen. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Phasen </td> 
      <td colname="col2"> <p>Optional. Die Namen der Verarbeitungsschritte, die in <span class="wintitle"> Einschließen von Umwandlungsdatensätzen </span> Dateien. Verarbeitungsschritte bieten eine Möglichkeit, die in <span class="wintitle"> Einschließen von Umwandlungsdatensätzen </span> Dateien. Dieser Parameter ist sehr hilfreich, wenn Sie eine oder mehrere Umwandlungen innerhalb mehrerer <span class="wintitle"> Einschließen von Umwandlungsdatensätzen </span> -Dateien und Sie möchten, dass bestimmte Umwandlungen an bestimmten Punkten während der Transformation vorgenommen werden. </p> <p> Die Reihenfolge, in der Sie die Phasen hier auflisten, bestimmt die Reihenfolge, in der die Umwandlungen in der <span class="wintitle"> Einschließen von Umwandlungsdatensätzen </span> -Dateien werden während der Transformation ausgeführt. <span class="wintitle"> Vorverarbeitung </span> und <span class="wintitle"> Nachbearbeitung </span> sind eingebaute Phasen; <span class="wintitle"> Vorverarbeitung </span> ist immer der erste Schritt und <span class="wintitle"> Nachbearbeitung </span> ist immer der letzte Schritt. Standardmäßig gibt es eine benannte Phase namens <span class="wintitle"> Standard </span>. </p> <p> <b>So fügen Sie eine neue Verarbeitungsphase hinzu</b> </p> <p> 
      <ul id="ul_6AF2EF72CEE34FA88575C46FA333BDA1"> 
       <li id="li_80627E7A89CE4E57A4228C4F5496533F"> Im <span class="filepath"> Transformation.cfg </span> Fenster, Rechtsklick <span class="uicontrol"> Phasen </span> und klicken Sie auf <span class="uicontrol"> Neu hinzufügen </span> &gt; <span class="uicontrol"> Staging </span>. </li> 
       <li id="li_321BEDB1E95F4AA4B282EED32A4CA196"> Geben Sie einen Namen für die neue Phase ein. </li> 
      </ul> </p> <p> <b>So löschen Sie eine vorhandene Verarbeitungsphase</b> </p> <p> 
      <ul id="ul_2EFA5A40982A48919E9946BF1955110A"> 
       <li id="li_3B3829DA34FD4774B3F9F94074099794"> Klicken Sie mit der rechten Maustaste auf die Nummer der Phase, die Sie löschen möchten, und klicken Sie auf <span class="uicontrol"> Entfernen </span><i>&lt; <span class="uicontrol"> #stage_number </span>&gt;</i>. </li> 
      </ul> </p> <p> <p>Hinweis: Wenn Sie eine Bühne in einem <span class="wintitle"> Einschließen von Umwandlungsdatensätzen </span> -Dateien muss der Name der Bühne genau mit dem Namen übereinstimmen, den Sie hier eingeben. Weitere Informationen zu Datensatzaufnahme-Dateien finden Sie unter <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md"> Datensatzaufnahme-Dateien </a>. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Startzeit </td> 
      <td colname="col2"> <p>Optional. Filtern Sie Daten, um Protokolleinträge mit Zeitstempeln zu dieser Zeit oder danach einzuschließen. Adobe empfiehlt die Verwendung eines der folgenden Zeitformate: 
      <ul id="ul_6BC86CCB1FC447ACAC4045E08C8EF8F8"> 
       <li id="li_2151B3F7FAD54F38B6C33E25CDCACBBE"> 1. Januar 2013 HH:MM:SS EDT </li> 
       <li id="li_CA1BB675C1244104915FB9ED96A3013D"> 1. Januar 2013 HH:MM:SS GMT </li> 
      </ul> </p> <p> Beispiel: 29. Juli 2013 00:00:00 EDT als <span class="wintitle"> Startzeit </span> enthält Daten ab dem 29. Juli 2013, 12:00:00 UHR EDT. </p> <p> Sie müssen eine Zeitzone angeben. Wenn nicht anders angegeben, wird in der Zeitzone nicht standardmäßig GMT verwendet. Eine Liste der vom Data Workbench-Server unterstützten Zeitzonen-Abkürzungen finden Sie unter <a href="../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> Zeitzonencodes </a>. </p> <p> <p>Hinweis: Wenn Sie einen Wert für Startzeit angeben, wird ein Parameter mit dem Namen Startzeit festgelegt und während der gesamten Transformationsphase der Datensatzerstellung angewendet. Informationen zu Parametern finden Sie unter <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-def-param-dataset-inc-files.md#concept-5ad06acc8dc44bf2a99643fafdd56b50"> Definieren von Parametern in Datensatzaufnahme-Dateien </a>. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Umwandlungen </td> 
      <td colname="col2"> Optional. Adobe empfiehlt die Definition von Transformationen für die Umwandlungsphase der Datensatzerstellung in einer oder mehreren <span class="wintitle"> Einschließen von Umwandlungsdatensätzen </span> Dateien. Weitere Informationen finden Sie unter <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace"> Datensatzaufnahme-Dateien zur Transformation </a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Zeitzone </td> 
      <td colname="col2"> <p>Zeitzone des Datensatzprofils. Zeitzonen werden für Zeitkonversionen und zum Erstellen von Zeitdimensionen verwendet. Siehe <a href="../../../home/c-dataset-const-proc/c-trans-config-file/c-spec-trans-param/c-time-zones.md#concept-9cf16b1cb4874f7d85e1dd950fdb4956"> Zeitzonen </a>. </p> <p> <p>Hinweis: Wenn im <span class="filepath"> Log Processing.cfg </span> -Datei, wird der Parameter Zeitzone nur für Zeitkonvertierungen verwendet. </p> </p> </td> 
   </tr> 
   </tbody> 
   </table>

1. Rechtsklick **[!UICONTROL (modified)]** Klicken Sie oben im Fenster auf **[!UICONTROL Save]**.
1. Im [!DNL Profile Manager]klicken Sie mit der rechten Maustaste auf das Häkchen für [!DNL Transformation.cfg]im [!DNL User] und klicken Sie auf **[!UICONTROL Save to]** > * **[!UICONTROL dataset profile name]** , damit die lokal vorgenommenen Änderungen wirksam werden. Die erneute Umwandlung der Daten beginnt nach der Synchronisierung des Datensatzprofils.

   >[!NOTE]
   >
   >Speichern Sie die geänderte Konfigurationsdatei nicht in einem der von Adobe bereitgestellten internen Profile, da Ihre Änderungen bei der Installation von Updates für diese Profile überschrieben werden.

   Weitere Informationen zur Neuverarbeitung oder Umformung Ihrer Daten finden Sie unter [Wiederaufbereitung und erneute Umwandlung](../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).
