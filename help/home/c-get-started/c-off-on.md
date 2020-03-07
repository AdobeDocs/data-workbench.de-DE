---
description: Informationen zum Arbeiten mit dem Data Workbench-Server entweder offline oder online.
solution: Analytics
title: Offline und online arbeiten
topic: Data workbench
uuid: 613699d4-6d06-4c3c-b0aa-620933ae4d67
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Offline und online arbeiten{#working-offline-and-online}

Informationen zum Arbeiten mit dem Data Workbench-Server entweder offline oder online.

Data Workbench lädt automatisch Aktualisierungen des Profils und der zugehörigen Daten vom Data Workbench-Server herunter, wenn Sie eine Netzwerkverbindung mit dem Server haben [!DNL server] und online arbeiten. Wenn Sie nicht angegeben haben, dass die Funktion online ausgeführt werden soll, lädt Data Workbench das Profil und seine Daten aus dem Cache Ihres Computers. In diesem Fall zeigen Sie die Version des Profils und die Daten an, die beim letzten Mal heruntergeladen wurden, wenn Sie mit dem Profil online gearbeitet haben.

Offline arbeiten bietet einen Vorteil bei der Verarbeitungsgeschwindigkeit, da Sie aus dem lokalen Cache arbeiten und die Daten auf Ihrem eigenen Computer abfragen. Beim Online-Betrieb muss jede Abfrage zurück zum Data Workbench-Server gehen, was länger dauert und Sie zwingt, mit anderen Online-Benutzern um Serverressourcen zu konkurrieren. Solange Sie über eine Netzwerkverbindung zum Data Workbench-Server verfügen, verhindert das Offline-Arbeiten, dass der Data Workbench-Server die Profile oder Daten in Ihrer Data Workbench aktualisiert, Sie aber nicht daran gehindert, Elemente auf dem Data Workbench-Server zu speichern.

Aufgrund der Fähigkeit, offline zu arbeiten, ist der Data Workbench-Server so ausgelegt, dass er eine gewisse Menge an Traffic-Eingaben in Echtzeit und einige Datenmengen im Dataset sowie eine gewisse Anzahl von Data Workbench-Benutzern verarbeitet. Die Größe muss jedoch nicht so angepasst werden, dass die maximale Anzahl gleichzeitiger Benutzer unterstützt wird (was in der Praxis nicht oft vorkommt). Da Benutzer in der Regel nach Trends und Verhältnissen suchen, müssen Sie die Daten in den meisten Fällen nicht genau zählen. Wenn Sie anhand aktueller Daten eine Abfrage und Auflösung zur genauen Zählung vornehmen müssen, können Sie diese online abrufen, aber die Abfragen dauern länger bis zu 100 Prozent.

**So arbeiten Sie online oder offline**

Klicken Sie in der Seitenleiste auf die **[!UICONTROL Connection]** Einstellung und dann auf **[!UICONTROL Work Online]**.

![](assets/sidebar_work_online.png)

Wenn Sie online arbeiten, stellt Data Workbench eine Verbindung zum Data Workbench-Server her und synchronisiert die Informationen auf Ihrem Computer mit dem Profil und den zugehörigen Datensatzinformationen, die sich auf dem Data Workbench-Server befinden.

Die Standardkonfiguration für Data Workbench funktioniert offline, aber wie im folgenden Abschnitt beschrieben kann jeder Benutzer seine [!DNL Insight.cfg] Datei ändern, damit seine Instanz von Data Workbench standardmäßig online funktioniert.

**So arbeiten Sie standardmäßig online**

1. Navigieren Sie zum Installationsordner von Insight.
1. Öffnen Sie die [!DNL Insight.cfg] Datei in einem Texteditor.
1. Fügen Sie der Datei die hervorgehobene Zeile hinzu, wie im folgenden Beispiel gezeigt:

```
Update Software = bool: true
Default to Online = bool: true
Color Set = int: 0
```

Wenn Sie Data Workbench das nächste Mal öffnen, stellt es eine Verbindung zum Data Workbench-Server her und funktioniert standardmäßig online.
