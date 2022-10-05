---
description: Eine Topografiebildebene zeigt Topografiebilder der Erde an.
title: Topografiebildebenen
uuid: 17968293-1ad2-4040-a174-d33f418af9b7
exl-id: 754211a7-0b1f-4353-86f8-9c634d70cd83
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '992'
ht-degree: 2%

---

# Topografiebildebenen{#terrain-image-layers}

{{eol}}

Eine Topografiebildebene zeigt Topografiebilder der Erde an.

[!DNL Terrain image layers] werden im [!DNL Geography] Profil in einem benutzerdefinierten Format. Diese Bildebenen können von Adobe erstellt werden, oder der Data Workbench-Server kann Ihre vom Benutzer bereitgestellten Topografiebilder in Topografiebilder umwandeln, die für die weltweite Visualisierung geeignet sind.

>[!NOTE]
>
>So arbeiten Sie mit [!DNL terrain image layers], müssen Sie die [!DNL Terrain Images.cfg] -Datei, die von Adobe bereitgestellt wird.

Um eine Topografiebildebene zu definieren, müssen Sie über Folgendes verfügen:

* **Eine oder mehrere Topografiebildedateien** mit den weltweit anzuzeigenden Bildern.
* **A [!DNL Terrain Images.cfg] file** , der die für die Ebene(n) zu verwendenden Topografiebildedateien angibt. Die [!DNL Terrain Images.cfg] -Datei können Sie eine oder mehrere Quellen hinzufügen, um eine [!DNL terrain image layer]. Das Format Ihrer Topografiebilddatei bestimmt den Quelltyp, den Sie hinzufügen sollten. Die folgende Tabelle enthält Beschreibungen der verfügbaren Quellen für Topografiebildebenen, einschließlich der unterstützten Dateiformate für Topografiebilder:

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
   <td colname="col2"> <p>Erstellt <span class="wintitle"> Topografiebildebenen</span> aus 24-Bit-Kopfzeilen-RGB-Dateien, die auf Längen- und Breitengrad ausgerichtet sind (nicht projiziert), wobei Nord der obere Bereich des Bildes und Ost der rechte ist. </p> <p>Unterstützte Bildformate: RAW </p> <p> <p>Hinweis: Diese Quelle erfordert Projektionsinformationen. Informationen zu Projektionsformaten finden Sie unter <a href="../../../../home/c-get-started/c-im-layers/c-ter-img-layers/c-proj-info-ter-imgs.md#concept-eec35baa01744895b847a02e69dad04e"> Festlegen von Projektionsinformationen für Topografiebilder</a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Allgemeines Bild, nicht projiziert </p> </td> 
   <td colname="col2"> <p>Erstellt <span class="wintitle"> Topografiebildebenen</span> von 24-Bit, Breitengrad-Längengrad ausgerichtet (nicht projiziert) Bildformate, wobei Nord der obere Bereich des Bildes und Ost der rechte ist. </p> <p>Unterstützte Bildformate: BMP, JPG, PNG, TIFF </p> <p> <p>Hinweis: Diese Quelle erfordert Projektionsinformationen. Informationen zu Projektionsformaten finden Sie unter <a href="../../../../home/c-get-started/c-im-layers/c-ter-img-layers/c-proj-info-ter-imgs.md#concept-eec35baa01744895b847a02e69dad04e"> Festlegen von Projektionsinformationen für Topografiebilder</a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Bild mit eingebetteter Projektion </p> </td> 
   <td colname="col2"> <p>Erstellt <span class="wintitle"> Topografiebildebenen</span> aus Bildformaten, die geodätische Daten in die Bilddatei einbetten. Die Projektionsinformationen werden aus dem Bild extrahiert. </p> <p>Unterstützte Bildformate: Erdas (IMG), GeoTIFF </p> <p> <p>Hinweis: Diese Quelle benötigt in der Regel keine Projektionsinformationen, unterstützt jedoch bei Bedarf das Hinzufügen solcher Informationen. Informationen zu Projektionsformaten finden Sie unter <a href="../../../../home/c-get-started/c-im-layers/c-ter-img-layers/c-proj-info-ter-imgs.md#concept-eec35baa01744895b847a02e69dad04e"> Festlegen von Projektionsinformationen für Topografiebilder</a>. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

**So definieren Sie eine Topografiebildebene**

