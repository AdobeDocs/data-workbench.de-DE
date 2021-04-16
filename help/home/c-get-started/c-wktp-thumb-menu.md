---
description: So exportieren, kopieren und mit Lesezeichen versehen von der Arbeitsfläche aus.
title: Verwenden des Miniaturansichten-Menüs der Arbeitsfläche
uuid: bada2260-3ae7-4fb6-938a-40b7acb1ffa7
exl-id: 2220051d-5c53-48ed-8e13-62883819f22a
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '490'
ht-degree: 3%

---

# Verwenden des Miniaturansichten-Menüs der Arbeitsfläche{#using-the-worktop-thumbnail-menu}

So exportieren, kopieren und mit Lesezeichen versehen von der Arbeitsfläche aus.

Klicken Sie mit der rechten Maustaste auf einen Arbeitsbereich, um Funktionen zu exportieren, zu kopieren und mit Lesezeichen zu versehen.

![](assets/thumbnail_menu.png)

## Schnittstellenbeschreibungen {#section-fd027dd94b7d4cb6b933d70c08ccd3e2}

Die folgenden Elemente sind im Miniaturmenü [!DNL Worktop] verfügbar:

**Server-Arbeitsbereich:** *Name*

Wird nur für nicht bearbeitete Serverarbeitsbereiche angezeigt. Identifiziert den benannten Arbeitsbereich als den Arbeitsbereich, der auf dem Server gespeichert ist.

**Datum:** *Tag und Uhrzeit*

Datum und Uhrzeit des letzten Öffnens der Arbeitsfläche.

**Lokale Version von:** *name*

Wird nur für lokale Versionen von Server-Arbeitsbereichen angezeigt. Identifiziert den benannten Arbeitsbereich als bearbeitete, lokale Version eines auf dem Server gespeicherten Arbeitsbereichs.

**Benutzerarbeitsbereich:** *Name*

Wird nur für Benutzerarbeitsflächen angezeigt. Identifiziert den benannten Arbeitsbereich als Arbeitsbereich, der nur auf dem lokalen Computer vorhanden ist.

**Im Hintergrund berechnen**

Wird nur angezeigt, wenn Sie online arbeiten. Behält die Abfragen im ausgewählten Arbeitsbereich im Hintergrund bei, während Sie weiter arbeiten. Wenn diese Option aktiviert ist, zeigt die Miniaturansicht die folgenden Informationen an, die den Fortschritt der Abfragen anzeigen:

* Arbeit: *n%* - gibt an, dass die Abfrage verarbeitet wird und in welchem Prozentsatz die Verarbeitung abgeschlossen ist.
* ** nMB Abfrage Load - Gesamtgröße des Abfragen-Ergebnisses. Abfrage Load ist proportional zur Gesamtspeicherlast des Data Workbench-Servers, korreliert aber nicht direkt. Als Richtlinie gilt, dass eine Abfrage von 10 MB oder mehr Ihr System belastet. Bei der aufgelisteten Abfrage-Last wird das Clustering nicht berücksichtigt.

   >[!NOTE]
   >
   >Wenn die Option &quot;Im Hintergrund berechnen&quot;weiterhin aktiviert ist, werden die Abfragen im ausgewählten Arbeitsbereich zu stehenden Abfragen, die aktualisiert werden und Arbeitsspeicherlast nutzen. Deaktivieren Sie nach Abschluss der Arbeit im Arbeitsbereich die Option &quot;Im Hintergrund berechnen&quot;.

**Nach Excel exportieren**

Exportieren Sie Workspace-Daten in eine Tabelle in Microsoft Excel (.xls- und .xslx-Dateien). Beim Exportieren einer Arbeitsfläche in Excel exportiert Data Workbench Daten aus bestimmten Visualisierungen, Dimensions- und Wertlegenden sowie Textanmerkungen in eine neue Excel-Arbeitsmappe mit einer Visualisierung pro Arbeitsblatt.

**In Excel-Vorlage exportieren**

Exportieren in eine Excel-Vorlage (.xltx).

**Copy**

Kopiert den Arbeitsbereich. Weitere Informationen zum Einfügen einer kopierten Arbeitsfläche finden Sie unter [Kopieren und Einfügen vorhandener Arbeitsbereiche](../../home/c-get-started/c-work-worksp/c-create-worksp.md#section-f91ae89b845640c9a4a52820a6110e65).

**Serverversion wiederherstellen**

Wird nur für lokale Versionen von Server-Arbeitsbereichen angezeigt. Löscht die lokale Kopie dieses Arbeitsbereichs. Das Original bleibt auf dem Server.

**Löschen**

Wird nur für Benutzerarbeitsflächen angezeigt. Löscht die Benutzerarbeitsfläche, die nur auf dem lokalen Computer vorhanden ist. Weitere Informationen zum Löschen von Arbeitsbereichen vom angeschlossenen Data Workbench-Server finden Sie unter [Löschen von Profile aus Ihrem Arbeitsfarbraum](../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-del-files-wkg-prof.md#task-1e29c25e6c824cc9b51cb651e835856b).

**Auf Server speichern**

Wird nur für lokale Versionen von Server-Arbeitsbereichen und Benutzerarbeitsbereichen angezeigt und funktioniert nur für Benutzer mit den entsprechenden Berechtigungen. Speichert die lokale Kopie des Arbeitsbereichs auf dem Server. Standardmäßig werden Arbeitsflächen im entsprechenden Arbeitsordner `<profile name>\Workspaces\<tab name>` gespeichert.

**Lesezeichen**

Markieren Sie einen Arbeitsbereich, um ihn später schnell abzurufen.

Über dem Arbeitsbereich auf der Arbeitsfläche wird ein Lesezeichensymbol ![](assets/bookmark_icon.png) angezeigt, und der Name des Arbeitsbereichs wird im Lesezeichenbedienfeld angezeigt. ![](assets/bookmark_worktop.png)
