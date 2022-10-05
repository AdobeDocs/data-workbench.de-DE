---
description: Sie können ein Segment der Elemente einer beliebigen zählbaren Dimension erstellen und dann Daten für dieses Segment auf Batch- oder fortlaufender Echtzeitbasis in einer tabulatorgetrennten Datei ausgeben.
title: Konfigurieren von Segmenten für den Export
uuid: 651be834-ee41-4487-8c5a-30d94580f6a0
exl-id: 4f53e02c-3f00-44b3-9f6d-a2f23903b3fa
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '865'
ht-degree: 6%

---

# Konfigurieren von Segmenten für den Export{#configure-segments-for-export}

{{eol}}

Sie können ein Segment der Elemente einer beliebigen zählbaren Dimension erstellen und dann Daten für dieses Segment auf Batch- oder fortlaufender Echtzeitbasis in einer tabulatorgetrennten Datei ausgeben.

Immer, wenn Sie ein Segment exportieren, geben Sie Metrik- oder Dimensionsdaten für alle im Segment mit eingeschlossenen Dimensionselemente aus. Sie können steuern, wie die Ausgabedaten formatiert werden, so dass die Daten problemlos von anderen Systemen geladen werden können.

>[!NOTE]
>
>Sie können keine Berichtsdimensionen exportieren, da sie eine [!DNL report time.metric] -Datei als Referenz. Wenn Sie als Problemumgehung eine hartcodierte [!DNL report time.metric] im Profil kann der Segmentexport ihn als Referenzpunkt für Berichtsdimensionen verwenden. Die Variable [!DNL report time.metric] wird nicht automatisch auf Grundlage des Ausführungszeitpunkts des Profils aktualisiert. Wenn Sie also den Verweis auf die Berichtsdimension ändern möchten, müssen Sie die hartcodierte [!DNL report time.metric] -Datei.

Um ein Segment für den Export zu konfigurieren, müssen Sie eine [!DNL .export] -Datei.

1. Im [!DNL Profile Manager], klicken Sie auf die **[!UICONTROL Export]** im Verzeichnis [!DNL File] -Spalte, um ihren Inhalt anzuzeigen.

       Wenn das Exportverzeichnis nicht vorhanden ist, erstellen Sie es wie folgt:
   
   1. Navigieren Sie zum Installationsverzeichnis der Data Workbench.
   1. Öffnen Sie das Verzeichnis für das Profil, mit dem Sie arbeiten.
   1. Erstellen Sie im Profilverzeichnis ein neues Verzeichnis mit dem Namen &quot;Export&quot;.

1. Im [!DNL Profile Manager]klicken Sie mit der rechten Maustaste auf die leere Zelle im [!DNL User] Spalte für das Exportverzeichnis und klicken Sie auf **[!UICONTROL Create]** > **[!UICONTROL New Segment Export]**.

   Eine Datei mit dem Namen [!DNL New Segment Export.export] im [!DNL File] -Spalte für Export.

1. Benennen Sie die neue Datei um, indem Sie mit der rechten Maustaste auf die [!DNL User] -Spalte für die Datei und geben Sie den neuen Namen in den Dateiparameter ein.
1. Öffnen Sie die neue Datei, indem Sie mit der rechten Maustaste auf die [!DNL User] Spalte für die Datei und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**.

   Das Konfigurationsfenster für die [!DNL .export] angezeigt.

1. Klicken **[!UICONTROL Query]**, ändern Sie dann die Felder der [!DNL .export] -Datei wie in der folgenden Tabelle beschrieben:

