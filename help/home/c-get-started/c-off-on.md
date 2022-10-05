---
description: Informationen zum Arbeiten mit dem Data Workbench-Server entweder offline oder online.
title: Arbeiten offline und online
uuid: 613699d4-6d06-4c3c-b0aa-620933ae4d67
exl-id: 1c9e0f4f-3172-40d3-b751-ebe6f9f57f8a
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '448'
ht-degree: 1%

---

# Arbeiten offline und online{#working-offline-and-online}

{{eol}}

Informationen zum Arbeiten mit dem Data Workbench-Server entweder offline oder online.

Data Workbench lädt automatisch Aktualisierungen des Profils und seiner Daten vom Data Workbench-Server herunter, wenn Sie eine Netzwerkverbindung zum [!DNL server] und arbeiten online. Wenn Sie nicht angegeben haben, dass Data Workbench online arbeiten soll, lädt das Profil und seine Daten aus dem Cache Ihres Computers. In diesem Fall sehen Sie die Version des Profils und die Daten, die beim letzten Mal heruntergeladen wurden, als Sie mit dem Profil online arbeiteten.

Offline arbeiten bietet einen Vorteil bei der Verarbeitungsgeschwindigkeit, da Sie aus dem lokalen Cache arbeiten und die Daten auf Ihrem eigenen Computer abfragen. Bei der Online-Arbeit muss jede Abfrage an den Server der Data Workbench zurückgesendet werden, was länger dauert und Sie zwingt, mit anderen Online-Nutzern um Serverressourcen zu konkurrieren. Solange Sie über eine Netzwerkverbindung zum Data Workbench-Server verfügen, verhindert die Offline-Arbeit, dass der Data Workbench-Server die  der Profile oder Daten auf Ihrer Data Workbench aktualisiert. Sie hindert jedoch nicht daran, Elemente auf dem Data Workbench-Server zu speichern.

Aufgrund der Fähigkeit, offline zu arbeiten, wird der Data Workbench-Server so skaliert, dass er eine gewisse Menge an Echtzeit-Traffic-Eingaben und Daten im Datensatz sowie eine gewisse Anzahl von Data Workbench-Benutzern verarbeiten kann. Die Größe muss jedoch nicht so geändert werden, dass die maximale Anzahl gleichzeitiger Benutzer unterstützt wird (was in der Praxis nicht oft vorkommt). Da Benutzer in der Regel nach Trends und Verhältnissen suchen, sollten Sie die Daten während des gesamten Zeitraums untersuchen. In den meisten Fällen benötigen Sie keine genauen Zählungen. Wenn Sie die Zählung mithilfe der aktuellen Daten abfragen und auflösen müssen, können Sie online arbeiten und diese abrufen. Die Auflösung der Abfragen dauert jedoch länger als 100 Prozent.

**So arbeiten Sie online oder offline**

Klicken Sie in der Seitenleiste auf die **[!UICONTROL Connection]** festlegen und auf **[!UICONTROL Work Online]**.

![](assets/sidebar_work_online.png)

Wenn Sie online arbeiten, stellt Data Workbench eine Verbindung zum Data Workbench-Server her und synchronisiert die Informationen auf Ihrem Computer mit dem Profil und den zugehörigen Datensatzinformationen auf dem Data Workbench-Server.

Die Standardkonfiguration für die Data Workbench besteht darin, offline zu arbeiten. Wie im folgenden Abschnitt beschrieben, kann jeder Benutzer seine [!DNL Insight.cfg] -Datei, damit ihre Instanz der Data Workbench standardmäßig online funktioniert.

**So arbeiten Sie standardmäßig online**

1. Navigieren Sie zum Installationsverzeichnis von Insight.
1. Öffnen Sie die [!DNL Insight.cfg] in einem Texteditor.
1. Fügen Sie die hervorgehobene Zeile zur Datei hinzu, wie im folgenden Beispiel gezeigt:

```
Update Software = bool: true
Default to Online = bool: true
Color Set = int: 0
```

Wenn Sie die Data Workbench das nächste Mal öffnen, stellt sie eine Verbindung zum Data Workbench-Server her und funktioniert standardmäßig online.
