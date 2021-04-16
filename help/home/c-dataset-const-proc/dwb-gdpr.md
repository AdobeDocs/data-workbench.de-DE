---
description: Adobe Data Workbench bietet Tools und Prozesse, um Ihre Daten gemäß den Allgemeinen Datenschutzbestimmungen (GDPR) bereitzustellen.
title: Data Workbench und die DSGVO
exl-id: fdc43567-0c57-4851-9073-e295258a8074
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 4%

---

# Data Workbench und die DSGVO

Adobe Data Workbench bietet Tools und Prozesse, mit denen Sie Ihre Daten entsprechend dem [!DNL General Data Protection Regulations] (GDPR) bereitstellen können.

Wie alle Adobe Analytics-Lösungen bietet Data Workbench Unterstützung für GDPR, indem sie bei der Verarbeitung des Adobe Analytics-Datenfeeds Datenbereingung, Löschen und Kennzeichnung von Analysevariablen bereitstellt. Zur Unterstützung von GDPR-Implementierungen können Sie mit Adobe Prozesse für GDPR entsprechend den Berechtigungen Ihrer Firma einrichten, die in Ihrem Vertrag mit der Adobe festgelegt sind. Weitere Informationen finden Sie unter [Adobe Analytics und GDPR.](https://docs.adobe.com/content/help/en/analytics/admin/data-governance/an-gdpr-overview.html)

In der GDPR-Verordnung werden die Rollen und Pflichten der verschiedenen für die GDPR-Aktivierung verantwortlichen Parteien festgelegt (siehe [GDPR und Ihr Unternehmen](https://www.adobe.com/de/privacy/general-data-protection-regulation.html)).

* Ihr Unternehmen fungiert als **Datencontroller**, um den Kontext und die Speicherung personenbezogener Daten basierend auf Ihren Bedürfnissen und Einschränkungen zu bestimmen. Adobe verarbeitet und speichert diese Daten dann in Ihrem Namen.
* Adobe fungiert als **Datenprozessor**, um die Software und Dienste zur Implementierung von GDPR-Anforderungen bereitzustellen, die auf Ihrem Vertrag mit Adobe basieren.
* Nach der Integration der Data Workbench mit dem GDPR-Dienst und gemäß GDPR-Standards können Besucher einer Site (die **Datensubjekte**) ihr &quot;Recht auf Vergessenheit&quot; durch die Adobe, den Datenprozessor, ausüben. Um das Recht zu vergessen, können Sie als Datencontroller herausfordernde Besucher-IDs von einer Benutzeroberfläche oder API in die Adobe hochladen. Weitere Informationen finden Sie in der Dokumentation zum [Adobe Analytics GDPR-Workflow](https://docs.adobe.com/help/en/analytics/admin/data-governance/an-gdpr-workflow.html), einschließlich des Abschnitts [Anforderungen senden und löschen](https://docs.adobe.com/content/help/en/analytics/admin/data-governance/gdpr-submit-access-delete.html).

>[!NOTE]
>
>Bei anderen Datenquellen ist Ihr Unternehmen dafür verantwortlich, herausfordernde Besucher-IDs aus anderen Protokollquellen wie CRM, POS, IVR und anderen Rohdatenquellen zu bereinigen. Benutzerdefinierte Dienstleistungspakete stehen zur Unterstützung von Organisationen zur Verfügung, indem _für jede Datenquelle_ ein vollständiger Ersatz-Satz von Dateien bereitgestellt wird, den fortlaufende Service-Aufbewahrer zur Unterstützung oder Wartung benötigen.

## Aktualisieren von DWB für die GDPR-Implementierung

Consulting berät Sie beim passenden Dienstleistungspaket, um bestehende Implementierungen in Übereinstimmung zu bringen. Weitere Informationen erhalten Sie von Ihrem Customer Success Manager (CSM).

Falls erforderlich:

* [Aktualisieren Sie auf die neueste ](https://docs.adobe.com/content/help/de-DE/data-workbench/using/release-notes/release-notes.html) Version der Data Workbench. Für höchste Sicherheit wurden in den DWB 6.7-Versionen, die für die GDPR-Integration erforderlich sind, neue Zertifikate und Sicherheitsfunktionen hinzugefügt.
* Wenn Sie ältere TSV Analytics-Ereignis-Protokolle verwenden, aktualisieren Sie auf den [Avro-Datenfeed](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/log-proc-config-file/c-log-sources.html#section-9a824b4c3d5549e7952a7111232035b2).
* Wenn Sie einen veralteten UCP (Unified Customer Process) mit Transform verwenden, um vorhandene Protokolle zu aktualisieren, aktualisieren Sie auf den aktuellen Prozess. Der aktualisierte Prozess generiert direkt eine Übergeordnet Lookup-Datei, um Besucher-IDs über mehrere Quellen hinweg zuzuordnen.
* Standardisieren Sie den Datenfluss, um den GDPR-Dienst aufzunehmen.
* Richten Sie ein kundenspezifisches Dienstleistungspaket ein, um andere Protokollquellen wie CRM, POS, IVR und andere Rohdatenquellen zu verwalten.
* Bestätigen Sie im Analytics-Vertrag eine Speicherdauer von Standarddaten von mindestens 25 Monaten.
