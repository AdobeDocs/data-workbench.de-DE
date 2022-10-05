---
description: Pfadbrowser können so konfiguriert werden, dass sie mit jeder Kombination aus Basisdimension, Gruppendimension, Ebenendimension und Metrik arbeiten, die für Ihre Anwendung und Ihren Datensatz sinnvoll ist.
title: Konfigurieren von Pfad-Browsern
uuid: 1ba3fb6e-b76f-428f-b6ec-077669c3b305
exl-id: be6a68f7-e3e3-4207-a112-3a4fdd5c5f57
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '422'
ht-degree: 1%

---

# Konfigurieren von Pfad-Browsern{#configure-a-path-browser}

{{eol}}

Pfadbrowser können so konfiguriert werden, dass sie mit jeder Kombination aus Basisdimension, Gruppendimension, Ebenendimension und Metrik arbeiten, die für Ihre Anwendung und Ihren Datensatz sinnvoll ist.

Nachdem Sie einen Pfad-Browser konfiguriert haben, wird er mit anderen Pfadbrowsern im [!DNL Add Visualization] Menü.

1. Im [!DNL Profile Manager]klicken **[!UICONTROL Menu]** Klicken Sie auf **[!UICONTROL Add Visualization]** und **[!UICONTROL Path Browser]**.

   Mindestens ein [!DNL *.vw] -Datei im Verzeichnis &quot;Pfad-Browser&quot;gespeichert.

1. Klicken Sie mit der rechten Maustaste auf das Häkchen für die gewünschte Datei und klicken Sie auf **[!UICONTROL Make Local]**.
1. Klicken Sie mit der rechten Maustaste auf das Häkchen für die Datei im [!DNL User] Spalte und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**.
1. Bearbeiten Sie die Parameter der Datei mithilfe der folgenden Beispieldatei und Tabelle als Handbücher:

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
   <th colname="col1" class="entry"> Für diesen Parameter ... </th> 
   <th colname="col2" class="entry"> Geben Sie diese Informationen an... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><i>Name der Basisdimension</i> </p> </td> 
   <td colname="col2"> <p>Der Name der Dimension, deren Elemente im Pfad-Browser angezeigt werden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>Name der Gruppendimension</i> </p> </td> 
   <td colname="col2"> <p>Der Name der Dimension, der bestimmt, wie die Elemente der Ebenendimension gruppiert werden, um die Pfade in einem Pfadbrowser zu bilden. Insbesondere dürfen die Dimensionselemente der Ebene, die mit einem einzelnen Pfad in einem Pfadbrowser verknüpft sind, nicht mehr als ein Element einer Gruppendimension umfassen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>Level dimension name</i> </p> </td> 
   <td colname="col2"> <p>Der Name der Ebene (übergeordnet) der Basisdimension, deren Elemente Sie in den Pfad-Browser ziehen. Wenn Sie einem Pfad von einem grundlegenden Dimensionselement zum nächsten folgen, wechseln Sie von einem Dimensionselement auf der Ebene zum nächsten. Wenn Sie einen Pfad von grundlegenden Dimensionselementen auswählen, wählen Sie Daten für die entsprechenden Elemente der Ebenendimension aus. Die Auswahl umfasst immer die Elemente der Ebenendimension, die sich auf den Stamm beziehen, und wird durch Hinzufügen weiterer Elemente zum Pfad verfeinert. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>Metrikname</i> </p> </td> 
   <td colname="col2"> <p>Der Name der Metrik, deren Wert für ein bestimmtes Element proportional zur Dicke des Pfads ist, der zu diesem Element führt. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Weitere Informationen zur Basisdimension, Gruppendimension, Ebenendimension und Metrik für einen Pfadbrowser finden Sie unter [Pfad-Browser](../../../home/c-get-started/c-analysis-vis/c-path-browsers/c-path-browsers.md#concept-f2e9fdafed6e49c2bd111ab425cd6e2b).

1. Klicken Sie im Editor auf **[!UICONTROL File]** > **[!UICONTROL Save As]** , um die Datei mit einem neuen Namen zu speichern, der auf der Gruppendimension basiert, d. h. *Name der Gruppendimension*.vw.

   Speichern Sie die Datei im Verzeichnis &quot;Pfad-Browser&quot;.

   >[!NOTE]
   >
   >Um sicherzustellen, dass Ihr Pfad-Browser als [!DNL *.vw] in der Datei [!DNL Save As] auf &quot;Alle Dateien&quot;setzen.

1. (Optional) Um die Änderungen allen Benutzern des Arbeitsprofils zur Verfügung zu stellen, klicken Sie auf [!DNL Profile Manager]klicken Sie mit der rechten Maustaste auf das Häkchen für die Datei im [!DNL User] Spalte und klicken Sie auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.
