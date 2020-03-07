---
description: Eine Bodenbildebene zeigt Geländebilder der Erde an.
solution: Analytics
title: Terrain-Bildebenen
topic: Data workbench
uuid: 17968293-1ad2-4040-a174-d33f418af9b7
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Terrain-Bildebenen{#terrain-image-layers}

Eine Bodenbildebene zeigt Geländebilder der Erde an.

[!DNL Terrain image layers] werden im Profil in einem benutzerdefinierten [!DNL Geography] Format gespeichert. Diese Bildebenen können von Adobe erstellt werden, oder der Data Workbench-Server kann Ihre vom Benutzer bereitgestellten Geländebilder in Terrain-Ebenen umwandeln, die für die weltweite Visualisierung geeignet sind.

>[!NOTE]
>
>Um mit arbeiten zu [!DNL terrain image layers]können, müssen Sie die von Adobe bereitgestellte [!DNL Terrain Images.cfg] Datei installieren.

Um eine Terrain-Bildebene zu definieren, müssen Sie über Folgendes verfügen:

* **Eine oder mehrere Terrain-Bilddateien** mit den auf der Welt anzuzeigenden Bildern.
* **Eine[!DNL Terrain Images.cfg]Datei** , die die für die Ebene(n) zu verwendende(n) Bodenbilddatei(en) angibt. Mit der [!DNL Terrain Images.cfg] Datei können Sie eine oder mehrere Quellen hinzufügen, um eine [!DNL terrain image layer]zu erstellen. Das Format Ihrer Terrain-Bilddatei bestimmt den Quelltyp, den Sie hinzufügen sollten. Die folgende Tabelle enthält Beschreibungen der verfügbaren Quellen für Terrain-Bildebenen, einschließlich der unterstützten Terrain-Bilddateiformate:

<table id="table_CFDF5E61FCCD40B29A9D35FFA42F68D1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Typ </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Unprojizierte Rohbitmap </p> </td> 
   <td colname="col2"> <p>Erstellt <span class="wintitle"> Terrain-Bildebenen</span> aus 24-Bit-RGB-Dateien ohne Kopf, die auf Längen- und Breitengrad ausgerichtet sind (nicht projiziert), wobei Nord der obere Teil des Bildes und Ost der rechte Teil ist. </p> <p>Unterstützte Bildformate: RAW </p> <p> <p>Hinweis: Diese Quelle erfordert Projektionsinformationen. Weitere Informationen zu Projektionsformaten finden Sie unter <a href="../../../../home/c-get-started/c-im-layers/c-ter-img-layers/c-proj-info-ter-imgs.md#concept-eec35baa01744895b847a02e69dad04e"> Festlegen von Projektinformationen für Terrain-Bilder</a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Allgemeines Bild, nicht projiziert </p> </td> 
   <td colname="col2"> <p>Erstellt <span class="wintitle"> Terrain-Bildebenen</span> aus 24-Bit-, Breiten- und Längengradlinformationen (nicht projiziert), wobei Nord der obere Teil des Bildes und Ost der rechte Teil ist. </p> <p>Unterstützte Bildformate: BMP, JPG, PNG, TIFF </p> <p> <p>Hinweis: Diese Quelle erfordert Projektionsinformationen. Weitere Informationen zu Projektionsformaten finden Sie unter <a href="../../../../home/c-get-started/c-im-layers/c-ter-img-layers/c-proj-info-ter-imgs.md#concept-eec35baa01744895b847a02e69dad04e"> Festlegen von Projektinformationen für Terrain-Bilder</a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Bild mit eingebetteter Projektion </p> </td> 
   <td colname="col2"> <p>Erstellt <span class="wintitle"> Terrain-Bildebenen</span> aus Bildformaten, die geografische Daten in die Bilddatei einbetten. Die Projektionsinformationen werden aus dem Bild extrahiert. </p> <p>Unterstützte Bildformate: Erdas (IMG), GeoTIFF </p> <p> <p>Hinweis: Diese Quelle erfordert in der Regel keine Projektionsinformationen, unterstützt aber bei Bedarf das Hinzufügen solcher Informationen. Weitere Informationen zu Projektionsformaten finden Sie unter <a href="../../../../home/c-get-started/c-im-layers/c-ter-img-layers/c-proj-info-ter-imgs.md#concept-eec35baa01744895b847a02e69dad04e"> Festlegen von Projektinformationen für Terrain-Bilder</a>. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

**So definieren Sie eine Terrain-Bildebene**

1. Klicken Sie in Data Workbench auf der Registerkarte **[!UICONTROL Admin]** > **[!UICONTROL Dataset and Profile]** auf die **[!UICONTROL Servers Manager]** Miniaturansicht, um den [!DNL Servers Manager] Arbeitsbereich zu öffnen.
1. Klicken Sie im [!DNL Servers Manager] Fenster mit der rechten Maustaste auf das Symbol des gewünschten Data Workbench-Servers und klicken Sie auf **[!UICONTROL Server Files]**.
1. Klicken Sie im [!DNL Server Files Manager]Fenster auf **[!UICONTROL Components]** , um den Inhalt anzuzeigen. Die [!DNL Terrain Images.cfg] Datei befindet sich in diesem Ordner.
1. Klicken Sie mit der rechten Maustaste auf das Häkchen in der Spalte Servername für [!DNL Terrain Images.cfg]und klicken Sie dann auf **[!UICONTROL Make Local]**. In der [!DNL Temp] Spalte für wird ein Häkchen angezeigt [!DNL Terrain Images.cfg].
1. Klicken Sie mit der rechten Maustaste auf das neu erstellte Häkchen in der **[!UICONTROL Temp]** Spalte und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Das [!DNL Terrain Images.cfg] Fenster wird angezeigt.
1. Klicken Sie im [!DNL Terrain Images] Fenster auf **[!UICONTROL component]** , um den Inhalt anzuzeigen.
1. Klicken Sie mit der rechten Maustaste **[!UICONTROL Sources]** > **[!UICONTROL Add new]** und wählen Sie einen der folgenden Quelltypen:

   * **[!UICONTROL Raw unprojected bitmap]**. (Nach dem Hinzufügen wird dieser Quelltyp im [!DNL Terrain Images] Fenster mit RawTerrainSource beschriftet.)

   * **[!UICONTROL General image, unprojected]**. (Nach dem Hinzufügen wird dieser Quelltyp [!DNL GDALTerrainSource] im [!DNL Terrain Images] Fenster beschriftet.)

   * **[!UICONTROL Image with embedded projection]**. (Nach dem Hinzufügen wird dieser Quelltyp [!DNL GDALTerrainSource] im [!DNL Terrain Images] Fenster beschriftet.)

1. Bearbeiten Sie die Parameter für die Quelle nach Bedarf mit der folgenden Beispieldatei und der Tabelle der Parameter als Hilfslinien.

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
   <td colname="col2"> <p>Optional für alle Quellen. Gibt die Gammakorrektur an, die auf das Quellbild angewendet werden soll. Dies kann wünschenswert sein, da Data Workbench normalerweise mit einer hohen Gammaeinstellung ausgeführt wird. Der Standardwert lautet 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Höhe </p> </td> 
   <td colname="col2"> <p>Erforderlich für unprojizierte Bitmapbilder. Die Höhe des Quellbilds in Pixel. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Projektinformationen </p> </td> 
   <td colname="col2"> <p>Erforderlich für unprojizierte Bitmapbilder und allgemeine Bilder, nicht projiziert, aber für Bilder mit eingebetteter Projektion unterstützt. Data Workbench unterstützt Prognosen zum Breiten- und Längengrad sowie Projektionen zum Transverse Mercator (TM) für Geländebilder. Das Standardprojektionsformat ist die Längen- und Breitenprojektion (LatLonProjection). </p> <p>Weitere Informationen zu Projektionsformaten finden Sie unter <a href="../../../../home/c-get-started/c-im-layers/c-ter-img-layers/c-proj-info-ter-imgs.md#concept-eec35baa01744895b847a02e69dad04e"> Festlegen von Projektinformationen für Terrain-Bilder</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Quellbild </p> </td> 
   <td colname="col2"> <p>Erforderlich für alle Quellen. Der Name der Quellbilddatei. Dies kann ein Dateiname oder ein Platzhaltermuster sein. Die Verwendung eines Musters kann nützlich sein, wenn beispielsweise Bilder für dieselbe Region zu unterschiedlichen Zeitpunkten hochgeladen werden, ohne dass die zugehörigen Metadaten geändert werden. Daher würde ein Muster wie <span class="filepath"> Tysons Corner *.raw</span> Ebenen aus <span class="filepath"> Tysons Corner 050211.raw</span>, <span class="filepath"> Tysons Corner 050218.raw</span>usw. erstellen, da neue Bilder hinzugefügt werden, ohne dass eine zusätzliche Konfiguration erforderlich wäre, wenn die Parameter für die Dateien andernfalls identisch wären. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Qualität der Kachelkomprimierung </p> </td> 
   <td colname="col2"> <p>Optional für alle Quellen. Bei der JPEG-Komprimierung eine Ganzzahl von 0 bis 100, die angibt, wie die Bildgröße und -qualität ausgeglichen werden. (Der Standardwert ist Null.) Eine höhere Anzahl führt zu einer besseren Bildqualität, erzeugt jedoch größere Bilder und längere Downloadzeiten für Data Workbench-Benutzer. </p> <p> <p>Hinweis:  Das Komprimieren von Bildern unter 70 kann zu einer Verschlechterung des Bildes führen. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Kachelkompressor </p> </td> 
   <td colname="col2"> <p>Optional für alle Quellen. Gibt an, mit welcher Komprimierungsmethode Ausgabedateien geschrieben werden. Die einzigen derzeit unterstützten Methoden sind RAWRGB (Standard, keine Komprimierung) und JPEG. Verwenden Sie die JPEG-Komprimierung, um die Größe der Ebenen zu verringern, die während der Profilsynchronisierung übertragen werden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Breite </p> </td> 
   <td colname="col2"> <p>Erforderlich für unprojizierte Bitmapbilder. Die Breite des Quellbilds in Pixel. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Bearbeiten Sie die Parameter &quot;Quellbildposition&quot;, &quot;Temporärer Bildspeicher&quot;und &quot;Ebenen in Parameter schreiben&quot;mithilfe der folgenden Tabelle als Anleitung. Diese Parameter gelten für alle Terrain-Bildquellen, die Sie im Abschnitt [!DNL Sources] dieser Datei definieren.

<table id="table_103F02C54ED94C6C922450F5B2781CAE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Quellbildposition </p> </td> 
   <td colname="col2"> <p>Erforderlich. Das Verzeichnis, das auf Bilder überprüft wird, die in Terrain-Ebenen übersetzt werden sollen. Wenn es sich nicht um einen absoluten Pfad handelt, wird er relativ zum Installationsordner des Data Workbench-Servers interpretiert. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Temporärer Bildspeicher </p> </td> 
   <td colname="col2"> <p>Optional. Der Name eines Ordners, der für die Speicherung von temporären Dateien verwendet wird, die bei der Übersetzung von Quellbildern in Terrain-Ebenen verwendet werden. Wenn es sich nicht um einen absoluten Pfad handelt, wird er relativ zum Installationsordner des Data Workbench-Servers interpretiert. Der Standardspeicherort ist der <span class="wintitle"> Temp</span> -Ordner. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ebenen schreiben in </p> </td> 
   <td colname="col2"> <p>Erforderlich. Der Ordner, in dem Geländeschichten ausgegeben werden. Normalerweise ist dies der Unterordner "Maps"eines Profilverzeichnisses, sodass die globale Visualisierung die Ebenen finden kann. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Speichern Sie die Datei, indem Sie mit der rechten Maustaste **[!UICONTROL (modified)]** am oberen Rand des Fensters klicken und auf **[!UICONTROL Save]**.
1. Um eine aktualisierte Datei auf dem Computer des Data Workbench-Servers zu speichern, [!DNL Server Files Manager]klicken Sie mit der rechten Maustaste auf das Häkchen [!DNL Terrain Images.cfg] in der [!DNL Temp] Spalte und dann auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

