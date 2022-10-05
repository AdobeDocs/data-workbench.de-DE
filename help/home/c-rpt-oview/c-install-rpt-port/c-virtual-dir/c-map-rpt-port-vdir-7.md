---
description: Schritte zum Zuordnen des Report Portals zu einem virtuellen Verzeichnis (IIS 7.0 oder höher).
title: Zuordnen von Report Portal zu einem virtuellen Verzeichnis (IIS 7.0 oder höher)
uuid: 9d18fb85-f9d7-48b6-a19b-1e7b68a5adca
exl-id: 2fa3439a-1fe5-4a20-83db-d233ae8b5263
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '441'
ht-degree: 5%

---

# Zuordnen von Report Portal zu einem virtuellen Verzeichnis (IIS 7.0 oder höher){#mapping-report-portal-to-a-virtual-directory-iis-or-higher}

{{eol}}

Schritte zum Zuordnen des Report Portals zu einem virtuellen Verzeichnis (IIS 7.0 oder höher).

Derzeit verfügen die meisten Managed Service-Clients über Server mit dem Windows Server 2008-Betriebssystem und dem IIS 7.0-Webserver oder höher.

## Voraussetzungen {#section-7b1cff24fc4f4c8591540b78de686f2f}

* Stellen Sie sicher, dass ASP und [!DNL ASP.Net] -Komponenten werden für IIS 7.0 oder höher installiert.
* Stellen Sie sicher, dass der IIS-Webbenutzer [!DNL Modify] Zugang zu [!DNL E:\Portal\data\users.mdb] -Datei. Sie können dies ändern, indem Sie mit der rechten Maustaste auf die **[!UICONTROL users.mdb]** Datei und [!DNL Properties], navigieren Sie zu [!DNL Security] Registerkarte. Wenn der IIS-Webbenutzer nicht aufgeführt ist oder Sie den IIS-Webbenutzer nicht zur Liste hinzufügen können, geben Sie einfach die [!DNL Users] Gruppe [!DNL Modify] Zugriff.

* Stellen Sie sicher, dass das für die Ausführung der [!DNL Application Pools] auch [!DNL Modify] Zugang zu [!DNL E:\Portal\data\users.mdb] und die Ordner [!DNL C:\Windows\Temp\].

## Installationsschritte {#section-2a6476a221fa43dfa91866c0d41f82e5}

1. Auf dem Computer, auf dem [!DNL Report Portal] installiert ist, starten Sie die [!DNL IIS Manager]:

   **[!UICONTROL Start]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Internet Information Services (IIS) Manager]**.

1. Auswählen **[!UICONTROL Local Machine]** > **[!UICONTROL Sites]** > **[!UICONTROL Default Web Site]**.

1. Rechtsklick **[!UICONTROL Default Web Site]** und wählen Sie **[!UICONTROL Add Virtual Directory]**.

1. Geben Sie als Alias &quot;Portal&quot;ein.
1. Geben Sie für den physischen Pfad [!DNL E:\Portal\PortalASP].
1. Klicken Sie auf **[!UICONTROL OK]**.

   Das von Ihnen erstellte virtuelle Verzeichnis wird unter dem [!DNL Default Web Site].

1. Fügen Sie die folgenden virtuellen Verzeichnisse unter dem virtuellen Verzeichnis hinzu, das Sie gerade erstellt haben.

   | Erstellen Sie diesen Alias... | Für diese physische Ressource |
   |---|---|
   | Core | [!DNL E:\Portal\PortalFiles\Core] |
   | CSS | [!DNL E:\Portal\PortalFiles\CSS] |
   | Bilder | [!DNL E:\Portal\PortalFiles\Images] |
   | Ausgabe | Physischer Speicherort des Ordners, in dem [!DNL Report Server] speichert die Ausgabe für Ihre Berichtssätze. Der Ausgabeordner kann sich an einer beliebigen Stelle befinden und beliebig benannt werden. Sie enthält einen Unterordner für jeden Berichtssatz. Sie können die [!DNL E:\Portal\PortalFiles\Output], aber verschieben Sie die [!DNL profiles.xml] an den physischen Speicherort der Ausgabedatei. |

1. Stellen Sie nach Abschluss sicher, dass IIS vier neue virtuelle Verzeichnisse anzeigt. Stellen Sie sicher, dass die Ordnerstruktur einen übergeordneten Ordner (mit demselben Namen wie Ihr Portal) und vier Unterordner hat.
1. Klicken Sie auf **[!UICONTROL Application Pools]**, dann **[!UICONTROL DefaultAppPool]** (vorausgesetzt, dies ist der Bereich, den Sie mit Ihrem Portal eingerichtet haben).

1. Klicken Sie auf **[!UICONTROL Advanced Settings]** und wählen Sie True für &quot;32-Bit-Anwendungen aktivieren&quot;.
1. So rufen Sie die [!DNL Portal] , müssen Sie sie in eine Anwendung konvertieren. Nachdem Sie die virtuellen Verzeichnisse eingerichtet haben, klicken Sie mit der rechten Maustaste auf das virtuelle Portal-Verzeichnis und wählen Sie **[!UICONTROL Convert to Application]**.

## Weitere Tipps und Tricks {#section-ff84ab3f66c94620a6a11f0e60471d44}

* Sie können die [!DNL Portal] von Software unter **[!UICONTROL Softdocs]** > **[!UICONTROL Report Portal]**. Sie können die [!DNL ReportPortal-Release-1-0-0-7.zip].

* Sie benötigen die [!DNL ReportPortalSetup.xml], damit sie gelöscht werden kann.
* Im Interesse der Standardisierung platzieren Sie den Inhalt dieser ZIP-Datei in [!DNL E:\Portal].
* Um den SMTP-Server für Clients mit verwalteten Diensten zu ermitteln, können Sie hier nachsehen.
* Senden Sie eine Anfrage mit NetOps, um den Domänennameneintrag in IIS für den Berichtsserver in etwas Freundlicheres zu ändern, z. B. [!DNL reports.clientname.insight.omniture.com], sodass Ihre gesamte Portal-URL [!DNL https://reports.clientname.insight.omniture.com/Portal]. Konfigurieren Sie Ihre [!DNL email.asa] Datei, nachdem diese Änderung vorgenommen wurde.
