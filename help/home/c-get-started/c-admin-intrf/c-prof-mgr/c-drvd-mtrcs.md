---
description: Sie definieren neue Metriken (die als abgeleitete Metriken bezeichnet werden) und bearbeiten vorhandene Metrikdefinitionen mithilfe des Metrik-Editors.
solution: Analytics
title: Arbeiten mit abgeleiteten Metriken
topic: Data workbench
uuid: 9767c170-e0cb-47b4-94f1-e9f6950b5926
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Arbeiten mit abgeleiteten Metriken{#work-with-derived-metrics}

Sie definieren neue Metriken (die als abgeleitete Metriken bezeichnet werden) und bearbeiten vorhandene Metrikdefinitionen mithilfe des Metrik-Editors.

Weitere Informationen zu Metriken, die in diesem Abschnitt und in der [Abfragesprachensyntax](../../../../home/c-get-started/c-qry-lang-syntx/c-qry-lang-syntx.md#concept-15d1d3f5164a47d49468c5acb7299d9f)angegeben sind, finden Sie im Handbuch *Metriken, Dimensionen und Filter*.

## Erstellen einer abgeleiteten Metrik {#section-d57b98bf0a9940daba4920ff7efc808d}

Mit einem können Sie eine neue Metrik [!DNL Metric Editor] nach Name, Formel und Format definieren, die im Ordner &quot;Benutzer\*Profilname*\Metriken&quot;zur späteren Verwendung gespeichert wird.

1. Öffnen Sie eine neue [!DNL Metric Editor] Datei mit der Menüoption **[!UICONTROL Admin]** > **[!UICONTROL Profile]** oder klicken Sie mit der rechten Maustaste auf die **[!UICONTROL User]** Spalte für den Ordner, in dem Sie die Metrik erstellen möchten, und klicken Sie auf **[!UICONTROL Create]** > **[!UICONTROL New Metric]**.

   Eine [!DNL Metric Editor] wird angezeigt.

1. Geben Sie im Parameter Name einen Namen für die neue Metrik ein.

   Beachten Sie, dass Leerzeichen ( ) zulässig sind, Unterstriche (_) nicht. Darüber hinaus können die folgenden Symbole nicht verwendet werden:

   `+ - * /`

   ![](assets/vis_MetricEditor_NewAndEditing.png)

1. Geben Sie im Parameter &quot;Formel&quot;einen Ausdruck für die neue Metrik ein. Beachten Sie, dass Filter in Klammern definiert werden müssen. [ ] im Ausdruck.

   Weitere Syntaxregeln für Metrikausdrücke finden Sie unter [Syntax für Metrikausdrücke](../../../../home/c-get-started/c-qry-lang-syntx/c-syntx-mtrc-exp.md#concept-bbf440a0307549e088df491b51b51d66).

   Die folgende Tabelle enthält Musterausdrücke für erweiterte Metriken.

   <table id="table_ED77997FC08F492490DCAC3C4153781C"> 
   <thead> 
   <tr> 
      <th colname="col1" class="entry"> Name der erweiterten Metrik </th> 
      <th colname="col2" class="entry"> Ausdruck </th> 
   </tr>
   </thead>
   <tbody> 
   <tr> 
      <td colname="col1"> <p>Erste Sitzungen in Prozent </p> </td> 
      <td colname="col2"> <p><span class="filepath"> Sitzungen [Sitzung_Nummer="1"]/Sitzungen</span> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>Konvertierungssitzungen erste Sitzungen </p> </td> 
      <td colname="col2"> <p><span class="filepath"> Konversion [Session_Number="1"]</span> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>Durchschnittlicher Wert pro Besucher </p> </td> 
      <td colname="col2"> <p><span class="filepath"> Wert/Besucher</span> </p> </td> 
   </tr> 
   </tbody> 
   </table>

   >[!NOTE]
   >
   >Wenn ein passender Ausdruck eingegeben wird, zeigt die Vorschauzeile den Wert der neuen Metrik an. Wenn der Ausdruck einen Fehler enthält, wird in der Zeile &quot;Vorschau&quot;eine Fehlermeldung angezeigt.

1. Klicken Sie mit der rechten Maustaste **[!UICONTROL (New)]** und klicken Sie **[!UICONTROL Save]**.

   Wenn Sie die Metrik speichern, wird auf Ihrem Computer im Installationsordner von Data Workbench eine Datei erstellt, die die neue Metrik darstellt \User\*Profilname*\Metrics.

   ![](assets/vis_MetricEditor_NewAndEditing.png)

Sie können die neue Metrik jetzt im gesamten aktuellen Profil verwenden, indem Sie sie wie jede integrierte Metrik auswählen. Informationen zum Ändern der Reihenfolge, in der Ihre Metriken im Menü &quot;Metriken&quot;angezeigt werden, finden Sie unter Menüs mithilfe der Dateien &quot;Reihenfolge.txt&quot; [anpassen](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999).

Wenn Sie möchten, dass alle Benutzer des Profils die von Ihnen erstellte Metrik verwenden, müssen Sie sie mithilfe der [!DNL Profile Manager]Funktion im Arbeitsprofil veröffentlichen. Siehe [Veröffentlichen von Dateien in Ihrem Arbeitsprofil](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task-a0106e010c834d16bd60eef4721b6af9).

## Bearbeiten abgeleiteter Metriken {#section-db6d924cf4e14bcc8d57cfe1059fc797}

1. Klicken Sie in der Spalte [!DNL Profile Manager] oder [!DNL Metrics Manager], in der Spalte *Profilname* , mit der rechten Maustaste auf das Häkchen für die Metrikdatei, die Sie bearbeiten möchten, und klicken Sie dann auf **[!UICONTROL Make Local]**.
1. Klicken Sie mit der rechten Maustaste auf das Häkchen für die Metrikdatei in der [!DNL User] Spalte und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**.

   >[!NOTE]
   >
   >Sie können eine Metrik auch öffnen, [!DNL Metric Editor] indem Sie mit der rechten Maustaste auf einen Metrikbereich innerhalb einer Visualisierung klicken, um das Metrikmenü anzuzeigen. Weitere Informationen finden Sie unter [Arbeiten mit Metrik- und Dimensionsmenüs](../../../../home/c-get-started/c-vis/c-met-dim-menus.md#concept-50f07ae47c3e4f94ad7d3d7f8293ccac).

1. Bearbeiten und speichern Sie die Metrikdefinition im [!DNL Metric Editor]Abschnitt 2-4 unter [Erstellen neuer abgeleiteter Metriken](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-drvd-mtrcs.md#section-d57b98bf0a9940daba4920ff7efc808d)nach Bedarf.

   Wenn Sie möchten, dass alle Benutzer des Profils die von Ihnen bearbeitete Metrik verwenden, müssen Sie sie mithilfe der [!DNL Profile Manager]Funktion im Arbeitsprofil veröffentlichen. Siehe [Veröffentlichen von Dateien in Ihrem Arbeitsprofil](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task-a0106e010c834d16bd60eef4721b6af9).

