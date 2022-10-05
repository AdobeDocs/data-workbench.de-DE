---
description: Adobe Data Workbench bietet Tools und Prozesse, mit denen Sie Ihre Daten gemäß den Datenschutz-Grundverordnung (DSGVO) bereitstellen können.
title: Data Workbench und die DSGVO
exl-id: fdc43567-0c57-4851-9073-e295258a8074
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '518'
ht-degree: 4%

---

# Data Workbench und die DSGVO

{{eol}}

Adobe Data Workbench bietet Tools und Prozesse, mit denen Ihre Daten an die Anforderungen der [!DNL General Data Protection Regulations] (DSGVO).

Wie alle Adobe Analytics-Lösungen unterstützt Data Workbench die DSGVO, indem es bei der Verarbeitung des Adobe Analytics-Daten-Feeds Analysevariablen bereinigt, löscht und kennzeichnet. Um DSGVO-Implementierungen zu unterstützen, können Sie mit Adobe Prozesse für die DSGVO gemäß den Berechtigungen Ihres Unternehmens einrichten, die in Ihrer Vereinbarung mit Adobe festgelegt sind. Siehe [Adobe Analytics und DSGVO für weitere Informationen](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/an-gdpr-overview.html?lang=de).

In der DSGVO-Verordnung werden die Rollen und Pflichten der verschiedenen für die DSGVO-Aktivierung zuständigen Parteien festgelegt (siehe [DSGVO und Ihr Unternehmen](https://www.adobe.com/de/privacy/general-data-protection-regulation.html)).

* Ihr Unternehmen fungiert als **Datenverantwortlicher** um den Kontext und die Aufbewahrung personenbezogener Daten basierend auf Ihren Bedürfnissen und Einschränkungen zu bestimmen. Adobe verarbeitet und speichert diese Daten dann in Ihrem Namen.
* Adobe fungiert als **Datenprozessor** Bereitstellung der Software und Dienste zur Implementierung der DSGVO-Anforderungen auf der Grundlage Ihrer Vereinbarung mit Adobe.
* Nach Integration der Data Workbench in den DSGVO-Dienst und gemäß den DSGVO-Standards können Besucher einer Site (die **Datensubjekte**) kann ihr &quot;Recht auf Vergessenwerden&quot;von Adobe, dem Datenverarbeiter, ausüben. Um das Recht auf Vergessenwerden zu erreichen, können Sie als Datenverantwortlicher herausfordernde Besucher-IDs von einer Benutzeroberfläche oder API in die Adobe hochladen. Siehe [DSGVO-Workflow von Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/an-gdpr-workflow.html?lang=en) Dokumentation für weitere Informationen, einschließlich [Zugriffs- und Löschanfragen einreichen](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/gdpr-submit-access-delete.html) Abschnitt.

>[!NOTE]
>
>Bei anderen Datenquellen ist Ihr Unternehmen für die Bereinigung von herausfordernden Besucher-IDs aus anderen Protokollquellen wie CRM, POS, IVR und anderen Rohdatenquellen verantwortlich. Benutzerdefinierte Dienstleistungspakete stehen zur Verfügung, um Unternehmen durch _Bereitstellung eines vollständigen Ersatzsatzes von Dateien für jede Datenquelle_ dass ständige Service-Reservierer zur Unterstützung oder Wartung erforderlich sind.

## Aktualisierung von DWB für die DSGVO-Implementierung

Consulting berät Sie bezüglich des entsprechenden Dienstleistungspakets, um die Kompatibilität vorhandener Implementierungen zu gewährleisten. Weitere Informationen erhalten Sie von Ihrem Customer Success Manager (CSM).

Falls erforderlich:

* [Aktualisierung auf die neueste Version](https://experienceleague.adobe.com/docs/data-workbench/using/release-notes/release-notes.html) der Data Workbench. Für höchste Sicherheit wurden in den DWB 6.7-Versionen, die für die DSGVO-Integration erforderlich sind, neue Zertifikate und Sicherheitsfunktionen hinzugefügt.
* Wenn Sie veraltete TSV Analytics-Ereignisprotokolle verwenden, aktualisieren Sie auf [Avro-Daten-Feed](https://experienceleague.adobe.com/docs/data-workbench/using/dataset/log-proc-config-file/c-log-sources.html#section-9a824b4c3d5549e7952a7111232035b2).
* Wenn Sie eine alte UCP (Unified Customer Process) mit Transform verwenden, um vorhandene Protokolle zu aktualisieren, aktualisieren Sie auf den aktuellen Prozess. Der aktualisierte Prozess generiert direkt eine Übergeordnete Lookup-Datei für die Quellenzuordnung von Besucher-IDs.
* Standardisieren Sie den Datenfluss, um den DSGVO-Dienst aufzunehmen.
* Richten Sie ein Dienstleistungspaket mit benutzerdefiniertem Umfang ein, um andere Protokollquellen wie CRM, POS, IVR und andere Rohdatenquellen zu verwalten.
* Bestätigen Sie im Analytics-Vertrag eine standardmäßige Datenaufbewahrungsdauer von 25 Monaten oder mehr.
