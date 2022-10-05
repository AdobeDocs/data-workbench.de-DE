---
description: Prozesskarten können so konfiguriert werden, dass sie mit jeder Kombination aus Basisdimension, Gruppendimension, Ebenendimension und Metrik verwendet werden, die für Ihre Anwendung und Ihren Datensatz sinnvoll ist.
title: Konfigurieren von Prozesskarten
uuid: e629191e-48b9-4b58-b6aa-3705ff7b387e
exl-id: 0b37e942-4596-45cc-bc31-db147626f4eb
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '449'
ht-degree: 1%

---

# Konfigurieren von Prozesskarten{#configure-a-process-map}

{{eol}}

Prozesskarten können so konfiguriert werden, dass sie mit jeder Kombination aus Basisdimension, Gruppendimension, Ebenendimension und Metrik verwendet werden, die für Ihre Anwendung und Ihren Datensatz sinnvoll ist.

Nachdem Sie eine Prozesszuordnung konfiguriert haben, wird sie mit anderen Prozesskarten im [!DNL Add Visualization menu].

1. Im [!DNL Profile Manager]klicken **[!UICONTROL Menu]** klicken **[!UICONTROL Add Visualization]** und klicken Sie dann auf den Typ des Prozesszuordnungstyps, den Sie konfigurieren möchten (2D-Metrikzuordnung, 2D-Prozesszuordnung oder 3D-Prozesszuordnung).

   Mindestens ein [!DNL *.vw] -Datei im Verzeichnis gespeichert.

1. Klicken Sie mit der rechten Maustaste auf das Häkchen für die gewünschte Datei und klicken Sie auf **[!UICONTROL Make Local]**.
1. Klicken Sie mit der rechten Maustaste auf das Häkchen für die Datei im [!DNL User] Spalte und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**.
1. Bearbeiten Sie die Parameter der Datei mithilfe der folgenden Beispieldatei und Tabelle als Handbücher:

   ```
   window = simpleBorderWindow: 
     client = processMap: 
       Traffic Metric = ref: wdata/model/metric/metric name
       center = v3d: (-0.741014, 0, 0.0639476)
       color_links = bool: true
       Map = PrefixDim: 
         Name = string: Map
         Base Dimension = ref: wdata/model/dim/base dimension name
         Element Prefixes = vector: 0 items
         Element Names = vector: 0 items
       Map Level = ref: wdata/model/dim/level dimension name
       Map Group = ref: wdata/model/dim/group dimension name
       node_label = vector<bool>: 
       node_positions = vector: 0 items
       quantify_links = int: 2
       range = double: 2.37386
       size = v3d: (430, 290, 0)
       xAxisMetric = ref: wdata/model/metric/metric name for metric map
     pos = v3d: (880, 595, 0)
     size = v3d: (430, 309, 0)
   ```

<table id="table_3F072DB1B68746C49DF9332718982EBE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Für diesen Parameter ... </th> 
   <th colname="col2" class="entry"> Geben Sie diese Informationen an... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><i>Metrikname</i> </p> </td> 
   <td colname="col2"> <p>Der Name der Metrik, deren Wert für einen bestimmten Knoten proportional zur Größe des Knotens ist. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>Name der Basisdimension</i> </p> </td> 
   <td colname="col2"> <p>Der Name der Dimension, deren Elemente als Knoten auf der Prozesszuordnung angezeigt werden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>Level dimension name</i> </p> </td> 
   <td colname="col2"> <p>Der Name der Ebene (der übergeordneten Ebene) der Basisdimension, deren Elemente Sie in die Prozesszuordnung ziehen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>Name der Gruppendimension</i> </p> </td> 
   <td colname="col2"> <p>Der Name der Dimension, der bestimmt, wie die Elemente der Ebenendimension gruppiert werden, um die Verbindungen zwischen Knoten zu bilden. Eine Verbindung zwischen zwei Knoten kann nicht mehr als ein Element einer Gruppendimension umfassen. Wenn Sie eine Auswahl basierend auf einem Knoten in einer Prozesszuordnung treffen, wählen Sie alle Elemente der Gruppendimension aus, die diesen Knoten betrifft. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>Metrikname für Metrikzuordnung</i> </p> </td> 
   <td colname="col2"> <p>Dieser Parameter gilt nur für 2D-Metrikzuordnungen. </p> <p>Der Name der Metrik, deren Wert die horizontale Position der Knoten auf der Zuordnung bestimmt. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Weitere Informationen zur Basisdimension, Gruppendimension, Ebenendimension und Metrik für eine Prozesszuordnung finden Sie unter [Prozesskarten](../../../home/c-get-started/c-analysis-vis/c-proc-maps/c-proc-maps.md#concept-880aee224404429785b733a4e80d275e).

1. Klicken Sie im Editor auf **[!UICONTROL File]** > **[!UICONTROL Save As]** , um die Datei mit einem neuen Namen zu speichern, der auf der Basisdimension basiert, d. h. *Name der Basisdimension*.vw.

   (Wenn Sie eine 2D-Metrikzuordnung konfigurieren, sollten Sie die Datei mit einem Namen speichern, der auf dem Metriknamen für die Metrikzuordnung basiert, d. h. *Metrikname für Metrikzuordnung*.vw.) Achten Sie darauf, die Datei im entsprechenden Ordner der Prozesszuordnung zu speichern.

   >[!NOTE]
   >
   >Um sicherzustellen, dass Ihre Prozesszuordnung als [!DNL *.vw] in der Datei [!DNL Save As] auf &quot;Alle Dateien&quot;setzen.

1. (Optional) Um die Änderungen allen Benutzern des Arbeitsprofils zur Verfügung zu stellen, klicken Sie auf [!DNL Profile Manager]klicken Sie mit der rechten Maustaste auf das Häkchen für die Datei im [!DNL User] Spalte und klicken Sie auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.
