---
description: Diese Schritte gelten nur für das Erstellen von Untermenüs und Menüelementen im Menü "Fenster"von Workspace.
title: Erstellen von Arbeitsbereichmenüs und Menüelementen
uuid: 9565fe7a-fa4c-42b6-9aa5-b652a2d62796
exl-id: 26f2b85c-ab23-41a4-bf4b-9e507952fede
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '503'
ht-degree: 3%

---

# Erstellen von Arbeitsbereichmenüs und Menüelementen{#create-a-workspace-menu-and-menu-item}

Diese Schritte gelten nur für das Erstellen von Untermenüs und Menüelementen im Menü &quot;Fenster&quot;von Workspace.

Sie können die Metrik- und Dimensionsmenüs anpassen, indem Sie neue Ordner und abgeleitete Metriken und Dimensionen erstellen. Weitere Informationen finden Sie unter [Erstellen und Bearbeiten abgeleiteter Metriken](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-drvd-mtrcs.md#concept-e41723b342a849309874b26232224a40) und [Erstellen und Bearbeiten abgeleiteter Dimensionen](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-dvrd-dim.md#concept-ece3c3ea8cdf4fc796680173993bff93).

**So erstellen Sie ein neues Menü im Arbeitsflächenfenster**

1. Klicken Sie im Ordner [!DNL Profile Manager] auf das **[!UICONTROL Menu]**-Verzeichnis, um den Inhalt Ansicht.
1. Klicken Sie in der Spalte [!DNL User] des Menüverzeichnisses auf **[!UICONTROL Create]** > **[!UICONTROL Folder]**. Ein Ordner mit dem Namen &quot;Neuer Ordner&quot;wird in der Spalte [!DNL File] für [!DNL Menu] angezeigt.

   >[!NOTE]
   >
   >Sie können auch einen neuen Ordner für jeden Unterordner im Ordner &quot;Menu&quot;erstellen.

1. Benennen Sie den neuen Ordner um, indem Sie mit der rechten Maustaste in die Spalte [!DNL User] für den Ordner klicken und den neuen Namen in den Parameter Dir eingeben.
1. hinzufügen Sie die gewünschten Dateien in den neuen Ordner.
1. (Optional) Klicken Sie in der Spalte [!DNL User] für den neuen Ordner auf **[!UICONTROL Create]** > **[!UICONTROL order.txt]**.

   Eine [!DNL order.txt]-Datei wird in der Spalte [!DNL File] für den neuen Ordner angezeigt, und ein Häkchen für die neue Datei wird in der Spalte [!DNL User] angezeigt.

1. (Optional) Bearbeiten Sie nach Bedarf die Datei [!DNL order.txt]. Siehe [Anpassen von Menüs mit order.txt-Dateien](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999).
1. (Optional) Um die Änderungen allen Benutzern des funktionierenden Profils zur Verfügung zu stellen, klicken Sie mit der rechten Maustaste auf das weiße Häkchen für den Ordner in der Spalte [!DNL User] und klicken Sie auf **[!UICONTROL Save Directory to]** > *&lt;**[!UICONTROL working profile name]***.

**So fügen Sie einem vorhandenen Menü ein neues Menüelement hinzu**

1. Führen Sie einen der folgenden Schritte aus:

   * Erstellen Sie ein neues Element (Visualisierung, Anmerkung usw.), das einem Menü hinzugefügt werden soll:

      1. Öffnen Sie einen Arbeitsbereich in der Data Workbench und erstellen Sie das gewünschte Element.
      1. Speichern Sie das Element im folgenden Verzeichnis:

         *Installationsordner* für Data Workbench\User\*Name des funktionierenden Profils*\Work

      1. Klicken Sie im Ordner [!DNL Profile Manager] auf das **[!UICONTROL Work]**-Verzeichnis, um den Inhalt Ansicht.
      1. Klicken Sie in der Spalte [!DNL User] mit der rechten Maustaste auf das Häkchen für die gewünschte Datei und klicken Sie auf **[!UICONTROL Copy]**.
      1. Klicken Sie in der Spalte [!DNL User] für den gewünschten Ordner auf **[!UICONTROL Paste]**.

         Eine Kopie der Datei wird in der Spalte [!DNL File] für den neuen Ordner angezeigt und ein Häkchen für die neue Datei wird in der Spalte [!DNL User] angezeigt.
   * Kopieren Sie ein vorhandenes Element aus einem Menü (Ordner) in ein anderes:

      1. Klicken Sie im Ordner [!DNL Profile Manager] auf das **[!UICONTROL Menu]**-Verzeichnis, um den Inhalt Ansicht.
      1. Klicken Sie in der Spalte *Arbeitsdateiname* mit der rechten Maustaste auf das Häkchen der gewünschten Profil und klicken Sie auf **[!UICONTROL Make Local]**.
      1. Klicken Sie mit der rechten Maustaste auf das Häkchen für die Datei in der Spalte [!DNL User] und klicken Sie auf **[!UICONTROL Copy]**.
      1. Klicken Sie in der Spalte [!DNL User] für den gewünschten Ordner auf **[!UICONTROL Paste]**. Eine Kopie der Datei wird in der Spalte [!DNL File] für den neuen Ordner angezeigt und ein Häkchen für die neue Datei wird in der Spalte [!DNL User] angezeigt.


1. (Optional) Bearbeiten Sie nach Bedarf die Datei [!DNL order.txt]. Siehe [Anpassen von Menüs mit order.txt-Dateien](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999).
1. (Optional) Um die Änderungen allen Benutzern des funktionierenden Profils zur Verfügung zu stellen, klicken Sie mit der rechten Maustaste auf das weiße Häkchen für jede Datei in der Spalte [!DNL User] und klicken Sie auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]***.
1. (Optional) Um zu vermeiden, dass ein Menüelement in mehreren Menüs angezeigt wird, sollten Sie die entsprechende Profil-Datei aus dem Originalordner löschen, indem Sie mit der rechten Maustaste auf das Häkchen für die Datei in der Spalte *Name des Arbeitsordners* klicken und **[!UICONTROL Remove]** > **[!UICONTROL Yes]** klicken.

   Wiederholen Sie diesen Schritt für das Häkchen der Datei in der Spalte [!DNL User].
