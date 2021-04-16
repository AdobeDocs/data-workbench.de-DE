---
description: Latenztabellenvisualisierungen sind Tabellen mit einer Latenzdimension, einer Art abgeleiteter Dimension, die die seit dem Auftreten eines bestimmten Ereignisses verstrichene Zeit misst.
title: Latenztabellen
uuid: 8081540c-f96c-424e-802d-05d1be5a728d
exl-id: 22f6d52f-e1c2-430a-9e69-3440be0ecdea
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '800'
ht-degree: 1%

---

# Latenztabellen{#latency-tables}

Latenztabellenvisualisierungen sind Tabellen mit einer Latenzdimension, einer Art abgeleiteter Dimension, die die seit dem Auftreten eines bestimmten Ereignisses verstrichene Zeit misst.

Sie definieren das Ereignis, indem Sie Auswahlen innerhalb einer oder mehrerer Visualisierungen treffen und diese Auswahlen mithilfe der Kontextmenüoption &quot;Ereignis festlegen&quot;als Ereignis festlegen. Latenztabellen sind besonders hilfreich, um Aktivitäten zu verfolgen, die sich auf eine Kampagne oder eine bestimmte Kundenbestellung beziehen, in der Sie nach einer Zeitkorrelation suchen.

In [!DNL Site]-Latenztabellen finden Sie Informationen zu den Besucher-Sitzungen, die bis zu sieben Tage vor oder nach dem Ereignis stattgefunden haben. Sie können jedoch Latenztabellen konfigurieren, um Informationen zu verschiedenen zählbaren und zeitbezogenen Dimensionen bereitzustellen. Siehe [Konfigurieren von Latenztabellen](../../../home/c-get-started/c-intf-anlys-ftrs/c-config-ltcy-tbls/c-config-ltcy-tbls.md#concept-7175c3defec64556994f0dfcccb7d15c).

Elemente der übergeordneten Dimension, z. B. eine Sitzung, die Teil des ausgewählten Ereignisses sind, haben eine Latenz von null. Allen anderen Elementen werden Latenzen zugewiesen, die den Abstand (in der entsprechenden Zeitdimension) zum Ereignis widerspiegeln.

Das folgende Beispiel zeigt, wie Sie die Latenztabelle verwenden können.

**Identifizieren Sie die Ereignis für Werte in Bezug auf eine Kampagne.**

Angenommen, Sie möchten die Aktivität der Kunden während der sieben Tage vor und nach der Antwort auf eine bestimmte Kampagne der Werbung verfolgen. Zur Ansicht der Latenz für eine bestimmte Kampagne der Werbung legen Sie die Kampagne des Interesses als Ereignis für die Latenztabelle fest.

Die Latenz im Arbeitsbereich unten basiert auf der Auswahl der Kampagne 11566 (die Sitzungen als Reaktion auf diese Kampagne).

![](assets/vis_Latency.png)

Eine Wartezeit von &quot;+0 Tagen&quot;bezeichnet die Sitzungen als Antwort auf Kampagne 11566 sowie alle anderen Sitzungen für dieselben Kunden, die am selben Tag stattgefunden haben.

Eine Wartezeit von &quot;-2 Tagen&quot;bezeichnet die Sitzungen für dieselben Kunden, die zwei Tage vor der Antwort der Kunden auf die Kampagne stattgefunden haben.

Eine Wartezeit von &quot;+7 Tagen&quot;gibt die Sitzungen für dieselben Kunden an, die sieben Tage nach der Antwort auf die Kampagne stattgefunden haben.

Zusätzlich zu den in den folgenden Abschnitten aufgeführten Verfahren können Sie alle Aufgaben durchführen, die Sie in einer Tabelle ausführen können, z. B. Elemente sortieren, Maskenelemente, eine Serienlegende hinzufügen, Daten exportieren usw. Weitere Informationen finden Sie unter [Tabellen](../../../home/c-get-started/c-analysis-vis/c-tables/c-tables.md#concept-c632cb8ad9724f90ac5c294d52ae667f).

## Erstellen einer Latenztabelle {#section-31a03031d9854ef7acc2462d4f37678d}

Um eine Latenztabelle zu erstellen, müssen Sie zunächst eine Auswahl treffen und diese Auswahl dann als Ereignis festlegen, für das Sie die Latenz verfolgen möchten.

1. Klicken Sie mit der rechten Maustaste in einen Arbeitsbereich und öffnen Sie die gewünschte(n) Visualisierung(en), die auf der zählbaren Dimension basieren muss, die zur Konfiguration der Latenztabelle verwendet wird.

   In [!DNL Site] müssten die Visualisierungen beispielsweise sitzungsbasiert sein.

1. Öffnen Sie eine leere Latenztabelle.
1. Treffen Sie eine Auswahl in Ihrer Arbeitsfläche.
1. Klicken Sie mit der rechten Maustaste in die Latenztabelle und klicken Sie auf **[!UICONTROL Set Event]**.

![](assets/vis_Latency_SetEvent.png)

>[!NOTE]
>
>Ereignis, die Sie auswählen, bleiben nur bestehen, wenn Sie die Auswahl als Latenzdimension speichern. Weitere Informationen finden Sie unter [Wiederverwenden einer Latenzzeit-Dimension](../../../home/c-get-started/c-analysis-vis/c-lat-tbls.md#section-29c6483bf9ba476fb1c24ad1df253f46).

## Latenztabelle {#section-05f741169d204213b6537dce553e4f73} wiederverwenden

Wenn Sie dieselbe Latenztabelle erneut verwenden möchten, können Sie die Latenztabelle lokal speichern oder mit den entsprechenden Berechtigungen auf dem Server speichern, damit alle Benutzer eines bestimmten Profils darauf zugreifen können.

**So speichern Sie die Latenztabelle für die Verwendung in anderen Arbeitsbereichen**

1. Klicken Sie mit der rechten Maustaste auf den oberen Rand der Visualisierung und klicken Sie auf **[!UICONTROL Save]**. Das Fenster [!DNL Save] wird angezeigt. Der Standardspeicherort ist der Ordner &quot;User\*Profil*\Work&quot;.
1. Geben Sie im Feld [!DNL File name] einen beschreibenden Namen für die Visualisierung ein und klicken Sie auf **[!UICONTROL Save]**.

**So rufen Sie die gespeicherte Latenztabelle ab**

1. Klicken Sie mit der rechten Maustaste in den Arbeitsbereich und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL File]**. Das Fenster [!DNL Open Visualization] wird angezeigt.
1. Navigieren Sie zu der von Ihnen gespeicherten Latenztabelle.
1. Wählen Sie die Visualisierungsdatei für die Latenztabelle ( [!DNL *.vw]) und klicken Sie auf **[!UICONTROL Open]**.

## Wiederverwenden der Latenzdimension {#section-29c6483bf9ba476fb1c24ad1df253f46}

Wenn Sie die gleiche Latenzdimension erneut verwenden möchten, können Sie die Latenzdimension lokal speichern oder mit den entsprechenden Berechtigungen auf dem Server speichern, damit alle Benutzer eines bestimmten Profils darauf zugreifen können.

Alle von Ihnen erstellten Latenzdimensionen werden im Ordner &quot;Dimensionen&quot;des Profils gespeichert und stehen in der Dropdown-Liste [!DNL Change Dimension] in der Data Workbench zur Verfügung.

**So speichern Sie die Latenzdimension für die Verwendung in anderen Arbeitsbereichen**

1. Klicken Sie mit der rechten Maustaste auf die Spaltenbezeichnung [!DNL Latency] oder auf eines der Elemente und klicken Sie auf **[!UICONTROL Save Dimension]**. Das Fenster [!DNL Save Dimension As] wird angezeigt.
1. Wählen Sie im Ordner &quot;Dimensionen&quot;den entsprechenden Unterordner aus oder erstellen Sie ihn.
1. Geben Sie im Feld [!DNL File name] einen beschreibenden Namen für die Dimension ein (z. B. [!DNL Latency for Campaign 11565.dim]) und klicken Sie auf **[!UICONTROL Save]**.

**So rufen Sie die Dimension &quot;gespeicherte Latenz&quot;ab**

1. Klicken Sie mit der rechten Maustaste in den Arbeitsbereich und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL File]**. Das Fenster [!DNL Open Visualization] wird angezeigt.
1. Navigieren Sie zur Latenzvisualisierung, die Sie im Ordner &quot;Profil*\Dimensionen&quot;gespeichert haben.
1. Wählen Sie die Latenzdimensionsdatei ( [!DNL *.dim]) und klicken Sie auf **[!UICONTROL Open]**.

## Exportieren in Microsoft Excel {#section-3dffa5c3aab14cdaa40c78b81b08fe53}

Informationen zum Exportieren von Fenstern finden Sie unter [Exportieren von Fensterdaten](../../../home/c-get-started/c-wk-win-wksp/c-exp-win-data.md#concept-8df61d64ed434cc5a499023c44197349).

## Exportieren in eine TSV-Datei {#section-fd921f351c994ed0a94f63d3bd5b5a87}

Informationen zum Exportieren von Fenstern finden Sie unter [Exportieren von Fensterdaten](../../../home/c-get-started/c-wk-win-wksp/c-exp-win-data.md#concept-8df61d64ed434cc5a499023c44197349).
