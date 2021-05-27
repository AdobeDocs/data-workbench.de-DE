---
description: Bei den Datendienstprofilen (IP-Geo-Intelligence und IP-Geolokation) handelt es sich um interne Profile, die zusätzliche Funktionen für Ihre Adobe App bieten.
title: Installieren des Profils des Daten-Services
uuid: 1c03d0cd-7eaa-4e48-bbff-8bfad8fed9e9
exl-id: 51d080bb-f874-426c-91ea-3912ffd38419
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '746'
ht-degree: 1%

---

# Installieren des Profils des Daten-Services{#installing-the-data-service-profile}

Bei den Datendienstprofilen (IP-Geo-Intelligence und IP-Geolokation) handelt es sich um interne Profile, die zusätzliche Funktionen für Ihre Adobe App bieten.

Wie alle anderen von Adobe bereitgestellten internen Profile sollten diese Profile nicht geändert werden. Alle Anpassungen müssen in Ihrem Datensatz oder in rollenspezifischen Profilen oder anderen von Ihnen erstellten Profilen vorgenommen werden.

Die Datendienstprofile enthalten die folgenden Datensatzdateien, die auf einem Data Workbench-Server installiert werden sollen:

* **Profile\*Profilname *\Dataset\Log Processing\Traffic\IP.cfg:** Listet das c-ip-Feld auf, das von der Protokollverarbeitung zur Transformation übergeben werden soll.
* **Profile\*Profilname *\Dataset\Transformation\Geography\IPLookup.cfg:** Definiert eine IPLookup-Transformation, die mithilfe der bereitgestellten IP-Geo-Intelligence- oder IP-Geo-Location-Lookup-Datei mehrere Felder geografischer Daten erzeugt.

Weitere Informationen zu Konvertierungsdatensätzen mit Include-Dateien finden Sie im *Handbuch zur Datensatzkonfiguration*.

Darüber hinaus stellt jedes Datendienstprofil eine Elementpunkteschichtdatei mit dem Namen [!DNL IP Coordinates.layer] bereit. Mit dieser Schichtdatei können Sie Positionen in Ihrem Datensatz auf der Welt dynamisch mithilfe von IP-Adressen zuordnen. Nach der Installation wird die Ebene im Ordner Profile\*data service name*\Maps im Installationsordner des Data Workbench-Servers gespeichert.

