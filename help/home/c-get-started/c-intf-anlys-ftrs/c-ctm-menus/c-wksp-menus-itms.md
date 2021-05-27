---
description: Diese Schritte gelten nur für die Erstellung von Untermenüs und Menüelementen für das Menü "Workspace-Fenster".
title: Erstellen von Arbeitsbereichmenüs und Menüelementen
uuid: 9565fe7a-fa4c-42b6-9aa5-b652a2d62796
exl-id: 26f2b85c-ab23-41a4-bf4b-9e507952fede
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '503'
ht-degree: 3%

---

# Erstellen von Arbeitsbereichmenüs und Menüelementen{#create-a-workspace-menu-and-menu-item}

Diese Schritte gelten nur für die Erstellung von Untermenüs und Menüelementen für das Menü &quot;Workspace-Fenster&quot;.

Sie können die Menüs für Metriken und Dimensionen anpassen, indem Sie neue Ordner und neue abgeleitete Metriken und Dimensionen erstellen. Weitere Informationen finden Sie unter [Erstellen und Bearbeiten abgeleiteter Metriken](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-drvd-mtrcs.md#concept-e41723b342a849309874b26232224a40) und [Erstellen und Bearbeiten abgeleiteter Dimensionen](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-dvrd-dim.md#concept-ece3c3ea8cdf4fc796680173993bff93).

**So erstellen Sie ein neues Fenster-Menü in einem Arbeitsbereich**

1. Klicken Sie im Ordner [!DNL Profile Manager] auf das Verzeichnis **[!UICONTROL Menu]** , um dessen Inhalt anzuzeigen.
1. Klicken Sie in der Spalte [!DNL User] für das Menü-Verzeichnis auf **[!UICONTROL Create]** > **[!UICONTROL Folder]**. In der Spalte [!DNL File] für [!DNL Menu] wird ein Ordner mit dem Namen &quot;New Folder&quot;angezeigt.

   >[!NOTE]
   >
   >Sie können auch einen neuen Ordner für jedes Unterverzeichnis im Verzeichnis Menu erstellen.

1. Benennen Sie den neuen Ordner um, indem Sie mit der rechten Maustaste in die Spalte [!DNL User] für den Ordner klicken und den neuen Namen in den Parameter Dir eingeben.
1. Fügen Sie die gewünschten Dateien zum neuen Ordner hinzu.
1. (Optional) Klicken Sie in der Spalte [!DNL User] für den neuen Ordner auf **[!UICONTROL Create]** > **[!UICONTROL order.txt]**.

   Eine [!DNL order.txt]-Datei wird in der Spalte [!DNL File] für den neuen Ordner angezeigt und ein Häkchen für die neue Datei wird in der Spalte [!DNL User] angezeigt.

1. (Optional) Bearbeiten Sie die Datei [!DNL order.txt] nach Bedarf. Siehe [Anpassen von Menüs mithilfe von &quot;Order.txt&quot;-Dateien](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999).
1. (Optional) Um die Änderungen für alle Benutzer des Arbeitsprofils verfügbar zu machen, klicken Sie mit der rechten Maustaste auf das weiße Häkchen für den Ordner in der Spalte [!DNL User] und klicken Sie auf **[!UICONTROL Save Directory to]** > *&lt;**[!UICONTROL working profile name]***.

**So fügen Sie einem vorhandenen Menü ein neues Menüelement hinzu**

1. Führen Sie einen der folgenden Schritte aus:

   * Erstellen Sie ein neues Element (Visualisierung, Anmerkung usw.), das einem Menü hinzugefügt werden soll:

      1. Öffnen Sie einen Arbeitsbereich in Data Workbench und erstellen Sie das gewünschte Element.
      1. Speichern Sie das Element im folgenden Verzeichnis:

         *Installationsordner von Data Workbench*\User\*Name des Arbeitsprofils*\Work

      1. Klicken Sie im Ordner [!DNL Profile Manager] auf das Verzeichnis **[!UICONTROL Work]** , um dessen Inhalt anzuzeigen.
      1. Klicken Sie in der Spalte [!DNL User] mit der rechten Maustaste auf das Häkchen für die gewünschte Datei und klicken Sie auf **[!UICONTROL Copy]**.
      1. Klicken Sie in der Spalte [!DNL User] für den gewünschten Ordner auf **[!UICONTROL Paste]**.

         Eine Kopie der Datei wird in der Spalte [!DNL File] für den neuen Ordner angezeigt und ein Häkchen für die neue Datei wird in der Spalte [!DNL User] angezeigt.
   * Kopieren Sie ein vorhandenes Element aus einem Menü (Ordner) in ein anderes:

      1. Klicken Sie im Ordner [!DNL Profile Manager] auf das Verzeichnis **[!UICONTROL Menu]** , um dessen Inhalt anzuzeigen.
      1. Klicken Sie in der Spalte *Arbeitsprofilname* mit der rechten Maustaste auf das Häkchen für die gewünschte Datei und klicken Sie auf **[!UICONTROL Make Local]**.
      1. Klicken Sie mit der rechten Maustaste auf das Häkchen für die Datei in der Spalte [!DNL User] und klicken Sie auf **[!UICONTROL Copy]**.
      1. Klicken Sie in der Spalte [!DNL User] für den gewünschten Ordner auf **[!UICONTROL Paste]**. Eine Kopie der Datei wird in der Spalte [!DNL File] für den neuen Ordner angezeigt und ein Häkchen für die neue Datei wird in der Spalte [!DNL User] angezeigt.


1. (Optional) Bearbeiten Sie die Datei [!DNL order.txt] nach Bedarf. Siehe [Anpassen von Menüs mithilfe von &quot;Order.txt&quot;-Dateien](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999).
1. (Optional) Um die Änderungen für alle Benutzer des Arbeitsprofils verfügbar zu machen, klicken Sie mit der rechten Maustaste auf das weiße Häkchen für jede Datei in der Spalte [!DNL User] und klicken Sie auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]***.
1. (Optional) Um zu vermeiden, dass ein Menüelement in mehreren Menüs angezeigt wird, sollten Sie die entsprechende Datei aus dem ursprünglichen Ordner löschen, indem Sie mit der rechten Maustaste in der Spalte *Name des Arbeitsprofils* auf das Häkchen für die Datei klicken und **[!UICONTROL Remove]** > **[!UICONTROL Yes]** klicken.

   Wiederholen Sie diesen Schritt für das Häkchen der Datei in der Spalte [!DNL User] .
