---
description: Eine Topografiebildebene zeigt Topografiebilder der Erde an.
title: 'Topografiebildebenen '
uuid: 17968293-1ad2-4040-a174-d33f418af9b7
exl-id: 754211a7-0b1f-4353-86f8-9c634d70cd83
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '992'
ht-degree: 2%

---

# Topografie-Bildebenen{#terrain-image-layers}

Eine Topografiebildebene zeigt Topografiebilder der Erde an.

[!DNL Terrain image layers] werden im  [!DNL Geography] Profil in einem benutzerdefinierten Format gespeichert. Diese Bildebenen können von Adobe erstellt werden, oder der Data Workbench-Server kann Ihre vom Benutzer bereitgestellten Topografiebilder in Topografiebilder umwandeln, die für die weltweite Visualisierung geeignet sind.

>[!NOTE]
>
>Um mit [!DNL terrain image layers] zu arbeiten, müssen Sie die von Adobe bereitgestellte [!DNL Terrain Images.cfg]-Datei installieren.

Um eine Topografiebildebene zu definieren, müssen Sie über Folgendes verfügen:

* **Eine oder mehrere** Topografiebilddateien mit den weltweit anzuzeigenden Bildern.
* **Eine  [!DNL Terrain Images.cfg]** Datei, die die für die Ebene(en) zu verwendenden Topografiebildedateien angibt. Mit der Datei [!DNL Terrain Images.cfg] können Sie eine oder mehrere Quellen hinzufügen, um eine [!DNL terrain image layer] zu erstellen. Das Format Ihrer Topografiebilddatei bestimmt den Quelltyp, den Sie hinzufügen sollten. Die folgende Tabelle enthält Beschreibungen der verfügbaren Quellen für Topografiebildebenen, einschließlich der unterstützten Dateiformate für Topografiebilder:

<table id="table_CFDF5E61FCCD40B29A9D35FFA42F68D1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Typ </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Unprognostizierte Rohbitmap </p> </td> 
   <td colname="col2"> <p>Erstellt <span class="wintitle"> Topografiebildebenen</span> aus 24-Bit-Kopfzeilen-RGB-Dateien, die auf Längen- und Breitengrad ausgerichtet sind (nicht projiziert), wobei Nord oben auf dem Bild und Ost rechts ist. </p> <p>Unterstützte Bildformate: RAW </p> <p> <p>Hinweis: Diese Quelle erfordert Projektionsinformationen. Weitere Informationen zu Projektionsformaten finden Sie unter <a href="../../../../home/c-get-started/c-im-layers/c-ter-img-layers/c-proj-info-ter-imgs.md#concept-eec35baa01744895b847a02e69dad04e"> Festlegen von Projektionsinformationen für Topografiebilder</a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Allgemeines Bild, nicht projiziert </p> </td> 
   <td colname="col2"> <p>Erstellt <span class="wintitle"> Topografiebildebenen</span> aus 24-Bit-Bildformaten mit Breitengrad und Längengrad, die auf (nicht projizierten) Bildformaten ausgerichtet sind, wobei Nord oben auf dem Bild und Ost rechts ist. </p> <p>Unterstützte Bildformate: BMP, JPG, PNG, TIFF </p> <p> <p>Hinweis: Diese Quelle erfordert Projektionsinformationen. Weitere Informationen zu Projektionsformaten finden Sie unter <a href="../../../../home/c-get-started/c-im-layers/c-ter-img-layers/c-proj-info-ter-imgs.md#concept-eec35baa01744895b847a02e69dad04e"> Festlegen von Projektionsinformationen für Topografiebilder</a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Bild mit eingebetteter Projektion </p> </td> 
   <td colname="col2"> <p>Erstellt <span class="wintitle"> Topografiebildebenen</span> aus Bildformaten, die geografische Daten in die Bilddatei einbetten. Die Projektionsinformationen werden aus dem Bild extrahiert. </p> <p>Unterstützte Bildformate: Erdas (IMG), GeoTIFF </p> <p> <p>Hinweis: Diese Quelle benötigt in der Regel keine Projektionsinformationen, unterstützt jedoch bei Bedarf das Hinzufügen solcher Informationen. Weitere Informationen zu Projektionsformaten finden Sie unter <a href="../../../../home/c-get-started/c-im-layers/c-ter-img-layers/c-proj-info-ter-imgs.md#concept-eec35baa01744895b847a02e69dad04e"> Festlegen von Projektionsinformationen für Topografiebilder</a>. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

