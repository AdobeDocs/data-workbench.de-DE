---
description: Die UTM-Projektion (Universal Transverse Mercator) wird durch acht Parameter definiert.
title: Universelle Transversal-Mercatorprojektionen
uuid: 55421412-5c68-4a4f-88d6-650d5999a77c
exl-id: 7d7610c3-14e7-474e-b792-ad413c86a2ef
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '333'
ht-degree: 3%

---

# Universelle Transversal-Mercatorprojektionen{#universal-transverse-mercator-projections}

Die UTM-Projektion (Universal Transverse Mercator) wird durch acht Parameter definiert.

Wenn Sie eine universelle Transverse-Mercator-Projektion für eine Terrain-Bildebene festlegen, müssen Ihre Terrain-Bilddateien mit &quot;false&quot;(projiziert) nach Norden gegen den oberen Bildrand und &quot;false east&quot;rechts neben dem Bild ausgerichtet werden.

Um eine UTM-Projektion für eine beliebige Terrain-Bildquelle anzugeben, müssen Sie die Datei [!DNL Terrain Images.cfg] in einem Texteditor wie Notepad öffnen, den Parameter Projektionsinformationen auf &quot;TransverseMercatorProjection&quot;setzen und Einstellungen für die UTM-Projektion hinzufügen.

**So legen Sie eine universelle Transverse-Mercator-Projektion fest**

1. Klicken Sie in [!DNL Server Files Manager] auf **[!UICONTROL Components]**, um den Inhalt Ansicht. Die Datei [!DNL Terrain Images.cfg] befindet sich in diesem Verzeichnis.

1. Klicken Sie mit der rechten Maustaste auf das Häkchen in der Spalte *Servername* für [!DNL Terrain Images.cfg] und klicken Sie dann auf **[!UICONTROL Make Local]**. In der Spalte [!DNL Temp] für [!DNL Terrain Images.cfg] wird ein Häkchen angezeigt.

1. Klicken Sie mit der rechten Maustaste auf das neu erstellte Häkchen in der Spalte [!DNL Temp] und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. Die Datei [!DNL Terrain Images.cfg]wird in einem Editor-Fenster angezeigt.

1. Bearbeiten Sie die Parameter &quot;Projektinfo&quot;mithilfe des folgenden Beispieldateifragments und der Parametertabelle als Hilfslinien. Achten Sie darauf, den Projektionstyp wie unten hervorgehoben anzugeben.

   ```
   Projection Info = TransverseMercatorProjection:
     Ellipsoid Inverse Flattening = double: 294.9786982139006
     Ellipsoid Semimajor Axis = double: 6378206.4000000004
     False Easting = double: 500000
     False Northing = double: 0
     Northwest Corner Coordinates = v3d: (550339, 5.42059e+006, 0)
     Prime Meridian = double: -123
     Scale Factor = double: 0.9996
     Southeast Corner Coordinates = v3d: (555099, 5.41356e+006, 0)
   ```

| Parameter | Beschreibung |
|---|---|
| Ellipsoid Inverse Flatting, Ellipsoid Semimajor Axis | Die Parameter des für die Projektion verwendeten Ellipsoids. Die Achse der Mittelachse ist in Metern angegeben. |
| Fehl | Die falsche Ostlage des zentralen Meridians der Projektion in Metern. Für UTM ist das immer 500.000. |
| Falsche Normsetzung | Die falsche Normsetzung des Äquators in der Projektion in Metern. Für UTM ist dies 0 für die Zonen auf der Nordhalbkugel und 10.000 für die Zonen auf der Südhalbkugel. |
| Nordwest-Corner-Koordinaten, Südost-Koordinaten | Die Koordinaten (in projizierten Metern) der oberen linken und unteren rechten Ecke des Bildes. |
| Premierminister Meridian | Der Längengrad des zentralen Längenkreises der Projektion, angegeben in Grad östlich von Greenwich. Negative Zahlen können verwendet werden, um Grad westlich anzugeben. |
| Skalierungsfaktor | Das Verhältnis zwischen dem Radius des Projektionszylinders und der Mittellinie des Ellipsoids. Bei UTM-Projektionen (Universal Transverse Mercator) ist dies immer 0,9996. |
