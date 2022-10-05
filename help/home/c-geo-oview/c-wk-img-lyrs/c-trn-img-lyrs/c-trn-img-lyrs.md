---
description: In Data Workbench zeigt eine Topografiebildebene Topografiebilder der Erde an.
title: Arbeiten mit Topografiebildebenen
uuid: 2f23a2c8-f551-4b84-bd87-5d7053910ab3
exl-id: 22026b41-4e12-4247-b019-461ae223bd07
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1021'
ht-degree: 2%

---

# Arbeiten mit Topografiebildebenen{#working-with-terrain-image-layers}

{{eol}}

In Data Workbench zeigt eine Topografiebildebene Topografiebilder der Erde an.

Topografiebildebenen werden in [!DNL Geography] Profil in einem benutzerdefinierten Format. Diese Bildebenen können von Adobe generiert werden, oder der Data Workbench-Server kann Ihre vom Benutzer bereitgestellten Topografiebilder in Topografiebilder umwandeln, die für die weltweite Visualisierung geeignet sind.

>[!NOTE]
>
>Um mit Topografiebildebenen zu arbeiten, müssen Sie die [!DNL Terrain Images.cfg] -Datei, die von Adobe bereitgestellt wird. Installationsanweisungen finden Sie unter [Installieren von Data Workbench Geography](../../../../home/c-geo-oview/c-inst-geo/c-inst-geo.md).

Um eine Topografiebildebene zu definieren, müssen Sie über Folgendes verfügen:

* **Eine oder mehrere Topografiebildedateien** mit den weltweit anzuzeigenden Bildern.
* **Ein Topografiebilder.cfg** -Datei, die die für die Ebene(en) zu verwendenden Topografiebildedateien angibt. Die [!DNL Terrain Images.cfg] -Datei können Sie eine oder mehrere Quellen hinzufügen, um eine Topografiebildebene zu erstellen. Das Format Ihrer Topografiebilddatei bestimmt den Quelltyp, den Sie hinzufügen sollten. Die folgende Tabelle enthält Beschreibungen der verfügbaren Quellen für Topografiebildebenen, einschließlich der unterstützten Dateiformate für Topografiebilder:

<table id="table_BF8D5933BFBE45039BD164C258D3B450"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Typ </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Unprognostizierte Rohbitmap </td> 
   <td colname="col2"> <p>Erstellt Topografiebildebenen aus 24-Bit-RGB-Dateien ohne Kopfzeilen, die auf Längen- und Breitengrad ausgerichtet sind (nicht projiziert), wobei Nord der obere Bereich des Bildes und Ost der rechte Bereich ist. </p> <p>Unterstützte Bildformate: RAW </p> <p> <p>Hinweis: Diese Quelle erfordert Projektionsinformationen. Informationen zu Projektionsformaten finden Sie unter <a href="../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-proj-info-trn-imgs.md#concept-69b0c668038f4de9bf430a3a468a2abd"> Festlegen von Projektionsinformationen für Topografiebilder</a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Allgemeines Bild, nicht projiziert </td> 
   <td colname="col2"> <p>Erstellt Topografiebildebenen aus 24-Bit-, Breitengrad- und Längengrad-Bildformaten, die auf (nicht projizierten) Bildformaten ausgerichtet sind, wobei Nord oben auf dem Bild und Ost rechts steht. </p> <p>Unterstützte Bildformate: BMP, JPG, PNG, TIFF </p> <p> <p>Hinweis: Diese Quelle erfordert Projektionsinformationen. Informationen zu Projektionsformaten finden Sie unter <a href="../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-proj-info-trn-imgs.md#concept-69b0c668038f4de9bf430a3a468a2abd"> Festlegen von Projektionsinformationen für Topografiebilder</a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Bild mit eingebetteter Projektion </td> 
   <td colname="col2"> <p>Erstellt Topografiebildebenen aus Bildformaten, die geografische Daten in die Bilddatei einbetten. Die Projektionsinformationen werden aus dem Bild extrahiert. </p> <p>Unterstützte Bildformate: Erdas (IMG), GeoTIFF </p> <p> <p>Hinweis: Diese Quelle benötigt in der Regel keine Projektionsinformationen, unterstützt jedoch bei Bedarf das Hinzufügen solcher Informationen. Informationen zu Projektionsformaten finden Sie unter <a href="../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-proj-info-trn-imgs.md#concept-69b0c668038f4de9bf430a3a468a2abd"> Festlegen von Projektionsinformationen für Topografiebilder</a>. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

