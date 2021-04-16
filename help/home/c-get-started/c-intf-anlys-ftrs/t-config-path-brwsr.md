---
description: Pfadbrowser können so konfiguriert werden, dass sie mit einer beliebigen Kombination aus Basisdimension, Gruppendimension, Ebenendimension und Metrik arbeiten, die für Ihre Anwendung und Ihren Datensatz sinnvoll ist.
title: Konfigurieren von Pfad-Browsern
uuid: 1ba3fb6e-b76f-428f-b6ec-077669c3b305
exl-id: be6a68f7-e3e3-4207-a112-3a4fdd5c5f57
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '422'
ht-degree: 2%

---

# Konfigurieren von Pfad-Browsern{#configure-a-path-browser}

Pfadbrowser können so konfiguriert werden, dass sie mit einer beliebigen Kombination aus Basisdimension, Gruppendimension, Ebenendimension und Metrik arbeiten, die für Ihre Anwendung und Ihren Datensatz sinnvoll ist.

Nachdem Sie einen Pfadbrowser konfiguriert haben, wird er mit anderen Pfadbrowsern im Menü [!DNL Add Visualization] aufgeführt.

1. Klicken Sie in [!DNL Profile Manager] auf **[!UICONTROL Menu]** und dann auf **[!UICONTROL Add Visualization]** und **[!UICONTROL Path Browser]**.

   Mindestens eine [!DNL *.vw]-Datei befindet sich im Pfad-Browser-Verzeichnis.

1. Klicken Sie mit der rechten Maustaste auf das Häkchen für die gewünschte Datei und klicken Sie auf **[!UICONTROL Make Local]**.
1. Klicken Sie mit der rechten Maustaste auf das Häkchen für die Datei in der Spalte [!DNL User] und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**.
1. Bearbeiten Sie die Parameter der Datei mithilfe der folgenden Beispieldatei und Tabelle als Hilfslinien:

   ```
   window = simpleBorderWindow: 
     client = pathBrowser: 
       Left Path = vector: 0 items
       Map = ref: wdata/model/dim/base dimension name
       Map Group = ref: wdata/model/dim/group dimension name
       Map Level = ref: wdata/model/dim/level dimension name
       Metric = ref: wdata/model/metric/metric name
       Right Path = vector: 0 items
       size = v3d: (673, 279, 0)
     pos = v3d: (714, 143, 0)
     size = v3d: (673, 298, 0)
   ```

<table id="table_1DCCB4B24B554B72A781B304B5EB155E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Für diesen Parameter... </th> 
   <th colname="col2" class="entry"> Geben Sie diese Informationen ein... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><i>Basisdimensionsname</i> </p> </td> 
   <td colname="col2"> <p>Der Name der Dimension, deren Elemente im Pfadbrowser angezeigt werden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>Name der Gruppendimension</i> </p> </td> 
   <td colname="col2"> <p>Der Name der Dimension, die bestimmt, wie die Elemente der Dimension "Ebene"gruppiert werden, um die Pfade in einem Pfadbrowser zu bilden. Insbesondere dürfen die Dimensionselemente der Ebene, die mit einem einzelnen Pfad in einem Pfadbrowser verknüpft sind, nicht mehr als ein Element einer Gruppendimension umfassen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>Level Dimensionsname</i> </p> </td> 
   <td colname="col2"> <p>Der Name der Ebene (übergeordnet) der Basisdimension, deren Elemente Sie in den Pfadbrowser ziehen. Wenn Sie einem Pfad von einem grundlegenden Dimensionselement zum nächsten folgen, wechseln Sie von einem Dimensionselement auf die nächste Ebene. Wenn Sie einen Pfad mit grundlegenden Dimensionselementen auswählen, wählen Sie Daten für die entsprechenden Elemente der Dimension "Ebene"aus. Die Auswahl enthält immer die Elemente der Dimension "Ebene", die mit dem Stammordner in Verbindung stehen, und wird durch Hinzufügen weiterer Elemente zum Pfad verfeinert. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>Name der Metrik</i> </p> </td> 
   <td colname="col2"> <p>Der Name der Metrik, deren Wert für ein bestimmtes Element proportional zur Stärke des Pfads ist, der zu diesem Element führt. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Weitere Informationen zur Basisdimension, Gruppendimension, Ebenendimension und Metrik für einen Pfadbrowser finden Sie unter [Pfadbrowser](../../../home/c-get-started/c-analysis-vis/c-path-browsers/c-path-browsers.md#concept-f2e9fdafed6e49c2bd111ab425cd6e2b).

1. Klicken Sie in Notepad auf **[!UICONTROL File]** > **[!UICONTROL Save As]**, um die Datei mit einem neuen Namen zu speichern, der auf der Gruppendimension basiert, d. h. *Gruppenname*.vw.

   Achten Sie darauf, die Datei im Ordner &quot;Path Browser&quot;zu speichern.

   >[!NOTE]
   >
   >Um sicherzustellen, dass Ihr Pfadbrowser als [!DNL *.vw]-Datei gespeichert wird, stellen Sie im Fenster [!DNL Save As] &quot;Speichern als&quot;auf &quot;Alle Dateien&quot;ein.

1. (Optional) Um die Änderungen allen Benutzern des funktionierenden Profils zur Verfügung zu stellen, klicken Sie in der Spalte [!DNL Profile Manager] mit der rechten Maustaste auf das Häkchen für die Datei und klicken Sie auf [!DNL User] und dann auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]***.
