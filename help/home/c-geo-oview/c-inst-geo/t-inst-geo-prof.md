---
description: Das mit Data WorkbenchGeography bereitgestellte Geography-Profil ist ein internes Profil, das zusätzliche Funktionen für Ihre Adobe App bietet.
title: Installieren des Geography-Profils
uuid: afc0699d-e58b-481b-a3f2-ab6d6998bdd8
exl-id: 9ab07fd4-d6e7-495e-ba34-04e53c9b0aa3
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 2%

---

# Installieren des Geography-Profils{#installing-the-geography-profile}

{{eol}}

Das mit Data WorkbenchGeography bereitgestellte Geography-Profil ist ein internes Profil, das zusätzliche Funktionen für Ihre Adobe App bietet.

Wie bei allen anderen von Adobe bereitgestellten internen Profilen wird die [!DNL Geography] Profil sollte nicht geändert werden. Alle Anpassungen müssen in Ihrem Datensatz oder in rollenspezifischen Profilen oder anderen von Ihnen erstellten Profilen vorgenommen werden.

Die [!DNL Geography] Das Profil enthält mehrere Transformations-Datensatz-Include-Dateien (unter [!DNL Dataset\Transformation\Geography] -Ordner), die geografische Dimensionen definieren. Im Folgenden finden Sie eine Liste des Transformationsdatensatzes mit Dateien, die mit der Variablen [!DNL Geography] profile:

* [!DNL City.cfg]
* [!DNL Coordinates.cfg]
* [!DNL Country.cfg]
* [!DNL DMA.cfg]
* [!DNL Domain.cfg]

Jede der Dateien wird nach der erweiterten Dimension benannt, die sie definiert. eine zusätzliche Datei, [!DNL IPLookup.cfg]definiert mehrere geografische Datenfelder, die zur Definition von Dimensionen im anderen Transformationsdatensatz verwendet werden, einschließlich Dateien.

Informationen zu den Konvertierungsdatensätzen für Include-Dateien finden Sie in der *Anleitung zur Datensatzkonfiguration*.

**So installieren Sie die [!DNL Geography] Profil auf dem Data Workbench-Server**

>[!NOTE]
>
>Bei den folgenden Installationsanweisungen wird davon ausgegangen, dass Sie Data Workbench installiert und eine Verbindung zwischen Data Workbench und dem Data Workbench-Server hergestellt haben, auf dem Sie Data Workbench installieren [!DNL Geography]. Wenn Sie dies noch nicht getan haben, lesen Sie den Abschnitt *Data Workbench-Benutzerhandbuch*.

1. Öffnen Sie den Ordner Profile im [!DNL .zip] -Datei, die Sie nach Adobe erhalten haben.
1. Kopieren Sie die [!DNL Geography] im Ordner Profile in Ihrem Installationsordner für den Data Workbench-Server. Sie möchten am Ende eine [!DNL ...\Profiles\Geography] Ordner auf Ihrem Data Workbench-Server, wie im folgenden Beispiel gezeigt. Die Namen der anderen Ordner im Ordner Profile unterscheiden sich möglicherweise von denen, die angezeigt werden.

   ![Schritt-Info](assets/Geo_installProfiles_dir.png)

1. Führen Sie die folgenden Schritte aus, um die [!DNL profile.cfg] Datei für jedes Profil, für das Sie Data Workbench verwenden möchten [!DNL Geography].

   1. Öffnen Sie den [!DNL Profile Manager].
   1. Klicken Sie mit der rechten Maustaste auf das Häkchen neben [!DNL profile.cfg] und klicken Sie auf **[!UICONTROL Make Local]**. Ein Häkchen für diese Datei wird im [!DNL User] Spalte.

   1. Klicken Sie mit der rechten Maustaste auf das neu erstellte Häkchen und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Die [!DNL profile.cfg] angezeigt.

   1. Im [!DNL profile.cfg] Fenster, Rechtsklick **[!UICONTROL Directories]** und klicken Sie auf **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

      Um den neuen Ordner am Ende der Liste der Ordner hinzuzufügen, klicken Sie mit der rechten Maustaste auf die Nummer oder den Namen des letzten Ordners in der Liste und klicken Sie auf **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

   1. Geben Sie den Namen des neuen Ordners ein: [!DNL Geography].
   1. Rechtsklick **[!UICONTROL (modified)]** Klicken Sie oben im Fenster auf **[!UICONTROL Save]**.

   1. Im [!DNL Profile Manager]klicken Sie mit der rechten Maustaste auf das Häkchen für [!DNL profile.cfg] im [!DNL User] und klicken Sie auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*.

      >[!NOTE]
      >
      >Speichern Sie die geänderte Konfigurationsdatei nicht in einem der von Adobe bereitgestellten internen Profile (einschließlich der Variablen [!DNL Geography] Profil), da Ihre Änderungen bei der Installation von Updates für diese Profile überschrieben werden.
