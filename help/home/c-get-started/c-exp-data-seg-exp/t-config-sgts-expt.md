---
description: Sie können ein Segment der Elemente einer zählbaren Dimension erstellen und dann Daten für dieses Segment stapelweise oder laufend in Echtzeit in einer tabulatorgetrennten Datei ausgeben.
solution: Analytics
title: Segmente für den Export konfigurieren
topic: Data workbench
uuid: 651be834-ee41-4487-8c5a-30d94580f6a0
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Segmente für den Export konfigurieren{#configure-segments-for-export}

Sie können ein Segment der Elemente einer zählbaren Dimension erstellen und dann Daten für dieses Segment stapelweise oder laufend in Echtzeit in einer tabulatorgetrennten Datei ausgeben.

Immer, wenn Sie ein Segment exportieren, geben Sie Metrik- oder Dimensionsdaten für alle im Segment mit eingeschlossenen Dimensionselemente aus. Sie können steuern, wie die Ausgabedaten formatiert werden, so dass die Daten problemlos von anderen Systemen geladen werden können.

>[!NOTE]
>
>Sie können keine Berichtsdimensionen exportieren, da sie eine [!DNL report time.metric] Datei als Referenz verwenden. Wenn Sie eine Hartkodierung [!DNL report time.metric] in das Profil einfügen, kann der Segmentexport sie als Referenzpunkt für die Berichterstellungsdimensionen verwenden. Der Bericht wird jedoch [!DNL report time.metric] nicht automatisch auf Grundlage der Ausführungszeit des Profils aktualisiert. Wenn Sie den Berichtsdimensionsverweis ändern möchten, müssen Sie die hartkodierte [!DNL report time.metric] Datei ändern.

Um ein Segment für den Export zu konfigurieren, müssen Sie eine [!DNL .export] Datei öffnen und bearbeiten.

1. Klicken Sie im [!DNL Profile Manager]Ordner auf das **[!UICONTROL Export]** Verzeichnis in der [!DNL File] Spalte, um den Inhalt anzuzeigen.

       Wenn der Exportordner nicht vorhanden ist, erstellen Sie ihn wie folgt:
   
   1. Navigieren Sie zum Installationsordner von Data Workbench.
   1. Öffnen Sie den Ordner für das Profil, mit dem Sie arbeiten.
   1. Erstellen Sie im Profilverzeichnis einen neuen Ordner mit dem Namen &quot;Export&quot;.

1. Klicken Sie im [!DNL Profile Manager]Kontextmenü mit der rechten Maustaste auf die leere Zelle in der [!DNL User] Spalte für den Exportordner und klicken Sie dann auf **[!UICONTROL Create]** > **[!UICONTROL New Segment Export]**.

   Eine Datei mit dem Namen [!DNL New Segment Export.export] wird in der [!DNL File] Spalte für den Export angezeigt.

1. Benennen Sie die neue Datei um, indem Sie mit der rechten Maustaste in die [!DNL User] Spalte für die Datei klicken und den neuen Namen im Dateiparameter eingeben.
1. Öffnen Sie die neue Datei, indem Sie mit der rechten Maustaste in die [!DNL User] Spalte für die Datei klicken und auf **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**.

   Das Konfigurationsfenster für die [!DNL .export] Datei wird angezeigt.

1. Klicken Sie auf **[!UICONTROL Query]** und ändern Sie dann die Felder der [!DNL .export] Datei wie in der folgenden Tabelle beschrieben:

<table id="table_C2EC8FCD3FA04DE78D2CADFA3F7FD8E3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Für diesen Parameter... </th> 
   <th colname="col2" class="entry"> Geben Sie diese Informationen ein... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Befehl </td> 
   <td colname="col2"> <p>Optional. Ein Programm, das nach dem Erstellen der Ausgabedatei ausgeführt wird. Dieses Feld muss auf eine ausführbare Datei (eine <span class="filepath"> .exe- </span> Datei) verweisen, nicht auf einen Shell-Befehl. </p> <p>Hinweis:  Der Segmentexport schlägt fehl, wenn der Befehlsparameter einen Leerzeichen enthält. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Filter </td> 
   <td colname="col2"> <p>Optional. Ein benannter Filter oder ein Filterausdruck. Sie können einen benannten Filter entweder mit einem Filter-Editor erstellen und dann den Namen des Filters hier eingeben oder Sie können einen Filterausdruck selbst eingeben. </p> <p>Weitere Informationen zu Filter-Editoren finden Sie unter <a href="../../../home/c-get-started/c-analysis-vis/c-filter-editors/c-filter-editors.md#concept-2f343ecbed8240f18b0c1f1eccef11e3"> Filter-Editoren </a>. Weitere Informationen zur Syntax von Filterausdrücken finden Sie unter <a href="../../../home/c-get-started/c-qry-lang-syntx/c-syntx-fltr-exp.md#concept-72f2563f809747a2a3cff7ec72462a15"> Syntax für Filterausdrücke </a>. </p> <p>Elemente der Ebene, die mit dem Filter übereinstimmen, werden exportiert, während alle anderen Elemente nicht. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ebene </td> 
   <td colname="col2"> <p>Die zählbare Dimension, deren Elemente exportiert werden sollen. </p> <p>Beispiel: Eine Besucherebene exportiert eine Datenzeile für jeden Besucher. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ausgabedatei </td> 
   <td colname="col2"> <p>Pfad und Dateiname der exportierten Daten. Wenn das Profil auf einem Data Workbench-Servercluster ausgeführt wird, schreibt jeder Data Workbench-Server eine Ausgabedatei, die einen Teil der Daten enthält. </p> <p>Der Installationsordner des Data Workbench-Servers enthält einen Exportordner, in dem Sie die Ausgabedatei speichern können. Sie können beispielsweise " <span class="filepath"> Exporte\Besuchersegment.txt"eingeben </span>, wobei " <span class="filepath"> Visitor Segment.txt"der Name der Datei mit den exportierten Daten </span> ist. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ausgabeformat </td> 
   <td colname="col2"> Die Metrik- oder Dimensionsdaten, die für jedes Level-Element exportiert werden sollen. Wenn es sich bei der Ausgabe um eine tabulatorgetrennte Datei handelt, sollten die Felder durch Tabulatorzeichen getrennt werden, und das Format sollte mit den entsprechenden Zeilenzeichen enden. Weitere Informationen finden Sie unter <a href="../../../home/c-get-started/c-exp-data-seg-exp/c-abt-otpt-frmt.md#concept-ac7e24d1374a4b418365db7cc98c361e"> Grundlagen zum Ausgabeformat </a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Endzeit planen </td> 
   <td colname="col2"> <p>Optional. Enddatum und -zeit des Zeitplans, einschließlich der Zeitzone. </p> <p>Format: JJJJ-MM-TT hh:mm Zeitzone </p> <p>Beispiel: 2013-08-01 12:01 EDT </p> <p>Geplante Exporte werden derzeit eingestellt. Die Ausgabedatei wird jedoch immer dann erneut generiert, wenn ihre Definition geändert wird. Dieses Feld ist ohne Definition von "Alle planen"aussagekräftig. Weitere Informationen zu Zeitzoneneinstellungen finden Sie im Handbuch zur Konfiguration von <i>Datasets</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Alle planen </td> 
   <td colname="col2"> Optional. Die Häufigkeit, mit der die Ausgabedatei neu generiert werden soll. Unterstützte Werte sind Stunde, Tag, Woche und Monat. Die Ausgabedatei wird immer noch regeneriert, wenn ihre Definition geändert wird. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Startzeit planen </td> 
   <td colname="col2"> <p>Optional. Das Startdatum und die Uhrzeit für den Zeitplan, einschließlich der Zeitzone. </p> <p>Format: JJJJ-MM-TT hh:mm Zeitzone </p> <p>Beispiel: 2013-08-01 12:01 EDT </p> <p>Geplante Exporte beginnen zu diesem Zeitpunkt und der Zeitplan ist relativ zu diesem Zeitpunkt. Dieses Feld ist ohne Definition von " <span class="wintitle"> Plan alle"aussagekräftig </span>. Weitere Informationen zu Zeitzoneneinstellungen finden Sie im Handbuch zur Konfiguration von <i>Datasets</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Zeitlimit (Sek.) </td> 
   <td colname="col2"> Optional. Die maximale Zeit, die vergehen darf, während ein Segmentexport generiert wird. Wenn das angegebene Intervall überschritten wird, beginnt der Export von vorn. Wenn Sie diesen Wert auf 0 (null) setzen, wird der Grenzwert entfernt. Der Standardwert ist 600 Sekunden. </td> 
  </tr> 
 </tbody> 
</table>

1. Klicken Sie mit der rechten Maustaste **[!UICONTROL (New)]** am oberen Rand des Fensters und klicken Sie dann auf **[!UICONTROL Save]**.
1. Um diese Datei allen Benutzern des Arbeitsprofils zur Verfügung zu stellen, klicken Sie mit der rechten Maustaste auf das Häkchen für die erstellte [!DNL .export] Datei in der [!DNL User] Spalte und klicken Sie dann auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.

   >[!NOTE]
   >
   >Wenn Sie die [!DNL .export] Datei auf dem Data Workbench-Server speichern, wird der Export einmal sofort ausgeführt, auch wenn die &quot;Planen-Startzeit&quot;auf ein künftiges Datum und eine Uhrzeit eingestellt ist.

   The following is a sample [!DNL .export] file.

   ![](assets/vis_Segment_Export_File.png)

   >[!NOTE]
   >
   >Die im Beispiel angezeigte [!DNL Visitor Segment.export] Datei bezieht sich auf den Filter &quot;Besuchersegment&quot;. Wenn Sie die Definition dieses Filters ändern, ändert sich die Definition des Exports.

