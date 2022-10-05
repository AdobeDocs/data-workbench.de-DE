---
description: Mit Insight Server (InsightServer64.exe) können Sie benutzerdefinierte Dimensionen aus Ereignisdaten oder Suchdaten definieren.
title: Über erweiterte Dimensionen
uuid: ae014a26-5286-4e36-9098-aaa463d9fe05
exl-id: f74aa85e-f880-4ab5-a8fb-128862aa808f
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '343'
ht-degree: 1%

---

# Über erweiterte Dimensionen{#about-extended-dimensions}

{{eol}}

Mit Insight Server (InsightServer64.exe) können Sie benutzerdefinierte Dimensionen aus Ereignisdaten oder Suchdaten definieren.

Alle benutzerdefinierten Dimensionen, die Sie definieren, werden als erweiterte Dimensionen bezeichnet. Sie können sie verwenden, um Visualisierungen zu erstellen, erweiterte Metriken zu erstellen oder Analysen durchzuführen, um die Vorgänge und Probleme im Zusammenhang mit Ihrem Geschäftskanal zu verstehen. Sie können mehrere Typen erweiterter Dimensionen im [!DNL Transformation.cfg] oder in [!DNL Transformation Dataset Include] Dateien.

Eine erweiterte Dimension stellt eine Beziehung zwischen den Protokollfeldwerten und einer übergeordneten Dimension dar. Eine übergeordnete Dimension kann eine beliebige benutzerdefinierte zählbare Dimension sein. Siehe [Zählbare Dimensionen](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-count-dim.md#concept-f28b633419494e7bbc510012dbfcc6f8). Sie legen das übergeordnete Element bei der Definition der Dimension im [!DNL Transformation.cfg] oder [!DNL Transformation Dataset Include] -Datei. Das übergeordnete Element einer Dimension entspricht der Ebene. Wenn Sie beispielsweise eine Dimension mit dem übergeordneten Element Sitzung definieren, ist diese Dimension eine Dimension auf Sitzungsebene.

>[!NOTE]
>
>Die Protokollfeldwerte können aus den im Protokoll verfügbaren inhärenten Werten stammen ( [!DNL .vsl]) oder anderen Ereignisdatenquellen oder aus erweiterten Protokollfeldern, die durch Umwandlungen erstellt wurden.

Um einer Visualisierung eine erweiterte Dimension hinzuzufügen, greifen Sie über die Liste Erweitert in der [!DNL Select Dimension] Menü. Um beispielsweise einer Diagrammvisualisierung eine erweiterte Dimension hinzuzufügen, klicken Sie mit der rechten Maustaste in den Arbeitsbereich und klicken Sie auf **[!UICONTROL Add Visualization]** > **[!UICONTROL Graph]** > **[!UICONTROL Extended]** > *&lt;**[!UICONTROL dimension name]**>*. Wenn Sie die Liste Ihrer erweiterten Dimensionen in der Data Workbench-Benutzeroberfläche organisieren möchten, können Sie die erweiterten Dimensionen in von Ihnen erstellte Unterordner verschieben. Siehe Kapitel &quot;Verwaltungsschnittstellen&quot;im Abschnitt *Data Workbench-Benutzerhandbuch*. Wenn Sie dies tun, werden die Namen der Unterordner auch im Menü angezeigt, wie unter Visualisierung hinzufügen > Diagramm > Erweitert > &lt;*Name des Unterordners*> > &lt;*Dimensionsname*>.

Um alle Dimensionen anzuzeigen, die für Ihr Datensatzprofil definiert wurden, und die Puffergröße für jede Dimension zu öffnen, öffnen Sie die [!DNL Detailed Status] Benutzeroberfläche in Data Workbench und klicken Sie auf **[!UICONTROL Performance]**, dann **[!UICONTROL Dimensions]** , um die Knoten zu erweitern. Die Puffergröße, die die Abfragezeiten steuert, wird in MB angegeben. Weitere Informationen zum [!DNL Detailed Status] -Schnittstelle, siehe Handbuch zur Serververwaltung und -installation.
