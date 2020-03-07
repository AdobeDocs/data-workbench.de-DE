---
description: Führen Sie die folgenden Schritte aus, um den Onboarding-Prozess für Adobe Data Workbench (DWB), eine Komponente von Adobe Analytics Premium (AAP), zu starten.
title: Grundlegende Anweisungen für DWB Managed Services
uuid: ad44a4eb-00ea-49c7-8401-58976d8fe39e
translation-type: tm+mt
source-git-commit: ded50c4eeadea80156c17a4cad985d0ceddd5500

---


# Grundlegende Anweisungen für DWB Managed Services{#basic-onboarding-instructions-for-dwb-managed-services}

Führen Sie die folgenden Schritte aus, um den Onboarding-Prozess für Adobe Data Workbench (DWB), eine Komponente von Adobe Analytics Premium (AAP), zu starten.

Diese Anweisungen zum Einstieg richten richten sich an Kunden, die Data Workbench mit einer einzigen Report Suite implementieren, indem sie von Adobe verwaltete Dienste ohne Beratungsdienste nutzen. Wenn Sie ein neuer AAP-Kunde sind, der DWB implementiert, ist das Adobe Onboarding-Team Ihr erster Ansprechpartner. Wenn Sie ein Upgrade vom Adobe Analytics-Standard oder von einer früheren Version von DWB durchführen, hilft Ihnen ein Adobe-Kundenbetreuer.

## Informationen zum Einstieg: Was wir von Ihnen brauchen {#section-bdeb9aa26dc14e45a6c90920832becaa}

Adobe wird Sie kontaktieren unter:

* Identifizieren Sie einen primären Benutzer für DWB, um ein Zertifikat speziell für diesen Benutzer im Netzwerkverzeichnis zu generieren. Der Hauptbenutzer fungiert auch als Ansprechpartner für die Interaktion mit der Adobe-Kundenunterstützung.
* Identifizieren Sie die Report Suite, die in DWB geladen werden soll.

Die Adobe Digital Marketing-Teams verwenden dann Ihre Informationen, um Profile zu erstellen, Konten einzurichten und eine Konfigurationsdatei für DWB bereitzustellen.

**Adobe Onboarding Tasks**

* Der Adobe-Kundendienst erstellt ein lizenziertes DWB-Konto. Der Adobe-Kundendienst generiert ein DWB-Zertifikat für den primären Benutzer.
* Der Adobe-Kundendienst definiert den primären Benutzer als &quot;unterstützten Benutzer&quot;, d. h. die für unterstützte Aufrufe und Problemlösungen identifizierte Person.
* Der Adobe-Kundendienst lädt das Softwarepaket in das DWB-Lizenz- und Softwareportal (SoftDocs/Software- und Docs-Profil), das Sie in Ihr Unternehmen herunterladen können.
* Das Adobe TechOps-Team bereitet die Produktions- und Entwicklungsumgebungen und deren Profile (pro Vertrag) für DWB vor.
* Das Adobe TechOps-Team konfiguriert Datenfeeds und Profilverwaltungsskripte.
* Das Adobe TechOps-Team erstellt die DWB-Konfigurationsdatei (Insight.cfg) und sendet sie an das Adobe Onboarding-Team, das für die mit Ihrem Unternehmen verbundenen Einstiegsaufgaben zuständig ist.

Nach der Anpassung Ihrer Datenfeeds und der Generierung von Berechtigungen, Zertifikaten und einer Profilkonfiguration sendet der Adobe-Kundendienst Ihre Konfigurationsdatei und Ihre Anmeldeinformationen, um den nächsten Schritt durchzuführen.

## Zugriff auf benutzerdefinierte Installationsdateien {#section-26962bf57fef435dbd1c5486d4b6f688}

Sie erhalten diese Setupdateien vom Adobe-Kundendienst, um die DWB-Workstation auf Ihrem Clientcomputer zu installieren.

* Ihre benutzerdefinierte DWB-Konfigurationsdatei (Insight.cfg)

   Diese Konfigurationsdatei auf dem Clientcomputer enthält Verbindungen zu Ihren verwalteten DWB-Servern.

* Melden Sie sich für das Lizenzportal an, um den DWB Setup Wizard und das erforderliche Zertifikat (PEM-Datei) mit dem Namen Ihres primären Benutzers herunterzuladen.

**Herunterladen zusätzlicher Setupdateien**

1. Gehen Sie zu: license.visualsciences.com zum Herunterladen des Lizenzzertifikats und der ausführbaren Datei des DWB Setup Wizard.
1. Geben Sie Ihre Organisation (Kontoname), den Namen des primären Benutzers und das Passwort ein, das Sie vom Adobe-Kundendienst erhalten haben, und klicken Sie dann auf Anmelden.

   >[!NOTE]
   >
   >Ihr Browser fordert Sie möglicherweise auf, zu diesem Zeitpunkt ein digitales Zertifikat vorzulegen. Wenn dies der Fall ist, klicken Sie auf &quot;Abbrechen&quot;, um das Dialogfeld zu schließen.

