---
description: Schritte zum Zuordnen des Report Portals zu einem virtuellen Verzeichnis (IIS 7.0 oder höher).
solution: Analytics
title: Zuordnen von Report Portal zu einem virtuellen Verzeichnis (IIS 7.0 oder höher)
topic: Data workbench
uuid: 9d18fb85-f9d7-48b6-a19b-1e7b68a5adca
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Zuordnen von Report Portal zu einem virtuellen Verzeichnis (IIS 7.0 oder höher){#mapping-report-portal-to-a-virtual-directory-iis-or-higher}

Schritte zum Zuordnen des Report Portals zu einem virtuellen Verzeichnis (IIS 7.0 oder höher).

Derzeit verfügen die meisten Managed Service-Clients über Server mit dem Betriebssystem Windows Server 2008 und dem IIS 7.0-Webserver oder höher.

## Voraussetzungen {#section-7b1cff24fc4f4c8591540b78de686f2f}

* Vergewissern Sie sich, dass ASP und [!DNL ASP.Net] Komponenten für IIS 7.0 oder höher installiert sind.
* Vergewissern Sie sich, dass der IIS-Webbenutzer [!DNL Modify] Zugriff auf die [!DNL E:\Portal\data\users.mdb] Datei hat. Sie können dies ändern, indem Sie mit der rechten Maustaste auf die **[!UICONTROL users.mdb]** Datei klicken und unter [!DNL Properties], gehen Sie zur [!DNL Security] Registerkarte. Wenn Sie den IIS-Webbenutzer nicht in der Liste sehen oder nicht in der Lage sind, den IIS-Webbenutzer der Liste hinzuzufügen, geben Sie der [!DNL Users] Gruppe einfach den [!DNL Modify] Zugriff.

* Achten Sie darauf, dass das für die Ausführung verwendete Benutzerkonto [!DNL Application Pools] auch [!DNL Modify] Zugriff auf die Ordner [!DNL E:\Portal\data\users.mdb] und [!DNL C:\Windows\Temp\] hat.

## Installationsschritte {#section-2a6476a221fa43dfa91866c0d41f82e5}

1. Starten Sie auf dem Computer, auf dem [!DNL Report Portal] der Computer installiert ist, Folgendes [!DNL IIS Manager]:

   **[!UICONTROL Start]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Internet Information Services (IIS) Manager]**.

1. Auswählen **[!UICONTROL Local Machine]** > **[!UICONTROL Sites]** > **[!UICONTROL Default Web Site]**.

1. Klicken Sie mit der rechten Maustaste **[!UICONTROL Default Web Site]** und wählen Sie **[!UICONTROL Add Virtual Directory]**.

1. Geben Sie als Alias Portal ein.
1. Geben Sie für den physischen Pfad [!DNL E:\Portal\PortalASP]ein.
1. Klicken Sie auf **[!UICONTROL OK]**.

   Das virtuelle Verzeichnis, das Sie erstellt haben, wird unter dem [!DNL Default Web Site]angezeigt.

1. Fügen Sie die folgenden virtuellen Verzeichnisse unter dem virtuellen Verzeichnis hinzu, das Sie gerade erstellt haben.

   | Erstellen Sie diesen Alias... | Für diese physische Ressource |
   |---|---|
   | Kern | [!DNL E:\Portal\PortalFiles\Core] |
   | CSS | [!DNL E:\Portal\PortalFiles\CSS] |
   | Bilder | [!DNL E:\Portal\PortalFiles\Images] |
   | Ausgabe | Der physische Speicherort des Ordners, in dem die Ausgabe für Ihre Berichtssätze [!DNL Report Server] gespeichert wird. Der Ausgabeordner kann sich an einer beliebigen Stelle befinden und beliebig benannt werden. Es enthält einen Unterordner für jeden Berichtsatz. Sie können die Datei löschen, [!DNL E:\Portal\PortalFiles\Output]aber [!DNL profiles.xml] an den physischen Speicherort der Ausgabedatei verschieben. |

1. Stellen Sie nach Abschluss des Vorgangs sicher, dass IIS vier neue virtuelle Ordner anzeigt. Vergewissern Sie sich, dass die Ordnerstruktur einen übergeordneten Ordner (mit demselben Namen wie das Portal) und vier Unterordner hat.
1. Klicken Sie auf **[!UICONTROL Application Pools]**, dann **[!UICONTROL DefaultAppPool]** (vorausgesetzt, das ist das, was Sie mit Ihrem Portal eingerichtet haben).

1. Klicken Sie auf **[!UICONTROL Advanced Settings]** und wählen Sie True für die Option 32-Bit-Anwendungen aktivieren.
1. Um die Funktion [!DNL Portal] zu aktivieren, müssen Sie sie in eine Anwendung konvertieren. Nachdem Sie die virtuellen Verzeichnisse eingerichtet haben, klicken Sie mit der rechten Maustaste auf das virtuelle Portal und wählen Sie **[!UICONTROL Convert to Application]**.

## Weitere Tipps und Tricks {#section-ff84ab3f66c94620a6a11f0e60471d44}

* Sie können die Datei [!DNL Portal] von Software unter **[!UICONTROL Softdocs]** > **[!UICONTROL Report Portal]**. Sie können die Datei einfach herunterladen [!DNL ReportPortal-Release-1-0-0-7.zip].

* Sie benötigen den [!DNL ReportPortalSetup.xml]Code nicht mehr, sodass er gelöscht werden kann.
* Der Standardisierung halber sollten Sie den Inhalt dieser ZIP-Datei in [!DNL E:\Portal]ablegen.
* Um den SMTP-Server für Clients mit verwalteten Diensten zu ermitteln, können Sie hier nachsehen.
* Geben Sie bei NetOps eine Anforderung ein, um den Domänennameneintrag in IIS für den Berichtsserver in etwas Freundlicheres zu ändern, [!DNL reports.clientname.insight.omniture.com]sodass Ihre Portal-URL insgesamt angezeigt wird [!DNL http://reports.clientname.insight.omniture.com/Portal]. Konfigurieren Sie Ihre [!DNL email.asa] Datei, nachdem diese Änderung vorgenommen wurde.

