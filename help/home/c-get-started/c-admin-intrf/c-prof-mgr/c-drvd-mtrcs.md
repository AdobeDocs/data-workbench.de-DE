---
description: Sie definieren neue Metriken (als abgeleitete Metriken bezeichnet) und bearbeiten vorhandene Metrikdefinitionen mithilfe des Metrik-Editors.
title: Arbeiten mit abgeleiteten Metriken
uuid: 9767c170-e0cb-47b4-94f1-e9f6950b5926
exl-id: 83467c64-4b9a-44ab-91a2-202c76c89979
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '468'
ht-degree: 1%

---

# Arbeiten mit abgeleiteten Metriken{#work-with-derived-metrics}

{{eol}}

Sie definieren neue Metriken (als abgeleitete Metriken bezeichnet) und bearbeiten vorhandene Metrikdefinitionen mithilfe des Metrik-Editors.

Weitere Informationen zu Metriken finden Sie in diesem Abschnitt und in [Syntax der Abfragesprache](../../../../home/c-get-started/c-qry-lang-syntx/c-qry-lang-syntx.md#concept-15d1d3f5164a47d49468c5acb7299d9f), siehe *Handbuch zu Metriken, Dimensionen und Filtern*.

## abgeleitete Metrik erstellen {#section-d57b98bf0a9940daba4920ff7efc808d}

Sie verwenden eine [!DNL Metric Editor] , um eine neue Metrik nach Name, Formel und Format zu definieren, die im Ordner &quot;User\*profile_name*\Metrics&quot;zur späteren Verwendung gespeichert wird.

1. Neu öffnen [!DNL Metric Editor] mithilfe der **[!UICONTROL Admin]** > **[!UICONTROL Profile]** oder durch Rechtsklick auf die **[!UICONTROL User]** für den Ordner, in dem Sie die Metrik erstellen möchten, und klicken Sie auf **[!UICONTROL Create]** > **[!UICONTROL New Metric]**.

   A [!DNL Metric Editor] angezeigt.

1. Geben Sie im Parameter Name einen Namen für die neue Metrik ein.

   Beachten Sie, dass Leerzeichen ( ) zulässig sind, Unterstriche (_) dagegen nicht. Außerdem können Sie die folgenden Symbole nicht verwenden:

   `+ - * /`

   ![](assets/vis_MetricEditor_NewAndEditing.png)

1. Geben Sie im Parameter Formel einen Ausdruck für die neue Metrik ein. Beachten Sie, dass Filter in Klammern definiert werden müssen. [ ] im Ausdruck.

   Weitere Syntax-Regeln für Metriken-Ausdrücke finden Sie unter [Syntax für Metrikausdrücke](../../../../home/c-get-started/c-qry-lang-syntx/c-syntx-mtrc-exp.md#concept-bbf440a0307549e088df491b51b51d66).

   Die folgende Tabelle enthält Beispielausdrücke für erweiterte Metriken.

   <table id="table_ED77997FC08F492490DCAC3C4153781C"> 
   <thead> 
   <tr> 
      <th colname="col1" class="entry"> Name der erweiterten Metrik </th> 
      <th colname="col2" class="entry"> Ausdruck </th> 
   </tr>
   </thead>
   <tbody> 
   <tr> 
      <td colname="col1"> <p>Prozentuale erste Sitzungen </p> </td> 
      <td colname="col2"> <p><span class="filepath"> Sitzungen [Session_Number="1"]/Sitzungen</span> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>Konversion Erste Sitzungen </p> </td> 
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
   >Wenn ein entsprechender Ausdruck eingegeben wird, zeigt die Vorschauzeile den Wert der neuen Metrik an. Wenn der Ausdruck einen Fehler enthält, zeigt die Vorschauzeile eine Fehlermeldung an.

1. Rechtsklick **[!UICONTROL (New)]** und klicken Sie auf **[!UICONTROL Save]**.

   Wenn Sie die Metrik speichern, wird eine Datei, die die neue Metrik darstellt, auf Ihrem Computer im Ordner &quot;Data Workbench Installation directory \User\*profile name*\Metrics&quot;erstellt.

   ![](assets/vis_MetricEditor_NewAndEditing.png)

Sie können die neue Metrik jetzt im gesamten aktuellen Profil verwenden, indem Sie sie wie jede integrierte Metrik auswählen. Informationen zum Ändern der Reihenfolge, in der Ihre Metriken im Menü &quot;Metriken&quot;angezeigt werden, finden Sie unter [Menüs mithilfe von &quot;order.txt&quot;-Dateien anpassen](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999).

Wenn Sie möchten, dass alle Benutzer des Profils die von Ihnen erstellte Metrik verwenden, müssen Sie sie mithilfe des [!DNL Profile Manager]. Siehe [Veröffentlichen von Dateien in Ihrem Arbeitsprofil](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task-a0106e010c834d16bd60eef4721b6af9).

## abgeleitete Metriken bearbeiten {#section-db6d924cf4e14bcc8d57cfe1059fc797}

1. Im [!DNL Profile Manager] oder [!DNL Metrics Manager]in der *Profilname* klicken Sie mit der rechten Maustaste auf das Häkchen für die Metrikdatei, die Sie bearbeiten möchten, und klicken Sie dann auf **[!UICONTROL Make Local]**.
1. Klicken Sie mit der rechten Maustaste auf das Häkchen für die Metrikdatei im [!DNL User] Spalte und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**.

   >[!NOTE]
   >
   >Sie können auch eine [!DNL Metric Editor] durch Rechtsklicken eines beliebigen metrikbezogenen Bereichs innerhalb einer Visualisierung, um das Metrikmenü anzuzeigen. Weitere Informationen finden Sie unter [Arbeiten mit Metrik- und Dimension-Menüs](../../../../home/c-get-started/c-vis/c-met-dim-menus.md#concept-50f07ae47c3e4f94ad7d3d7f8293ccac).

1. Im [!DNL Metric Editor], bearbeiten und speichern Sie die Metrikdefinition bei Bedarf mithilfe der Schritte 2 bis 4 unter [Erstellen neuer abgeleiteter Metriken](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-drvd-mtrcs.md#section-d57b98bf0a9940daba4920ff7efc808d).

   Wenn Sie möchten, dass alle Benutzer des Profils die bearbeitete Metrik verwenden, müssen Sie sie mithilfe des [!DNL Profile Manager]. Siehe [Veröffentlichen von Dateien in Ihrem Arbeitsprofil](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task-a0106e010c834d16bd60eef4721b6af9).
