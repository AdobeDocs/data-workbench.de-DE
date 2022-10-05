---
description: Diese Schritte gelten nur für die Erstellung von Untermenüs und Menüelementen für das Menü "Workspace-Fenster".
title: Erstellen von Arbeitsbereichmenüs und Menüelementen
uuid: 9565fe7a-fa4c-42b6-9aa5-b652a2d62796
exl-id: 26f2b85c-ab23-41a4-bf4b-9e507952fede
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '503'
ht-degree: 3%

---

# Erstellen von Arbeitsbereichmenüs und Menüelementen{#create-a-workspace-menu-and-menu-item}

{{eol}}

Diese Schritte gelten nur für die Erstellung von Untermenüs und Menüelementen für das Menü &quot;Workspace-Fenster&quot;.

Sie können die Menüs für Metriken und Dimensionen anpassen, indem Sie neue Ordner und neue abgeleitete Metriken und Dimensionen erstellen. Weitere Informationen finden Sie unter [Erstellen und Bearbeiten abgeleiteter Metriken](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-drvd-mtrcs.md#concept-e41723b342a849309874b26232224a40) und [Erstellen und Bearbeiten abgeleiteter Dimensionen](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-dvrd-dim.md#concept-ece3c3ea8cdf4fc796680173993bff93).

**So erstellen Sie ein neues Fenster-Menü in einem Arbeitsbereich**

1. Im [!DNL Profile Manager], klicken Sie auf die **[!UICONTROL Menu]** Verzeichnis, um seinen Inhalt anzuzeigen.
1. Im [!DNL User] Spalte für den Ordner Menu (Menü), klicken Sie auf **[!UICONTROL Create]** > **[!UICONTROL Folder]**. Der Ordner Neuer Ordner wird im [!DNL File] Spalte für [!DNL Menu].

   >[!NOTE]
   >
   >Sie können auch einen neuen Ordner für jedes Unterverzeichnis im Verzeichnis Menu erstellen.

1. Benennen Sie den neuen Ordner um, indem Sie mit der rechten Maustaste auf [!DNL User] und geben Sie den neuen Namen in den Parameter Dir ein.
1. Fügen Sie die gewünschten Dateien zum neuen Ordner hinzu.
1. (Optional) Im [!DNL User] Spalte für den neuen Ordner, klicken Sie auf **[!UICONTROL Create]** > **[!UICONTROL order.txt]**.

   Ein [!DNL order.txt] -Datei im [!DNL File] -Spalte für den neuen Ordner und ein Häkchen für die neue Datei wird im [!DNL User] Spalte.

1. (Optional) Bearbeiten Sie die [!DNL order.txt] Datei nach Bedarf. Siehe [Menüs mithilfe von &quot;order.txt&quot;-Dateien anpassen](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999).
1. (Optional) Um die Änderungen allen Benutzern des Arbeitsprofils zur Verfügung zu stellen, klicken Sie mit der rechten Maustaste auf das weiße Häkchen für den Ordner im [!DNL User] Spalte und klicken Sie auf **[!UICONTROL Save Directory to]** > *&lt;**[!UICONTROL working profile name]**>*.

**So fügen Sie einem vorhandenen Menü ein neues Menüelement hinzu**

1. Führen Sie einen der folgenden Schritte aus:

   * Erstellen Sie ein neues Element (Visualisierung, Anmerkung usw.), das einem Menü hinzugefügt werden soll:

      1. Öffnen Sie einen Arbeitsbereich in Data Workbench und erstellen Sie das gewünschte Element.
      1. Speichern Sie das Element im folgenden Verzeichnis:

         *Installationsordner von Data Workbench*\Benutzer\*Name des Arbeitsprofils*\Work

      1. Im [!DNL Profile Manager], klicken Sie auf die **[!UICONTROL Work]** Verzeichnis, um seinen Inhalt anzuzeigen.
      1. Im [!DNL User] klicken Sie mit der rechten Maustaste auf das Häkchen für die gewünschte Datei und klicken Sie auf **[!UICONTROL Copy]**.
      1. Im [!DNL User] Spalte für den gewünschten Ordner, klicken Sie auf **[!UICONTROL Paste]**.

         Eine Kopie der Datei wird im [!DNL File] -Spalte für den neuen Ordner und ein Häkchen für die neue Datei wird im [!DNL User] Spalte.
   * Kopieren Sie ein vorhandenes Element aus einem Menü (Ordner) in ein anderes:

      1. Im [!DNL Profile Manager], klicken Sie auf die **[!UICONTROL Menu]** Verzeichnis, um seinen Inhalt anzuzeigen.
      1. Im *Name des Arbeitsprofils* klicken Sie mit der rechten Maustaste auf das Häkchen für die gewünschte Datei und klicken Sie auf **[!UICONTROL Make Local]**.
      1. Klicken Sie mit der rechten Maustaste auf das Häkchen für die Datei im [!DNL User] Spalte und klicken Sie auf **[!UICONTROL Copy]**.
      1. Im [!DNL User] Spalte für den gewünschten Ordner, klicken Sie auf **[!UICONTROL Paste]**. Eine Kopie der Datei wird im [!DNL File] -Spalte für den neuen Ordner und ein Häkchen für die neue Datei wird im [!DNL User] Spalte.


1. (Optional) Bearbeiten Sie die [!DNL order.txt] Datei nach Bedarf. Siehe [Menüs mithilfe von &quot;order.txt&quot;-Dateien anpassen](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999).
1. (Optional) Um die Änderungen allen Benutzern des Arbeitsprofils zur Verfügung zu stellen, klicken Sie mit der rechten Maustaste auf das weiße Häkchen für jede Datei im [!DNL User] Spalte und klicken Sie auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.
1. (Optional) Um zu vermeiden, dass ein Menüelement in mehreren Menüs angezeigt wird, sollten Sie die entsprechende Datei aus dem ursprünglichen Ordner löschen, indem Sie mit der rechten Maustaste auf das Häkchen für die Datei im *Name des Arbeitsprofils* Spalte und Klicken **[!UICONTROL Remove]** > **[!UICONTROL Yes]**.

   Wiederholen Sie diesen Schritt für das Häkchen der Datei im [!DNL User] Spalte.
