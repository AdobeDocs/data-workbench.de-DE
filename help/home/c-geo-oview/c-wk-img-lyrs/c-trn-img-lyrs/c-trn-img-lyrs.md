---
description: In Data Workbench zeigt eine Terrain-Bildebene Terrain-Bilder der Erde an.
title: Arbeiten mit Topografiebildebenen
uuid: 2f23a2c8-f551-4b84-bd87-5d7053910ab3
exl-id: 22026b41-4e12-4247-b019-461ae223bd07
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1021'
ht-degree: 2%

---

# Arbeiten mit Topografiebildebenen{#working-with-terrain-image-layers}

In Data Workbench zeigt eine Terrain-Bildebene Terrain-Bilder der Erde an.

Terrain-Bildebenen werden im Profil [!DNL Geography] in einem benutzerdefinierten Format gespeichert. Diese Bildebenen können durch Adobe erzeugt werden, oder der Data Workbench-Server kann Ihre vom Benutzer bereitgestellten Geländebilder in Terrain-Ebenen umwandeln, die für die weltweite Visualisierung geeignet sind.

>[!NOTE]
>
>Um mit Terrain-Bildebenen zu arbeiten, müssen Sie die [!DNL Terrain Images.cfg]-Datei installieren, die von der Adobe bereitgestellt wird. Installationsanweisungen finden Sie unter [Data Workbench-Geografie installieren](../../../../home/c-geo-oview/c-inst-geo/c-inst-geo.md).

Um eine Terrain-Bildebene zu definieren, müssen Sie über Folgendes verfügen:

* **Eine oder mehrere** Geländebilder mit den Bildern, die auf der Welt angezeigt werden sollen.
* **Eine Datei &quot;Terrain Images.** cfgfile&quot;, die die für die Ebene(n) zu verwendende(n) Bodenbilddatei(en) angibt. Mit der Datei [!DNL Terrain Images.cfg] können Sie eine oder mehrere Quellen hinzufügen, um eine Terrain-Bildebene zu erstellen. Das Format Ihrer Terrain-Bilddatei bestimmt den Quelltyp, den Sie hinzufügen sollten. Die folgende Tabelle enthält Beschreibungen der verfügbaren Quellen für Terrain-Bildebenen, einschließlich der unterstützten Terrain-Bilddateiformate:

<table id="table_BF8D5933BFBE45039BD164C258D3B450"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Typ </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Unprojizierte Rohbitmap </td> 
   <td colname="col2"> <p>Erstellt Terrain-Bildebenen aus 24-Bit-RGB-Dateien ohne Kopf, die auf Längen- und Breitengrad ausgerichtet sind (nicht projiziert), wobei Nord der obere Teil des Bildes und Ost der rechte Teil ist. </p> <p>Unterstützte Bildformate: RAW </p> <p> <p>Hinweis: Diese Quelle erfordert Projektionsinformationen. Weitere Informationen zu Projektionsformaten finden Sie unter <a href="../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-proj-info-trn-imgs.md#concept-69b0c668038f4de9bf430a3a468a2abd"> Projektionsinformationen für Terrain-Bilder angeben</a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Allgemeines Bild, nicht projiziert </td> 
   <td colname="col2"> <p>Erstellt Terrain-Bildebenen aus 24-Bit-, Breiten- und Längengradlinformationen (nicht projiziert), wobei Nord der obere Teil des Bildes und Ost der rechte Teil ist. </p> <p>Unterstützte Bildformate: BMP, JPG, PNG, TIFF </p> <p> <p>Hinweis: Diese Quelle erfordert Projektionsinformationen. Weitere Informationen zu Projektionsformaten finden Sie unter <a href="../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-proj-info-trn-imgs.md#concept-69b0c668038f4de9bf430a3a468a2abd"> Projektionsinformationen für Terrain-Bilder angeben</a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Bild mit eingebetteter Projektion </td> 
   <td colname="col2"> <p>Erstellt Terrain-Bildebenen aus Bildformaten, die geografische Daten in die Bilddatei einbetten. Die Projektionsinformationen werden aus dem Bild extrahiert. </p> <p>Unterstützte Bildformate: Erdas (IMG), GeoTIFF </p> <p> <p>Hinweis: Diese Quelle erfordert in der Regel keine Projektionsinformationen, unterstützt aber bei Bedarf das Hinzufügen solcher Informationen. Weitere Informationen zu Projektionsformaten finden Sie unter <a href="../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-proj-info-trn-imgs.md#concept-69b0c668038f4de9bf430a3a468a2abd"> Projektionsinformationen für Terrain-Bilder angeben</a>. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

