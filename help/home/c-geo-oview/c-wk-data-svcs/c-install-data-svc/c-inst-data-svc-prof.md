---
description: Bei den Datendienstprofilen (IP-Geo-Intelligence und IP-Geolokation) handelt es sich um interne Profile, die zusätzliche Funktionen für Ihre Adobe App bieten.
title: Installieren des Profils des Daten-Services
uuid: 1c03d0cd-7eaa-4e48-bbff-8bfad8fed9e9
exl-id: 51d080bb-f874-426c-91ea-3912ffd38419
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '746'
ht-degree: 1%

---

# Installieren des Profils des Daten-Services{#installing-the-data-service-profile}

{{eol}}

Bei den Datendienstprofilen (IP-Geo-Intelligence und IP-Geolokation) handelt es sich um interne Profile, die zusätzliche Funktionen für Ihre Adobe App bieten.

Wie alle anderen von Adobe bereitgestellten internen Profile sollten diese Profile nicht geändert werden. Alle Anpassungen müssen in Ihrem Datensatz oder in rollenspezifischen Profilen oder anderen von Ihnen erstellten Profilen vorgenommen werden.

Die Datendienstprofile enthalten die folgenden Datensatzdateien, die auf einem Data Workbench-Server installiert werden sollen:

* **Profile\*Profilname *\DataSet\Log Processing\Traffic\IP.cfg:** Listet das c-ip-Feld auf, das von der Protokollverarbeitung zur Transformation übergeben werden soll.
* **Profile\*Profilname *\Dataset\Transformation\Geography\IPLookup.cfg:** Definiert eine IPLookup-Transformation, die mithilfe der bereitgestellten IP-Geo-Intelligence- oder IP-Geo-Position-Lookup-Datei mehrere Felder geografischer Daten erzeugt.

Informationen zu den Konvertierungsdatensätzen für Include-Dateien finden Sie in der *Anleitung zur Datensatzkonfiguration*.

Darüber hinaus stellt jedes Datendienstprofil eine Elementpunkteschichtdatei mit dem Namen [!DNL IP Coordinates.layer]. Mit dieser Schichtdatei können Sie Positionen in Ihrem Datensatz auf der Welt dynamisch mithilfe von IP-Adressen zuordnen. Nach der Installation wird die Ebene im Ordner Profile\*data service name*\Maps im Installationsordner des Data Workbench-Servers gespeichert.

