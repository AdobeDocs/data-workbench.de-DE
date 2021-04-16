---
description: Das mit Data WorkbenchGeography bereitgestellte Geografie-Profil ist ein internes Profil, das zusätzliche Funktionen für Ihre Adobe bietet.
title: Installieren des Geography-Profils
uuid: afc0699d-e58b-481b-a3f2-ab6d6998bdd8
exl-id: 9ab07fd4-d6e7-495e-ba34-04e53c9b0aa3
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 2%

---

# Installieren des Geography-Profils{#installing-the-geography-profile}

Das mit Data WorkbenchGeography bereitgestellte Geografie-Profil ist ein internes Profil, das zusätzliche Funktionen für Ihre Adobe bietet.

Wie bei allen anderen internen Profilen, die von der Adobe bereitgestellt werden, sollte das [!DNL Geography]-Profil nicht geändert werden. Alle Anpassungen müssen in Ihrem Datensatz oder in rollenspezifischen Profilen oder anderen von Ihnen erstellten Profilen vorgenommen werden.

Das [!DNL Geography]-Profil enthält mehrere Transformationsdatasets mit Dateien (im Ordner [!DNL Dataset\Transformation\Geography]), die geografische Dimensionen definieren. Im Folgenden finden Sie eine Liste des Transformationsdatasets enthält Dateien, die mit dem Profil [!DNL Geography] bereitgestellt werden:

* [!DNL City.cfg]
* [!DNL Coordinates.cfg]
* [!DNL Country.cfg]
* [!DNL DMA.cfg]
* [!DNL Domain.cfg]

Jede der Dateien wird nach der von ihr definierten erweiterten Dimension benannt. Eine zusätzliche Datei, [!DNL IPLookup.cfg], definiert mehrere geografische Datenfelder, die zum Definieren von Dimensionen im anderen Transformationsdataset verwendet werden, einschließlich Dateien.

Weitere Informationen zu Transformationsdataset-Include-Dateien finden Sie im Handbuch *Dataset-Konfiguration*.

**So installieren Sie das  [!DNL Geography] Profil auf dem Data Workbench-Server**

>[!NOTE]
>
>Bei den folgenden Installationsanweisungen wird davon ausgegangen, dass Sie Data Workbench installiert und eine Verbindung zwischen Data Workbench und dem Data Workbench-Server hergestellt haben, auf dem Sie Data Workbench [!DNL Geography] installieren. Wenn Sie dies noch nicht getan haben, lesen Sie das *Data Workbench Benutzerhandbuch*.

1. Öffnen Sie den Ordner &quot;Profils&quot;in der Datei [!DNL .zip], die Sie nach Adobe erhalten haben.
1. Kopieren Sie den Ordner [!DNL Geography] in den Ordner &quot;Profils&quot;im Installationsordner des Data Workbench-Servers. Sie möchten, wie im folgenden Beispiel gezeigt, am Ende einen Ordner [!DNL ...\Profiles\Geography] auf Ihrem Data Workbench-Server haben. Die Namen der anderen Ordner im Ordner &quot;Profils&quot;unterscheiden sich möglicherweise von denen, die angezeigt werden.

   ![Schritt-Info](assets/Geo_installProfiles_dir.png)

1. Führen Sie die folgenden Schritte aus, um die [!DNL profile.cfg]-Datei für jedes Profil zu aktualisieren, mit dem Sie Data Workbench [!DNL Geography] verwenden möchten.

   1. Öffnen Sie den [!DNL Profile Manager].
   1. Klicken Sie mit der rechten Maustaste auf das Häkchen neben [!DNL profile.cfg] und klicken Sie auf **[!UICONTROL Make Local]**. In der Spalte [!DNL User] wird ein Häkchen für diese Datei angezeigt.

   1. Klicken Sie mit der rechten Maustaste auf das neu erstellte Häkchen und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Das Fenster [!DNL profile.cfg] wird angezeigt.

   1. Klicken Sie im Fenster [!DNL profile.cfg] mit der rechten Maustaste auf **[!UICONTROL Directories]** und dann auf **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

      Um den neuen Ordner am Ende der Liste der Ordner hinzuzufügen, klicken Sie mit der rechten Maustaste auf die Nummer oder den Namen des letzten Ordners in der Liste und klicken Sie auf **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

   1. Geben Sie den Namen des neuen Ordners ein: [!DNL Geography].
   1. Klicken Sie mit der rechten Maustaste auf **[!UICONTROL (modified)]** oben im Fenster und klicken Sie auf **[!UICONTROL Save]**.

   1. Klicken Sie in der Spalte [!DNL Profile Manager] mit der rechten Maustaste auf das Häkchen für [!DNL profile.cfg] in der Spalte [!DNL User] und dann auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]***.

      >[!NOTE]
      >
      >Speichern Sie die geänderte Konfigurationsdatei nicht in einem der von der Adobe bereitgestellten internen Profil (einschließlich des [!DNL Geography]-Profils), da Ihre Änderungen bei der Installation von Updates auf diesen Profilen überschrieben werden.
