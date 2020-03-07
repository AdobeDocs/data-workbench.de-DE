---
description: Wählen Sie Eingabevariablen, die Anzahl der Cluster und eine Zielpopulation (falls gewünscht) aus, um Cluster im Datensatz zu definieren.
solution: Analytics
title: Erstellen von Clustern
topic: Data workbench
uuid: f8462445-b7d2-48ae-aed7-2a3abc491cfb
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Erstellen von Clustern{#building-clusters}

Wählen Sie Eingabevariablen, die Anzahl der Cluster und eine Zielpopulation (falls gewünscht) aus, um Cluster im Datensatz zu definieren.

**Erstellen von Clustern**

1. Öffnen Sie den **[!UICONTROL Cluster Builder]**.

   Klicken Sie auf **Visualisierung** > **Predictive Analytics** > **Clustering** > **Cluster Builder**.

   ![](assets/cluster-builder-step1.png)

1. Wählen Sie Eingabevariablen.

   * Fügen Sie der **[!UICONTROL Input Variables]** Liste Metriken hinzu, indem Sie sie aus dem **[!UICONTROL Metric]** Menü in der Symbolleiste auswählen.

      ![](assets/cluster_metric_select.png)

   * Fügen Sie Dimensionselemente zur **[!UICONTROL Input Variables]** Liste hinzu, indem Sie sie aus der Tabelle einer Dimension ziehen.

      Drücken Sie die Taste **[!UICONTROL Ctrl + Alt]** und ziehen Sie die ausgewählten Dimensionselemente in die **[!UICONTROL Input Variables]** Liste oder in das **[!UICONTROL Element]** Feld in der Symbolleiste.

      ![](assets/cluster_dim_select.png)
   Standardmäßig wird das Clustering für den gesamten Datensatz durchgeführt. Sie können alle Eingabevariablen im linken **[!UICONTROL Preprocessing]** Bereich sehen.
1. Wählen Sie im **[!UICONTROL Options]** Menü die gewünschte Anzahl von Clustern aus.

   ![](assets/build_cluster_2.png)

1. Wenn Sie eine Untergruppe der Besucher in Ihrem Datensatz gruppieren möchten, können Sie einen Populationsfilter definieren.

   ![](assets/build_cluster_3.png)

   Beginnen Sie mit der Definition der gewünschten Untergruppe, indem Sie die Auswahl in Ihrem Arbeitsbereich oder mithilfe der **[!UICONTROL Filter Editor]** Option Nachdem Sie die gewünschte Untergruppe ausgewählt haben, legen Sie die Zielgruppe im **[!UICONTROL Options]** Menü fest. Es wird empfohlen, der Zielgruppe einen eindeutigen Namen zuzuweisen.

   Das **[!UICONTROL Options]** Menü verfügt auch über Einstellungen, um die maximale Anzahl der Pässe und den akzeptablen Schwellenwert für die mittlere Konvergenz zu steuern.

1. Nachdem die Eingaben und Optionen konfiguriert wurden, klicken Sie auf die Schaltfläche **Los** , um das Clustering lokal auszuführen, oder drücken Sie die Eingabetaste, **[!UICONTROL Submit]** um die Aufgabe an den Predictive Analytics-Server zu senden. Übermittlungen an den Server speichern die resultierende Dimension im Datensatz, wenn die Konvergenz abgeschlossen ist.

   Beim lokalen Ausführen sehen Sie, wie der Cluster Builder vier Baumkronen-Clustering-Phasen durchläuft, da er intelligente Zentren auf der Grundlage der Eingaben definiert.

   Sobald sich die Zentren der Cluster nicht mehr als den angegebenen Konvergenzschwellenwert ändern, wird die Clusterdimension konvertiert und der Cluster Builder zeigt zusätzliche Informationen darüber an, wie relevant ein Input für jeden Cluster war.

1. Passen Sie die Cluster an.

   Wenn Sie mit der rechten Maustaste auf die Farbleiste der Statistik klicken, wird ein Kontextmenü geöffnet, in dem Sie die Relevanzschwellenwerte anpassen können. Im Fall der Dimensionselementverteilungen können Sie auswählen, welcher Test angezeigt wird.

   ![](assets/build_cluster_7.png)

   Metrikeingaben stellen einen T-Test für jeden Cluster bereit, während Dimensionselementeingaben drei Verteilungstests (Chi squared, eine entropy U-Statistik und Cramers V-Statistik) für jeden Cluster bereitstellen.

   >[!NOTE]
   >
   >Wenn Sie Eingaben während der Konvergenz hinzufügen oder entfernen, wird der Prozess angehalten, bis Sie erneut **Go** drücken.

   Nach dem Erstellen von Clustern können Sie die Farbauswahl öffnen, um Farben für unterschiedliche Verteilungsergebnisse zuzuweisen.

   ![](assets/build_cluster_5.png)

1. Wenn die Clusterdimension konvertiert ist, können Sie der Tabelle Metriken hinzufügen und die Auswahl als normal festlegen. Sie können auch mit der rechten Maustaste auf die Elementnamen (Cluster 1, Cluster 2 usw.) klicken, um das Kontextmenü zu öffnen, um sie in etwas aussagekräftigeres umzubenennen.

   ![](assets/build_cluster_6.png)

1. Wenn Sie diese Clusterdimension in anderen Visualisierungen verwenden möchten, können Sie sie lokal oder auf dem Server **[!UICONTROL Save]** verwenden **[!UICONTROL Submit]** .

Wenn Sie die Konvergenz erneut ausführen oder die Relevanz der Eingaben sehen möchten, können Cluster Builder auch vorhandene Clusterdimensionen laden.

>[!TIP]
>
>Wenn diese Option aktiviert ist, **[!UICONTROL Reset]** werden alle Eingabevariablen vollständig freigegeben und Sie erhalten eine leere Cluster-Builder-Visualisierung, um neue Cluster zu definieren.

