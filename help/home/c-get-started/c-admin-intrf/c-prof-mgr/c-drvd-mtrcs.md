---
description: Sie definieren neue Metriken (die als abgeleitete Metriken bezeichnet werden) und bearbeiten vorhandene Metrikdefinitionen mithilfe des Metrik-Editors.
title: Arbeiten mit abgeleiteten Metriken
uuid: 9767c170-e0cb-47b4-94f1-e9f6950b5926
exl-id: 83467c64-4b9a-44ab-91a2-202c76c89979
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '468'
ht-degree: 1%

---

# Arbeiten mit abgeleiteten Metriken{#work-with-derived-metrics}

Sie definieren neue Metriken (die als abgeleitete Metriken bezeichnet werden) und bearbeiten vorhandene Metrikdefinitionen mithilfe des Metrik-Editors.

Weitere Informationen zu Metriken, die in diesem Abschnitt und in [Abfrage Language Syntax](../../../../home/c-get-started/c-qry-lang-syntx/c-qry-lang-syntx.md#concept-15d1d3f5164a47d49468c5acb7299d9f) angegeben sind, finden Sie im Handbuch *Metrik, Dimensionen und Filter*.

## Eine abgeleitete Metrik {#section-d57b98bf0a9940daba4920ff7efc808d} erstellen

Verwenden Sie ein [!DNL Metric Editor], um eine neue Metrik nach Name, Formel und Format zu definieren, die im Ordner &quot;User\*Profil_Name*\Metrics&quot;zur späteren Verwendung gespeichert wird.

1. Öffnen Sie ein neues [!DNL Metric Editor] mit der Menüoption **[!UICONTROL Admin]** > **[!UICONTROL Profile]** oder indem Sie mit der rechten Maustaste auf die Spalte **[!UICONTROL User]** für den Ordner klicken, in dem Sie die Metrik erstellen möchten, und auf **[!UICONTROL Create]** > **[!UICONTROL New Metric]** klicken.

   Es wird ein [!DNL Metric Editor] angezeigt.

1. Geben Sie im Parameter Name einen Namen für die neue Metrik ein.

   Beachten Sie, dass Leerzeichen ( ) zulässig sind, Unterstriche (_) nicht. Darüber hinaus können die folgenden Symbole nicht verwendet werden:

   `+ - * /`

   ![](assets/vis_MetricEditor_NewAndEditing.png)

1. Geben Sie im Parameter &quot;Formel&quot;einen Ausdruck für die neue Metrik ein. Beachten Sie, dass Filter in Klammern [ definiert werden müssen. ] im Ausdruck.

   Weitere Metrik-Syntaxregeln für Ausdruck finden Sie unter [Syntax für metrische Ausdruck](../../../../home/c-get-started/c-qry-lang-syntx/c-syntx-mtrc-exp.md#concept-bbf440a0307549e088df491b51b51d66).

   Die folgende Tabelle enthält Ausdrücke für erweiterte Metriken.

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
   >Wenn ein passender Ausdruck eingegeben wird, zeigt die Zeile &quot;Vorschau&quot;den Wert der neuen Metrik an. Wenn der Ausdruck einen Fehler enthält, wird in der Zeile &quot;Vorschau&quot;eine Fehlermeldung angezeigt.

1. Klicken Sie mit der rechten Maustaste auf **[!UICONTROL (New)]** und dann auf **[!UICONTROL Save]**.

   Wenn Sie die Metrik speichern, wird auf Ihrem Computer eine Datei erstellt, die die neue Metrik darstellt, im Installationsordner der Data Workbench \User\*Profil*\Metrics.

   ![](assets/vis_MetricEditor_NewAndEditing.png)

Sie können die neue Metrik jetzt im gesamten aktuellen Profil verwenden, indem Sie sie wie jede integrierte Metrik auswählen. Informationen zum Ändern der Reihenfolge, in der Ihre Metriken im Menü &quot;Metriken&quot;angezeigt werden, finden Sie unter [Menüs mithilfe der Datei &quot;Order.txt&quot;anpassen](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999).

Wenn Sie möchten, dass alle Benutzer des Profils die von Ihnen erstellte Metrik verwenden, müssen Sie sie mit dem [!DNL Profile Manager] im funktionierenden Profil veröffentlichen. Siehe [Veröffentlichen von Dateien in Ihrem Profil](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task-a0106e010c834d16bd60eef4721b6af9).

## Bearbeiten von abgeleiteten Metriken {#section-db6d924cf4e14bcc8d57cfe1059fc797}

1. Klicken Sie in der Spalte [!DNL Profile Manager] oder [!DNL Metrics Manager] in der Spalte *Profil* mit der rechten Maustaste auf das Häkchen für die Metrikdatei, die Sie bearbeiten möchten, und klicken Sie dann auf **[!UICONTROL Make Local]**.
1. Klicken Sie mit der rechten Maustaste auf das Häkchen für die Metrikdatei in der Spalte [!DNL User] und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**.

   >[!NOTE]
   >
   >Sie können auch ein [!DNL Metric Editor] öffnen, indem Sie mit der rechten Maustaste auf einen Metrikbereich innerhalb einer Visualisierung klicken, um das Metrikmenü anzuzeigen. Weitere Informationen finden Sie unter [Arbeiten mit Metrik- und Dimension-Menüs](../../../../home/c-get-started/c-vis/c-met-dim-menus.md#concept-50f07ae47c3e4f94ad7d3d7f8293ccac).

1. Bearbeiten und speichern Sie unter [!DNL Metric Editor] die Metrikdefinition nach Bedarf mit den Schritten 2-4 in [Erstellen neuer abgeleiteter Metriken](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-drvd-mtrcs.md#section-d57b98bf0a9940daba4920ff7efc808d).

   Wenn Sie möchten, dass alle Benutzer des Profils die von Ihnen bearbeitete Metrik verwenden, müssen Sie sie mit dem [!DNL Profile Manager] im funktionierenden Profil veröffentlichen. Siehe [Veröffentlichen von Dateien in Ihrem Profil](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task-a0106e010c834d16bd60eef4721b6af9).
