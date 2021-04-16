---
description: Seitenüberlagerungen werden nur in der Site-Anwendung konfiguriert, können jedoch auch für andere Anwendungen konfiguriert werden.
title: Konfigurieren von Seitenüberlagerungen
uuid: c4c612ed-5154-4b20-96ab-24b74fba19a2
exl-id: 4e0dfce8-def2-49f3-93e8-41d82922fb88
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '857'
ht-degree: 1%

---

# Konfigurieren von Seitenüberlagerungen{#configure-a-page-overlay}

Seitenüberlagerungen werden nur in der Site-Anwendung konfiguriert, können jedoch auch für andere Anwendungen konfiguriert werden.

Informationen zum Konfigurieren von Seitenüberlagerungen für eine andere Anwendung erhalten Sie bei Adobe Consulting Services.

Die Visualisierung von Seitenüberlagerungen ist ein Tool zur Analyse von HTML-Links. Wenn Sie eine Überlagerung für eine bestimmte Seite anfordern, erstellt Data Workbench einen Schnappschuss der eigentlichen Seite, wie sie in einem Webbrowser angezeigt wird, und analysiert den HTML-Code, der Links entsprechend einer Liste von regulären Ausdrücken darstellt, die Sie definieren. Für jeden Link auf der jeweiligen Seite versucht die Software, eine Übereinstimmung mit dem Muster des regulären Ausdrucks zu finden, indem die Liste heruntergefahren wird, bis die erste Übereinstimmung gefunden wurde. Wenn eine Übereinstimmung vorliegt, wird der Link in der Seitenüberlagerung hervorgehoben dargestellt.

Die Seitenüberlagerung zeigt nur Daten an, wenn Sie der Arbeitsfläche, die die Seitenüberlagerung enthält, eine Farblegende hinzufügen.

>[!NOTE]
>
>Die Konfiguration von Seitenüberlagerungen erfordert sorgfältige Konfigurationsarbeit, und es ist möglich, irreführende Ergebnisse zu erzielen, wenn Links nicht angemessen den Daten zugeordnet werden. Die Arbeit beim Konfigurieren von Seitenüberlagerungen für eine bestimmte Site hängt davon ab, wie Links im HTML-Code auf den Seiten der Site dargestellt werden.

Seitenüberlagerungen weisen dem Benutzer naturgemäß das mentale Modell darauf hin, dass es &quot;wo die Leute klicken&quot;anzeigt. Wenn die Daten, die die Visualisierung unterstützen, nicht mit diesem Modell übereinstimmen, ist das Verwirrungsrisiko hoch.

In [!DNL Site] stellt ein Link normalerweise ein Element aus der Dimension &quot;Nächster URI&quot;oder &quot;Nächster Link&quot;dar. Sie können jedoch einen Link zu einer Dimension zuordnen, die für Ihre Analyse sinnvoll ist. Informationen zum Konfigurieren von Seitenüberlagerungen für andere Dimensionen erhalten Sie bei Adobe Consulting Services.

>[!NOTE]
>
>Die Verwendung der Seitendimension für Seitenüberlagerungen wird nicht empfohlen. Benutzer können die Elemente der Seitendimensionen umbenennen und dadurch die Linksyntax ändern, auf der die Seitenüberlagerungsfunktion basiert.

Zum Konfigurieren der Seitenüberlagerung für [!DNL Site] müssen Sie zwei Dateien bearbeiten:

* **[!DNL Page Overlay.vw]:** Diese Datei ist eine Vorlagendatei zum Erstellen von Visualisierungen für Seitenüberlagerungen. Mindestens eine Vorlagendatei muss in dem Profil vorhanden sein, für das Sie die Seitenüberlagerung konfigurieren.
* **[!DNL Page Overlay Link Templates.cfg]:** Wenn die Visualisierung der Seitenüberlagerung eine Seite lädt, werden die Links auf der Seite und ihre Ziele automatisch identifiziert. Um diese Links mit Datenelementen zu verknüpfen, müssen Sie eine Reihe von regulären Ausdrücken in dieser Datei definieren.

   Sie können mehrere reguläre Ausdruck definieren, die mit den Elementen der Dimension übereinstimmen. Die Reihenfolge, in der Sie die Ausdruck definieren, ist wichtig. Wenn Sie eine Überlagerung für eine bestimmte Seite anfordern, erstellt Data Workbench einen Schnappschuss der eigentlichen Seite, wie sie in einem Webbrowser angezeigt wird, und analysiert den HTML-Code, der Links entsprechend einer Liste von regulären Ausdrücken darstellt, die Sie definieren. Für jeden Link auf der jeweiligen Seite versucht die Software, eine Übereinstimmung mit dem Muster des regulären Ausdrucks zu finden, indem die Liste heruntergefahren wird, bis die erste Übereinstimmung gefunden wurde. Der erste Ausdruck, der mit einem Dimensionselement übereinstimmt, ist der verwendete. Daher ist es am besten, den regulären Ausdruck zuerst mit dem spezifischsten Übereinstimmungsmuster, gefolgt von weniger spezifischen Ausdrücken, Liste. Wenn eine Übereinstimmung vorliegt, wird der Link in der Visualisierung der Seitenüberlagerung hervorgehoben dargestellt.

