---
description: Seitenüberlagerungen werden nur in der Site-Anwendung konfiguriert, können jedoch für andere Anwendungen konfiguriert werden.
title: Konfigurieren von Seitenüberlagerungen
uuid: c4c612ed-5154-4b20-96ab-24b74fba19a2
exl-id: 4e0dfce8-def2-49f3-93e8-41d82922fb88
source-git-commit: 79981e92dd1c2e552f958716626a632ead940973
workflow-type: tm+mt
source-wordcount: '857'
ht-degree: 1%

---

# Konfigurieren von Seitenüberlagerungen{#configure-a-page-overlay}

Seitenüberlagerungen werden nur in der Site-Anwendung konfiguriert, können jedoch für andere Anwendungen konfiguriert werden.

Informationen zum Konfigurieren von Seitenüberlagerungen für eine andere Anwendung erhalten Sie von Adobe Consulting Services.

Die Visualisierung von Seitenüberlagerungen ist ein Tool für die HTML-Linkanalyse. Wenn Sie eine Überlagerung für eine bestimmte Seite anfordern, erstellt Data Workbench eine Momentaufnahme der tatsächlichen Seite, wie sie in einem Webbrowser angezeigt wird, und analysiert den HTML-Code, der Links entsprechend einer von Ihnen definierten Liste regulärer Ausdrücke darstellt. Für jeden Link auf der ausgewählten Seite versucht die Software, eine Übereinstimmung mit dem Muster für reguläre Ausdrücke zu finden, indem sie die Liste hinunter arbeitet, bis die erste Übereinstimmung gefunden wurde. Wenn eine Übereinstimmung vorliegt, wird der Link in der Seitenüberlagerung hervorgehoben dargestellt.

Die Seitenüberlagerung zeigt nur Daten an, wenn Sie dem Arbeitsbereich, der die Seitenüberlagerung enthält, eine Farblegende hinzufügen.

>[!NOTE]
>
>Die Konfiguration von Seitenüberlagerungen erfordert eine sorgfältige Konfiguration und es ist möglich, irreführende Ergebnisse zu erstellen, wenn Links nicht den Daten angemessen zugeordnet sind. Die Arbeit beim Konfigurieren von Seitenüberlagerungen für eine bestimmte Site hängt davon ab, wie Links im HTML-Code auf den Seiten der Site angezeigt werden.

Seitenüberlagerungen weisen dem Benutzer naturgemäß das mentale Modell darauf hin, dass es anzeigt, &quot;wo die Benutzer klicken&quot;. Wenn die Daten, die die Visualisierung unterstützen, nicht mit diesem Modell übereinstimmen, ist das Verwirrungspotenzial hoch.

In [!DNL Site] stellt ein Link normalerweise ein Element aus der Dimension &quot;Nächster URI&quot;oder &quot;Nächster Link&quot;dar. Sie können jedoch einen Link zu einer Dimension zuordnen, die für Ihre Analyse sinnvoll ist. Informationen zum Konfigurieren von Seitenüberlagerungen für andere Dimensionen erhalten Sie von Adobe Consulting Services.

>[!NOTE]
>
>Die Verwendung der Dimension Seite für Seitenüberlagerungen wird nicht empfohlen. Benutzer können die Elemente der Seitendimensionen umbenennen und dadurch die Linksyntax ändern, auf der die Seitenüberlagerungsfunktion basiert.

Um die Seitenüberlagerung für [!DNL Site] zu konfigurieren, müssen Sie zwei Dateien bearbeiten:

* **[!DNL Page Overlay.vw]:** Diese Datei ist eine Vorlagendatei zum Erstellen von Visualisierungen von Seitenüberlagerungen. Mindestens eine Vorlagendatei muss im Profil vorhanden sein, für das Sie die Seitenüberlagerung konfigurieren.
* **[!DNL Page Overlay Link Templates.cfg]:** Wenn die Visualisierung der Seitenüberlagerung eine Seite lädt, identifiziert sie automatisch die Links auf der Seite und ihre Ziele. Um diese Relationen mit Elementen in den Daten zu verknüpfen, müssen Sie in dieser Datei einen Satz regulärer Ausdrücke definieren.

   Sie können mehrere reguläre Ausdrücke definieren, die mit den Elementen der Dimension übereinstimmen. Die Reihenfolge, in der Sie die Ausdrücke definieren, ist wichtig. Wenn Sie eine Überlagerung für eine bestimmte Seite anfordern, erstellt Data Workbench eine Momentaufnahme der tatsächlichen Seite, wie sie in einem Webbrowser angezeigt wird, und analysiert den HTML-Code, der Links entsprechend einer von Ihnen definierten Liste regulärer Ausdrücke darstellt. Für jeden Link auf der ausgewählten Seite versucht die Software, eine Übereinstimmung mit dem Muster für reguläre Ausdrücke zu finden, indem sie die Liste hinunter arbeitet, bis die erste Übereinstimmung gefunden wurde. Der erste Ausdruck, der mit einem Dimensionselement übereinstimmt, ist der verwendete. Daher ist es am besten, den regulären Ausdruck mit dem spezifischsten Übereinstimmungsmuster zuerst aufzulisten, gefolgt von weniger spezifischen Ausdrücken. Wenn eine Übereinstimmung vorliegt, wird der Link in der Visualisierung der Seitenüberlagerung hervorgehoben.

