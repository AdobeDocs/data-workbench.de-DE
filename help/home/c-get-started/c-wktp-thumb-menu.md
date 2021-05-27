---
description: Exportieren, Kopieren und Lesezeichen aus der Arbeitsfläche.
title: Verwenden des Miniaturansichten-Menüs der Arbeitsfläche
uuid: bada2260-3ae7-4fb6-938a-40b7acb1ffa7
exl-id: 2220051d-5c53-48ed-8e13-62883819f22a
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '490'
ht-degree: 3%

---

# Verwenden des Miniaturansichten-Menüs der Arbeitsfläche{#using-the-worktop-thumbnail-menu}

Exportieren, Kopieren und Lesezeichen aus der Arbeitsfläche.

Klicken Sie mit der rechten Maustaste auf einen Arbeitsbereich, um Funktionen zu exportieren, zu kopieren und mit Lesezeichen zu versehen.

![](assets/thumbnail_menu.png)

## Schnittstellenbeschreibungen {#section-fd027dd94b7d4cb6b933d70c08ccd3e2}

Die folgenden Elemente sind im Menü [!DNL Worktop] Miniaturansicht verfügbar:

**Server-Arbeitsbereich:** *name*

Wird nur für nicht bearbeitete Server-Arbeitsbereiche angezeigt. Identifiziert den benannten Arbeitsbereich als identisch mit dem auf dem Server gespeicherten Arbeitsbereich.

**Datum:** *Tag und Uhrzeit*

Datum und Uhrzeit des letzten Öffnens des Arbeitsbereichs.

**Lokale Version von:** *name*

Wird nur für lokale Versionen von Server-Arbeitsbereichen angezeigt. Identifiziert den benannten Arbeitsbereich als bearbeitete, lokale Version eines auf dem Server gespeicherten Arbeitsbereichs.

**Benutzerarbeitsbereich:** *name*

Wird nur für Benutzer-Arbeitsbereiche angezeigt. Identifiziert den benannten Arbeitsbereich als Arbeitsbereich, der nur auf dem lokalen Computer vorhanden ist.

**Im Hintergrund berechnen**

Wird nur angezeigt, wenn Sie online arbeiten. Behält die Abfragen im ausgewählten Arbeitsbereich im Hintergrund bei, während Sie mit der Arbeit fortfahren. Wenn diese Option aktiviert ist, zeigt die Miniaturansicht die folgenden Informationen an, die den Fortschritt der Abfragen anzeigen:

* Arbeit: *n%* - zeigt an, dass die Abfrage verarbeitet wird, und zeigt den Prozentsatz der Verarbeitung an, der abgeschlossen ist.
* ** nMB Query Load - Gesamtgröße des Abfrageergebnisses. Query Load ist proportional zur Gesamtspeicherlast Ihres Data Workbench-Servers, korreliert jedoch nicht direkt. Als Richtlinie kann eine Abfrage von 10 MB oder mehr Ihr System belasten. Die angegebene Abfrage-Load berücksichtigt kein Clustering.

   >[!NOTE]
   >
   >Wenn die Option Im Hintergrund berechnen ausgewählt bleibt, werden die Abfragen im ausgewählten Arbeitsbereich zu statigen Abfragen, die weiterhin aktualisiert werden und Arbeitsspeicherlast nutzen. Deaktivieren Sie unbedingt die Option Im Hintergrund berechnen , wenn Sie mit der Arbeit im Arbeitsbereich fertig sind.

**Nach Excel exportieren**

Exportieren Sie Workspace-Daten in eine Tabelle in Microsoft Excel (.xls- und .xslx-Dateien). Beim Exportieren eines Arbeitsbereichs in Excel exportiert Data Workbench Daten aus bestimmten Visualisierungen, Dimensions- und Wertlegenden sowie Textanmerkungen in eine neue Excel-Arbeitsmappe mit einer Visualisierung pro Arbeitsblatt.

**In Excel-Vorlage exportieren**

Exportieren in eine Excel-Vorlage (.xltx).

**Copy**

Kopiert den Arbeitsbereich. Weitere Informationen zum Einfügen eines kopierten Arbeitsbereichs finden Sie unter [Kopieren und Einfügen vorhandener Arbeitsbereiche](../../home/c-get-started/c-work-worksp/c-create-worksp.md#section-f91ae89b845640c9a4a52820a6110e65).

**Auf Serverversion zurücksetzen**

Wird nur für lokale Versionen von Server-Arbeitsbereichen angezeigt. Löscht die lokale Kopie dieses Arbeitsbereichs. Das Original verbleibt auf dem Server.

**Löschen**

Wird nur für Benutzer-Arbeitsbereiche angezeigt. Löscht den Benutzerarbeitsbereich, der nur auf dem lokalen Computer vorhanden ist. Informationen zum Löschen von Arbeitsbereichen vom verbundenen Data Workbench-Server finden Sie unter [Löschen von  aus Ihrem Arbeitsprofil](../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-del-files-wkg-prof.md#task-1e29c25e6c824cc9b51cb651e835856b).

**Auf Server speichern**

Wird nur für lokale Versionen von Server-Arbeitsbereichen und Benutzer-Arbeitsbereichen angezeigt und funktioniert nur für Benutzer mit den entsprechenden Berechtigungen. Speichert die lokale Kopie des Arbeitsbereichs auf dem Server. Standardmäßig werden Arbeitsbereiche im entsprechenden Ordner `<profile name>\Workspaces\<tab name>` gespeichert.

**Lesezeichen**

Markieren Sie einen Arbeitsbereich, um ihn später schnell abzurufen.

Das Lesezeichensymbol ![](assets/bookmark_icon.png) wird über dem Arbeitsbereich auf der Arbeitsfläche angezeigt und der Name des Arbeitsbereichs wird im Bereich Lesezeichen angezeigt. ![](assets/bookmark_worktop.png)
