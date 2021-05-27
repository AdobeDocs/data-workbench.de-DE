---
description: Legenden lenken die Aufmerksamkeit auf ein bestimmtes Dimensionselement, indem sie eine neue Visualisierung mit einer virtuellen Auswahl eines bestimmten Dimensionselements in einer Visualisierung erstellen.
title: Konfigurieren von Hinweisen
uuid: 779764bd-86c3-49cf-aabc-edb39caf0490
exl-id: 509163b2-0bd1-47b4-8612-aac460a501cc
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '492'
ht-degree: 1%

---

# Konfigurieren von Hinweisen{#configure-a-callout}

Legenden lenken die Aufmerksamkeit auf ein bestimmtes Dimensionselement, indem sie eine neue Visualisierung mit einer virtuellen Auswahl eines bestimmten Dimensionselements in einer Visualisierung erstellen.

Sie können Legenden hinzufügen oder bearbeiten, indem Sie die im Installationsordner &quot;Profile\*Profilname*\Context\Callout folder of the [!DNL Server]&quot;gespeicherten Callout-Dateien konfigurieren. Legenden, die in einer Arbeitsblattvisualisierung auf eine bestimmte Metrik aufmerksam machen, werden als Metrikberechnungen bezeichnet. Metrik-Metadatenberechnungsdateien werden im Ordner Profile\*Profilname*\Context\Metric Callout folder. gespeichert.

Anweisungen zum Hinzufügen eines Callout- oder Metrikberechnungen zu einer Visualisierung finden Sie unter [Hinzufügen von Legenden zu einem Arbeitsbereich](../../../home/c-get-started/c-vis/c-call-wkspc.md#concept-212b09e763044d938987b4a9c658adc0).

**So erstellen Sie einen neuen Auflistungstyp**

1. Erstellen Sie in einem beliebigen Arbeitsbereich eine Visualisierung, die die Daten enthält, die im neuen Legotyp angezeigt werden sollen. Wenn Sie beispielsweise möchten, dass Ihr Callout eine Tabelle ist, erstellen Sie eine Tabellenvisualisierung, die die gewünschte Metrik und Dimension anzeigt.
1. Klicken Sie mit der rechten Maustaste auf den oberen Rand des Fensters und klicken Sie auf **[!UICONTROL Save]**.
1. Klicken Sie im Fenster [!DNL Save] auf ![](assets/btn_folder_up.png), doppelklicken Sie auf **[!UICONTROL Context]** und doppelklicken Sie dann auf **[!UICONTROL Callout]**. Geben Sie im Feld [!DNL File Name] einen Namen für die Datei ein und klicken Sie auf **[!UICONTROL Save]**. Die Callout-Datei wird im Arbeitsprofilnamen des Benutzers gespeichert.

   >[!NOTE]
   >
   >Wählen Sie bei der Benennung Ihres Callout einen beschreibenden Namen, der den Visualisierungstyp sowie die angezeigte Metrik und Dimension widerspiegelt. Wenn Sie z. B. einen aus einer Tabellenvisualisierung stammenden Callout erstellen möchten, der die Metrik Sitzungen über die Dimension Tag anzeigt, können Sie den Callout &quot;Sitzungen nach Tagestabelle&quot;nennen.

1. (Optional) Um diese Änderung allen Benutzern des Arbeitsprofils zur Verfügung zu stellen:

   1. Klicken Sie in [!DNL Profile Manager] auf **[!UICONTROL Context]** und dann auf **[!UICONTROL Callout]**. Dieser Ordner enthält alle Visualisierungsdateien ( [!DNL .vw]), die die vorhandenen Callout-Typen definieren.

   1. Klicken Sie in der Spalte [!DNL User] mit der rechten Maustaste auf das Häkchen neben dem Dateinamen des neuen Callout und klicken Sie auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.

**So ändern Sie eine Berechnung in eine Metrikberechnung**

1. Klicken Sie in [!DNL Profile Manager] auf **[!UICONTROL Context]** und dann auf **[!UICONTROL Callout]**. Dieser Ordner enthält alle Visualisierungsdateien ( [!DNL .vw]), die die vorhandenen Callout-Typen definieren.

1. Klicken Sie mit der rechten Maustaste auf das Häkchen neben dem Dateinamen des zu ändernden Aufruftyps und klicken Sie auf **[!UICONTROL Make Local]**. Nachdem die Datei auf den lokalen Computer heruntergeladen wurde, erscheint in der Spalte [!DNL User] ein Häkchen.

1. Klicken Sie in der Spalte [!DNL User] mit der rechten Maustaste auf das Häkchen neben dem Dateinamen und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL In Notepad]**.

1. Suchen Sie den Eintrag [!DNL metric_y = ref:] in der Callout-Datei und ersetzen Sie den vorhandenen Wert durch das Wort Metrik . Der hervorgehobene Text im folgenden Dateifragment zeigt an, wo Sie dieses Wort einfügen.

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

1. Klicken Sie auf **[!UICONTROL File]** > **[!UICONTROL Save As]**. Klicken Sie im Fenster **[!UICONTROL Save As]** einmal auf und doppelklicken Sie dann auf **[!UICONTROL Metric Callout]**. Geben Sie im Feld [!DNL File Name] einen Namen für die Datei ein und klicken Sie auf **[!UICONTROL Save]**. Die Metrikberechnungsdatei wird im Arbeitsprofilnamen des Benutzers gespeichert.\*\Context\Metric Callout folder.

1. (Optional) Um diesen Metrikbericht allen Benutzern des Arbeitsprofils zur Verfügung zu stellen, klicken Sie in der Spalte [!DNL Profile Manager] mit der rechten Maustaste auf das Häkchen neben dem Dateinamen in der Spalte [!DNL User] und klicken Sie auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]***.