**So konfigurieren Sie die Seitenüberlagerung für Site**

1. I

   Navigieren Sie in [!DNL Profile Manager] zu **[!UICONTROL Context]** > **[!UICONTROL Dimension Element]** > **[!UICONTROL URI]**.

   >[!NOTE]
   >
   >Der Ordner &quot;Dimension Element&quot;enthält die Kontextmenüelemente, die angezeigt werden, wenn Sie mit der rechten Maustaste auf ein Dimensionselement klicken. Öffnen Sie beispielsweise eine URI-Tabelle und wählen Sie ein URI-Element aus. Klicken Sie mit der rechten Maustaste auf den URI und die Seitenüberlagerung wird angezeigt.

1. Klicken Sie im URI-Ordner mit der rechten Maustaste auf das Häkchen neben der Datei [!DNL Page Overlay.vw] und klicken Sie auf **[!UICONTROL Make Local]**. Ein Häkchen für diese Datei wird in der Spalte [!DNL User] angezeigt.
1. Klicken Sie mit der rechten Maustaste auf das neu erstellte Häkchen und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**.
1. Geben Sie die Domäne (und ggf. die Browserhöhe) an.

   ```
   window = simpleBorderWindow:
     client = scrollWindow:
       client = PageOverlay:
         URI Template = string: https://%Domain%%Element%
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
1. Um diese Änderung allen Benutzern des Arbeitsprofils zur Verfügung zu stellen, klicken Sie in der Spalte [!DNL Profile Manager] mit der rechten Maustaste auf das Häkchen für die Datei [!DNL .vw] in der Spalte [!DNL User] und klicken Sie auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]***.

   >[!NOTE]
   >
   >Sie können zusätzliche Vorlagendateien für andere Sites oder Subdomänen erstellen. Jede von Ihnen erstellte Vorlage wird im [!DNL Page Overlay menu] angezeigt.

1. Klicken Sie im Kontextordner von [!DNL Profile Manager] mit der rechten Maustaste auf das Häkchen neben der Datei [!DNL Page Overlay Link Templates.cfg] und klicken Sie auf **[!UICONTROL Make Local]**.

   Ein Häkchen für diese Datei wird in der Spalte [!DNL User] angezeigt.

1. Klicken Sie mit der rechten Maustaste auf das neu erstellte Häkchen und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**.
1. Klicken Sie mit der rechten Maustaste auf **[!UICONTROL Link Templates]** und klicken Sie auf **[!UICONTROL Add new]** > **[!UICONTROL Regular Expression]**.
1. Bearbeiten Sie die Parameter für den LinkRegex-Vektor nach Bedarf:

<table id="table_24DD4BB5009542F7BB1DA3318E2E6E2B">
 <thead>
  <tr>
   <th colname="col1" class="entry"> Für diesen Parameter ... </th>
   <th colname="col2" class="entry"> Geben Sie diese Informationen an... </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> <p>Dimension </p> </td>
   <td colname="col2"> <p>Die Dimension (normalerweise die Dimension "Nächster URI"), die durch den Link dargestellt wird. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>Ausdruck </p> </td>
   <td colname="col2"> <p>Der reguläre Ausdruck, der verwendet wird, um den entsprechenden Teil des HTML-Links auszuwählen und das nächste Element aus der Dimension zu finden. Der reguläre Ausdruck muss eine exakte Übereinstimmung aufweisen, und das gewünschte Ausgabemuster ist in Klammern gruppiert. Weitere Informationen zu regulären Ausdrücken finden Sie im <i>Handbuch zur Datensatzkonfiguration</i>. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>Ausgabemuster </p> </td>
   <td colname="col2"> <p>Das Ausgabemuster des regulären Ausdrucks, mit dem das resultierende Element des Dimension-Parameters extrahiert wird. </p> </td>
  </tr>
 </tbody>
</table>

Die folgende Beispieldatei zeigt drei reguläre Ausdrücke:

![](assets/cfg_PageOverlayLinkTemplates_Example.png)

1. Klicken Sie zum Speichern der Datei mit der rechten Maustaste auf **[!UICONTROL (modified)]** oben im Fenster und klicken Sie auf **[!UICONTROL Save]**.
1. Um diese Änderung allen Benutzern des Arbeitsprofils zur Verfügung zu stellen, klicken Sie mit der rechten Maustaste auf das Häkchen für [!DNL Page Overlay Link Templates.cfg] in der Spalte [!DNL User] und klicken Sie auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]***.
