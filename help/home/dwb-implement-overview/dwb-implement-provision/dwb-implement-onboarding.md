---
description: Führen Sie diese Schritte aus, um das Onboarding für die Adobe Data Workbench (DWB), eine Komponente von Adobe Analytics Premium (AAP), zu starten.
title: Grundlegende Onboarding-Anweisungen für DWB Managed Services
uuid: ad44a4eb-00ea-49c7-8401-58976d8fe39e
exl-id: 49fb6afe-b417-4554-9238-fd6381c00029
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '922'
ht-degree: 2%

---

# Grundlegende Onboarding-Anweisungen für DWB Managed Services{#basic-onboarding-instructions-for-dwb-managed-services}

{{eol}}

Führen Sie diese Schritte aus, um das Onboarding für die Adobe Data Workbench (DWB), eine Komponente von Adobe Analytics Premium (AAP), zu starten.

Diese Onboarding-Anweisungen richten sich an Kunden, die Data Workbench mit einer einzelnen Report Suite implementieren, indem sie Adobe Managed Services ohne Beratungsdienste nutzen. Wenn Sie ein neuer AAP-Kunde sind, der DWB implementiert, ist das Adobe Onboarding-Team Ihr erster Ansprechpartner. Bei der Aktualisierung vom Adobe Analytics-Standard oder von einer früheren DWB-Version unterstützt Sie ein Adobe Customer Success Manager.

## Onboarding-Informationen: Was wir von Ihnen brauchen {#section-bdeb9aa26dc14e45a6c90920832becaa}

Adobe wird Sie kontaktieren, um:

* Identifizieren Sie einen Primären Benutzer für DWB, um ein Zertifikat speziell für diesen Benutzer im Netzwerkverzeichnis zu generieren. Der primäre Anwender fungiert außerdem als Ansprechpartner für die Interaktion mit der Kundenunterstützung von Adobe.
* Identifizieren Sie die Report Suite, die in DWB geladen werden soll.

Die Adobe Digital Marketing-Teams verwenden dann Ihre Informationen, um Profile zu erstellen, Konten einzurichten und eine Konfigurationsdatei für DWB bereitzustellen.

**Adobe Onboarding-Aufgaben**

* Adobe-Kundenunterstützung erstellt ein lizenziertes DWB-Konto. Die Adobe-Kundenunterstützung generiert ein DWB-Zertifikat für den primären Benutzer.
* Die Adobe-Kundenunterstützung definiert den primären Benutzer als &quot;unterstützten Benutzer&quot;, die Person, die für unterstützte Aufrufe und Problemlösungen identifiziert wurde.
* Die Adobe-Kundenunterstützung lädt das Softwarepaket in das DWB-Lizenz- und Softwareportal (SoftDocs/Software und Docs-Profil) zum Herunterladen in Ihr Unternehmen.
* Das Adobe TechOps-Team bereitet die Produktions- und Entwicklungsumgebungen und deren Profile (pro Vertrag) für DWB vor.
* Das Adobe TechOps-Team konfiguriert Daten-Feeds und Profilverwaltungsskripte.
* Das Adobe TechOps-Team erstellt und sendet die DWB-Konfigurationsdatei (Insight.cfg) an das Adobe Onboarding-Team, das für Onboarding-Aufgaben im Zusammenhang mit Ihrem Unternehmen zuständig ist.

Nachdem Sie Ihre Daten-Feeds angepasst und Anmeldeinformationen, Zertifikate und eine Profilkonfiguration generiert haben, sendet die Adobe-Kundenunterstützung Ihre Konfigurationsdatei und Ihre Anmeldeinformationen, um den nächsten Schritt zu tun.

## Zugriff auf benutzerdefinierte Installationsdateien {#section-26962bf57fef435dbd1c5486d4b6f688}

Sie erhalten diese Setupdateien von der Adobe-Kundenunterstützung, um die DWB-Workstation auf Ihrem Clientcomputer zu installieren.

* Ihre benutzerdefinierte DWB-Konfigurationsdatei (Insight.cfg)

   Diese Konfigurationsdatei auf dem Clientcomputer enthält Verbindungen zu Ihren verwalteten DWB-Servern.

* Melden Sie sich für das Lizenzportal an, um den DWB-Einrichtungs-Assistenten und das erforderliche Zertifikat (.pem-Datei) mit dem Namen Ihres primären Benutzers herunterzuladen.

**Herunterladen zusätzlicher Setup-Dateien**

1. Navigieren Sie zu: license.visualsciences.com , um Ihr Lizenzzertifikat und die ausführbare Datei des DWB-Einrichtungs-Assistenten herunterzuladen.
1. Geben Sie Ihr Unternehmen (Kontoname), den Namen des Primärbenutzers und das Passwort ein, das Sie von der Kundenunterstützung von Adobe erhalten haben, und klicken Sie dann auf &quot;Anmelden&quot;.

   >[!NOTE]
   >
   >Ihr Browser fordert Sie an dieser Stelle möglicherweise auf, ein digitales Zertifikat vorzulegen. Wenn dies der Fall ist, klicken Sie auf Abbrechen , um das Dialogfeld zu schließen.