<table id="table_C2EC8FCD3FA04DE78D2CADFA3F7FD8E3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Für diesen Parameter ... </th> 
   <th colname="col2" class="entry"> Geben Sie diese Informationen an... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Befehl </td> 
   <td colname="col2"> <p>Optional. Ein Programm, das ausgeführt wird, nachdem die Ausgabedatei erstellt wurde. Dieses Feld muss auf eine ausführbare Datei (eine <span class="filepath"> .exe </span> -Datei), kein Shell-Befehl. </p> <p>Hinweis: Der Segmentexport schlägt fehl, wenn im Befehlsparameter ein Leerzeichen vorhanden ist. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Filter </td> 
   <td colname="col2"> <p>Optional. Ein benannter Filter oder ein Filterausdruck. Sie können entweder einen benannten Filter mithilfe eines Filter-Editors erstellen und dann den Namen dieses Filters hier eingeben oder einen Filterausdruck selbst eingeben. </p> <p>Weitere Informationen zu Filter-Editoren finden Sie unter <a href="../../../home/c-get-started/c-analysis-vis/c-filter-editors/c-filter-editors.md#concept-2f343ecbed8240f18b0c1f1eccef11e3"> Filter-Editoren </a>. Weitere Informationen zur Syntax von Filterausdrücken finden Sie unter <a href="../../../home/c-get-started/c-qry-lang-syntx/c-syntx-fltr-exp.md#concept-72f2563f809747a2a3cff7ec72462a15"> Syntax für Filterausdrücke </a>. </p> <p>Elemente der Ebene, die mit dem Filter übereinstimmen, werden exportiert, alle anderen Elemente hingegen nicht. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ebene </td> 
   <td colname="col2"> <p>Die zählbare Dimension, deren Elemente exportiert werden sollen. </p> <p>Beispiel: Eine Besucherebene exportiert eine Datenzeile für jeden Besucher. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ausgabedatei </td> 
   <td colname="col2"> <p>Pfad und Dateiname der exportierten Daten. Wenn das Profil auf einem Data Workbench-Server-Cluster ausgeführt wird, schreibt jeder Data Workbench-Server eine Ausgabedatei, die einen Teil der Daten enthält. </p> <p>Der Installationsordner des Data Workbench-Servers enthält einen Ordner "Exporte", in dem Sie die Ausgabedatei speichern können. Sie können beispielsweise <span class="filepath"> Exports\Visitor Segment.txt </span>, wobei <span class="filepath"> Visitor Segment.txt </span> ist der Name der Datei, die die exportierten Daten enthält. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ausgabeformat </td> 
   <td colname="col2"> Die Metrik- oder Dimensionsdaten, die für jedes Level-Element exportiert werden sollen. Wenn es sich bei der Ausgabe um eine tabulatorgetrennte Datei handelt, sollten die Felder durch Tabulatorzeichen getrennt werden und das Format sollte mit den entsprechenden neuen Zeilenzeichen enden. Weitere Informationen finden Sie unter <a href="../../../home/c-get-started/c-exp-data-seg-exp/c-abt-otpt-frmt.md#concept-ac7e24d1374a4b418365db7cc98c361e"> Über das Ausgabeformat </a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Endzeit planen </td> 
   <td colname="col2"> <p>Optional. Enddatum und -zeit für den Zeitplan, einschließlich der Zeitzone. </p> <p>Format: JJJJ-MM-TT hh:mm Zeitzone </p> <p>Beispiel: 01.08.2013 12:01 EDT </p> <p>Geplante Exporte werden zu diesem Zeitpunkt eingestellt. Die Ausgabedatei wird jedoch bei jeder Änderung ihrer Definition erneut generiert. Dieses Feld ist ohne Definition von "Alle planen"ohne Bedeutung. Weitere Informationen zu Zeitzoneneinstellungen finden Sie unter <i>Anleitung zur Datensatzkonfiguration</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Zeitplan </td> 
   <td colname="col2"> Optional. Die Häufigkeit, mit der die Ausgabedatei neu generiert werden soll. Unterstützte Werte sind Stunde, Tag, Woche und Monat. Die Ausgabedatei wird immer noch neu generiert, wenn ihre Definition geändert wird. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Startzeit planen </td> 
   <td colname="col2"> <p>Optional. Das Startdatum und die Startzeit für den Zeitplan, einschließlich der Zeitzone. </p> <p>Format: JJJJ-MM-TT hh:mm Zeitzone </p> <p>Beispiel: 01.08.2013 12:01 EDT </p> <p>Geplante Exporte beginnen zu diesem Zeitpunkt und der Zeitplan ist relativ zu diesem Zeitpunkt. Dieses Feld ist ohne Definition von Bedeutung <span class="wintitle"> Zeitplan </span>. Weitere Informationen zu Zeitzoneneinstellungen finden Sie unter <i>Anleitung zur Datensatzkonfiguration</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Zeitlimit (Sek.) </td> 
   <td colname="col2"> Optional. Die maximale Zeit, die verstreichen darf, während ein Segmentexport generiert wird. Wenn das angegebene Intervall überschritten wird, beginnt der Export von vorn. Wenn Sie diesen Wert auf 0 (null) setzen, wird die Begrenzung entfernt. Der Standardwert ist 600 Sekunden. </td> 
  </tr> 
 </tbody> 
</table>

1. Rechtsklick **[!UICONTROL (New)]** Klicken Sie oben im Fenster auf **[!UICONTROL Save]**.
1. Um diese Datei allen Benutzern des Arbeitsprofils zur Verfügung zu stellen, klicken Sie mit der rechten Maustaste auf das Häkchen für die erstellte Datei [!DNL .export] in der Datei [!DNL User] und klicken Sie auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.

   >[!NOTE]
   >
   >Speichern der [!DNL .export] -Datei auf den Data Workbench-Server zu laden, führt der Export einmal sofort durch, selbst wenn die Option &quot;Planen Sie die Startzeit&quot;auf ein zukünftiges Datum und eine zukünftige Uhrzeit festgelegt ist.

   Im Folgenden finden Sie ein Beispiel [!DNL .export] -Datei.

   ![](assets/vis_Segment_Export_File.png)

   >[!NOTE]
   >
   >Die [!DNL Visitor Segment.export] -Datei, die im Beispiel angezeigt wird, bezieht sich auf den Filter Besuchersegment . Durch die Änderung der Definition dieses Filters wird die Definition des Exports geändert.
