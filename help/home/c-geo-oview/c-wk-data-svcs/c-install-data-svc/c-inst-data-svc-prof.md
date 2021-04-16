---
description: Bei den Datendienst-Profilen (IP Geo-Intelligence und IP Geo-Location) handelt es sich um interne Profil, die zusätzliche Funktionen für Ihre Adobe bieten.
title: Installieren des Profils des Daten-Services
uuid: 1c03d0cd-7eaa-4e48-bbff-8bfad8fed9e9
exl-id: 51d080bb-f874-426c-91ea-3912ffd38419
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '746'
ht-degree: 1%

---

# Installieren des Profils des Daten-Services{#installing-the-data-service-profile}

Bei den Datendienst-Profilen (IP Geo-Intelligence und IP Geo-Location) handelt es sich um interne Profil, die zusätzliche Funktionen für Ihre Adobe bieten.

Wie bei allen anderen internen Profilen der Adobe sollten diese Profil nicht geändert werden. Alle Anpassungen müssen in Ihrem Datensatz oder in rollenspezifischen Profilen oder anderen von Ihnen erstellten Profilen vorgenommen werden.

Zu den Datendienst-Profilen gehören die folgenden Datendateien, die auf einem Datenbasis-Server installiert werden sollen:

* **Profile\*Profil name *\Dataset\Log Processing\Traffic\IP.cfg:** Liste des c-ip-Felds, das von der Protokollverarbeitung zur Konvertierung weitergeleitet wird.
* **Profile\*Profil name *\Dataset\Transformation\Geography\IPLookup.cfg:** Definiert eine IPLookup-Transformation, die mithilfe der bereitgestellten IP-Geo-Intelligence- oder IP-Geo-Location-Nachschlagedatei mehrere geografische Datenfelder erstellt.

Weitere Informationen zu Transformationsdataset-Include-Dateien finden Sie im Handbuch *Dataset-Konfiguration*.

Darüber hinaus stellt jedes Datendienst-Profil eine Elementpunktebenendatei mit dem Namen [!DNL IP Coordinates.layer] bereit. Mit dieser Ebenendatei können Sie Positionen in Ihrem Datensatz auf der Welt dynamisch mithilfe von IP-Adressen zuordnen. Nach der Installation wird die Ebene im Installationsordner des Data Workbench-Servers im Ordner &quot;Profils\*data service name*\Maps&quot;gespeichert.