**So definieren Sie eine Topografiebildebene**

1. Klicken Sie in Data Workbench auf der Registerkarte **[!UICONTROL Admin]** > **[!UICONTROL Dataset and Profile]** auf die Miniaturansicht **[!UICONTROL Servers Manager]** , um den Arbeitsbereich [!DNL Servers Manager] zu öffnen.
1. Klicken Sie im Fenster [!DNL Servers Manager] mit der rechten Maustaste auf das Symbol des gewünschten Data Workbench-Servers und klicken Sie auf **[!UICONTROL Server Files]**.
1. Klicken Sie in [!DNL Server Files Manager] auf **[!UICONTROL Components]** , um den Inhalt anzuzeigen. Die Datei [!DNL Terrain Images.cfg] befindet sich in diesem Verzeichnis.
1. Klicken Sie mit der rechten Maustaste auf das Häkchen in der Spalte mit dem Servernamen für [!DNL Terrain Images.cfg] und klicken Sie dann auf **[!UICONTROL Make Local]**. In der Spalte [!DNL Temp] für [!DNL Terrain Images.cfg] wird ein Häkchen angezeigt.
1. Klicken Sie mit der rechten Maustaste auf das neu erstellte Häkchen in der Spalte **[!UICONTROL Temp]** und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Das Fenster [!DNL Terrain Images.cfg] wird angezeigt.
1. Klicken Sie im Fenster [!DNL Terrain Images] auf **[!UICONTROL component]** , um den Inhalt anzuzeigen.
1. Klicken Sie mit der rechten Maustaste auf **[!UICONTROL Sources]** > **[!UICONTROL Add new]** und wählen Sie einen der folgenden Quelltypen:

   * **[!UICONTROL Raw unprojected bitmap]**. (Nach dem Hinzufügen wird dieser Quelltyp im Fenster [!DNL Terrain Images] mit RawTerrainSource beschriftet.)

   * **[!UICONTROL General image, unprojected]**. (Nach dem Hinzufügen wird dieser Quelltyp im Fenster [!DNL Terrain Images] mit [!DNL GDALTerrainSource] beschriftet.)

   * **[!UICONTROL Image with embedded projection]**. (Nach dem Hinzufügen wird dieser Quelltyp im Fenster [!DNL Terrain Images] mit [!DNL GDALTerrainSource] beschriftet.)

1. Bearbeiten Sie die Parameter für die Quelle nach Bedarf mithilfe der folgenden Beispieldatei und der Tabelle der Parameter als Anleitungen.

   ![](assets/cfg_TerrainImages_ALL.png)

