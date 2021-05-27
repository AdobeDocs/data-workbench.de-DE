---
description: Informationen zu Ihrem Report Server-Status und Berichtsset-Status.
title: Überprüfen des Report Server- und Berichtssatzstatus
uuid: 0f78a9fd-83d5-4e05-b7d1-d841033a5616
exl-id: a986f148-f019-457c-ade8-a4eaecbb1de7
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 2%

---

# Überprüfen des Report Server- und Berichtssatzstatus{#reviewing-report-status}

Informationen zu Ihrem Report Server-Status und Berichtsset-Status.

* [Report Server-Status](../../../home/c-rpt-oview/c-admin-rpt/c-rev-rpt-st.md#section-1a84f22439ee4a4ba2b3434e51e82ce0)
* [Status der Berichtssätze](../../../home/c-rpt-oview/c-admin-rpt/c-rev-rpt-st.md#section-8569b94266b74a1f85d2a85106a2aaef)

## Berichtsserverstatus {#section-1a84f22439ee4a4ba2b3434e51e82ce0}

**Empfohlene Häufigkeit:** Nur bei Bedarf

[!DNL Report] sendet alle zwei Minuten Statusinformationen zum Status des  [!DNL Report] Servers an den Data Workbench-Server. Diese Informationen finden Sie unter dem Knoten [!DNL Report Server Status] in der [!DNL Detailed Status]-Benutzeroberfläche.

**So öffnen Sie die  [!DNL Detailed Status] Visualisierung**

1. Klicken Sie in Data Workbench mit der rechten Maustaste in einen Arbeitsbereich und klicken Sie auf **[!UICONTROL Admin]** > **[!UICONTROL Servers]**.

1. Klicken Sie in der [!DNL Servers]-Benutzeroberfläche mit der rechten Maustaste auf das Symbol des Data Workbench-Servers, mit dem sich der [!DNL Report]-Computer verbindet, und klicken Sie auf **[!UICONTROL Detailed Status.]**.

1. Klicken Sie auf **[!UICONTROL Report Server Status]**.

Wenn mehr als ein [!DNL Report] mit dem Data Workbench-Server verbunden ist, wird für jedes [!DNL Report Server] im Statusvektor ein Eintrag angezeigt. Das zweiminütige Intervall kann überschrieben werden, indem im [!DNL Reporting]-Knoten der Datei [!DNL ReportServer.cfg] ein Wert im Parameter Statusintervall (Sekunden) angegeben wird.

Weitere Informationen zur Datei [!DNL ReportServer.cfg] finden Sie unter [Konfigurieren des Berichtssatzes](../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/t-config-rpt-set.md#task-cfb2fd0c28bc48c2acdd582fe0d670d0). Informationen zur Konfiguration von [!DNL Report] finden Sie unter [Installieren von Berichten](../../../home/c-rpt-oview/c-inst-rpt/c-inst-rpt.md#concept-3b8696a5b7f04ebfaafec7ff55890d91).

Weitere Informationen zu [!DNL Detailed Status] finden Sie im Kapitel &quot;Verwaltungsschnittstellen&quot;des *Data Workbench-Benutzerhandbuchs*.

## Status der Berichtssätze {#section-8569b94266b74a1f85d2a85106a2aaef}

**Empfohlene Häufigkeit:** Nur bei Bedarf

[!DNL Report] übermittelt Statusinformationen für jeden Berichtssatz an den Data Workbench-Server. Grundlegende Informationen, z. B. wann ein Berichtssatz generiert und wo er verteilt wird, werden in Data Workbench über dem Berichtssatz in grünem Text angezeigt. Während der Ausführung von Berichten gibt der Server alle zwei Minuten eine Meldung aus, die den prozentualen Abschluss der aktuellen Abfragen angibt. [!DNL Report] Dieses zweiminütige Intervall kann überschrieben werden, indem ein Wert im Parameter Abschlussmeldung Interval (seconds) im Knoten [!DNL Reporting] der Datei [!DNL ReportServer.cfg] angegeben wird.

![](assets/report_status.png)

>[!NOTE]
>
>Wenn bei der Ausführung eines Berichts ein Fehler aufgetreten ist, wird der Fehler in rotem Text unter der Miniaturansicht dieses Berichts angezeigt. Sie können mit der rechten Maustaste auf den Arbeitsbereich klicken, um die vollständige Fehlermeldung anzuzeigen.