1. Suchen Sie im Abschnitt Downloads das für Ihre Instanz von Adobe Data Workbench (`<PrimaryUser>`.pem) ausgestellte Zertifikat und laden Sie es herunter.
1. Suchen Sie im Abschnitt Downloads nach dem Standard-Client-Installationsprogramm, um den DWB Setup Wizard (InsightSetup-x.xx.exe-Datei) herunterzuladen.
1. Nachdem Sie Dateien vom Adobe-Kundendienst erhalten und heruntergeladen haben, führen Sie den DWB-Setup-Assistenten aus, um die Workstation-Software auf Ihrem Clientcomputer zu installieren.

>[!NOTE]
Der DWB-Setup-Assistent führt Sie durch die Installation der DWB-Client-Workstation und hilft Ihnen bei der Suche der Insight.cfg- und `<PrimaryUser>`.pem-Dateien, die in den erforderlichen Ordnern platziert werden sollen. Die Datei &quot;Insight.cfg&quot;befindet sich zusammen mit der Datei &quot;Insight.exe&quot;in Ihrer installierten Client-Workstation. Die Datei `<PrimaryUser>`.pem befindet sich im Ordner &quot;Certificates&quot;mit der Datei &quot;trust_ca_cert.pem&quot;. Alle Zertifikat- und Konfigurationsdateien müssen vorhanden sein, damit DWB funktioniert.

Weitere Informationen finden Sie im [DWB-Setup-Assistenten](https://docs.adobe.com/content/help/en/data-workbench/using/install/workstation-setup/install-setup.html).

## Verbindung zu DWB-Servern {#section-8e79c4e07c2a4342a5bb8af6ee7be3c9}

Ihre verwalteten Server werden in der Datei Insight.cfg identifiziert, die Sie vom Adobe-Kundendienst erhalten, und befinden sich auf Ihrer Client-Workstation. Adobe TechOps richtet Ihre Server ein, und der Adobe-Kundendienst fügt der Datei Insight.cfg Verweise auf diese verwalteten Server und Profile hinzu, bevor sie an Sie gesendet wird. (Die Dokumentation zum DWB-Setup-Assistenten zum Konfigurieren von Verbindungen mit dem Server in Schritt 12 wird abgeschlossen.)

>[!NOTE]
Im Arbeitsbereich &quot;Workstation-Konfiguration&quot;auf der DWB-Client-Workstation können Sie Ihre angeschlossenen Server und Profile sehen.

**Adobe Managed Services**

・ Adobe TechOps verwaltet die Infrastruktur einschließlich Netzwerk, Rechenzentrum, Server und Speicher. Die Überwachung der Infrastruktur und die Reaktion auf Warnungen erfolgen rund um die Uhr bei Warnungen, die eine TechOps-Aktion erfordern. Bei anderen Warnungen benachrichtigt TechOps den Adobe-Kundendienst, sich mit Ihnen abzustimmen.

・ Adobe TechOps führt Wartungs- und Firmware-Updates für Ihre verwalteten Server durch. Für Wartungsarbeiten, die zu Ausfallzeiten führen, erhalten Sie vom Kundendienst mindestens zwei Wochen im Voraus Benachrichtigungen über das Wartungsfenster. Adobe TechOps wird so schnell wie möglich auf dringende Bedürfnisse eingehen. Die Benachrichtigung hängt von der Dringlichkeit ab und wird nach Bekanntwerden des Zeitplans gelöst.

・ Adobe TechOps richtet eine geplante Aufgabe ein, um Daten automatisch zu verwalten. Analytische Feed-Daten werden jeden Abend ab 21:00 Uhr zur Verarbeitung und Konvertierung in DWB verschoben.

・ Adobe TechOps verarbeitet bei Bedarf andere Adobe Managed Services wie Datensicherungen, FTP-Konten, Datenarchivierung und Datenübertragung.

・ Adobe TechOps konfiguriert den primären Produktionscluster so, dass er drei Monate rollierende Daten enthält, die monatlich zurückgesetzt und erneut verarbeitet werden. Aktualisierungen der Suche (Geografie, DeviceAtlas, Standard-Klassifizierungen) werden ebenfalls im Rahmen der Wiederaufbereitung vorgenommen. Die Aufgabe wird standardmäßig am ersten Freitag eines jeden Monats ausgeführt. Bei Bedarf kann der Zeitplan vom Kundendienst geändert werden.

Weitere Informationen erhalten Sie beim [Adobe-Kundendienst](https://helpx.adobe.com/support/programs/enterprise-support-terms.html).
