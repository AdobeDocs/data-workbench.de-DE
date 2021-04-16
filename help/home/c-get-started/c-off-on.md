---
description: Informationen zum Arbeiten mit dem Data Workbenchs-Server entweder offline oder online.
title: Arbeiten offline und online
uuid: 613699d4-6d06-4c3c-b0aa-620933ae4d67
exl-id: 1c9e0f4f-3172-40d3-b751-ebe6f9f57f8a
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '448'
ht-degree: 1%

---

# Arbeiten offline und online{#working-offline-and-online}

Informationen zum Arbeiten mit dem Data Workbenchs-Server entweder offline oder online.

Data Workbench lädt automatisch Updates des Profils und seiner Daten vom Data Workbenchs-Server herunter, wenn Sie eine Netzwerkverbindung zum [!DNL server] haben und online arbeiten. Wenn Sie nicht angegeben haben, dass das Profil und die Daten von der Data Workbench aus dem Cache Ihres Computers geladen werden sollen. In diesem Fall zeigen Sie die Version des Profils und die Daten an, die beim letzten Mal heruntergeladen wurden, wenn Sie mit dem Profil online gearbeitet haben.

Die Arbeit mit Offline-Angeboten bietet einen Vorteil bei der Verarbeitungsgeschwindigkeit, da Sie aus dem lokalen Cache arbeiten und die Daten auf Ihrem eigenen Computer abfragen. Wenn Sie online arbeiten, muss jede Abfrage auf den Server der Data Workbench zurückgreifen, was Sie länger dauert und Sie zwingt, mit anderen Online-Nutzern um Serverressourcen zu konkurrieren. Solange Sie über eine Netzwerkverbindung zum Data Workbench-Server verfügen, verhindert das Offline-Arbeiten, dass der Data Workbench-Server die Profil oder Daten auf Ihrer Data Workbench aktualisiert, Sie werden jedoch nicht daran gehindert, Elemente auf dem Data Workbench-Server zu speichern.

Aufgrund der Fähigkeit, offline zu arbeiten, ist der Data Workbench-Server so groß, dass er Traffic-Eingaben in Echtzeit und einige Datenmengen im Datensatz sowie einige Data Workbenchs verarbeitet. Die Größe muss jedoch nicht angepasst werden, um die maximale Anzahl gleichzeitiger Benutzer zu unterstützen (was in der Praxis nicht oft vorkommt). Da Benutzer in der Regel nach Trends und Verhältnissen suchen, müssen Sie die Daten in den meisten Fällen nicht genau zählen. Wenn die Abfrage und die Auflösung der Zählung anhand der aktuellen Daten erforderlich ist, können Sie online arbeiten und das bekommen, aber die Abfragen nehmen länger auf 100 Prozent zu.

**So arbeiten Sie online oder offline**

Klicken Sie in der Seitenleiste auf die Einstellung **[!UICONTROL Connection]** und dann auf **[!UICONTROL Work Online]**.

![](assets/sidebar_work_online.png)

Wenn Sie online arbeiten, stellt Data Workbench eine Verbindung zum Data Workbench-Server her und synchronisiert die Informationen auf Ihrem Computer mit dem Profil und den zugehörigen Datensatzinformationen, die sich auf dem Data Workbench-Server befinden.

Die Standardkonfiguration für die Data Workbench besteht darin, offline zu arbeiten. Wie im folgenden Abschnitt beschrieben, kann jeder Benutzer seine [!DNL Insight.cfg]-Datei ändern, damit seine Instanz der Data Workbench standardmäßig online funktioniert.

**So arbeiten Sie standardmäßig online**

1. Navigieren Sie zum Installationsordner von Insight.
1. Öffnen Sie die Datei [!DNL Insight.cfg] in einem Texteditor.
1. hinzufügen Sie die hervorgehobene Zeile wie im folgenden Beispiel gezeigt an die Datei an:

```
Update Software = bool: true
Default to Online = bool: true
Color Set = int: 0
```

Wenn Sie die Data Workbench das nächste Mal öffnen, stellt sie eine Verbindung zum Data Workbench-Server her und funktioniert standardmäßig online.