Die Datei [!DNL IP Coordinates.layer] verweist auf die Dimension &quot;Koordinaten&quot;, die in der Datei [!DNL Coordinates.cfg] definiert ist, die mit dem Profil [!DNL Geography] bereitgestellt wird und sich im Ordner &quot;Dataset\Transformation\Geography folder&quot;befindet. Jedes Element der Dimension &quot;Koordinaten&quot;in Ihrem Datensatz wird mithilfe der Breiten- und Längengradinformationen, die in diesem Element enthalten sind, auf der Welt zugeordnet. Weitere Informationen zu Elementpunktebenen, die dynamische Punkte verwenden, finden Sie unter [Definieren von Elementpunktebenen mit dynamischen Punkten](../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyr-file-frmt/c-dyn-pts.md#concept-77ae65bedc3f465489bc135ae7e3c2f3).

>[!NOTE]
>
>Wenn Sie den IP-Geo-Intelligence- und IP-Geo-Location-Datendienst vor Version 5.1 installiert haben, verweist Ihre Elementpunktschichtdatei auf eine Lookup-Datei, anstatt dynamische Punkte zu verwenden. Jede Ebenendatei verweist auf die IP-Geocodes-Nachschlagedatei und die IP-Geocode-Dimension. Die IP-Geocodes-Nachschlagedatei enthält eine Liste von IP-Geocodes (geografische Standorte, die auf IP-Adressen basieren) und Breiten- und Längengrad für jede IP-Datei. Jedes Element einer IP-Geocode-Dimension, das in Ihrem Datensatz definiert ist, wird auf der Welt mithilfe der Breiten- und Längengrade zugeordnet, die für diesen IP-Geocode in der IP-Geocodes-Nachschlagedatei aufgeführt sind.

Der Name der Ebenendatei und die referenzierten Dateien unterscheiden sich für jeden Datendienst:

* Die [!DNL IP Geocodes D.layer]-Datei wird mit dem IP-Geo-Intelligence-Profil (Digital Envoy) installiert. Diese Elementpunktebene verweist auf die [!DNL IP Geocodes D yyyymmdd.txt]-Nachschlagedatei (die Sie regelmäßig aktualisieren müssen) und die IP-Geocode-D-Dimension.

* Die [!DNL IP Geocodes Q.layer]-Datei wird mit dem IP-Geo-Position-Profil (Quova) installiert. Diese Elementpunktebene verweist auf die [!DNL IP Geocodes Q yyyymmdd.txt]-Lookup-Datei (die Sie regelmäßig aktualisieren müssen) und die IP-Geocode-Q-Dimension.

Weitere Informationen zu Elementpunktebenen, die Lookup-Dateien verwenden, finden Sie unter [Definieren von Elementpunktebenen, die auf Lookup-Dateien verweisen](../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyrs-ref-lkp-files.md#concept-c40bd0890a984112bce831b596827f0f).

## So installieren Sie das IP-Geo-Intelligence- oder IP-Geo-Location-Profil {#section-6dff402ffdcb4b31b9bcd0c40a5f7625}

>[!NOTE]
>
>Bei den folgenden Installationsanweisungen wird davon ausgegangen, dass Sie Data Workbench installiert und eine Verbindung zwischen Data Workbench und dem Data Workbench-Server hergestellt haben, auf dem Sie Data Workbench [!DNL Geography] installieren. Wenn Sie dies noch nicht getan haben, lesen Sie das *Data Workbench Benutzerhandbuch*.

1. Öffnen Sie den Ordner &quot;Profils&quot;aus der [!DNL .zip]-Datei, die Sie von der Adobe erhalten haben.
1. Kopieren Sie den Ordner &quot;IP-Geo-Intelligence&quot;oder &quot;IP-Geo-Speicherort&quot;in den Ordner &quot;Profils&quot;im Installationsordner des Data Workbench-Servers. Du willst am Ende mit einem ...\Profiles\IP Geo-intelligence folder or a ...\Profiles\IP Geo-location on your data workbench server as shown in the following example. Die Namen der anderen Ordner im Ordner [!DNL Profiles] können von denen abweichen, die angezeigt werden.

   ![](assets/Geo_installProfiles_dirIP.png)

1. Führen Sie die folgenden Schritte aus, um die [!DNL profile.cfg]-Datei für jedes Profil zu aktualisieren, mit dem Sie das [!DNL IP Geo-intelligence]- oder [!DNL IP Geo-location]-Profil verwenden möchten.

   1. Öffnen Sie den **[!UICONTROL Profile Manager]**.
   1. Klicken Sie mit der rechten Maustaste auf das Häkchen neben [!DNL profile.cfg] und klicken Sie auf **[!UICONTROL Make Local]**. In der Spalte [!DNL User] wird ein Häkchen für diese Datei angezeigt.

   1. Klicken Sie mit der rechten Maustaste auf das neu erstellte Häkchen und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Das Fenster [!DNL profile.cfg] wird angezeigt.

   1. Klicken Sie im Fenster [!DNL profile.cfg]mit der rechten Maustaste auf **[!UICONTROL Directories]** und dann auf **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

      Um den neuen Ordner am Ende der Liste der Ordner hinzuzufügen, klicken Sie mit der rechten Maustaste auf die Nummer oder den Namen des letzten Ordners in der Liste und klicken Sie auf **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

   1. Geben Sie den Namen des neuen Ordners ein: [!DNL IP Geo-intelligence] oder I [!DNL P Geo-location].

   1. Klicken Sie mit der rechten Maustaste auf **[!UICONTROL (modified)]** oben im Fenster und klicken Sie auf **[!UICONTROL Save]**.

   1. Klicken Sie in der Spalte [!DNL Profile Manager] mit der rechten Maustaste auf das Häkchen für [!DNL profile.cfg] in der Spalte [!DNL User] und dann auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]***.

>[!NOTE]
>
>Speichern Sie die geänderte Konfigurationsdatei nicht in einem der von der Adobe bereitgestellten internen Profil (einschließlich des [!DNL IP Geo-location]- oder [!DNL IP Geo-intelligence]-Profils), da Ihre Änderungen bei der Installation von Updates auf diesen Profilen überschrieben werden.