Die Datei [!DNL IP Coordinates.layer] verweist auf die Dimension Koordinaten , die in der mit dem Profil [!DNL Geography] bereitgestellten Datei [!DNL Coordinates.cfg] definiert ist und sich im Ordner &quot;Dataset\Transformation\Geography folder&quot;befindet. Jedes Element der Dimension Koordinaten , das in Ihrem Datensatz definiert ist, wird auf der Welt mithilfe der in diesem Element enthaltenen Informationen zu Breiten- und Längengrad zugeordnet. Weitere Informationen zu Elementpunktebenen, die dynamische Punkte verwenden, finden Sie unter [Definieren von Elementpunktebenen mit dynamischen Punkten](../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyr-file-frmt/c-dyn-pts.md#concept-77ae65bedc3f465489bc135ae7e3c2f3).

>[!NOTE]
>
>Wenn Sie den IP-Geo-Intelligence- und IP-Geolokations-Datendienst vor Version 5.1 installiert haben, verweist Ihre Elementpunktebenen-Datei auf eine Lookup-Datei, anstatt dynamische Punkte zu verwenden. Jede Ebenendatei verweist auf die IP-Geocode-Lookup-Datei und die IP-Geocode-Dimension. Die IP-Geocode-Lookup-Datei enthält eine Liste von IP-Geocodes (geografische Standorte basierend auf der IP-Adresse) sowie jeweils den Längen- und Breitengrad. Jedes Element einer IP-Geocode-Dimension, das in Ihrem Datensatz definiert ist, wird auf der Welt mithilfe des Breiten- und Längengrads zugeordnet, der für diese IP-Geocode in der IP-Geocode-Lookup-Datei aufgelistet ist.

Der Name der Ebenendatei und die Dateien, auf die sie verweist, unterscheiden sich für jeden Datendienst:

* Die [!DNL IP Geocodes D.layer]-Datei wird mit dem IP-Geo-Intelligence-Profil (Digital Envoy) installiert. Diese Elementpunktebene verweist auf die Suchdatei [!DNL IP Geocodes D yyyymmdd.txt] (die Sie regelmäßig aktualisieren müssen) und die Dimension IP-Geocode D .

* Die Datei [!DNL IP Geocodes Q.layer] wird mit dem IP-Geostandort-Profil (Quova) installiert. Diese Elementpunktebene verweist auf die Suchdatei [!DNL IP Geocodes Q yyyymmdd.txt] (die Sie regelmäßig aktualisieren müssen) und die Dimension IP-Geocode Q .

Weitere Informationen zu Elementpunktebenen, die Lookup-Dateien verwenden, finden Sie unter [Definieren von Elementpunktebenen mit Verweis auf Lookup-Dateien](../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyrs-ref-lkp-files.md#concept-c40bd0890a984112bce831b596827f0f).

## So installieren Sie das IP-Geo-Intelligence- oder IP-Geostandortprofil {#section-6dff402ffdcb4b31b9bcd0c40a5f7625}

>[!NOTE]
>
>In den folgenden Installationsanweisungen wird davon ausgegangen, dass Sie Data Workbench installiert und eine Verbindung zwischen Data Workbench und dem Data Workbench-Server hergestellt haben, auf dem Sie Data Workbench [!DNL Geography] installieren. Wenn Sie dies noch nicht getan haben, lesen Sie das *Data Workbench-Benutzerhandbuch*.

1. Öffnen Sie den Ordner Profile in der Datei [!DNL .zip] , die Sie von Adobe erhalten haben.
1. Kopieren Sie den Ordner &quot;IP-Geo-Intelligence&quot;oder &quot;IP-Geo-Speicherort&quot;in den Ordner &quot;Profile&quot;in Ihrem Installationsordner für den Data Workbench-Server. Sie wollen mit einem ...\Profiles\IP Geo-intelligence folder or a ..\Profiles\IP Geo-location on your data workbench server as shown in the following example Die Namen der anderen Ordner im Ordner [!DNL Profiles] unterscheiden sich möglicherweise von denen, die angezeigt werden.

   ![](assets/Geo_installProfiles_dirIP.png)

1. Führen Sie die folgenden Schritte aus, um die Datei [!DNL profile.cfg] für jedes Profil zu aktualisieren, für das Sie das Profil [!DNL IP Geo-intelligence] oder [!DNL IP Geo-location] verwenden möchten.

   1. Öffnen Sie den **[!UICONTROL Profile Manager]**.
   1. Klicken Sie mit der rechten Maustaste auf das Häkchen neben [!DNL profile.cfg] und klicken Sie auf **[!UICONTROL Make Local]**. Ein Häkchen für diese Datei wird in der Spalte [!DNL User] angezeigt.

   1. Klicken Sie mit der rechten Maustaste auf das neu erstellte Häkchen und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Das Fenster [!DNL profile.cfg] wird angezeigt.

   1. Klicken Sie im Fenster [!DNL profile.cfg]mit der rechten Maustaste auf **[!UICONTROL Directories]** und klicken Sie auf **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

      Um das neue Verzeichnis am Ende der Verzeichnisliste hinzuzufügen, klicken Sie mit der rechten Maustaste auf die Nummer oder den Namen des letzten Verzeichnisses in der Liste und klicken Sie auf **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

   1. Geben Sie den Namen des neuen Ordners ein: [!DNL IP Geo-intelligence] oder I [!DNL P Geo-location].

   1. Klicken Sie oben im Fenster mit der rechten Maustaste auf **[!UICONTROL (modified)]** und klicken Sie auf **[!UICONTROL Save]**.

   1. Klicken Sie in der Spalte [!DNL Profile Manager] mit der rechten Maustaste auf das Häkchen für [!DNL profile.cfg] in der Spalte [!DNL User] und klicken Sie dann auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]***.

>[!NOTE]
>
>Speichern Sie die geänderte Konfigurationsdatei nicht in einem der von Adobe bereitgestellten internen Profile (einschließlich des Profils [!DNL IP Geo-location] oder [!DNL IP Geo-intelligence] ), da Ihre Änderungen bei der Installation von Updates für diese Profile überschrieben werden.
