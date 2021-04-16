---
description: Prozesskarten können für jede Kombination aus Basisdimension, Gruppendimension, Level-Dimension und Metrik konfiguriert werden, die für Ihre Anwendung und Ihren Datensatz sinnvoll ist.
title: Konfigurieren von Prozesskarten
uuid: e629191e-48b9-4b58-b6aa-3705ff7b387e
exl-id: 0b37e942-4596-45cc-bc31-db147626f4eb
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '449'
ht-degree: 2%

---

# Konfigurieren von Prozesskarten{#configure-a-process-map}

Prozesskarten können für jede Kombination aus Basisdimension, Gruppendimension, Level-Dimension und Metrik konfiguriert werden, die für Ihre Anwendung und Ihren Datensatz sinnvoll ist.

Nachdem Sie eine Prozesszuordnung konfiguriert haben, wird sie mit anderen Prozesszuordnungen in [!DNL Add Visualization menu] aufgeführt.

1. Klicken Sie in [!DNL Profile Manager] auf **[!UICONTROL Menu]**, klicken Sie auf **[!UICONTROL Add Visualization]** und dann auf den Typ der zu konfigurierenden Prozesszuordnung (2D-Metrikzuordnung, 2D-Prozesszuordnung oder 3D-Prozesszuordnung).

   Mindestens eine [!DNL *.vw]-Datei befindet sich im Verzeichnis.

1. Klicken Sie mit der rechten Maustaste auf das Häkchen für die gewünschte Datei und klicken Sie auf **[!UICONTROL Make Local]**.
1. Klicken Sie mit der rechten Maustaste auf das Häkchen für die Datei in der Spalte [!DNL User] und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**.
1. Bearbeiten Sie die Parameter der Datei mithilfe der folgenden Beispieldatei und Tabelle als Hilfslinien:

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
   <th colname="col1" class="entry"> Für diesen Parameter... </th> 
   <th colname="col2" class="entry"> Geben Sie diese Informationen ein... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><i>Name der Metrik</i> </p> </td> 
   <td colname="col2"> <p>Der Name der Metrik, deren Wert für eine bestimmte Node proportional zur Größe der Node ist. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>Basisdimensionsname</i> </p> </td> 
   <td colname="col2"> <p>Der Name der Dimension, deren Elemente als Knoten auf der Prozesszuordnung angezeigt werden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>Level Dimensionsname</i> </p> </td> 
   <td colname="col2"> <p>Der Name der Ebene (übergeordnet) der Basisdimension, deren Elemente Sie in die Prozesszuordnung ziehen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>Name der Gruppendimension</i> </p> </td> 
   <td colname="col2"> <p>Der Name der Dimension, die bestimmt, wie die Elemente der Dimension "level"gruppiert werden, um die Verbindungen zwischen Knoten zu bilden. Eine Verbindung zwischen zwei Knoten kann nicht mehr als ein Element einer Gruppendimension umfassen. Wenn Sie eine Auswahl basierend auf einer Node in einer Prozesszuordnung treffen, wählen Sie alle Elemente der Gruppendimension aus, an der diese Node beteiligt war. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>Metrikname für Metrikzuordnung</i> </p> </td> 
   <td colname="col2"> <p>Dieser Parameter gilt nur für 2D-Metrikzuordnungen. </p> <p>Der Name der Metrik, deren Wert die horizontale Position der Knoten auf der Map bestimmt. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Weitere Informationen zur Basisdimension, Gruppendimension, Ebenendimension und Metrik für eine Prozesszuordnung finden Sie unter [Prozesszuordnungen](../../../home/c-get-started/c-analysis-vis/c-proc-maps/c-proc-maps.md#concept-880aee224404429785b733a4e80d275e).

1. Klicken Sie in Notepad auf **[!UICONTROL File]** > **[!UICONTROL Save As]**, um die Datei mit einem neuen Namen zu speichern, der auf der Basisdimension basiert, d. h. *Basisdimensionsname*.vw.

   (Wenn Sie eine 2D-Metrikzuordnung konfigurieren, sollten Sie die Datei mit einem Namen speichern, der auf dem Metriknamen für die Metrikzuordnung basiert, d. h. *Metrikname für Metrikzuordnung*.vw.) Vergewissern Sie sich, dass Sie die Datei im entsprechenden Ordner für die Prozesszuordnung speichern.

   >[!NOTE]
   >
   >Um sicherzustellen, dass Ihre Prozesszuordnung als [!DNL *.vw]-Datei gespeichert wird, stellen Sie im Fenster [!DNL Save As] &quot;Dateityp&quot;auf Alle Dateien ein.

1. (Optional) Um die Änderungen allen Benutzern des funktionierenden Profils zur Verfügung zu stellen, klicken Sie in der Spalte [!DNL Profile Manager] mit der rechten Maustaste auf das Häkchen für die Datei und klicken Sie auf [!DNL User] und dann auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]***.
