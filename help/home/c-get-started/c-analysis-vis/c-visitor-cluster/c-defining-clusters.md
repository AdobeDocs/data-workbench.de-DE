---
description: Wählen Sie Eingabevariablen, die Anzahl der Cluster und eine Zielpopulation (falls gewünscht) aus, um Cluster in Ihrem Datensatz zu definieren.
title: Erstellen von Clustern
uuid: f8462445-b7d2-48ae-aed7-2a3abc491cfb
exl-id: 60bc75bf-2f89-455b-8be9-aa20bb837752
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '508'
ht-degree: 1%

---

# Erstellen von Clustern{#building-clusters}

{{eol}}

Wählen Sie Eingabevariablen, die Anzahl der Cluster und eine Zielpopulation (falls gewünscht) aus, um Cluster in Ihrem Datensatz zu definieren.

**Erstellen von Clustern**

1. Öffnen Sie den **[!UICONTROL Cluster Builder]**.

   Klicken **Visualisierung** > **Predictive Analytics** > **Clustering** > **Cluster Builder**.

   ![](assets/cluster-builder-step1.png)

1. Wählen Sie Eingabevariablen aus.

   * Metriken zum **[!UICONTROL Input Variables]** Liste durch Auswahl aus **[!UICONTROL Metric]** in der Symbolleiste.

      ![](assets/cluster_metric_select.png)

   * Fügen Sie Dimensionselemente zu der **[!UICONTROL Input Variables]** aus, indem Sie sie aus der Tabelle einer Dimension ziehen.

      Presse **[!UICONTROL Ctrl + Alt]** und ziehen Sie die ausgewählten Dimensionselemente in den **[!UICONTROL Input Variables]** oder **[!UICONTROL Element]** in der Symbolleiste.

      ![](assets/cluster_dim_select.png)
   Standardmäßig wird das Clustering für den gesamten Datensatz durchgeführt. Alle Eingabevariablen werden links angezeigt **[!UICONTROL Preprocessing]** -Bereich.
1. Verwenden Sie die **[!UICONTROL Options]** -Menü, um die gewünschte Anzahl von Clustern auszuwählen.

   ![](assets/build_cluster_2.png)

1. Wenn Sie eine Untergruppe der Besucher in Ihrem Datensatz gruppieren möchten, können Sie einen Populationsfilter definieren.

   ![](assets/build_cluster_3.png)

   Definieren Sie zunächst die gewünschte Teilmenge mithilfe der Auswahl in Ihrem Arbeitsbereich oder mithilfe der **[!UICONTROL Filter Editor]**. Nachdem Sie die gewünschte Teilmenge ausgewählt haben, legen Sie die Zielpopulation im **[!UICONTROL Options]** Menü. Es wird empfohlen, der Zielgruppe einen Identifizierungsnamen zu geben.

   Die **[!UICONTROL Options]** -Menü verfügt auch über Einstellungen, um die maximale Anzahl der Pässe und den akzeptablen Schwellenwert für die mittlere Konvergenz zu steuern.

1. Nachdem die Eingaben und Optionen konfiguriert wurden, klicken Sie auf das **Los** -Schaltfläche, um das Clustering lokal auszuführen, oder drücken Sie **[!UICONTROL Submit]** , um die Aufgabe an den Predictive Analytics-Server zu senden. Durch Übermittlungen an den Server wird die resultierende Dimension im Datensatz gespeichert, wenn die Konvergenz abgeschlossen ist.

   Wenn Sie lokal ausführen, sehen Sie, wie sich der Cluster Builder durch vier Baumkronen-Clustering-Phasen bewegt, da er intelligente Zentren basierend auf den Eingaben definiert.

   Sobald die Cluster-Zentren aufhören, mehr als den angegebenen Konvergenzschwellenwert zu ändern, wird die Cluster-Dimension konvertiert und der Cluster-Builder zeigt zusätzliche Informationen darüber an, wie relevant ein Input für jeden Cluster war.

1. Passen Sie die Cluster an.

   Wenn Sie mit der rechten Maustaste auf die Farbleiste der Statistiken klicken, wird ein Kontextmenü geöffnet, in dem Sie die Relevanzschwellen anpassen können. Im Fall der Verteilung der Dimensionselemente können Sie festlegen, welcher Test angezeigt wird.

   ![](assets/build_cluster_7.png)

   Metrikeingaben bieten einen t-Test für jeden Cluster, während die Eingaben von Dimensionselementen drei Verteilungstests (Chi squared, eine entropy U-Statistik und Cramers V-Statistik) für jeden Cluster bereitstellen.

   >[!NOTE]
   >
   >Wenn Sie während der Konvergenz Eingaben hinzufügen oder entfernen, wird der Prozess angehalten, bis Sie die Taste drücken **Los** erneut.

   Nach dem Erstellen von Clustern können Sie die Farbauswahl öffnen, um Farben für unterschiedliche Verteilungsergebnisse zuzuweisen.

   ![](assets/build_cluster_5.png)

1. Wenn die Cluster-Dimension konvertiert ist, können Sie der Tabelle Metriken hinzufügen und Auswahlen wie gewohnt vornehmen. Sie können auch mit der rechten Maustaste auf die Elementnamen (Cluster 1, Cluster 2 usw.) klicken, um das Kontextmenü zu öffnen und sie in eine aussagekräftigere Bezeichnung umzubenennen.

   ![](assets/build_cluster_6.png)

1. Wenn Sie diese Clusterdimension in anderen Visualisierungen verwenden möchten, können Sie **[!UICONTROL Save]** lokal oder **[!UICONTROL Submit]** auf den Server.

Wenn Sie die Konvergenz erneut ausführen oder die Relevanz der Eingaben sehen möchten, kann Cluster Builder auch vorhandene Cluster-Dimensionen laden.

>[!TIP]
>
>Wenn ausgewählt, **[!UICONTROL Reset]** werden alle Eingabevariablen vollständig freigegeben und Sie erhalten eine leere Cluster-Builder-Visualisierung, um neue Cluster zu definieren.
