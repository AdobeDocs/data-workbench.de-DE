---
description: Die Datendienstprofile (IP Geo-Intelligence und IP Geo-Location) sind interne Profile, die zusätzliche Funktionen für Ihre Adobe-Anwendung bieten.
solution: Analytics
title: Datendienstprofil installieren
topic: Data workbench
uuid: 1c03d0cd-7eaa-4e48-bbff-8bfad8fed9e9
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Datendienstprofil installieren{#installing-the-data-service-profile}

Die Datendienstprofile (IP Geo-Intelligence und IP Geo-Location) sind interne Profile, die zusätzliche Funktionen für Ihre Adobe-Anwendung bieten.

Wie bei allen anderen von Adobe bereitgestellten internen Profilen sollten diese Profile nicht geändert werden. Alle Anpassungen müssen in Ihrem Datensatz, in Ihren rollenspezifischen Profilen oder in anderen Profilen, die Sie erstellen, vorgenommen werden.

Zu den Datendienstprofilen gehören die folgenden Datensatzdateien, die auf einem Data Workbench-Server installiert werden sollen:

* **Profile\*Profilname *\Dataset\Log Processing\Traffic\IP.cfg:** Listet das c-ip-Feld auf, das von der Protokollverarbeitung zur Konvertierung weitergeleitet werden soll.
* **Profile\*Profilname *\Dataset\Transformation\Geography\IPLookup.cfg:** Definiert eine IPLookup-Transformation, die mehrere Felder geografischer Daten mithilfe der bereitgestellten IP-Geo-Intelligence- oder IP-Geo-Location-Nachschlagedatei erstellt.

Weitere Informationen zum Einschließen von Dateien in Transformationsdatasets finden Sie im Handbuch zur Konfiguration von *Datasets*.

Darüber hinaus bietet jedes Datendienstprofil eine Elementpunktebenendatei mit dem Namen [!DNL IP Coordinates.layer]. Mit dieser Ebenendatei können Sie Positionen in Ihrem Datensatz auf der Welt dynamisch mithilfe von IP-Adressen zuordnen. Nach der Installation wird die Ebene im Ordner &quot;Profiles\*data service name*\Maps&quot;im Installationsordner des Data Workbench-Servers gespeichert.

Die [!DNL IP Coordinates.layer] Datei verweist auf die Dimension &quot;Koordinaten&quot;, die in der mit dem [!DNL Coordinates.cfg] [!DNL Geography] Profil bereitgestellten Datei definiert ist und sich im Ordner &quot;Dataset\Transformation\Geography folder&quot;befindet. Jedes Element der Dimension &quot;Koordinaten&quot;in Ihrem Datensatz wird mithilfe der Breiten- und Längengradinformationen, die in diesem Element enthalten sind, auf der Welt zugeordnet. Weitere Informationen zu Elementpunktebenen, die dynamische Punkte verwenden, finden Sie unter [Definieren von Elementpunktebenen mit dynamischen Punkten](../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyr-file-frmt/c-dyn-pts.md#concept-77ae65bedc3f465489bc135ae7e3c2f3).

>[!NOTE]
>
>Wenn Sie den IP-Geo-Intelligence- und IP-Geo-Location-Datendienst vor Version 5.1 installiert haben, verweist Ihre Elementpunktschichtdatei auf eine Lookup-Datei, anstatt dynamische Punkte zu verwenden. Jede Ebenendatei verweist auf die IP-Geocodes-Nachschlagedatei und die IP-Geocode-Dimension. Die IP-Geocodes-Nachschlagedatei enthält eine Liste der IP-Geocodes (geografische Standorte, die auf der IP-Adresse basieren) und den Breiten- und Längengrad. Jedes Element einer IP-Geocode-Dimension, das in Ihrem Datensatz definiert ist, wird auf der Welt mithilfe der Breiten- und Längengrade zugeordnet, die für diesen IP-Geocode in der IP-Geocodes-Nachschlagedatei aufgeführt sind.

Der Name der Ebenendatei und die referenzierten Dateien unterscheiden sich für jeden Datendienst:

* Die [!DNL IP Geocodes D.layer] Datei wird mit dem IP Geo-Intelligence-Profil (Digital Envoy) installiert. Diese Elementpunktebene verweist auf die [!DNL IP Geocodes D yyyymmdd.txt] Lookup-Datei (die Sie regelmäßig aktualisieren müssen) und die IP-Geocode-D-Dimension.

* Die [!DNL IP Geocodes Q.layer] Datei wird mit dem IP-Geolocation-Profil (Quova) installiert. Diese Elementpunktebene verweist auf die [!DNL IP Geocodes Q yyyymmdd.txt] Lookup-Datei (die Sie regelmäßig aktualisieren müssen) und die IP-Geocode-Q-Dimension.

Weitere Informationen zu Elementpunktebenen, die Lookup-Dateien verwenden, finden Sie unter [Definieren von Elementpunktebenen mit Verweis auf Lookup-Dateien](../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyrs-ref-lkp-files.md#concept-c40bd0890a984112bce831b596827f0f).

## So installieren Sie das Geo-Intelligence- oder IP-Geo-Positionsprofil {#section-6dff402ffdcb4b31b9bcd0c40a5f7625}

>[!NOTE]
>
>Bei den folgenden Installationsanweisungen wird davon ausgegangen, dass Sie Data Workbench installiert und eine Verbindung zwischen Data Workbench und dem Data Workbench-Server hergestellt haben, auf dem Sie Data Workbench installieren [!DNL Geography]. Wenn Sie dies noch nicht getan haben, finden Sie weitere Informationen im *Data Workbench-Benutzerhandbuch*.

1. Öffnen Sie den Ordner &quot;Profile&quot;aus der [!DNL .zip] Datei, die Sie von Adobe erhalten haben.
1. Kopieren Sie den Ordner &quot;IP-Geo-Intelligence&quot;oder &quot;IP-Geo-Speicherort&quot;in den Ordner &quot;Profile&quot;im Installationsordner des Data Workbench-Servers. Du willst am Ende mit einem ...\Profiles\IP Geo-intelligence folder or a ...\Profiles\IP Geo-location on your data workbench server as shown in the following example. Die Namen der anderen Ordner innerhalb des [!DNL Profiles] Ordners unterscheiden sich möglicherweise von denen, die angezeigt werden.

   ![](assets/Geo_installProfiles_dirIP.png)

1. Führen Sie die folgenden Schritte aus, um die [!DNL profile.cfg] Datei für jedes Profil zu aktualisieren, mit dem Sie das Profil [!DNL IP Geo-intelligence] oder [!DNL IP Geo-location] Profil verwenden möchten.

   1. Öffnen Sie den **[!UICONTROL Profile Manager]**.
   1. Klicken Sie mit der rechten Maustaste auf das Häkchen neben [!DNL profile.cfg] und klicken Sie auf **[!UICONTROL Make Local]**. Ein Häkchen für diese Datei wird in der [!DNL User] Spalte angezeigt.

   1. Klicken Sie mit der rechten Maustaste auf das neu erstellte Häkchen und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Das [!DNL profile.cfg] Fenster wird angezeigt.

   1. Klicken Sie im [!DNL profile.cfg]Fenster mit der rechten Maustaste **[!UICONTROL Directories]** und klicken Sie auf **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

      Um den neuen Ordner am Ende der Liste der Ordner hinzuzufügen, klicken Sie mit der rechten Maustaste auf die Nummer oder den Namen des letzten Ordners in der Liste und klicken Sie auf **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

   1. Geben Sie den Namen des neuen Ordners ein: [!DNL IP Geo-intelligence] oder ich [!DNL P Geo-location].

   1. Klicken Sie mit der rechten Maustaste **[!UICONTROL (modified)]** am oberen Rand des Fensters und klicken Sie auf **[!UICONTROL Save]**.

   1. Klicken Sie in der [!DNL Profile Manager]Spalte mit der rechten Maustaste auf das Häkchen für [!DNL profile.cfg] die [!DNL User] Spalte und klicken Sie dann auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*.

>[!NOTE]
>
>Speichern Sie die geänderte Konfigurationsdatei nicht in einem der von Adobe bereitgestellten internen Profile (einschließlich des Profils [!DNL IP Geo-location] [!DNL IP Geo-intelligence] oder des Profils), da Ihre Änderungen überschrieben werden, wenn Sie Updates für diese Profile installieren.

