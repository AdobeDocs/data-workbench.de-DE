---
description: Berechnungen lenken die Aufmerksamkeit auf ein bestimmtes Dimensionselement, indem sie eine neue Visualisierung mit einer virtuellen Auswahl eines bestimmten Dimensionselements in einer Visualisierung erstellen.
title: Konfigurieren von Hinweisen
uuid: 779764bd-86c3-49cf-aabc-edb39caf0490
exl-id: 509163b2-0bd1-47b4-8612-aac460a501cc
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '492'
ht-degree: 1%

---

# Konfigurieren von Hinweisen{#configure-a-callout}

Berechnungen lenken die Aufmerksamkeit auf ein bestimmtes Dimensionselement, indem sie eine neue Visualisierung mit einer virtuellen Auswahl eines bestimmten Dimensionselements in einer Visualisierung erstellen.

Sie können Aufschlüsselungen hinzufügen oder bearbeiten, indem Sie die im Installationsordner eines Profils gespeicherten Aufrufdateien konfigurieren\*Profil-Name*\Context\Callout folder of the [!DNL Server]. Berechnungen, die auf eine bestimmte Metrik in einer Arbeitsblattvisualisierung aufmerksam machen, werden als Metrikberechnungen bezeichnet. Metrik-Aufrufdateien werden im Profil\*Profil-Name*\Context\Metric Callout folder gespeichert.

Eine Anleitung zum Hinzufügen eines Callout- oder Metrikaufrufs zu einer Visualisierung finden Sie unter [Hinzufügen von Aufrufen zu einem Arbeitsbereich](../../../home/c-get-started/c-vis/c-call-wkspc.md#concept-212b09e763044d938987b4a9c658adc0).

**So erstellen Sie einen neuen Typ von Callout**

1. Erstellen Sie in jedem Arbeitsbereich eine Visualisierung mit den Daten, die im neuen Aufruftyp angezeigt werden sollen. Wenn Sie z. B. möchten, dass Ihre Berechnung eine Tabelle ist, erstellen Sie eine Tabellenvisualisierung, die die gewünschte Metrik und Dimension anzeigt.
1. Klicken Sie mit der rechten Maustaste auf den oberen Rand des Aufruffensters und klicken Sie auf **[!UICONTROL Save]**.
1. Klicken Sie im Fenster [!DNL Save] auf ![](assets/btn_folder_up.png), klicken Sie mit der Dublette auf **[!UICONTROL Context]** und dann mit der Dublette auf **[!UICONTROL Callout]**. Geben Sie im Feld [!DNL File Name] einen Namen für die Datei ein und klicken Sie auf **[!UICONTROL Save]**. Die Callout-Datei wird unter dem Benutzernamen\*Profil gespeichert*\Context\Callout folder.

   >[!NOTE]
   >
   >Wählen Sie bei der Benennung der Berechnung einen beschreibenden Namen, der den Visualisierungstyp sowie die angezeigte Metrik und Dimension widerspiegelt. Wenn Sie z. B. eine Berechnung aus einer Tabellenvisualisierung erstellen möchten, die die Metrik &quot;Sitzungen&quot;über die Dimension &quot;Tag&quot;anzeigt, können Sie der Callout-Tabelle &quot;Sitzungen nach Tag&quot;einen Namen geben.

1. (Optional) Diese Änderung allen Benutzern des Profils im Arbeitsablauf zur Verfügung stellen:

   1. Klicken Sie in [!DNL Profile Manager] auf **[!UICONTROL Context]** und dann auf **[!UICONTROL Callout]**. Dieser Ordner enthält alle Visualisierungsdateien ( [!DNL .vw]), die die vorhandenen Callout-Typen definieren.

   1. Klicken Sie mit der rechten Maustaste auf das Häkchen neben dem Dateinamen des neuen Aufrufs in der Spalte [!DNL User] und klicken Sie auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.

**So ändern Sie eine Berechnung in eine Metrikberechnung**

1. Klicken Sie in [!DNL Profile Manager] auf **[!UICONTROL Context]** und dann auf **[!UICONTROL Callout]**. Dieser Ordner enthält alle Visualisierungsdateien ( [!DNL .vw]), die die vorhandenen Callout-Typen definieren.

1. Klicken Sie mit der rechten Maustaste auf das Häkchen neben dem Dateinamen des zu ändernden Aufruftyps und klicken Sie auf **[!UICONTROL Make Local]**. Nachdem die Datei auf den lokalen Computer heruntergeladen wurde, wird in der Spalte [!DNL User] ein Häkchen angezeigt.

1. Klicken Sie mit der rechten Maustaste auf das Häkchen neben dem Dateinamen in der Spalte [!DNL User] und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL In Notepad]**.

1. Suchen Sie den Eintrag [!DNL metric_y = ref:] in der Callout-Datei und ersetzen Sie den vorhandenen Wert durch das Wort Metrik. Der hervorgehobene Text im folgenden Dateifragment zeigt an, wo Sie dieses Wort einfügen.

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

1. Klicken Sie auf **[!UICONTROL File]** > **[!UICONTROL Save As]**. Klicken Sie im Fenster **[!UICONTROL Save As]** einmal auf und klicken Sie dann mit der Dublette auf **[!UICONTROL Metric Callout]**. Geben Sie im Feld [!DNL File Name] einen Namen für die Datei ein und klicken Sie auf **[!UICONTROL Save]**. Die Metrik-Aufrufdatei wird im Profil User\*working_name*\Context\Metric Callout folder gespeichert.

1. (Optional) Um diese Metrikberechnung allen Benutzern des funktionierenden Profils zur Verfügung zu stellen, klicken Sie mit der rechten Maustaste auf das Häkchen neben dem Dateinamen in der Spalte [!DNL User] und klicken Sie auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]***[!DNL Profile Manager].
