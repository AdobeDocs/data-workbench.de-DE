---
description: Schritte zum Zuordnen des Report Portals zu einem virtuellen Verzeichnis (IIS 7.0 oder höher).
title: Zuordnen von Report Portal zu einem virtuellen Verzeichnis (IIS 7.0 oder höher)
uuid: 9d18fb85-f9d7-48b6-a19b-1e7b68a5adca
exl-id: 2fa3439a-1fe5-4a20-83db-d233ae8b5263
source-git-commit: 79981e92dd1c2e552f958716626a632ead940973
workflow-type: tm+mt
source-wordcount: '437'
ht-degree: 5%

---

# Zuordnen von Report Portal zu einem virtuellen Verzeichnis (IIS 7.0 oder höher){#mapping-report-portal-to-a-virtual-directory-iis-or-higher}

Schritte zum Zuordnen des Report Portals zu einem virtuellen Verzeichnis (IIS 7.0 oder höher).

Derzeit verfügen die meisten Managed Service-Clients über Server mit dem Windows Server 2008-Betriebssystem und dem IIS 7.0-Webserver oder höher.

## Voraussetzungen {#section-7b1cff24fc4f4c8591540b78de686f2f}

* Stellen Sie sicher, dass ASP- und [!DNL ASP.Net]-Komponenten für IIS 7.0 oder höher installiert sind.
* Stellen Sie sicher, dass der IIS-Webbenutzer [!DNL Modify] Zugriff auf die Datei [!DNL E:\Portal\data\users.mdb] hat. Sie können dies ändern, indem Sie mit der rechten Maustaste auf die Datei **[!UICONTROL users.mdb]** klicken und unter [!DNL Properties] zur Registerkarte [!DNL Security] wechseln. Wenn der IIS-Webbenutzer nicht aufgeführt ist oder Sie den IIS-Webbenutzer nicht zur Liste hinzufügen können, geben Sie einfach der Gruppe [!DNL Users] den Zugriff [!DNL Modify].

* Stellen Sie sicher, dass jedes Benutzerkonto, das zum Ausführen von [!DNL Application Pools] verwendet wird, auch [!DNL Modify] Zugriff auf die Ordner [!DNL E:\Portal\data\users.mdb] und [!DNL C:\Windows\Temp\] hat.

## Installationsschritte {#section-2a6476a221fa43dfa91866c0d41f82e5}

1. Starten Sie auf dem Computer, auf dem [!DNL Report Portal] installiert ist, den [!DNL IIS Manager]:

   **[!UICONTROL Start]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Internet Information Services (IIS) Manager]**.

1. Auswählen **[!UICONTROL Local Machine]** > **[!UICONTROL Sites]** > **[!UICONTROL Default Web Site]**.

1. Klicken Sie mit der rechten Maustaste auf **[!UICONTROL Default Web Site]** und wählen Sie **[!UICONTROL Add Virtual Directory]** aus.

1. Geben Sie als Alias &quot;Portal&quot;ein.
1. Geben Sie für den physischen Pfad [!DNL E:\Portal\PortalASP] ein.
1. Klicken Sie auf **[!UICONTROL OK]**.

   Das von Ihnen erstellte virtuelle Verzeichnis wird unter [!DNL Default Web Site] angezeigt.

1. Fügen Sie die folgenden virtuellen Verzeichnisse unter dem virtuellen Verzeichnis hinzu, das Sie gerade erstellt haben.

   | Erstellen Sie diesen Alias... | Für diese physische Ressource |
   |---|---|
   | Core | [!DNL E:\Portal\PortalFiles\Core] |
   | CSS | [!DNL E:\Portal\PortalFiles\CSS] |
   | Bilder | [!DNL E:\Portal\PortalFiles\Images] |
   | Ausgabe | Der physische Speicherort des Ordners, in dem [!DNL Report Server] die Ausgabe für Ihre Berichtssätze speichert. Der Ausgabeordner kann sich an einer beliebigen Stelle befinden und beliebig benannt werden. Sie enthält einen Unterordner für jeden Berichtssatz. Sie können [!DNL E:\Portal\PortalFiles\Output] löschen, aber [!DNL profiles.xml] an den physischen Speicherort der Ausgabedatei verschieben. |

1. Stellen Sie nach Abschluss sicher, dass IIS vier neue virtuelle Verzeichnisse anzeigt. Stellen Sie sicher, dass die Ordnerstruktur einen übergeordneten Ordner (mit demselben Namen wie Ihr Portal) und vier Unterordner hat.
1. Klicken Sie auf **[!UICONTROL Application Pools]** und dann auf **[!UICONTROL DefaultAppPool]** (vorausgesetzt, dies ist der Bereich, den Sie mit Ihrem Portal eingerichtet haben).

1. Klicken Sie auf **[!UICONTROL Advanced Settings]** und wählen Sie True für die Option &quot;32-Bit-Anwendungen aktivieren&quot;.
1. Damit [!DNL Portal] funktioniert, müssen Sie es in eine Anwendung konvertieren. Nachdem Sie die virtuellen Verzeichnisse eingerichtet haben, klicken Sie mit der rechten Maustaste auf das virtuelle Portal-Verzeichnis und wählen Sie **[!UICONTROL Convert to Application]** aus.

## Weitere Tipps und Tricks {#section-ff84ab3f66c94620a6a11f0e60471d44}

* Sie können [!DNL Portal] von Software unter **[!UICONTROL Softdocs]** > **[!UICONTROL Report Portal]** herunterladen. Sie können einfach [!DNL ReportPortal-Release-1-0-0-7.zip] herunterladen.

* Sie benötigen den [!DNL ReportPortalSetup.xml] nicht mehr, daher kann er gelöscht werden.
* Der Standardisierung halber platzieren Sie den Inhalt dieser ZIP-Datei in [!DNL E:\Portal].
* Um den SMTP-Server für Clients mit verwalteten Diensten zu ermitteln, können Sie hier nachsehen.
* Stellen Sie eine Anfrage mit NetOps, um den Domänennameneintrag in IIS für den Berichtsserver in etwas Freundlicheres zu ändern, z. B. [!DNL reports.clientname.insight.omniture.com], sodass Ihre Portal-URL [!DNL https://reports.clientname.insight.omniture.com/Portal] lautet. Konfigurieren Sie Ihre [!DNL email.asa]-Datei, nachdem diese Änderung vorgenommen wurde.