<table id="table_345ACB4C48524516AADB731D87FC6792"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Gamma </p> </td> 
   <td colname="col2"> <p>Optional für alle Quellen. Gibt die Gammakorrektur an, die auf das Quellbild angewendet werden soll. Dies kann wünschenswert sein, da die Data Workbench normalerweise mit einer hohen Gammaeinstellung läuft. Der Standardwert lautet 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Höhe </p> </td> 
   <td colname="col2"> <p>Erforderlich für nicht projizierte Raw-Bitmap-Bilder. Die Höhe des Quellbilds in Pixel. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Projektinformationen </p> </td> 
   <td colname="col2"> <p>Erforderlich für nicht projizierte Raw-Bilder und allgemeine Bilder, nicht projiziert, aber für Bilder mit eingebetteter Projektion unterstützt. Data Workbench unterstützt Breiten- und Längengrad-Projektionen und Projektionen des Transverse Mercator (TM) für Topografiebildebenen. Das standardmäßige Projektionsformat ist die Breiten-/Längengrad-Projektion (LatLonProjection). </p> <p>Weitere Informationen zu Projektionsformaten finden Sie unter <a href="../../../../home/c-get-started/c-im-layers/c-ter-img-layers/c-proj-info-ter-imgs.md#concept-eec35baa01744895b847a02e69dad04e"> Festlegen von Projektionsinformationen für Topografiebilder</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Quellbild </p> </td> 
   <td colname="col2"> <p>Erforderlich für alle Quellen. Der Name der Quellbilddatei. Dies kann ein Dateiname oder ein Platzhaltermuster sein. Die Verwendung eines Musters kann nützlich sein, wenn beispielsweise Bilder für denselben Bereich zu unterschiedlichen Daten hochgeladen werden, ohne dass die zugehörigen Metadaten geändert werden. Daher würde ein Muster wie <span class="filepath"> Tysons Corner *.raw</span> Ebenen aus <span class="filepath"> Tysons Corner 050211.raw</span>, <span class="filepath"> Tysons Corner 050218.raw</span> erstellen, und so weiter, wie neue Bilder hinzugefügt werden, ohne zusätzliche Konfiguration erforderlich -Parameter für die Dateien sind ansonsten identisch. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Kachelkomprimierungsqualität </p> </td> 
   <td colname="col2"> <p>Optional für alle Quellen. Bei JPEG-Komprimierung eine Ganzzahl von 0 bis 100, die angibt, wie die Bildgröße und -qualität ausgeglichen werden sollen. (Der Standardwert ist null.) Eine höhere Anzahl führt zu einer höheren Bildqualität, erzeugt jedoch größere Bilder und längere Download-Zeiten für Data Workbench-Benutzer. </p> <p> <p>Hinweis:  Das Komprimieren von Bildern unter 70 kann zu einer Verschlechterung des Bildes führen. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Kachelkompressor </p> </td> 
   <td colname="col2"> <p>Optional für alle Quellen. Gibt an, welche Komprimierungsmethode zum Schreiben von Ausgabedateien verwendet wird. Die einzigen derzeit unterstützten Methoden sind RAWRGB (der Standard, der zu keiner Komprimierung führt) und JPEG. Verwenden Sie die JPEG-Komprimierung, um die Größe der Ebenen zu reduzieren, die bei der Profilsynchronisierung übertragen werden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Breite </p> </td> 
   <td colname="col2"> <p>Erforderlich für nicht projizierte Raw-Bitmap-Bilder. Die Breite des Quellbilds in Pixel. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Bearbeiten Sie die Parameter Quellbildspeicherort, temporärer Bildspeicher und Ebenen in , indem Sie die folgende Tabelle als Anleitung verwenden. Diese Parameter gelten für alle Topografiebildequellen, die Sie im Abschnitt [!DNL Sources] dieser Datei definieren.

<table id="table_103F02C54ED94C6C922450F5B2781CAE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Speicherort des Quellbilds </p> </td> 
   <td colname="col2"> <p>Erforderlich. Das Verzeichnis, das auf Bilder gescannt wird, um sie in Terrain-Ebenen zu übersetzen. Wenn es sich nicht um einen absoluten Pfad handelt, wird er relativ zum Installationsordner des Data Workbench-Servers interpretiert. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Temporärer Bildspeicher </p> </td> 
   <td colname="col2"> <p>Optional. Der Name eines Ordners, der für die Speicherung temporärer Dateien verwendet wird, die bei der Übersetzung von Quellbildern in Topografieebenen verwendet werden. Wenn es sich nicht um einen absoluten Pfad handelt, wird er relativ zum Installationsordner des Data Workbench-Servers interpretiert. Der Standardspeicherort ist das Verzeichnis <span class="wintitle"> Temp</span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ebenen in schreiben </p> </td> 
   <td colname="col2"> <p>Erforderlich. Das Verzeichnis, in das Topografiebeschichten ausgegeben werden. Normalerweise ist dies das Unterverzeichnis Maps eines Profilverzeichnisses, sodass die globale Visualisierung die Ebenen finden kann. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Speichern Sie die Datei, indem Sie mit der rechten Maustaste auf **[!UICONTROL (modified)]** oben im Fenster klicken und **[!UICONTROL Save]** klicken.
1. Um eine aktualisierte Datei auf dem Data Workbench-Servercomputer zu speichern, klicken Sie in der Spalte [!DNL Server Files Manager] mit der rechten Maustaste auf das Häkchen für [!DNL Terrain Images.cfg] in der Spalte [!DNL Temp] und klicken Sie dann auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]***.