**So konfigurieren Sie die Seitenüberlagerung für die Site**

1. I

   Navigieren Sie in [!DNL Profile Manager] zu **[!UICONTROL Context]** > **[!UICONTROL Dimension Element]** > **[!UICONTROL URI]**.

   >[!NOTE]
   >
   >Der Ordner &quot;Dimension-Element&quot;enthält die Elemente im Kontextmenü, die angezeigt werden, wenn Sie mit der rechten Maustaste auf ein Dimensionselement klicken. Öffnen Sie beispielsweise eine URI-Tabelle und wählen Sie dann ein URI-Element aus. Klicken Sie mit der rechten Maustaste auf den URI und die Seitenüberlagerung wird angezeigt.

1. Klicken Sie im Ordner &quot;URI&quot;mit der rechten Maustaste auf das Häkchen neben der Datei [!DNL Page Overlay.vw] und klicken Sie auf **[!UICONTROL Make Local]**. In der Spalte [!DNL User] wird ein Häkchen für diese Datei angezeigt.
1. Klicken Sie mit der rechten Maustaste auf das neu erstellte Häkchen und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**.
1. Geben Sie die Domäne (und ggf. die Browserhöhe) an.

   ```
   window = simpleBorderWindow: 
     client = scrollWindow: 
       client = PageOverlay: 
         URI Template = string: http://%Domain%%Element%
         URI Parameters = map: 
           Domain = string: domain name
           Element = ref: Element/Name
         Dim = ref: wdata/model/dim/URI
         Dim Element = ref: Element/Name
         Level = ref: wdata/model/dim/Page View
         Group = ref: wdata/model/dim/Session
         Browser Height = int: browser height
     pos = v3d: (518, 202, 0)
     size = v3d: (810, 610, 0)
     titleBar = editor: 
       size = v3d: (61, 19, 0)
       text = string: 
   ```

1. Speichern Sie die Datei.
1. Um diese Änderung allen Benutzern des funktionierenden Profils zur Verfügung zu stellen, klicken Sie in der Spalte [!DNL Profile Manager] mit der rechten Maustaste auf das Häkchen für die [!DNL .vw]-Datei in der Spalte [!DNL User] und klicken Sie auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]***.

   >[!NOTE]
   >
   >Sie können zusätzliche Vorlagendateien für andere Sites oder Subdomänen erstellen. Jede Vorlage, die Sie erstellen, wird im Ordner [!DNL Page Overlay menu] angezeigt.

1. Klicken Sie im Kontextordner von [!DNL Profile Manager] mit der rechten Maustaste auf das Häkchen neben der Datei [!DNL Page Overlay Link Templates.cfg] und klicken Sie auf **[!UICONTROL Make Local]**.

   In der Spalte [!DNL User] wird ein Häkchen für diese Datei angezeigt.

1. Klicken Sie mit der rechten Maustaste auf das neu erstellte Häkchen und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**.
1. Klicken Sie mit der rechten Maustaste auf **[!UICONTROL Link Templates]** und klicken Sie auf **[!UICONTROL Add new]** > **[!UICONTROL Regular Expression]**.
1. Bearbeiten Sie die Parameter für den LinkRegex-Vektor nach Bedarf:

<table id="table_24DD4BB5009542F7BB1DA3318E2E6E2B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Für diesen Parameter... </th> 
   <th colname="col2" class="entry"> Geben Sie diese Informationen ein... </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Dimension </p> </td> 
   <td colname="col2"> <p>Die Dimension (in der Regel die Dimension "Nächster URI"), die durch den Link dargestellt wird. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ausdruck </p> </td> 
   <td colname="col2"> <p>Der reguläre Ausdruck, mit dem der relevante Teil des HTML-Links ausgewählt wird, um das nächste Element aus der Dimension zu finden. Der reguläre Ausdruck muss exakt übereinstimmen, und das gewünschte Ausgabemuster wird mit Klammern gruppiert. Weitere Informationen zu regulären Ausdrücken finden Sie im <i>Handbuch zur Konfiguration von Datasets</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ausgabemuster </p> </td> 
   <td colname="col2"> <p>Das Ausgabemuster des regulären Ausdrucks, mit dem das Ergebniselement des Parameters Dimension extrahiert wird. </p> </td> 
  </tr> 
 </tbody> 
</table>

Die folgende Beispieldatei zeigt drei reguläre Ausdruck:

![](assets/cfg_PageOverlayLinkTemplates_Example.png)

1. Klicken Sie zum Speichern der Datei mit der rechten Maustaste auf **[!UICONTROL (modified)]** oben im Fenster und klicken Sie auf **[!UICONTROL Save]**.
1. Um diese Änderung allen Benutzern des funktionierenden Profils zur Verfügung zu stellen, klicken Sie mit der rechten Maustaste auf das Häkchen für [!DNL Page Overlay Link Templates.cfg] in der Spalte [!DNL User] und klicken Sie auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]***.