**So definieren Sie eine Terrain-Bildebene**

1. Klicken Sie in Data Workbench auf der Registerkarte [!DNL Admin] > [!DNL Dataset and Profile] auf die Miniaturansicht von **[!UICONTROL Servers Manager]**, um den Arbeitsbereich [!DNL Servers Manager] zu öffnen.

1. Klicken Sie im Fenster [!DNL Servers Manager] mit der rechten Maustaste auf das Symbol des gewünschten Data Workbench-Servers und klicken Sie auf **[!UICONTROL Server Files]**.

1. Klicken Sie in [!DNL Server Files Manager] auf **[!UICONTROL Components]**, um den Inhalt Ansicht. Die Datei [!DNL Terrain Images.cfg] befindet sich in diesem Verzeichnis.

1. Klicken Sie mit der rechten Maustaste auf das Häkchen in der Spalte Servername für [!DNL Terrain Images.cfg] und klicken Sie dann auf **[!UICONTROL Make Local]**. In der Spalte [!DNL Temp] für [!DNL Terrain Images.cfg.] wird ein Häkchen angezeigt.

1. Klicken Sie mit der rechten Maustaste auf das neu erstellte Häkchen in der Spalte [!DNL Temp] und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Das Fenster [!DNL Terrain Images.cfg]wird angezeigt.

1. Klicken Sie im Fenster [!DNL Terrain Images] auf **[!UICONTROL component]**, um den Inhalt Ansicht.

1. Klicken Sie mit der rechten Maustaste auf **[!UICONTROL Sources]** > **[!UICONTROL Add new]** und wählen Sie einen der folgenden Quelltypen:

   * **[!UICONTROL Raw unprojected bitmap]**. (Nach dem Hinzufügen ist dieser Quelltyp im Fenster [!DNL Terrain Images] mit &quot;RawTerrainSource&quot;beschriftet.)

   * **[!UICONTROL General image, unprojected]**. (Nach dem Hinzufügen wird dieser Quelltyp im Fenster [!DNL Terrain Images] mit der Bezeichnung GDALTerrainSource gekennzeichnet.)

   * **[!UICONTROL Image with embedded projection]**. (Nach dem Hinzufügen wird dieser Quelltyp im Fenster [!DNL Terrain Images] mit der Bezeichnung GDALTerrainSource gekennzeichnet.)

1. Bearbeiten Sie die Parameter für die Quelle nach Bedarf mit der folgenden Beispieldatei und der Tabelle der Parameter als Hilfslinien.

   ![](assets/cfg_TerrainImages_ALL.png)

