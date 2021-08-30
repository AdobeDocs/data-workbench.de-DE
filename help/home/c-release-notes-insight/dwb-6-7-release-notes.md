---
description: Neue Funktionen, Fehlerbehebungen und bekannte Probleme in Data Workbench 6.7.
title: Versionshinweise zu Data Workbench 6.7
uuid: b84f5f2b-4f1c-490c-982b-6bd8d3a63e25
exl-id: e5ec3224-66d1-47a6-9bf3-8be9f6568b8d
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '648'
ht-degree: 34%

---

# Versionshinweise zu Data Workbench 6.7{#data-workbench-release-notes}

Neue Funktionen, Fehlerbehebungen und bekannte Probleme in Data Workbench 6.7.

## Versionshinweise zu Data Workbench 6.7 {#topic-7655534554ac4a4b816af1bd73b06aad}

Neue Funktionen, Fehlerbehebungen und bekannte Probleme in Data Workbench 6.7.

## Neue Funktionen in Version 6.7 {#section-8bd7a36ac3a24b8497a9ea9724e0d750}

**Neues Authentifizierungsmodell für Data Workbench Workstation (IMS-Integration)**

Data Workbench Workstation unterstützt nun die Benutzerauthentifizierung per Benutzername und Passwort. Dank dieser neuen Methode können Administratoren eigene Benutzerkonten erstellen und verwalten und müssen sich nicht mehr an die Kundenunterstützung wenden.

