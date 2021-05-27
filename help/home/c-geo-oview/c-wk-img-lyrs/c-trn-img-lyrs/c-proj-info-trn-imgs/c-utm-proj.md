---
description: Die UTM-Projektion (Universal Transverse Mercator) wird durch acht Parameter definiert.
title: Universelle Transversal-Mercatorprojektionen
uuid: 55421412-5c68-4a4f-88d6-650d5999a77c
exl-id: 7d7610c3-14e7-474e-b792-ad413c86a2ef
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '333'
ht-degree: 3%

---

# Universelle Transversal-Mercatorprojektionen{#universal-transverse-mercator-projections}

Die UTM-Projektion (Universal Transverse Mercator) wird durch acht Parameter definiert.

Wenn Sie eine universelle Transversal-Mercatorprojektion für eine Topografiebildebene festlegen, müssen Ihre Topografiebildedateien mit false (projiziert) nördlich an die Bildspitze und false Eastern an die rechte Bildseite ausgerichtet werden.

Um eine UTM-Projektion für eine beliebige Topografiebildquelle anzugeben, müssen Sie die Datei [!DNL Terrain Images.cfg] in einem Texteditor wie Notepad öffnen, den Parameter Projektionsinformationen auf &quot;TransverseMercatorProjection&quot;setzen und Einstellungen für die UTM-Projektion hinzufügen.

**So legen Sie eine universelle Transversal-Mercatorprojektion fest**

1. Klicken Sie in [!DNL Server Files Manager] auf **[!UICONTROL Components]** , um den Inhalt anzuzeigen. Die Datei [!DNL Terrain Images.cfg] befindet sich in diesem Verzeichnis.

1. Klicken Sie mit der rechten Maustaste auf das Häkchen in der Spalte *Servername* für [!DNL Terrain Images.cfg] und klicken Sie dann auf **[!UICONTROL Make Local]**. In der Spalte [!DNL Temp] für [!DNL Terrain Images.cfg] wird ein Häkchen angezeigt.

1. Klicken Sie mit der rechten Maustaste auf das neu erstellte Häkchen in der Spalte [!DNL Temp] und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. Die Datei [!DNL Terrain Images.cfg]wird in einem Editor-Fenster angezeigt.

1. Bearbeiten Sie die Parameter Projektionsinformationen mithilfe des folgenden Beispieldateifragments und der Parametertabelle als Handbücher. Stellen Sie sicher, dass Sie den Projektionstyp wie unten hervorgehoben angeben.

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
| Ellipsoid Inverse Flatening, Ellipsoid Semimajor Axis | Die Parameter des für die Projektion verwendeten Auslassungspunkts. Die Achse der Hauptachsen ist in Metern angegeben. |
| Falsch verzehrt | Das falsche Ost des zentralen Meridians der Projektion in Metern. Für UTM ist dies immer 500.000. |
| Falsche Normung | Die falsche Normalisierung des Äquators in der Projektion in Metern. UTM: 0 für die Zonen auf der Nordhalbkugel und 10.000 für die Gebiete auf der Südhalbkugel. |
| Nordwest-Kornkoordinaten, Südostkornkoordinaten | Die Koordinaten (in projizierten Metern) der oberen linken und unteren rechten Ecke des Bildes. |
| Premierminister Meridian | Der Längengrad des zentralen Längenkreises der Projektion, angegeben in Grad östlich von Greenwich. Negative Zahlen können verwendet werden, um westliche Grade anzugeben. |
| Skalierungsfaktor | Das Verhältnis zwischen dem Radius des Projektionszylinders und der halben Achse des Ellipsoiums. Für UTM-Projektionen (Universal Transverse Mercator) ist dies immer 0,9996. |
