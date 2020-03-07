---
description: Neue Funktionen, Fehlerbehebungen und bekannte Probleme in Data Workbench 6.7.
title: Data Workbench 6.7 - Versionshinweise
uuid: b84f5f2b-4f1c-490c-982b-6bd8d3a63e25
translation-type: tm+mt
source-git-commit: 2cba66a160fec9154796f093d04a422a5b0da265

---


# Data Workbench 6.7 Release Notes{#data-workbench-release-notes}

Neue Funktionen, Fehlerbehebungen und bekannte Probleme in Data Workbench 6.7.

## Data Workbench 6.7 Release Notes {#topic-7655534554ac4a4b816af1bd73b06aad}

Neue Funktionen, Fehlerbehebungen und bekannte Probleme in Data Workbench 6.7.

## Neue Funktionen in Version 6.7 {#section-8bd7a36ac3a24b8497a9ea9724e0d750}

**Neues Authentifizierungsmodell für Data Workbench Workstation (IMS-Integration)**

Data Workbench Workstation unterstützt nun die Benutzerauthentifizierung per Benutzername und Passwort. Dank dieser neuen Methode können Administratoren eigene Benutzerkonten erstellen und verwalten und müssen sich nicht mehr an die Kundenunterstützung wenden.

Sehen Sie sich hierzu auch unsere Informationen zur [Eigenbereitstellung von Benutzern](https://docs.adobe.com/content/help/en/data-workbench/using/client/c-self-provisioning-users.html) an.

**Flatfile-Abruf**

Data Workbench Workstation unterstützt nun die Benutzerauthentifizierung per Benutzername und Passwort. Dank dieser neuen Methode können Administratoren eigene Benutzerkonten erstellen und verwalten und müssen sich nicht mehr an die Kundenunterstützung wenden.

Beim Flatfile-Abruf wurde bisher die gesamte Datei in speicherinterne Puffer geladen, sodass die Speichernutzung stark beansprucht war und Leistungsprobleme für andere Subsysteme entstanden. Für die Dateien ist nun eine Speicherzuordnung und Zwischenspeicherung in Windows möglich, sodass die Speichernutzung optimiert werden kann. Hierzu muss für *Memory Mapped Lookup Files* der Wert true in [!DNL MemorySettings.cfg] festgelegt werden.

Sehen Sie sich hierzu auch unsere Informationen zur [Eigenbereitstellung von Benutzern](https://docs.adobe.com/content/help/en/data-workbench/using/client/c-self-provisioning-users.html) an.

**Speichernutzung**

Large Page usage can now be disabled by setting *Use Large Pages* to false in [!DNL MemorySettings.cfg]. Sehen Sie sich hierzu auch unsere Informationen zur [Überwachung der Speichernutzung](https://docs.adobe.com/content/help/en/data-workbench/using/server-admin-install/admin-dwb-server/t-mntr-mry-usg.html) an.

**Sicherheitsverschlüsselungen**

Es werden nun auch ECDHE und DHE unterstützt.

Email support in [!DNL User List.cfg]

Added support for Email attribute in [!DNL User List.cfg]. Sehen Sie sich hierzu auch unsere Informationen zur [Benutzerverwaltung von Gruppenmitgliedern](https://docs.adobe.com/help/en/data-workbench/using/server-admin-install/admin-dwb-server/access-control/dwb-self-admin-member-access.html) an.

**Hilfe-Menü**

Im Hilfe-Menü wird nun eine Verknüpfung zum Open Certificates-Verzeichnis angezeigt.

**`TargetBulkUpload`Export **

URLs werden am Ende der Exportnachverfolgungsdatei und der Datei `targetbulkuploadexportname.log.completed` bereitgestellt, um hängengebliebene Batches nachverfolgen zu können.

Eine neue Datei, [!DNL TargetBulkUpload.cfg], wurde bereitgestellt, um das Intervall für die maximale Zeitüberschreitung zu konfigurieren (in Minuten). Die Datei finden Sie unter [!DNL Server\Admin\Export\].

## Fehlerkorrekturen {#section-160baf6ea04c45a993777ee4260691ed}

* Es wurde ein Problem behoben, bei dem die Clickthrough-Dimension der Kampagne überhöhte Werte anzeigte.
* Es wurde ein Problem beim Generieren von Excel-Dateien vom Berichtsserver behoben.
* Der RC4-Chipher ist jetzt standardmäßig deaktiviert.
* Es wurde ein Fehler behoben, der dazu führte, dass die Data Workstation abstürzte, wenn ein Dimensionselement zu einer Tabelle mit der Wertebelung hinzugefügt wurde.
* Es wurde ein Problem mit Data Workbench für AAM-Exporte behoben, das Timeouts verursachte.
* Es wurde ein Problem behoben, das dazu führte, dass die Data Workstation abstürzte, wenn ein Benutzer ohne ausreichende Zugriffsebene den Arbeitsbereich auf Server speicherte.
* Es wurde ein Problem behoben, bei dem das Datumsformat nicht korrekt oder nicht lokalisiert [!DNL report.cfg] war.
* Es wurde ein Problem behoben, bei dem die Zeilen für Mobilgeräte und Produkte im AVRO-Feed verwirrende Informationen anzeigten.
* Es wurde ein Problem behoben, das die Reihenfolge der Dateien `*.1cd` und `*.1ad` Dateien in verhinderte [!DNL order.txt].

* Die Option &quot;An Server übermitteln&quot;wurde für den Algorithmus zur Maximierung der Erwartungen während der Ausführung von Clustering deaktiviert.
* Es wurde ein Problem behoben, durch das die `TargetBulkUpload` ausführbare Datei angehalten wurde und nicht vollständig ausgeführt werden konnte.

## Bekannte Probleme {#section-d76322bdac5043f087ab303dc68b8fff}

* Beim Abmelden wird die [!DNL user cache.db] Datei gelöscht.
* IMS-Benutzer-E-Mail-Adressen, die Zeichen &quot;+&quot;oder &quot;%&quot;enthalten, werden nicht unterstützt.
* Benutzer kann sich während eines Fehlers im Verbindungsstatus nicht abmelden. Als Problemumgehung melden Sie sich im Offlinemodus an.
* Das IMS-Anmeldefenster wird auf einigen Hardware mit hoher Auflösung und hoher DPI nicht korrekt dargestellt. Um dies zu umgehen, klicken Sie mit der rechten Maustaste darauf [!DNL Insight.exe] und navigieren Sie zu **[!UICONTROL Properties]** > **[!UICONTROL Compatability]**, und markieren Sie das Kontrollkästchen **[!UICONTROL Override high DPI scaling behavior]**.

## Upgrade-Anforderungen {#section-b74adf981ac8446a8d7ffcdc4e9cf939}

1. Aktualisieren Sie [!DNL trust_ca_cert.pem] auf den Insight-Servern, die Teil des Build-Pakets sind.
1. Aktualisieren Sie das Zertifikat des Servers und des Berichtsservers, indem Sie neue Zertifikate von [https://aap.adobe.com](https://aap.adobe.com)herunterladen.
1. Um Workstation und Report Server automatisch zu aktualisieren, müssen Sie sie manuell [!DNL trust_ca_cert.pem] vom Lizenzserver herunterladen.
1. Die automatische Updatefunktion von Sensor erfordert Version 5.0, um mit Insight Server Version 6.70 kommunizieren zu können. Außerdem [!DNL trust_ca_cert.pem] müssen Sensors manuell aktualisiert werden, indem sie vom Lizenzserver heruntergeladen werden.

## Systemaktualisierungen {#section-c1b4949ea734440aa62658ac313261db}

Zu den neuen Dateien gehören:

1. [!DNL Server\Admin\Export\TargetBulkUpload.cfg]
1. [!DNL Server\Components for Processing Servers\MemorySettings.cfg]
1. [!DNL Server\Components\MemorySettings.cfg]

Aktualisierte Dateien umfassen:

1. [!DNL trust_ca_cert.pem] für alle Komponenten.
1. [!DNL Access Control.cfg] , um die IMS-Konfiguration zu unterstützen.
1. [!DNL Base\Context\meta.cfg] für die Unterstützung der Formate Startdatum und Enddatum in [!DNL Report.cfg]

1. Ergänzung [!DNL Insight.cfg] zur Unterstützung des Proxys für die IMS-Authentifizierung:

   ```
   IMS Proxy Info = IMSProxyInfo: 
     Proxy Password = EncryptedString:
     Proxy User Name = string:
   ```

Siehe [archivierte Versionshinweise](https://docs.adobe.com/content/help/en/data-workbench/using/release-notes/release-notes.html) für Data Workbench 5.3 bis 5.52.
