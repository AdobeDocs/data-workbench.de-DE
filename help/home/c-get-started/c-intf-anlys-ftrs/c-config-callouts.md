---
description: Berechnungen lenken die Aufmerksamkeit auf ein bestimmtes Dimensionselement, indem sie eine neue Visualisierung mit einer virtuellen Auswahl eines bestimmten Dimensionselements in einer Visualisierung erstellen.
solution: Analytics
title: Konfigurieren eines Callout
topic: Data workbench
uuid: 779764bd-86c3-49cf-aabc-edb39caf0490
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Konfigurieren eines Callout{#configure-a-callout}

Berechnungen lenken die Aufmerksamkeit auf ein bestimmtes Dimensionselement, indem sie eine neue Visualisierung mit einer virtuellen Auswahl eines bestimmten Dimensionselements in einer Visualisierung erstellen.

Sie können Aufschlüsselungen hinzufügen oder bearbeiten, indem Sie die in einem Profilnamen\*\Context\Callout folder of the [!DNL Server] -Installationsordner gespeicherten Aufrufdateien konfigurieren. Berechnungen, die auf eine bestimmte Metrik in einer Arbeitsblattvisualisierung aufmerksam machen, werden als Metrikberechnungen bezeichnet. Metrikberechnungsdateien werden im Profil\*Profilname*\Context\Metric Callout folder gespeichert.

Eine Anleitung zum Hinzufügen eines Callouts oder einer Metrikaufforderung zu einer Visualisierung finden Sie unter [Hinzufügen von Aufrufen zu einer Arbeitsfläche](../../../home/c-get-started/c-vis/c-call-wkspc.md#concept-212b09e763044d938987b4a9c658adc0).

**So erstellen Sie einen neuen Typ von Callout**

1. Erstellen Sie in jedem Arbeitsbereich eine Visualisierung mit den Daten, die im neuen Aufruftyp angezeigt werden sollen. Wenn Sie z. B. möchten, dass Ihre Berechnung eine Tabelle ist, erstellen Sie eine Tabellenvisualisierung, die die gewünschte Metrik und Dimension anzeigt.
1. Klicken Sie mit der rechten Maustaste auf den oberen Rand des Aufruffensters und klicken Sie auf **[!UICONTROL Save]**.
1. Klicken Sie im [!DNL Save] Fenster auf ![](assets/btn_folder_up.png), doppelklicken Sie **[!UICONTROL Context]** und doppelklicken Sie dann auf **[!UICONTROL Callout]**. Geben Sie im [!DNL File Name] Feld einen Namen für die Datei ein und klicken Sie auf **[!UICONTROL Save]**. Die Callout-Datei wird im Arbeitsprofilnamen des Benutzers gespeichert*\Context\Callout folder.

   >[!NOTE]
   >
   >Wählen Sie bei der Benennung der Berechnung einen beschreibenden Namen, der den Visualisierungstyp sowie die angezeigte Metrik und Dimension widerspiegelt. Wenn Sie z. B. eine Berechnung aus einer Tabellenvisualisierung erstellen möchten, die die Metrik &quot;Sitzungen&quot;über die Dimension &quot;Tag&quot;anzeigt, können Sie der Callout-Tabelle &quot;Sitzungen nach Tag&quot;einen Namen geben.

1. (Optional) Um diese Änderung allen Benutzern des Arbeitsprofils zur Verfügung zu stellen:

   1. Klicken Sie im [!DNL Profile Manager]Fenster auf **[!UICONTROL Context]** und dann auf **[!UICONTROL Callout]**. Dieser Ordner enthält alle Visualisierungsdateien ( [!DNL .vw]), die die vorhandenen Callout-Typen definieren.

   1. Klicken Sie mit der rechten Maustaste auf das Häkchen neben dem Dateinamen des neuen Aufrufs in der [!DNL User] Spalte und klicken Sie auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.

**So ändern Sie eine Berechnung in eine Metrikberechnung**

1. Klicken Sie im [!DNL Profile Manager]Fenster auf **[!UICONTROL Context]** und dann auf **[!UICONTROL Callout]**. Dieser Ordner enthält alle Visualisierungsdateien ( [!DNL .vw]), die die vorhandenen Callout-Typen definieren.

1. Klicken Sie mit der rechten Maustaste auf das Häkchen neben dem Dateinamen des zu ändernden Aufruftyps und klicken Sie auf **[!UICONTROL Make Local]**. Nachdem die Datei auf den lokalen Computer heruntergeladen wurde, wird ein Häkchen in der [!DNL User] Spalte angezeigt.

1. Klicken Sie mit der rechten Maustaste auf das Häkchen neben dem Dateinamen in der [!DNL User] Spalte und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL In Notepad]**.

1. Suchen Sie den [!DNL metric_y = ref:] Eintrag in der Callout-Datei und ersetzen Sie den vorhandenen Wert durch das Wort Metrik. Der hervorgehobene Text im folgenden Dateifragment zeigt an, wo Sie dieses Wort einfügen.

   ```
   window = simpleBorderWindow: 
     client = graph: 
       bars = bool: true
       dim_x = ref: wdata/model/dim/dimension name
       lines = bool: false
       metrics = vector: 1 items
         0 = gr_metric: 
           metric_y = ref: Metric
           yaxis = axisLegend: 
             max_value = double: maximum y-value
             min_value = double: minimum y-value
             zoom_max = double: maximum y-zoom
             zoom_min = double: minimum y-zoom
   . . . 
   ```

1. Klicken Sie auf **[!UICONTROL File]** > **[!UICONTROL Save As]**. Klicken Sie im **[!UICONTROL Save As]** Fenster einmal und doppelklicken Sie dann auf **[!UICONTROL Metric Callout]**. Geben Sie im [!DNL File Name] Feld einen Namen für die Datei ein und klicken Sie auf **[!UICONTROL Save]**. Die Metrikaufrufdatei wird im Arbeitsprofilnamen des Benutzers gespeichert*\Context\Metric Callout folder.

1. (Optional) Um diese Metrikberechnung allen Benutzern des Arbeitsprofils zur Verfügung zu stellen, [!DNL Profile Manager]klicken Sie mit der rechten Maustaste auf das Häkchen neben dem Dateinamen in der [!DNL User] Spalte und klicken Sie auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.