Sehen Sie sich hierzu auch unsere Informationen zur [Eigenbereitstellung von Benutzern](https://experienceleague.adobe.com/docs/data-workbench/using/client/c-self-provisioning-users.html) an.

**Flatfile-Abruf**

Data Workbench Workstation unterstützt nun die Benutzerauthentifizierung per Benutzername und Passwort. Dank dieser neuen Methode können Administratoren eigene Benutzerkonten erstellen und verwalten und müssen sich nicht mehr an die Kundenunterstützung wenden.

Beim Flatfile-Abruf wurde bisher die gesamte Datei in speicherinterne Puffer geladen, sodass die Speichernutzung stark beansprucht war und Leistungsprobleme für andere Subsysteme entstanden. Für die Dateien ist nun eine Speicherzuordnung und Zwischenspeicherung in Windows möglich, sodass die Speichernutzung optimiert werden kann. Hierzu muss für *Memory Mapped Lookup Files* der Wert true in [!DNL MemorySettings.cfg] festgelegt werden.

Sehen Sie sich hierzu auch unsere Informationen zur [Eigenbereitstellung von Benutzern](https://experienceleague.adobe.com/docs/data-workbench/using/client/c-self-provisioning-users.html) an.

**Speichernutzung**

Die Verwendung großer Seiten kann jetzt deaktiviert werden, indem *Use Large Pages* in [!DNL MemorySettings.cfg] auf false gesetzt wird. Sehen Sie sich hierzu auch unsere Informationen zur [Überwachung der Speichernutzung](https://experienceleague.adobe.com/docs/data-workbench/using/server-admin-install/admin-dwb-server/t-mntr-mry-usg.html) an.

**Sicherheitsverschlüsselungen**

Es werden nun auch ECDHE und DHE unterstützt.

E-Mail-Unterstützung in [!DNL User List.cfg]

Unterstützung für E-Mail-Attribut in [!DNL User List.cfg] hinzugefügt. Sehen Sie sich hierzu auch unsere Informationen zur [Benutzerverwaltung von Gruppenmitgliedern](https://docs.adobe.com/help/en/data-workbench/using/server-admin-install/admin-dwb-server/access-control/dwb-self-admin-member-access.html) an.

**Hilfemenü**

Im Hilfe-Menü wird nun eine Verknüpfung zum Open Certificates-Verzeichnis angezeigt.

**`TargetBulkUpload`export**

URLs werden am Ende der Exportnachverfolgungsdatei und der Datei `targetbulkuploadexportname.log.completed` bereitgestellt, um hängengebliebene Batches nachverfolgen zu können.

Eine neue Datei, [!DNL TargetBulkUpload.cfg], wurde bereitgestellt, um das Intervall für die maximale Zeitüberschreitung zu konfigurieren (in Minuten). Die Datei befindet sich unter [!DNL Server\Admin\Export\].

## Fehlerbehebungen {#section-160baf6ea04c45a993777ee4260691ed}

* Es wurde ein Problem behoben, bei dem die Kampagnen-Clickthrough -Dimension überhöhte Werte anzeigte.
* Es wurde ein Problem beim Generieren von Excel-Dateien vom Berichtsserver behoben.
* Die RC4-Verschlüsselung ist jetzt standardmäßig deaktiviert.
* Fehlerkorrektur - Die Data Workbenchs-Workstation stürzt beim Hinzufügen eines Dimensionselements zu einer Wertlegendentabelle nicht mehr ab.
* Es wurde ein Problem mit der Data Workbench behoben, Exporte zu AAM, die Timeouts verursachten.
* Es wurde ein Problem behoben, das zum Absturz der Data Workbench-Workstation führte, wenn ein Benutzer ohne ausreichende Zugriffsstufe den Arbeitsbereich auf Server speicherte.
* Es wurde ein Problem behoben, durch das das Datumsformat in [!DNL report.cfg] falsch oder nicht lokalisiert war.
* Es wurde ein Problem behoben, bei dem die Zeilen für Mobilgeräte und Produkte im AVRO-Feed verwirrende Informationen anzeigten.
* Fehlerkorrektur - Die Reihenfolge von `*.1cd`- und `*.1ad`-Dateien in [!DNL order.txt] ist jetzt möglich.

* Die Option &quot;An Server übermitteln&quot;wurde während der Ausführung des Clustering für den Algorithmus zur Erwartungsmaximierung deaktiviert.
* Es wurde ein Problem behoben, bei dem die ausführbare Datei `TargetBulkUpload` angehalten wurde und nicht vollständig ausgeführt werden konnte.

## Bekannte Probleme {#section-d76322bdac5043f087ab303dc68b8fff}

* Beim Abmelden wird die Datei [!DNL user cache.db] bereinigt.
* E-Mail-Adressen von IMS-Benutzern, die Zeichen &#39;+&#39; oder &#39;%&#39; enthalten, werden nicht unterstützt.
* Der Benutzer kann sich während eines Fehlers im Verbindungsstatus nicht abmelden. Melden Sie sich als Workaround im Offline-Modus ab.
* Das IMS-Anmeldefenster wird auf einigen Hardware mit hoher Auflösung und hoher DPI-Einstellung nicht ordnungsgemäß gerendert. Klicken Sie als Problemumgehung mit der rechten Maustaste auf [!DNL Insight.exe], navigieren Sie zu **[!UICONTROL Properties]** > **[!UICONTROL Compatability]** und aktivieren Sie dann das Kontrollkästchen **[!UICONTROL Override high DPI scaling behavior]**.

## Upgrade-Anforderungen {#section-b74adf981ac8446a8d7ffcdc4e9cf939}

1. Aktualisieren Sie [!DNL trust_ca_cert.pem] auf den Insight-Servern, die Teil des Build-Pakets sind.
1. Aktualisieren Sie das Zertifikat von Server und Report Server, indem Sie neue Zertifikate von [https://aap.adobe.com](https://aap.adobe.com) herunterladen.
1. Um Workstation und Report Server automatisch zu aktualisieren, müssen Sie [!DNL trust_ca_cert.pem] manuell aktualisieren, indem Sie sie vom Lizenzserver herunterladen.
1. Die automatische Update-Funktion von Sensor erfordert Version 5.0, um mit Insight Server Version 6.70 kommunizieren zu können. Außerdem muss der Sensor [!DNL trust_ca_cert.pem] manuell aktualisiert werden, indem er vom Lizenzserver heruntergeladen wird.

## Systemaktualisierungen {#section-c1b4949ea734440aa62658ac313261db}

Zu den neuen Dateien gehören:

1. [!DNL Server\Admin\Export\TargetBulkUpload.cfg]
1. [!DNL Server\Components for Processing Servers\MemorySettings.cfg]
1. [!DNL Server\Components\MemorySettings.cfg]

Zu den aktualisierten Dateien gehören:

1. [!DNL trust_ca_cert.pem] für alle Komponenten.
1. [!DNL Access Control.cfg] , um die IMS-Konfiguration zu unterstützen.
1. [!DNL Base\Context\meta.cfg] zur Unterstützung der Formate für Startdatum und Enddatum in  [!DNL Report.cfg]

1. Hinzufügung von [!DNL Insight.cfg] zur Unterstützung des Proxys für die IMS-Authentifizierung:

   ```
   IMS Proxy Info = IMSProxyInfo: 
     Proxy Password = EncryptedString:
     Proxy User Name = string:
   ```

Siehe [archivierte Versionshinweise](https://experienceleague.adobe.com/docs/data-workbench/using/release-notes/release-notes.html) für Data Workbench 5.3 bis 5.52.