**So definieren Sie eine Topografiebildebene**

1. In Data Workbench auf der [!DNL Admin] > [!DNL Dataset and Profile] klicken Sie auf die **[!UICONTROL Servers Manager]** Miniaturansicht zum Öffnen der [!DNL Servers Manager] Arbeitsbereich.

1. Innerhalb der [!DNL Servers Manager] ein Fenster öffnen, klicken Sie mit der rechten Maustaste auf das Symbol des gewünschten Data Workbench-Servers und klicken Sie auf **[!UICONTROL Server Files]**.

1. Im [!DNL Server Files Manager]klicken **[!UICONTROL Components]** , um den Inhalt anzuzeigen. Die [!DNL Terrain Images.cfg] -Datei befindet sich in diesem Verzeichnis.

1. Klicken Sie mit der rechten Maustaste auf das Häkchen in der Spalte &quot;Servername&quot;für [!DNL Terrain Images.cfg]Klicken Sie auf **[!UICONTROL Make Local]**. Ein Häkchen wird im [!DNL Temp] Spalte für [!DNL Terrain Images.cfg.]

1. Klicken Sie mit der rechten Maustaste auf das neu erstellte Häkchen im [!DNL Temp] Spalte und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Die [!DNL Terrain Images.cfg]angezeigt.

1. Im [!DNL Terrain Images] Fenster, klicken Sie auf **[!UICONTROL component]** , um den Inhalt anzuzeigen.

1. Rechtsklick **[!UICONTROL Sources]** > **[!UICONTROL Add new]** und wählen Sie einen der folgenden Quelltypen:

   * **[!UICONTROL Raw unprojected bitmap]**. (Nach dem Hinzufügen wird dieser Quelltyp im [!DNL Terrain Images] Fenster.)

   * **[!UICONTROL General image, unprojected]**. (Nach dem Hinzufügen wird dieser Quelltyp im [!DNL Terrain Images] Fenster.)

   * **[!UICONTROL Image with embedded projection]**. (Nach dem Hinzufügen wird dieser Quelltyp im [!DNL Terrain Images] Fenster.)

