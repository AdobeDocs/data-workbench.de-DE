---
description: Diese Schritte gelten nur für das Erstellen von Untermenüs und Menüelementen im Menü "Fenster"von Workspace.
solution: Analytics
title: Erstellen eines Arbeitsflächenmenüs und eines Menüelements
topic: Data workbench
uuid: 9565fe7a-fa4c-42b6-9aa5-b652a2d62796
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Erstellen eines Arbeitsflächenmenüs und eines Menüelements{#create-a-workspace-menu-and-menu-item}

Diese Schritte gelten nur für das Erstellen von Untermenüs und Menüelementen im Menü &quot;Fenster&quot;von Workspace.

Sie können die Metrik- und Dimensionsmenüs anpassen, indem Sie neue Ordner und abgeleitete Metriken und Dimensionen erstellen. Weitere Informationen finden Sie unter [Erstellen und Bearbeiten abgeleiteter Metriken](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-drvd-mtrcs.md#concept-e41723b342a849309874b26232224a40) und [Erstellen und Bearbeiten abgeleiteter Dimensionen](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-dvrd-dim.md#concept-ece3c3ea8cdf4fc796680173993bff93).

**So erstellen Sie ein neues Menü im Arbeitsflächenfenster**

1. Klicken Sie im [!DNL Profile Manager]Ordner auf das **[!UICONTROL Menu]** Verzeichnis, um dessen Inhalt anzuzeigen.
1. Klicken Sie in der [!DNL User] Spalte für den Ordner &quot;Menü&quot;auf **[!UICONTROL Create]** > **[!UICONTROL Folder]**. Ein Ordner mit dem Namen &quot;Neuer Ordner&quot;wird in der [!DNL File] Spalte für angezeigt [!DNL Menu].

   >[!NOTE]
   >
   >Sie können auch einen neuen Ordner für jeden Unterordner im Ordner &quot;Menu&quot;erstellen.

1. Benennen Sie den neuen Ordner um, indem Sie mit der rechten Maustaste in die [!DNL User] Spalte für den Ordner klicken und den neuen Namen in den Dir-Parameter eingeben.
1. Fügen Sie die gewünschten Dateien zum neuen Ordner hinzu.
1. (Optional) Klicken Sie in der [!DNL User] Spalte für den neuen Ordner auf **[!UICONTROL Create]** > **[!UICONTROL order.txt]**.

   Eine [!DNL order.txt] Datei wird in der [!DNL File] Spalte für den neuen Ordner angezeigt und ein Häkchen für die neue Datei wird in der [!DNL User] Spalte angezeigt.

1. (Optional) Bearbeiten Sie die [!DNL order.txt] Datei nach Bedarf. Siehe [Anpassen von Menüs mithilfe von &quot;order.txt&quot;-Dateien](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999).
1. (Optional) Um die Änderungen allen Benutzern des Arbeitsprofils zur Verfügung zu stellen, klicken Sie mit der rechten Maustaste auf das weiße Häkchen für den Ordner in der [!DNL User] Spalte und klicken Sie auf **[!UICONTROL Save Directory to]** > *&lt;**[!UICONTROL working profile name]**>*.

**So fügen Sie einem vorhandenen Menü ein neues Menüelement hinzu**

1. Führen Sie einen der folgenden Schritte aus:

   * Erstellen Sie ein neues Element (Visualisierung, Anmerkung usw.), das einem Menü hinzugefügt werden soll:

      1. Öffnen Sie einen Arbeitsbereich in Data Workbench und erstellen Sie das gewünschte Element.
      1. Speichern Sie das Element im folgenden Verzeichnis:

         *Installationsordner* der Data Workbench \User\*Name des Arbeitsprofils*\Work

      1. Klicken Sie im [!DNL Profile Manager]Ordner auf das **[!UICONTROL Work]** Verzeichnis, um dessen Inhalt anzuzeigen.
      1. Klicken Sie in der [!DNL User] Spalte mit der rechten Maustaste auf das Häkchen für die gewünschte Datei und klicken Sie auf **[!UICONTROL Copy]**.
      1. In the [!DNL User] column for the desired folder, click **[!UICONTROL Paste]**.

         Eine Kopie der Datei wird in der [!DNL File] Spalte für den neuen Ordner angezeigt, und ein Häkchen für die neue Datei wird in der [!DNL User] Spalte angezeigt.
   * Kopieren Sie ein vorhandenes Element aus einem Menü (Ordner) in ein anderes:

      1. Klicken Sie im [!DNL Profile Manager]Ordner auf das **[!UICONTROL Menu]** Verzeichnis, um dessen Inhalt anzuzeigen.
      1. Klicken Sie in der Spalte *Arbeitsprofilname* mit der rechten Maustaste auf das Häkchen für die gewünschte Datei und klicken Sie auf **[!UICONTROL Make Local]**.
      1. Klicken Sie mit der rechten Maustaste auf das Häkchen für die Datei in der [!DNL User] Spalte und klicken Sie auf **[!UICONTROL Copy]**.
      1. In the [!DNL User] column for the desired folder, click **[!UICONTROL Paste]**. Eine Kopie der Datei wird in der [!DNL File] Spalte für den neuen Ordner angezeigt, und ein Häkchen für die neue Datei wird in der [!DNL User] Spalte angezeigt.


1. (Optional) Bearbeiten Sie die [!DNL order.txt] Datei nach Bedarf. Siehe [Anpassen von Menüs mithilfe von &quot;order.txt&quot;-Dateien](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999).
1. (Optional) Um die Änderungen allen Benutzern des Arbeitsprofils zur Verfügung zu stellen, klicken Sie mit der rechten Maustaste auf das weiße Häkchen für jede Datei in der [!DNL User] Spalte und klicken Sie auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.
1. (Optional) Um zu vermeiden, dass ein Menüelement in mehreren Menüs angezeigt wird, sollten Sie die entsprechende Datei aus dem Originalordner löschen, indem Sie mit der rechten Maustaste auf das Häkchen für die Datei in der Spalte *Arbeitsprofilname* klicken und auf **[!UICONTROL Remove]** > **[!UICONTROL Yes]** klicken.

   Wiederholen Sie diesen Schritt für das Häkchen der Datei in der [!DNL User] Spalte.

