---
description: Informationen zum Status Ihres Berichtsservers und zum Berichtssatzstatus.
solution: Analytics
title: Berichtsstatus überprüfen
topic: Data workbench
uuid: 0f78a9fd-83d5-4e05-b7d1-d841033a5616
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Berichtsstatus überprüfen{#reviewing-report-status}

Informationen zum Status Ihres Berichtsservers und zum Berichtssatzstatus.

* [Berichtsserverstatus](../../../home/c-rpt-oview/c-admin-rpt/c-rev-rpt-st.md#section-1a84f22439ee4a4ba2b3434e51e82ce0)
* [Berichtsstatus](../../../home/c-rpt-oview/c-admin-rpt/c-rev-rpt-st.md#section-8569b94266b74a1f85d2a85106a2aaef)

## Berichtsserverstatus {#section-1a84f22439ee4a4ba2b3434e51e82ce0}

**Empfohlene Häufigkeit:** Nur bei Bedarf

[!DNL Report] sendet alle zwei Minuten Statusinformationen zum Status des [!DNL Report] Servers an den Data Workbench-Server. Diese Informationen können Sie unter dem [!DNL Report Server Status] Knoten in der [!DNL Detailed Status] Oberfläche sehen.

**So öffnen Sie die[!DNL Detailed Status]Visualisierung**

1. Klicken Sie in Data Workbench mit der rechten Maustaste in einen Arbeitsbereich und klicken Sie auf **[!UICONTROL Admin]** > **[!UICONTROL Servers]**.

1. Klicken Sie in der [!DNL Servers] Oberfläche mit der rechten Maustaste auf das Symbol des Data Workbench-Servers, mit dem der [!DNL Report] Computer verbunden ist, und klicken Sie auf **[!UICONTROL Detailed Status.]**

1. Klicken Sie auf **[!UICONTROL Report Server Status]**.

Wenn mehr als eine Verbindung mit dem Data Workbench-Server [!DNL Report] besteht, wird für jede Komponente [!DNL Report Server] im Statusvektor ein Eintrag angezeigt. Das zweiminütige Intervall kann überschrieben werden, indem ein Wert im Parameter &quot;Statusintervall (seconds)&quot;im [!DNL Reporting] Knoten der [!DNL ReportServer.cfg] Datei angegeben wird.

Informationen zur [!DNL ReportServer.cfg] Datei finden Sie unter [Konfigurieren des Berichtssatzes](../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/t-config-rpt-set.md#task-cfb2fd0c28bc48c2acdd582fe0d670d0). Weitere Informationen zum Konfigurieren [!DNL Report]finden Sie unter [Installieren des Berichts](../../../home/c-rpt-oview/c-inst-rpt/c-inst-rpt.md#concept-3b8696a5b7f04ebfaafec7ff55890d91).

Weitere Informationen finden Sie [!DNL Detailed Status]im Kapitel &quot;Verwaltungsschnittstellen&quot;des *Data Workbench-Benutzerhandbuchs*.

## Berichtsstatus {#section-8569b94266b74a1f85d2a85106a2aaef}

**Empfohlene Häufigkeit:** Nur bei Bedarf

[!DNL Report] Sendet Statusinformationen für jeden Berichtssatz an den Data Workbench-Server. Grundlegende Informationen, z. B. wann ein Bericht generiert und wo er verteilt wird, werden in der Data Workbench über dem Berichtssatz in grünem Text angezeigt. Während der Ausführung von Berichten gibt der [!DNL Report] Server alle zwei Minuten eine Meldung aus, die den prozentualen Anteil der aktuellen Abfragen angibt. Dieses zweiminütige Intervall kann überschrieben werden, indem ein Wert im Parameter &quot;Intervall für Abschlussmeldung (Sekunden)&quot;im [!DNL Reporting] Knoten der [!DNL ReportServer.cfg] Datei angegeben wird.

![](assets/report_status.png)

>[!NOTE]
>
>Wenn beim Ausführen eines Berichts ein Fehler auftrat, wird der Fehler in rotem Text unter der Miniaturansicht des Berichts angezeigt. Sie können mit der rechten Maustaste auf den Arbeitsbereich klicken, um die vollständige Fehlermeldung anzuzeigen.