<table id="table_83171CB58F8B4816BCCA9BFFD5ECD92A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Gamma </td> 
   <td colname="col2"> Optional für alle Quellen. Gibt die Gammakorrektur an, die auf das Quellbild angewendet werden soll. Dies kann wünschenswert sein, da Data Workbench normalerweise mit einer hohen Gammaeinstellung ausgeführt wird. Der Standardwert lautet 1. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Höhe </td> 
   <td colname="col2"> Erforderlich für unprojizierte Bitmapbilder. Die Höhe des Quellbilds in Pixel. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Projektinformationen </td> 
   <td colname="col2"> <p>Erforderlich für unprojizierte Bitmapbilder und allgemeine Bilder, nicht projiziert, aber für Bilder mit eingebetteter Projektion unterstützt. Data Workbench<span class="wintitle"> Geografie</span> unterstützt Breitengradprojektionen und Transverse Mercator (TM)-Projektionen für Geländebilder. Das Standardprojektionsformat ist die Längen- und Breitenprojektion (LatLonProjection). </p> <p>Weitere Informationen zu Projektionsformaten finden Sie unter <a href="../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-proj-info-trn-imgs.md#concept-69b0c668038f4de9bf430a3a468a2abd"> Projektionsinformationen für Terrain-Bilder angeben</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Quellbild </td> 
   <td colname="col2">Erforderlich für alle Quellen. Der Name der Quellbilddatei. Dies kann ein Dateiname oder ein Platzhaltermuster sein. Die Verwendung eines Musters kann nützlich sein, wenn beispielsweise Bilder für dieselbe Region zu unterschiedlichen Zeitpunkten hochgeladen werden, ohne dass die zugehörigen Metadaten geändert werden. Daher würde ein Muster wie "<span class="filepath"> Tysons Corner *.raw</span>"Ebenen aus <span class="filepath"> Tysons Corner 050211.raw</span>, <span class="filepath"> Tysons Corner 050218.raw</span> erstellen usw., da neue Bilder hinzugefügt werden, ohne zusätzliche Konfiguration wenn die Parameter für die Dateien anders identisch sind. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Qualität der Kachelkomprimierung </td> 
   <td colname="col2"> <p>Optional für alle Quellen. Bei der JPEG-Komprimierung eine Ganzzahl von 0 bis 100, die angibt, wie die Bildgröße und -qualität ausgeglichen werden. (Der Standardwert ist Null.) Eine höhere Anzahl führt zu einer besseren Bildqualität, erzeugt jedoch größere Bilder und längere Downloadzeiten für Benutzer von Data Workbench. </p> <p>Das Komprimieren von Bildern unter 70 kann zu einer Verschlechterung des Bildes führen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Kachelkompressor </td> 
   <td colname="col2"> Optional für alle Quellen. Gibt an, mit welcher Komprimierungsmethode Ausgabedateien geschrieben werden. Die einzigen derzeit unterstützten Methoden sind RAWRGB (Standard, keine Komprimierung) und JPEG. Verwenden Sie die JPEG-Komprimierung, um die Größe der Ebenen zu verringern, die während der Synchronisierung des Profils übertragen werden. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Breite </td> 
   <td colname="col2"> Erforderlich für unprojizierte Bitmapbilder. Die Breite des Quellbilds in Pixel. </td> 
  </tr> 
 </tbody> 
</table>

1. Bearbeiten Sie die Parameter &quot;Quellbildposition&quot;, &quot;Temp-Datenspeicherung&quot;und &quot;Ebenen in Parameter schreiben&quot;mithilfe der folgenden Tabelle als Anleitung. Diese Parameter gelten für alle Terrain-Bildquellen, die Sie im Abschnitt &quot;Quellen&quot;dieser Datei definieren.

   | Parameter | Beschreibung |
   |---|---|
   | Quellbildposition | Erforderlich. Das Verzeichnis, das auf Bilder überprüft wird, die in Terrain-Ebenen übersetzt werden sollen. Wenn es sich nicht um einen absoluten Pfad handelt, wird er relativ zum Installationsordner des Data Workbench-Servers interpretiert. |
   | Datenspeicherung des Temp-Bildes | Optional. Der Name eines Ordners, der für die Datenspeicherung von temporären Dateien verwendet wird, die bei der Übersetzung von Quellbildern in Terrain-Ebenen verwendet werden. Wenn es sich nicht um einen absoluten Pfad handelt, wird er relativ zum Installationsordner des Data Workbench-Servers interpretiert. Der Standardspeicherort ist der temporäre Ordner. |
   | Ebenen schreiben in | Erforderlich. Der Ordner, in dem Geländeschichten ausgegeben werden. Normalerweise ist dies der Unterordner &quot;Maps&quot;eines Profil-Ordners, sodass die Visualisierung [!DNL Globe] die Ebenen finden kann. |

1. Speichern Sie die Datei, indem Sie mit der rechten Maustaste auf **[!UICONTROL (modified)]** oben im Fenster klicken und auf **[!UICONTROL Save]** klicken.

1. Um die aktualisierte Datei auf dem Datenbasis-Server zu speichern, klicken Sie in der Spalte [!DNL Server Files Manager] mit der rechten Maustaste auf das Häkchen für [!DNL Terrain Images.cfg] in der Spalte [!DNL Temp] und klicken Sie dann auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]***.
