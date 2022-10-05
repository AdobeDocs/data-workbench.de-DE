---
description: Informationen zu Ihrem Report Server-Status und Berichtsset-Status.
title: Überprüfen des Report Server- und Berichtssatzstatus
uuid: 0f78a9fd-83d5-4e05-b7d1-d841033a5616
exl-id: a986f148-f019-457c-ade8-a4eaecbb1de7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 2%

---

# Überprüfen des Report Server- und Berichtssatzstatus{#reviewing-report-status}

{{eol}}

Informationen zu Ihrem Report Server-Status und Berichtsset-Status.

* [Report Server-Status](../../../home/c-rpt-oview/c-admin-rpt/c-rev-rpt-st.md#section-1a84f22439ee4a4ba2b3434e51e82ce0)
* [Status der Berichtssätze](../../../home/c-rpt-oview/c-admin-rpt/c-rev-rpt-st.md#section-8569b94266b74a1f85d2a85106a2aaef)

## Report Server-Status {#section-1a84f22439ee4a4ba2b3434e51e82ce0}

**Empfohlene Häufigkeit:** Nur bei Bedarf

[!DNL Report] sendet alle zwei Minuten Statusinformationen zum Status der [!DNL Report] Server. Diese Informationen finden Sie unter der [!DNL Report Server Status] Knoten in [!DNL Detailed Status] -Schnittstelle.

**So öffnen Sie die [!DNL Detailed Status] Visualisierung**

1. Klicken Sie in Data Workbench mit der rechten Maustaste in einen Arbeitsbereich und klicken Sie auf **[!UICONTROL Admin]** > **[!UICONTROL Servers]**.

1. Im [!DNL Servers] -Oberfläche verwenden, klicken Sie mit der rechten Maustaste auf das Symbol des Data Workbench-Servers, auf dem die [!DNL Report] Maschine verbindet sich mit und klickt **[!UICONTROL Detailed Status.]**

1. Klicken Sie auf **[!UICONTROL Report Server Status]**.

Wenn mehr als ein [!DNL Report] mit dem Data Workbench-Server verbunden ist, wird für jeden [!DNL Report Server] im Statusvektor. Das zweiminütige Intervall kann überschrieben werden, indem ein Wert im Parameter Statusintervall (Sekunden) im [!DNL Reporting] Knoten der [!DNL ReportServer.cfg] -Datei.

Informationen zum [!DNL ReportServer.cfg] -Datei, siehe [Berichtssatz konfigurieren](../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/t-config-rpt-set.md#task-cfb2fd0c28bc48c2acdd582fe0d670d0). Informationen zur Konfiguration [!DNL Report], siehe [Installieren von Berichten](../../../home/c-rpt-oview/c-inst-rpt/c-inst-rpt.md#concept-3b8696a5b7f04ebfaafec7ff55890d91).

Weitere Informationen finden Sie unter [!DNL Detailed Status], siehe das Kapitel &quot;Verwaltungsschnittstellen&quot;im Abschnitt *Data Workbench-Benutzerhandbuch*.

## Status der Berichtssätze {#section-8569b94266b74a1f85d2a85106a2aaef}

**Empfohlene Häufigkeit:** Nur bei Bedarf

[!DNL Report] übermittelt Statusinformationen für jeden Berichtssatz an den Data Workbench-Server. Grundlegende Informationen, z. B. wann ein Berichtssatz generiert und wo er verteilt wird, werden in Data Workbench über dem Berichtssatz in grünem Text angezeigt. Beim Ausführen von Berichten, [!DNL Report] Der Server gibt alle zwei Minuten eine Meldung aus, die den prozentualen Abschluss der aktuellen Abfragen angibt. Dieses zweiminütige Intervall kann überschrieben werden, indem ein Wert im Parameter &quot;Abschlussmeldung Interval (Sekunden)&quot;im [!DNL Reporting] Knoten der [!DNL ReportServer.cfg] -Datei.

![](assets/report_status.png)

>[!NOTE]
>
>Wenn bei der Ausführung eines Berichts ein Fehler aufgetreten ist, wird der Fehler in rotem Text unter der Miniaturansicht dieses Berichts angezeigt. Sie können mit der rechten Maustaste auf den Arbeitsbereich klicken, um die vollständige Fehlermeldung anzuzeigen.
