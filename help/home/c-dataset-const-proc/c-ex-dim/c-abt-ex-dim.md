---
description: Mit dem Insight-Server (InsightServer64.exe) können Sie benutzerdefinierte Dimensionen aus Ereignis- oder Suchdaten definieren.
title: Über erweiterte Dimensionen
uuid: ae014a26-5286-4e36-9098-aaa463d9fe05
exl-id: f74aa85e-f880-4ab5-a8fb-128862aa808f
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '343'
ht-degree: 1%

---

# Über erweiterte Dimensionen{#about-extended-dimensions}

Mit dem Insight-Server (InsightServer64.exe) können Sie benutzerdefinierte Dimensionen aus Ereignis- oder Suchdaten definieren.

Alle benutzerdefinierten Dimensionen, die Sie definieren, werden als erweiterte Dimensionen bezeichnet. Sie können diese verwenden, um Visualisierungen zu erstellen, erweiterte Metriken zu erstellen oder Analysen durchzuführen, um die Vorgänge und Probleme zu verstehen, die mit Ihrem geschäftlichen Kanal verbunden sind. Sie können mehrere Arten von erweiterten Dimensionen in der Datei [!DNL Transformation.cfg] oder in [!DNL Transformation Dataset Include] definieren.

Eine erweiterte Dimension stellt eine Beziehung zwischen Protokollfeldwerten und einer übergeordneten Dimension dar. Eine übergeordnete Dimension kann eine beliebige benutzerdefinierte zählbare Dimension sein. Siehe [Zählbare Dimensionen](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-count-dim.md#concept-f28b633419494e7bbc510012dbfcc6f8). Sie geben das übergeordnete Element an, wenn Sie die Dimension in der Datei [!DNL Transformation.cfg] oder in einer Datei [!DNL Transformation Dataset Include] definieren. Die übergeordnete Dimension einer Dimension ist die gleiche Ebene. Wenn Sie beispielsweise eine Dimension mit einem übergeordneten Element der Sitzung definieren, ist diese Dimension eine Dimension auf Sitzungsebene.

>[!NOTE]
>
>Die Protokollfeldwerte können von den inhärenten Werten stammen, die in den Protokolldateien ( [!DNL .vsl]) oder anderen Ereignis-Datenquellen verfügbar sind, oder von erweiterten Protokollfeldern, die durch Transformationen erstellt wurden.

Um einer Visualisierung eine erweiterte Dimension hinzuzufügen, greifen Sie über die erweiterte Liste im Menü [!DNL Select Dimension] darauf zu. Um beispielsweise einer Diagrammvisualisierung eine erweiterte Dimension hinzuzufügen, klicken Sie mit der rechten Maustaste in den Arbeitsbereich und klicken Sie auf **[!UICONTROL Add Visualization]** > **[!UICONTROL Graph]** > **[!UICONTROL Extended]** > *&lt;**[!UICONTROL dimension name]***. Wenn Sie die Liste der erweiterten Dimensionen in der Data Workbench-Oberfläche organisieren möchten, können Sie die erweiterten Dimensionen in von Ihnen erstellte Unterordner verschieben. Weitere Informationen finden Sie im Kapitel &quot;Verwaltungsschnittstellen&quot;des *Data Workbench-Benutzerhandbuchs*. In diesem Fall werden die Namen der Unterordner auch im Menü angezeigt, wie unter Hinzufügen Visualisierung > Diagramm > Erweitert > &lt;*Unterordnername* > &lt;*Dimensionsname*>.

Um alle für Ihr DataSet-Profil definierten Dimensionen und die jeweilige Puffergröße anzuzeigen, öffnen Sie die [!DNL Detailed Status]-Schnittstelle in Data Workbench und klicken Sie auf **[!UICONTROL Performance]** und dann auf **[!UICONTROL Dimensions]**, um die Knoten zu erweitern. Die Puffergröße, die die Abfrage steuert, wird in MB angegeben. Weitere Informationen zur [!DNL Detailed Status]-Schnittstelle finden Sie im Handbuch &quot;Serververwaltung und -installation&quot;.