1. Bearbeiten Sie die Parameter für die Quelle nach Bedarf mithilfe der folgenden Beispieldatei und der Tabelle der Parameter als Anleitungen.

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
   <td colname="col2"> Erforderlich für nicht projizierte Raw-Bitmap-Bilder. Die Höhe des Quellbilds in Pixel. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Projektinformationen </td> 
   <td colname="col2"> <p>Erforderlich für nicht projizierte Raw-Bilder und allgemeine Bilder, nicht projiziert, aber für Bilder mit eingebetteter Projektion unterstützt. Data Workbench<span class="wintitle"> Geografie</span> unterstützt Breiten- und Längengrad-Projektionen sowie Projektionen des Transverse Mercator (TM) für Topografiebildebenen. Das standardmäßige Projektionsformat ist die Breiten-/Längengrad-Projektion (LatLonProjection). </p> <p>Informationen zu Projektionsformaten finden Sie unter <a href="../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-proj-info-trn-imgs.md#concept-69b0c668038f4de9bf430a3a468a2abd"> Festlegen von Projektionsinformationen für Topografiebilder</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Quellbild </td> 
   <td colname="col2">Erforderlich für alle Quellen. Der Name der Quellbilddatei. Dies kann ein Dateiname oder ein Platzhaltermuster sein. Die Verwendung eines Musters kann nützlich sein, wenn beispielsweise Bilder für denselben Bereich zu unterschiedlichen Daten hochgeladen werden, ohne dass die zugehörigen Metadaten geändert werden. Daher ist ein Muster wie "<span class="filepath"> Tysons Corner *.raw</span>" erstellt Ebenen aus <span class="filepath"> Tysons Corner 050211.raw</span>, <span class="filepath"> Tysons Corner 050218.raw</span>und so weiter, wenn neue Bilder hinzugefügt werden, ohne zusätzliche Konfiguration erforderlich, wenn die Parameter für die Dateien anders identisch sind. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Kachelkomprimierungsqualität </td> 
   <td colname="col2"> <p>Optional für alle Quellen. Für die JPEG-Komprimierung eine Ganzzahl von 0 bis 100, die angibt, wie Bildgröße und -qualität ausgeglichen werden. (Der Standardwert ist null.) Eine höhere Anzahl führt zu einer höheren Bildqualität, erzeugt jedoch größere Bilder und längere Download-Zeiten für Data Workbench-Benutzer. </p> <p>Das Komprimieren von Bildern unter 70 kann zu einer Verschlechterung des Bildes führen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Kachelkompressor </td> 
   <td colname="col2"> Optional für alle Quellen. Gibt an, welche Komprimierungsmethode zum Schreiben von Ausgabedateien verwendet wird. Die einzigen derzeit unterstützten Methoden sind RAWRGB (der Standard, der zu keiner Komprimierung führt) und JPEG. Verwenden Sie die JPEG-Komprimierung, um die Größe der Ebenen zu reduzieren, die bei der Profilsynchronisierung übertragen werden. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Breite </td> 
   <td colname="col2"> Erforderlich für nicht projizierte Raw-Bitmap-Bilder. Die Breite des Quellbilds in Pixel. </td> 
  </tr> 
 </tbody> 
</table>

1. Bearbeiten Sie die Parameter Quellbildspeicherort, temporärer Bildspeicher und Ebenen in , indem Sie die folgende Tabelle als Anleitung verwenden. Diese Parameter gelten für alle Topografiebildequellen, die Sie im Abschnitt Quellen dieser Datei definieren.

   | Parameter | Beschreibung |
   |---|---|
   | Speicherort des Quellbilds | Erforderlich. Das Verzeichnis, das auf Bilder gescannt wird, um sie in Terrain-Ebenen zu übersetzen. Wenn es sich nicht um einen absoluten Pfad handelt, wird er relativ zum Installationsordner des Data Workbench-Servers interpretiert. |
   | Temporärer Bildspeicher | Optional. Der Name eines Ordners, der für die Speicherung temporärer Dateien verwendet wird, die bei der Übersetzung von Quellbildern in Topografieebenen verwendet werden. Wenn es sich nicht um einen absoluten Pfad handelt, wird er relativ zum Installationsordner des Data Workbench-Servers interpretiert. Der Standardspeicherort ist der Temp-Ordner. |
   | Ebenen in schreiben | Erforderlich. Das Verzeichnis, in das Topografiebeschichten ausgegeben werden. Normalerweise ist dies das Unterverzeichnis Maps eines Profilordners, sodass die Variable [!DNL Globe] Visualisierung kann die Ebenen finden. |

1. Speichern Sie die Datei durch Rechtsklick **[!UICONTROL (modified)]** oben im Fenster und klicken Sie auf **[!UICONTROL Save]**.

1. Zum Speichern der aktualisierten Datei auf dem Data Workbench-Servercomputer im [!DNL Server Files Manager]klicken Sie mit der rechten Maustaste auf das Häkchen für [!DNL Terrain Images.cfg] im [!DNL Temp] und klicken Sie auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.