1. In Data Workbench auf der **[!UICONTROL Admin]** > **[!UICONTROL Dataset and Profile]** klicken Sie auf die **[!UICONTROL Servers Manager]** Miniaturansicht zum Öffnen der [!DNL Servers Manager] Arbeitsbereich.
1. Innerhalb der [!DNL Servers Manager] -Fenster, klicken Sie mit der rechten Maustaste auf das Symbol des gewünschten Data Workbench-Servers und klicken Sie auf **[!UICONTROL Server Files]**.
1. Im [!DNL Server Files Manager]klicken **[!UICONTROL Components]** , um den Inhalt anzuzeigen. Die [!DNL Terrain Images.cfg] -Datei befindet sich in diesem Verzeichnis.
1. Klicken Sie mit der rechten Maustaste auf das Häkchen in der Spalte &quot;Servername&quot;für [!DNL Terrain Images.cfg]Klicken Sie auf **[!UICONTROL Make Local]**. Ein Häkchen wird im [!DNL Temp] Spalte für [!DNL Terrain Images.cfg].
1. Klicken Sie mit der rechten Maustaste auf das neu erstellte Häkchen im **[!UICONTROL Temp]** Spalte und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Die [!DNL Terrain Images.cfg] angezeigt.
1. Im [!DNL Terrain Images] Fenster, klicken Sie auf **[!UICONTROL component]** , um den Inhalt anzuzeigen.
1. Rechtsklick **[!UICONTROL Sources]** > **[!UICONTROL Add new]** und wählen Sie einen der folgenden Quelltypen:

   * **[!UICONTROL Raw unprojected bitmap]**. (Nach dem Hinzufügen wird dieser Quelltyp im [!DNL Terrain Images] Fenster.)

   * **[!UICONTROL General image, unprojected]**. (Nach dem Hinzufügen wird dieser Quelltyp mit einer Beschriftung versehen [!DNL GDALTerrainSource] im [!DNL Terrain Images] Fenster.)

   * **[!UICONTROL Image with embedded projection]**. (Nach dem Hinzufügen wird dieser Quelltyp mit einer Beschriftung versehen [!DNL GDALTerrainSource] im [!DNL Terrain Images] Fenster.)

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
   <td colname="col2"> <p>Erforderlich für nicht projizierte Raw-Bilder und allgemeine Bilder, nicht projiziert, aber für Bilder mit eingebetteter Projektion unterstützt. Data Workbench unterstützt Breiten- und Längengrad-Projektionen und Projektionen des Transverse Mercator (TM) für Topografiebildebenen. Das standardmäßige Projektionsformat ist die Breiten-/Längengrad-Projektion (LatLonProjection). </p> <p>Informationen zu Projektionsformaten finden Sie unter <a href="../../../../home/c-get-started/c-im-layers/c-ter-img-layers/c-proj-info-ter-imgs.md#concept-eec35baa01744895b847a02e69dad04e"> Festlegen von Projektionsinformationen für Topografiebilder</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Quellbild </p> </td> 
   <td colname="col2"> <p>Erforderlich für alle Quellen. Der Name der Quellbilddatei. Dies kann ein Dateiname oder ein Platzhaltermuster sein. Die Verwendung eines Musters kann nützlich sein, wenn beispielsweise Bilder für denselben Bereich zu unterschiedlichen Daten hochgeladen werden, ohne dass die zugehörigen Metadaten geändert werden. Daher ist ein Muster wie <span class="filepath"> Tysons Corner *.raw</span> erstellt Ebenen aus <span class="filepath"> Tysons Corner 050211.raw</span>, <span class="filepath"> Tysons Corner 050218.raw</span>und so weiter, wenn neue Bilder hinzugefügt werden, ohne zusätzliche Konfiguration erforderlich, wenn die Parameter für die Dateien anders identisch sind. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Kachelkomprimierungsqualität </p> </td> 
   <td colname="col2"> <p>Optional für alle Quellen. Für die JPEG-Komprimierung eine Ganzzahl von 0 bis 100, die angibt, wie Bildgröße und -qualität ausgeglichen werden. (Der Standardwert ist null.) Eine höhere Anzahl führt zu einer höheren Bildqualität, erzeugt jedoch größere Bilder und längere Download-Zeiten für Data Workbench-Benutzer. </p> <p> <p>Hinweis: Das Komprimieren von Bildern unter 70 kann zu einer Verschlechterung des Bildes führen. </p> </p> </td> 
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

1. Bearbeiten Sie die Parameter Quellbildspeicherort, temporärer Bildspeicher und Ebenen in , indem Sie die folgende Tabelle als Anleitung verwenden. Diese Parameter gelten für alle Topografiebildequellen, die Sie in der Variablen [!DNL Sources] -Abschnitt dieser Datei.

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
   <td colname="col2"> <p>Optional. Der Name eines Ordners, der für die Speicherung temporärer Dateien verwendet wird, die bei der Übersetzung von Quellbildern in Topografieebenen verwendet werden. Wenn es sich nicht um einen absoluten Pfad handelt, wird er relativ zum Installationsordner des Data Workbench-Servers interpretiert. Der Standardspeicherort ist die <span class="wintitle"> Temp</span> Verzeichnis. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ebenen in schreiben </p> </td> 
   <td colname="col2"> <p>Erforderlich. Das Verzeichnis, in das Topografiebeschichten ausgegeben werden. Normalerweise ist dies das Unterverzeichnis Maps eines Profilverzeichnisses, sodass die globale Visualisierung die Ebenen finden kann. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Speichern Sie die Datei durch Rechtsklick **[!UICONTROL (modified)]** oben im Fenster und klicken Sie auf **[!UICONTROL Save]**.
1. Um eine aktualisierte Datei auf dem Data Workbench-Server-Computer zu speichern, verwenden Sie die [!DNL Server Files Manager]klicken Sie mit der rechten Maustaste auf das Häkchen für [!DNL Terrain Images.cfg] im [!DNL Temp] und klicken Sie auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.
