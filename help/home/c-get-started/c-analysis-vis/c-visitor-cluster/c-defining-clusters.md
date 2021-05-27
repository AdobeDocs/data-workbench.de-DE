---
description: Wählen Sie Eingabevariablen, die Anzahl der Cluster und eine Zielpopulation (falls gewünscht) aus, um Cluster in Ihrem Datensatz zu definieren.
title: Erstellen von Clustern
uuid: f8462445-b7d2-48ae-aed7-2a3abc491cfb
exl-id: 60bc75bf-2f89-455b-8be9-aa20bb837752
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '508'
ht-degree: 1%

---

# Erstellen von Clustern{#building-clusters}

Wählen Sie Eingabevariablen, die Anzahl der Cluster und eine Zielpopulation (falls gewünscht) aus, um Cluster in Ihrem Datensatz zu definieren.

**Erstellen von Clustern**

1. Öffnen Sie den **[!UICONTROL Cluster Builder]**.

   Klicken Sie auf **Visualisierung** > **Prädiktive Analyse** > **Clustering** > **Cluster-Builder**.

   ![](assets/cluster-builder-step1.png)

1. Wählen Sie Eingabevariablen aus.

   * Fügen Sie der Liste **[!UICONTROL Input Variables]** Metriken hinzu, indem Sie aus dem Menü **[!UICONTROL Metric]** in der Symbolleiste eine Auswahl treffen.

      ![](assets/cluster_metric_select.png)

   * Fügen Sie Dimensionselemente zur Liste **[!UICONTROL Input Variables]** hinzu, indem Sie sie aus der Tabelle einer Dimension ziehen.

      Drücken Sie die Taste **[!UICONTROL Ctrl + Alt]** und ziehen Sie die ausgewählten Dimensionselemente in die Liste **[!UICONTROL Input Variables]** oder in das Feld **[!UICONTROL Element]** in der Symbolleiste.

      ![](assets/cluster_dim_select.png)
   Standardmäßig wird das Clustering für den gesamten Datensatz durchgeführt. Sie können alle Eingabevariablen im linken Bereich **[!UICONTROL Preprocessing]** sehen.
1. Wählen Sie im Menü **[!UICONTROL Options]** die gewünschte Anzahl von Clustern aus.

   ![](assets/build_cluster_2.png)

1. Wenn Sie eine Untergruppe der Besucher in Ihrem Datensatz gruppieren möchten, können Sie einen Populationsfilter definieren.

   ![](assets/build_cluster_3.png)

   Definieren Sie zunächst die gewünschte Teilmenge mithilfe von Auswahlen in Workspace oder mithilfe von **[!UICONTROL Filter Editor]**. Nachdem Sie die gewünschte Teilmenge ausgewählt haben, legen Sie die Zielpopulation im Menü **[!UICONTROL Options]** fest. Es wird empfohlen, der Zielgruppe einen Identifizierungsnamen zu geben.

   Das Menü **[!UICONTROL Options]** verfügt auch über Einstellungen, mit denen die maximale Anzahl von Durchgängen und der akzeptable Schwellenwert für mittlere Konvergenz gesteuert werden.

1. Nachdem die Eingaben und Optionen konfiguriert wurden, klicken Sie auf die Schaltfläche **Go** , um das Clustering lokal auszuführen, oder drücken Sie **[!UICONTROL Submit]**, um die Aufgabe an den Predictive Analytics-Server zu senden. Durch Übermittlungen an den Server wird die resultierende Dimension im Datensatz gespeichert, wenn die Konvergenz abgeschlossen ist.

   Wenn Sie lokal ausführen, sehen Sie, wie sich der Cluster Builder durch vier Baumkronen-Clustering-Phasen bewegt, da er intelligente Zentren basierend auf den Eingaben definiert.

   Sobald die Cluster-Zentren aufhören, mehr als den angegebenen Konvergenzschwellenwert zu ändern, wird die Cluster-Dimension konvertiert und der Cluster-Builder zeigt zusätzliche Informationen darüber an, wie relevant ein Input für jeden Cluster war.

1. Passen Sie die Cluster an.

   Wenn Sie mit der rechten Maustaste auf die Farbleiste der Statistiken klicken, wird ein Kontextmenü geöffnet, in dem Sie die Relevanzschwellen anpassen können. Im Fall der Verteilung der Dimensionselemente können Sie festlegen, welcher Test angezeigt wird.

   ![](assets/build_cluster_7.png)

   Metrikeingaben bieten einen t-Test für jeden Cluster, während die Eingaben von Dimensionselementen drei Verteilungstests (Chi squared, eine entropy U-Statistik und Cramers V-Statistik) für jeden Cluster bereitstellen.

   >[!NOTE]
   >
   >Wenn Sie Eingaben während der Konvergenz hinzufügen oder entfernen, wird der Prozess angehalten, bis Sie die Taste **Go** erneut drücken.

   Nach dem Erstellen von Clustern können Sie die Farbauswahl öffnen, um Farben für unterschiedliche Verteilungsergebnisse zuzuweisen.

   ![](assets/build_cluster_5.png)

1. Wenn die Cluster-Dimension konvertiert ist, können Sie der Tabelle Metriken hinzufügen und Auswahlen wie gewohnt vornehmen. Sie können auch mit der rechten Maustaste auf die Elementnamen (Cluster 1, Cluster 2 usw.) klicken, um das Kontextmenü zu öffnen und sie in eine aussagekräftigere Bezeichnung umzubenennen.

   ![](assets/build_cluster_6.png)

1. Wenn Sie diese Cluster-Dimension in anderen Visualisierungen verwenden möchten, können Sie sie lokal oder **[!UICONTROL Submit]** lokal für den Server verwenden.**[!UICONTROL Save]**

Wenn Sie die Konvergenz erneut ausführen oder die Relevanz der Eingaben sehen möchten, kann Cluster Builder auch vorhandene Cluster-Dimensionen laden.

>[!TIP]
>
>Wenn diese Option aktiviert ist, werden alle Eingabevariablen vollständig freigegeben und Sie erhalten eine leere Cluster-Builder-Visualisierung, um neue Cluster zu definieren.**[!UICONTROL Reset]**
