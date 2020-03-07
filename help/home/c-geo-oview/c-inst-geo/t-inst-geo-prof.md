---
description: Das mit Data WorkbenchGeography bereitgestellte Geografie-Profil ist ein internes Profil, das zusätzliche Funktionen für Ihre Adobe-Anwendung bietet.
solution: Analytics
title: Installieren des geografischen Profils
topic: Data workbench
uuid: afc0699d-e58b-481b-a3f2-ab6d6998bdd8
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Installieren des geografischen Profils{#installing-the-geography-profile}

Das mit Data WorkbenchGeography bereitgestellte Geografie-Profil ist ein internes Profil, das zusätzliche Funktionen für Ihre Adobe-Anwendung bietet.

Wie bei allen anderen von Adobe bereitgestellten internen Profilen sollte das [!DNL Geography] Profil nicht geändert werden. Alle Anpassungen müssen in Ihrem Datensatz, in Ihren rollenspezifischen Profilen oder in anderen Profilen, die Sie erstellen, vorgenommen werden.

Das [!DNL Geography] Profil enthält mehrere Transformationsdatasets mit Dateien (im [!DNL Dataset\Transformation\Geography] Ordner), die geografische Dimensionen definieren. Im Folgenden finden Sie eine Liste des Transformationsdatasets enthält Dateien, die mit dem [!DNL Geography] Profil bereitgestellt werden:

* [!DNL City.cfg]
* [!DNL Coordinates.cfg]
* [!DNL Country.cfg]
* [!DNL DMA.cfg]
* [!DNL Domain.cfg]

Jede der Dateien wird nach der von ihr definierten erweiterten Dimension benannt. Eine zusätzliche Datei definiert [!DNL IPLookup.cfg]mehrere geografische Datenfelder, die zur Definition von Dimensionen in den anderen Transformationsdatensätzen verwendet werden, einschließlich Dateien.

Weitere Informationen zum Einschließen von Dateien in den Transformationsdataset finden Sie im Handbuch zur *Datenkonfiguration*.

**So installieren Sie das[!DNL Geography]Profil auf dem Data Workbench-Server**

>[!NOTE]
>
>Bei den folgenden Installationsanweisungen wird davon ausgegangen, dass Sie Data Workbench installiert und eine Verbindung zwischen Data Workbench und dem Data Workbench-Server hergestellt haben, auf dem Sie Data Workbench installieren [!DNL Geography]. Wenn Sie dies noch nicht getan haben, finden Sie weitere Informationen im *Data Workbench-Benutzerhandbuch*.

1. Öffnen Sie den Ordner &quot;Profile&quot;in der [!DNL .zip] Datei, die Ihnen von Adobe bereitgestellt wird.
1. Kopieren Sie den [!DNL Geography] Ordner in den Ordner &quot;Profile&quot;im Installationsordner des Data Workbench-Servers. Sie möchten, wie im folgenden Beispiel gezeigt, am Ende einen [!DNL ...\Profiles\Geography] Ordner auf Ihrem Data Workbench-Server haben. Die Namen der anderen Ordner im Ordner &quot;Profiles&quot;unterscheiden sich möglicherweise von denen, die angezeigt werden.

   ![Schritt-Info](assets/Geo_installProfiles_dir.png)

1. Führen Sie die folgenden Schritte aus, um die [!DNL profile.cfg] Datei für jedes Profil zu aktualisieren, mit dem Sie Data Workbench verwenden möchten [!DNL Geography].

   1. Öffnen Sie den [!DNL Profile Manager].
   1. Klicken Sie mit der rechten Maustaste auf das Häkchen neben [!DNL profile.cfg] und klicken Sie auf **[!UICONTROL Make Local]**. Ein Häkchen für diese Datei wird in der [!DNL User] Spalte angezeigt.

   1. Klicken Sie mit der rechten Maustaste auf das neu erstellte Häkchen und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Das [!DNL profile.cfg] Fenster wird angezeigt.

   1. Klicken Sie im [!DNL profile.cfg] Fenster mit der rechten Maustaste **[!UICONTROL Directories]** und klicken Sie auf **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

      Um den neuen Ordner am Ende der Liste der Ordner hinzuzufügen, klicken Sie mit der rechten Maustaste auf die Nummer oder den Namen des letzten Ordners in der Liste und klicken Sie auf **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

   1. Geben Sie den Namen des neuen Ordners ein: [!DNL Geography].
   1. Klicken Sie mit der rechten Maustaste **[!UICONTROL (modified)]** am oberen Rand des Fensters und klicken Sie auf **[!UICONTROL Save]**.

   1. Klicken Sie in der [!DNL Profile Manager]Spalte mit der rechten Maustaste auf das Häkchen für [!DNL profile.cfg] die [!DNL User] Spalte und klicken Sie dann auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*.

      >[!NOTE]
      >
      >Speichern Sie die geänderte Konfigurationsdatei nicht in einem der von Adobe bereitgestellten internen Profile (einschließlich des [!DNL Geography] Profils), da Ihre Änderungen überschrieben werden, wenn Sie Updates für diese Profile installieren.