1. Suchen Sie das für Ihre Instanz der Adobe-Data Workbench ausgestellte Zertifikat (`<PrimaryUser>`.pem) im Abschnitt Downloads und laden Sie herunter.
1. Suchen Sie im Abschnitt Downloads nach dem Standard-Client-Installationsprogramm , um den DWB-Einrichtungs-Assistenten (InsightSetup-x.xx.exe-Datei) herunterzuladen.
1. Nachdem Sie Dateien von der Adobe-Kundenunterstützung erhalten und heruntergeladen haben, führen Sie den DWB-Einrichtungs-Assistenten aus, um die Workstation-Software auf Ihrem Clientcomputer zu installieren.

>[!NOTE]
Der DWB-Einrichtungs-Assistent führt Sie durch die Installation der DWB-Client-Workstation und hilft Ihnen bei der Suche nach Insight.cfg und `<PrimaryUser>`.pem-Dateien, die in den erforderlichen Ordnern platziert werden sollen. Die Datei Insight.cfg befindet sich zusammen mit der Datei Insight.exe in Ihrer installierten Client-Workstation. Die `<PrimaryUser>`.pem-Datei befindet sich im Ordner Zertifikate mit der Datei trust_ca_cert.pem . Damit DWB funktioniert, müssen alle Zertifikat- und Konfigurationsdateien vorhanden sein.

Weitere Informationen finden Sie im Abschnitt [DWB-Einrichtungs-Assistent](https://experienceleague.adobe.com/docs/data-workbench/using/install/workstation-setup/install-setup.html).

## Verbindung zu Ihren DWB-Servern {#section-8e79c4e07c2a4342a5bb8af6ee7be3c9}

Ihre verwalteten Server werden in der Datei Insight.cfg identifiziert, die Sie von der Adobe-Kundenunterstützung erhalten und sich auf Ihrer Client-Workstation befindet. Adobe TechOps richtet Ihre Server ein und die Adobe-Kundenunterstützung fügt der Datei Insight.cfg Verweise auf diese verwalteten Server und Profile hinzu, bevor sie sie an Sie sendet. (Die Konfiguration der Verbindungen zum Server in Schritt 12 der Dokumentation zum DWB-Einrichtungs-Assistenten wird abgeschlossen.)

>[!NOTE]
Im Arbeitsbereich Workstation-Konfiguration auf der DWB-Client-Workstation können Sie Ihre verbundenen Server und Profile sehen.

**Adobe Managed Services**

・ Adobe TechOps verwaltet die Infrastruktur einschließlich Netzwerk, Rechenzentrum, Server und Speicher. Die Überwachung der Infrastruktur und die Reaktion auf Warnhinweise erfolgen rund um die Uhr, wenn Warnhinweise erforderlich sind, die Maßnahmen von TechOps erfordern. Für andere Warnhinweise benachrichtigt TechOps die Kundenunterstützung der Adobe, um sich mit Ihnen abzustimmen.

・ Adobe TechOps führt Wartungs- und Firmware-Updates für Ihre verwalteten Server durch. Für Wartungsarbeiten, die zu Ausfallzeiten führen, erhalten Sie mindestens zwei Wochen im Voraus Wartungsfenster von der Kundenunterstützung. Adobe TechOps wird so schnell wie möglich auf dringende Bedürfnisse eingehen. Die Benachrichtigung hängt von der Dringlichkeit ab und wird aufgelöst, sobald der Zeitplan bekannt ist.

・ Adobe TechOps richtet eine geplante Aufgabe ein, um Daten automatisch zu verwalten. Analytische Feed-Daten werden jeden Abend ab 21:00 Uhr in die DWB verschoben, um verarbeitet und umgewandelt zu werden.

・ Adobe TechOps verarbeitet bei Bedarf weitere Adobe Managed Services, einschließlich Datensicherungen, FTP-Konten, Datenarchivierung und Datenübertragung.

・ Adobe TechOps konfiguriert den primären Produktionscluster so, dass er drei Monate rollierende Daten enthält, die monatlich zurückgesetzt und erneut verarbeitet werden. Aktualisierungen der Suche (Geografie, DeviceAtlas, Standardklassifizierungen) werden ebenfalls im Rahmen der Neuverarbeitungsaufgabe vorgenommen. Standardmäßig wird die Aufgabe am ersten Freitag eines jeden Monats ausgeführt. Bei Bedarf kann der Zeitplan von der Kundenunterstützung geändert werden.

Für weitere Informationen wenden Sie sich bitte an [Adobe-Kundenunterstützung](https://helpx.adobe.com/support/programs/enterprise-support-terms.html).
