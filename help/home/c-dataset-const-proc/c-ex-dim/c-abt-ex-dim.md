---
description: Mit dem Insight Server (InsightServer64.exe) können Sie benutzerdefinierte Dimensionen aus Ereignisdaten oder Nachschlagedaten definieren.
solution: Analytics
title: Erweiterte Dimensionen
topic: Data workbench
uuid: ae014a26-5286-4e36-9098-aaa463d9fe05
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Erweiterte Dimensionen{#about-extended-dimensions}

Mit dem Insight Server (InsightServer64.exe) können Sie benutzerdefinierte Dimensionen aus Ereignisdaten oder Nachschlagedaten definieren.

Alle benutzerdefinierten Dimensionen, die Sie definieren, werden als erweiterte Dimensionen bezeichnet. Sie können diese verwenden, um Visualisierungen zu erstellen, erweiterte Metriken zu erstellen oder Analysen durchzuführen, um die Vorgänge und Probleme im Zusammenhang mit Ihrem Geschäftskanal zu verstehen. Sie können mehrere Arten erweiterter Dimensionen in der [!DNL Transformation.cfg] Datei oder in [!DNL Transformation Dataset Include] Dateien definieren.

Eine erweiterte Dimension stellt eine Beziehung zwischen Protokollfeldwerten und einer übergeordneten Dimension dar. Eine übergeordnete Dimension kann eine beliebige benutzerdefinierte zählbare Dimension sein. Siehe [Zählbare Dimensionen](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-count-dim.md#concept-f28b633419494e7bbc510012dbfcc6f8). Sie geben das übergeordnete Element an, wenn Sie die Dimension in der [!DNL Transformation.cfg] Datei oder in einer [!DNL Transformation Dataset Include] Datei definieren. Die übergeordnete Dimension einer Dimension ist die gleiche Ebene. Wenn Sie beispielsweise eine Dimension mit einem übergeordneten Element der Sitzung definieren, ist diese Dimension eine Dimension auf Sitzungsebene.

>[!NOTE]
>
>Die Werte der Protokollfelder können von den inhärenten Werten stammen, die in den Protokolldateien ( [!DNL .vsl]) oder anderen Ereignisdatenquellen verfügbar sind, oder von erweiterten Protokollfeldern, die durch Transformationen erstellt wurden.

Um einer Visualisierung eine erweiterte Dimension hinzuzufügen, greifen Sie über die Liste &quot;Erweitert&quot;im [!DNL Select Dimension] Menü darauf zu. Um beispielsweise einer Diagrammvisualisierung eine erweiterte Dimension hinzuzufügen, klicken Sie mit der rechten Maustaste auf den Arbeitsbereich und klicken Sie auf **[!UICONTROL Add Visualization]** > **[!UICONTROL Graph]** > **[!UICONTROL Extended]** > *&lt;**[!UICONTROL dimension name]**>*. Wenn Sie die Liste der erweiterten Dimensionen in der Data Workbench-Oberfläche organisieren möchten, können Sie die erweiterten Dimensionen in von Ihnen erstellte Unterordner verschieben. Siehe Kapitel &quot;Verwaltungsschnittstellen&quot;des *Data Workbench-Benutzerhandbuchs*. In diesem Fall werden die Namen der Unterordner auch im Menü angezeigt, wie unter Visualisierung hinzufügen > Diagramm > Erweitert > &lt;Name des *Unterordners*> > &lt;Name der *Dimension*>.

Um alle Dimensionen anzuzeigen, die für Ihr Datenset-Profil definiert wurden, und die Puffergröße für jede dieser Dimensionen, öffnen Sie die [!DNL Detailed Status] Schnittstelle in Data Workbench und klicken Sie auf **[!UICONTROL Performance]**, und erweitern Sie dann **[!UICONTROL Dimensions]** die Knoten. Die Puffergröße, die die Abfragezeit steuert, wird in MB angegeben. Weitere Informationen zur [!DNL Detailed Status] Benutzeroberfläche finden Sie im Handbuch &quot;Serververwaltung und -installation&quot;.