Die [!DNL IP Coordinates.layer] -Datei referenziert die Dimension Koordinaten , die in der [!DNL Coordinates.cfg] -Datei, die mit dem [!DNL Geography] Profil und befinden sich im Ordner Datensatz\Transformation\Geografie . Jedes Element der Dimension Koordinaten , das in Ihrem Datensatz definiert ist, wird auf der Welt mithilfe der in diesem Element enthaltenen Informationen zu Breiten- und Längengrad zugeordnet. Weitere Informationen zu Elementpunktebenen, die dynamische Punkte verwenden, finden Sie unter [Definieren von Elementpunktebenen mit dynamischen Punkten](../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyr-file-frmt/c-dyn-pts.md#concept-77ae65bedc3f465489bc135ae7e3c2f3).

>[!NOTE]
>
>Wenn Sie den IP-Geo-Intelligence- und IP-Geolokations-Datendienst vor Version 5.1 installiert haben, verweist Ihre Elementpunktebenen-Datei auf eine Lookup-Datei, anstatt dynamische Punkte zu verwenden. Jede Ebenendatei verweist auf die IP-Geocode-Lookup-Datei und die IP-Geocode-Dimension. Die IP-Geocode-Lookup-Datei enthält eine Liste von IP-Geocodes (geografische Standorte basierend auf der IP-Adresse) sowie jeweils den Längen- und Breitengrad. Jedes Element einer IP-Geocode-Dimension, das in Ihrem Datensatz definiert ist, wird auf der Welt mithilfe des Breiten- und Längengrads zugeordnet, der für diese IP-Geocode in der IP-Geocode-Lookup-Datei aufgelistet ist.

Der Name der Ebenendatei und die Dateien, auf die sie verweist, unterscheiden sich für jeden Datendienst:

* Die [!DNL IP Geocodes D.layer] -Datei mit dem IP-Geo-Intelligence-Profil (Digital Envoy) installiert. Diese Elementpunktebene verweist auf [!DNL IP Geocodes D yyyymmdd.txt] Suchdatei (die Sie regelmäßig aktualisieren müssen) und die Dimension IP-Geocode-D .

* Die [!DNL IP Geocodes Q.layer] -Datei mit dem IP-Geostandort-Profil (Quova) installiert. Diese Elementpunktebene verweist auf [!DNL IP Geocodes Q yyyymmdd.txt] Suchdatei (die Sie regelmäßig aktualisieren müssen) und die Dimension IP-Geocode Q .

Weitere Informationen zu Elementpunktebenen, die Lookup-Dateien verwenden, finden Sie unter [Definieren von Elementpunktebenen mit Verweis auf Lookup-Dateien](../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyrs-ref-lkp-files.md#concept-c40bd0890a984112bce831b596827f0f).

## So installieren Sie das IP-Geo-Intelligence- oder IP-Geostandortprofil {#section-6dff402ffdcb4b31b9bcd0c40a5f7625}

>[!NOTE]
>
>Bei den folgenden Installationsanweisungen wird davon ausgegangen, dass Sie Data Workbench installiert und eine Verbindung zwischen Data Workbench und dem Data Workbench-Server hergestellt haben, auf dem Sie Data Workbench installieren [!DNL Geography]. Wenn Sie dies noch nicht getan haben, lesen Sie den Abschnitt *Data Workbench-Benutzerhandbuch*.

1. Öffnen Sie den Ordner Profile im [!DNL .zip] -Datei, die Sie von Adobe erhalten haben.
1. Kopieren Sie den Ordner &quot;IP-Geo-Intelligence&quot;oder &quot;IP-Geo-Speicherort&quot;in den Ordner &quot;Profile&quot;in Ihrem Installationsordner für den Data Workbench-Server. Sie wollen mit einem ...\Profiles\IP Geo-Intelligence-Ordner oder ein ...\Profiles\IP Geolocation auf Ihrem Data Workbench-Server, wie im folgenden Beispiel gezeigt. Die Namen der anderen Ordner in der [!DNL Profiles] kann sich von den angezeigten unterscheiden.

   ![](assets/Geo_installProfiles_dirIP.png)

1. Führen Sie die folgenden Schritte aus, um die [!DNL profile.cfg] Datei für jedes Profil, für das Sie die [!DNL IP Geo-intelligence] oder [!DNL IP Geo-location] Profil.

   1. Öffnen Sie den **[!UICONTROL Profile Manager]**.
   1. Klicken Sie mit der rechten Maustaste auf das Häkchen neben [!DNL profile.cfg] und klicken Sie auf **[!UICONTROL Make Local]**. Ein Häkchen für diese Datei wird im [!DNL User] Spalte.

   1. Klicken Sie mit der rechten Maustaste auf das neu erstellte Häkchen und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Die [!DNL profile.cfg] angezeigt.

   1. Im [!DNL profile.cfg]Fenster, Rechtsklick **[!UICONTROL Directories]** und klicken Sie auf **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

      Um den neuen Ordner am Ende der Liste der Ordner hinzuzufügen, klicken Sie mit der rechten Maustaste auf die Nummer oder den Namen des letzten Ordners in der Liste und klicken Sie auf **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

   1. Geben Sie den Namen des neuen Ordners ein: [!DNL IP Geo-intelligence] I [!DNL P Geo-location].

   1. Rechtsklick **[!UICONTROL (modified)]** Klicken Sie oben im Fenster auf **[!UICONTROL Save]**.

   1. Im [!DNL Profile Manager]klicken Sie mit der rechten Maustaste auf das Häkchen für [!DNL profile.cfg] im [!DNL User] und klicken Sie auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*.

>[!NOTE]
>
>Speichern Sie die geänderte Konfigurationsdatei nicht in einem der von Adobe bereitgestellten internen Profile (einschließlich der Variablen [!DNL IP Geo-location] oder [!DNL IP Geo-intelligence] Profil), da Ihre Änderungen bei der Installation von Updates für diese Profile überschrieben werden.
