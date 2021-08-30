---
description: Adobe Data Workbench bietet Tools und Prozesse, mit denen Sie Ihre Daten gemäß den Datenschutz-Grundverordnung (DSGVO) bereitstellen können.
title: Data Workbench und die DSGVO
exl-id: fdc43567-0c57-4851-9073-e295258a8074
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '517'
ht-degree: 4%

---

# Data Workbench und die DSGVO

Adobe Data Workbench bietet Tools und Prozesse, mit denen Ihre Daten an die [!DNL General Data Protection Regulations] (DSGVO) angepasst werden können.

Wie alle Adobe Analytics-Lösungen unterstützt Data Workbench die DSGVO, indem es bei der Verarbeitung des Adobe Analytics-Daten-Feeds Analysevariablen bereinigt, löscht und kennzeichnet. Um DSGVO-Implementierungen zu unterstützen, können Sie mit Adobe Prozesse für die DSGVO gemäß den Berechtigungen Ihres Unternehmens einrichten, die in Ihrer Vereinbarung mit Adobe festgelegt sind. Weitere Informationen finden Sie unter [Adobe Analytics und die DSGVO](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/an-gdpr-overview.html?lang=de).

In der DSGVO-Verordnung werden die Rollen und Pflichten der verschiedenen für die DSGVO-Aktivierung verantwortlichen Parteien festgelegt (siehe [DSGVO und Ihr Unternehmen](https://www.adobe.com/de/privacy/general-data-protection-regulation.html)).

* Ihr Unternehmen fungiert als **Datenverantwortlicher**, um den Kontext und die Aufbewahrung personenbezogener Daten basierend auf Ihren Anforderungen und Einschränkungen zu bestimmen. Adobe verarbeitet und speichert diese Daten dann in Ihrem Namen.
* Adobe fungiert als **Datenverarbeiter**, der die Software und Dienste bereitstellt, um DSGVO-Anforderungen auf der Grundlage Ihrer Vereinbarung mit Adobe zu implementieren.
* Nach Integration der Data Workbench in den DSGVO-Dienst und gemäß den DSGVO-Standards können Besucher einer Site (die **Datensubjekte**) ihr &quot;Recht auf Vergessenwerden&quot;von der Adobe, dem Datenverarbeiter, ausüben. Um das Recht auf Vergessenwerden zu erreichen, können Sie als Datenverantwortlicher herausfordernde Besucher-IDs von einer Benutzeroberfläche oder API in die Adobe hochladen. Weitere Informationen finden Sie in der Dokumentation [Adobe Analytics DSGVO-Workflow](https://docs.adobe.com/help/en/analytics/admin/data-governance/an-gdpr-workflow.html) , einschließlich des Abschnitts [Zugriffs- und Löschanfragen senden](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/gdpr-submit-access-delete.html) .

>[!NOTE]
>
>Bei anderen Datenquellen ist Ihr Unternehmen für die Bereinigung von herausfordernden Besucher-IDs aus anderen Protokollquellen wie CRM, POS, IVR und anderen Rohdatenquellen verantwortlich. Es stehen Pakete für benutzerdefinierte Dienste zur Verfügung, die Unternehmen unterstützen können, indem sie _einen vollständigen Ersatz-Satz von Dateien für jede Datenquelle_ bereitstellen, für die fortlaufende Service-Provider zur Unterstützung oder Wartung erforderlich sind.

## Aktualisierung von DWB für die DSGVO-Implementierung

Consulting berät Sie bezüglich des entsprechenden Dienstleistungspakets, um die Kompatibilität vorhandener Implementierungen zu gewährleisten. Weitere Informationen erhalten Sie von Ihrem Customer Success Manager (CSM).

Falls erforderlich:

* [Aktualisieren Sie auf die neueste ](https://experienceleague.adobe.com/docs/data-workbench/using/release-notes/release-notes.html) Version der Data Workbench. Für höchste Sicherheit wurden in den DWB 6.7-Versionen, die für die DSGVO-Integration erforderlich sind, neue Zertifikate und Sicherheitsfunktionen hinzugefügt.
* Wenn Sie veraltete TSV Analytics-Ereignisprotokolle verwenden, aktualisieren Sie auf den [Avro-Datenfeed](https://experienceleague.adobe.com/docs/data-workbench/using/dataset/log-proc-config-file/c-log-sources.html#section-9a824b4c3d5549e7952a7111232035b2).
* Wenn Sie eine alte UCP (Unified Customer Process) mit Transform verwenden, um vorhandene Protokolle zu aktualisieren, aktualisieren Sie auf den aktuellen Prozess. Der aktualisierte Prozess generiert direkt eine Übergeordnete Lookup-Datei für die Quellenzuordnung von Besucher-IDs.
* Standardisieren Sie den Datenfluss, um den DSGVO-Dienst aufzunehmen.
* Richten Sie ein Dienstleistungspaket mit benutzerdefiniertem Umfang ein, um andere Protokollquellen wie CRM, POS, IVR und andere Rohdatenquellen zu verwalten.
* Bestätigen Sie im Analytics-Vertrag eine standardmäßige Datenaufbewahrungsdauer von 25 Monaten oder mehr.
