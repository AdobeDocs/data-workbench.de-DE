---
description: Seitenüberlagerungen werden nur in der Site-Anwendung konfiguriert, können jedoch auch für andere Anwendungen konfiguriert werden.
solution: Analytics
title: Konfigurieren einer Seitenüberlagerung
topic: Data workbench
uuid: c4c612ed-5154-4b20-96ab-24b74fba19a2
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Konfigurieren einer Seitenüberlagerung{#configure-a-page-overlay}

Seitenüberlagerungen werden nur in der Site-Anwendung konfiguriert, können jedoch auch für andere Anwendungen konfiguriert werden.

Informationen zum Konfigurieren von Seitenüberlagerungen für eine andere Anwendung erhalten Sie bei Adobe Consulting Services.

Die Visualisierung von Seitenüberlagerungen ist ein Tool zur Analyse von HTML-Links. Wenn Sie eine Überlagerung für eine bestimmte Seite anfordern, erstellt Data Workbench eine Momentaufnahme der tatsächlichen Seite, wie sie in einem Webbrowser angezeigt wird, und analysiert den HTML-Code, der Links gemäß einer Liste von regulären Ausdrücken darstellt, die Sie definieren. Für jeden Link auf der ausgewählten Seite versucht die Software, eine Übereinstimmung mit dem Muster für reguläre Ausdrücke zu finden, indem sie die Liste so lange heruntersetzt, bis die erste Übereinstimmung gefunden wurde. Wenn eine Übereinstimmung vorliegt, wird der Link in der Seitenüberlagerung hervorgehoben dargestellt.

Die Seitenüberlagerung zeigt nur Daten an, wenn Sie der Arbeitsfläche, die die Seitenüberlagerung enthält, eine Farblegende hinzufügen.

>[!NOTE]
>
>Die Konfiguration von Seitenüberlagerungen erfordert sorgfältige Konfigurationsarbeit, und es ist möglich, irreführende Ergebnisse zu erzielen, wenn Links nicht angemessen den Daten zugeordnet werden. Die Arbeit beim Konfigurieren von Seitenüberlagerungen für eine bestimmte Site hängt davon ab, wie Links im HTML-Code auf den Seiten der Site dargestellt werden.

Seitenüberlagerungen weisen dem Benutzer naturgemäß das mentale Modell darauf hin, dass es &quot;wo die Leute klicken&quot;anzeigt. Wenn die Daten, die die Visualisierung unterstützen, nicht mit diesem Modell übereinstimmen, ist das Verwirrungsrisiko hoch.

In [!DNL Site]der Regel stellt ein Link ein Element aus der Dimension &quot;Nächster URI&quot;oder &quot;Nächster Link&quot;dar. Sie können jedoch einen Link zu einer Dimension zuordnen, die für Ihre Analyse sinnvoll ist. Informationen zum Konfigurieren von Seitenüberlagerungen für andere Dimensionen erhalten Sie bei Adobe Consulting Services.

>[!NOTE]
>
>Die Verwendung der Seitendimension für Seitenüberlagerungen wird nicht empfohlen. Benutzer können die Elemente der Seitendimensionen umbenennen und dadurch die Linksyntax ändern, auf der die Seitenüberlagerungsfunktion basiert.

Zum Konfigurieren der Seitenüberlagerung für [!DNL Site]müssen Sie zwei Dateien bearbeiten:

* **[!DNL Page Overlay.vw]:**Diese Datei ist eine Vorlagendatei zum Erstellen von Visualisierungen für Seitenüberlagerungen. Mindestens eine Vorlagendatei muss im Profil vorhanden sein, für das Sie die Seitenüberlagerung konfigurieren.
* **[!DNL Page Overlay Link Templates.cfg]:**Wenn die Visualisierung von Seitenüberlagerungen eine Seite lädt, identifiziert sie automatisch die Links auf der Seite und deren Ziele. Um diese Links mit Elementen in den Daten zu verknüpfen, müssen Sie einen Satz regulärer Ausdrücke in dieser Datei definieren.

   Sie können mehrere reguläre Ausdrücke definieren, die mit den Elementen der Dimension übereinstimmen. Die Reihenfolge, in der Sie die Ausdrücke definieren, ist wichtig. Wenn Sie eine Überlagerung für eine bestimmte Seite anfordern, erstellt Data Workbench eine Momentaufnahme der tatsächlichen Seite, wie sie in einem Webbrowser angezeigt wird, und analysiert den HTML-Code, der Links gemäß einer Liste von regulären Ausdrücken darstellt, die Sie definieren. Für jeden Link auf der ausgewählten Seite versucht die Software, eine Übereinstimmung mit dem Muster für reguläre Ausdrücke zu finden, indem sie die Liste so lange heruntersetzt, bis die erste Übereinstimmung gefunden wurde. Der erste Ausdruck, der mit einem Dimensionselement übereinstimmt, ist der verwendete. Daher ist es am besten, den regulären Ausdruck mit dem spezifischsten Übereinstimmungsmuster zuerst aufzulisten, gefolgt von weniger spezifischen Ausdrücken. Wenn eine Übereinstimmung vorliegt, wird der Link in der Visualisierung der Seitenüberlagerung hervorgehoben dargestellt.

**So konfigurieren Sie die Seitenüberlagerung für die Site**

1. I

   Navigieren Sie in der [!DNL Profile Manager]Liste zu **[!UICONTROL Context]** > **[!UICONTROL Dimension Element]** > **[!UICONTROL URI]**.

   >[!NOTE]
   >
   >Der Ordner &quot;Dimensionselemente&quot;enthält die Elemente des Kontextmenüs, die angezeigt werden, wenn Sie mit der rechten Maustaste auf ein Dimensionselement klicken. Öffnen Sie beispielsweise eine URI-Tabelle und wählen Sie dann ein URI-Element aus. Klicken Sie mit der rechten Maustaste auf den URI und die Seitenüberlagerung wird angezeigt.

1. Klicken Sie im Ordner &quot;URI&quot;mit der rechten Maustaste auf das Häkchen neben der [!DNL Page Overlay.vw] Datei und klicken Sie auf **[!UICONTROL Make Local]**. Ein Häkchen für diese Datei wird in der [!DNL User] Spalte angezeigt.
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
1. Um diese Änderung allen Benutzern des Arbeitsprofils zur Verfügung zu stellen, klicken Sie mit der rechten Maustaste auf das [!DNL Profile Manager]Häkchen für die [!DNL .vw] Datei in der [!DNL User] Spalte und klicken Sie auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.

   >[!NOTE]
   >
   >Sie können zusätzliche Vorlagendateien für andere Sites oder Subdomänen erstellen. Jede von Ihnen erstellte Vorlage wird im [!DNL Page Overlay menu]Fenster angezeigt.

1. Klicken Sie im Kontextordner des [!DNL Profile Manager]Ordners mit der rechten Maustaste auf das Häkchen neben der [!DNL Page Overlay Link Templates.cfg] Datei und klicken Sie auf **[!UICONTROL Make Local]**.

   Ein Häkchen für diese Datei wird in der [!DNL User] Spalte angezeigt.

1. Klicken Sie mit der rechten Maustaste auf das neu erstellte Häkchen und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**.
1. Klicken Sie mit der rechten Maustaste **[!UICONTROL Link Templates]** und klicken Sie auf **[!UICONTROL Add new]** > **[!UICONTROL Regular Expression]**.
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
   <td colname="col2"> <p>Der reguläre Ausdruck, mit dem der relevante Teil des HTML-Links ausgewählt wird, um das nächste Element aus der Dimension zu finden. Der reguläre Ausdruck muss exakt übereinstimmen, und das gewünschte Ausgabemuster wird mit Klammern gruppiert. Weitere Informationen zu regulären Ausdrücken finden Sie im Handbuch zur Konfiguration von <i>DataSet</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ausgabemuster </p> </td> 
   <td colname="col2"> <p>Das Ausgabemuster des regulären Ausdrucks, mit dem das resultierende Element des Dimensionsparameters extrahiert wird. </p> </td> 
  </tr> 
 </tbody> 
</table>

Die folgende Beispieldatei zeigt drei reguläre Ausdrücke:

![](assets/cfg_PageOverlayLinkTemplates_Example.png)

1. Um die Datei zu speichern, klicken Sie mit der rechten Maustaste **[!UICONTROL (modified)]** am oberen Rand des Fensters und klicken Sie auf **[!UICONTROL Save]**.
1. Um diese Änderung allen Benutzern des Arbeitsprofils zur Verfügung zu stellen, klicken Sie mit der rechten Maustaste auf das Häkchen [!DNL Page Overlay Link Templates.cfg] in der [!DNL User] Spalte und klicken Sie auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.

