---
description: Adobe Data Workbench bietet Werkzeuge und Prozesse, mit denen Sie Ihre Daten entsprechend den allgemeinen Datenschutzbestimmungen (GDPR) bereitstellen können.
solution: Analytics
title: Data Workbench-Unterstützung für GDPR
topic: Data workbench
translation-type: tm+mt
source-git-commit: 4002d01c4c9aaa7d8833415aba3fa5105cb7ac1f

---


# Data Workbench-Unterstützung für GDPR

Adobe Data Workbench bietet Werkzeuge und Prozesse, mit denen Sie Ihre Daten an die [!DNL General Data Protection Regulations] (GDPR) anpassen können.

Wie alle Adobe Analytics-Lösungen bietet Data Workbench Unterstützung für GDPR, indem es bei der Verarbeitung des Adobe Analytics-Datenfeeds Datenbereingung, Löschung und Kennzeichnung von Analysevariablen bereitstellt. Um GDPR-Implementierungen zu unterstützen, können Sie mit Adobe Prozesse für GDPR gemäß den in Ihrem Vertrag mit Adobe festgelegten Berechtigungen Ihrer Firma einrichten. Weitere Informationen finden Sie unter [Adobe Analytics und GDPR](https://docs.adobe.com/content/help/en/analytics/admin/data-governance/an-gdpr-overview.html).

In der GDPR-Verordnung werden die Rollen und Pflichten der verschiedenen für die GDPR-Aktivierung verantwortlichen Parteien festgelegt (siehe [GDPR und Ihr Geschäft](https://www.adobe.com/de/privacy/general-data-protection-regulation.html)).

* Ihr Unternehmen fungiert als **für die Verarbeitung** von Daten verantwortlicher Person, um den Kontext und die Speicherung personenbezogener Daten anhand Ihrer Bedürfnisse und Einschränkungen zu bestimmen. Adobe verarbeitet und speichert diese Daten dann in Ihrem Namen.
* Adobe fungiert als **Datenverarbeiter** , der die Software und Dienste bereitstellt, um GDPR-Anforderungen auf der Grundlage Ihrer Vereinbarung mit Adobe zu implementieren.
* Nach der Integration von Data Workbench mit dem GDPR-Dienst und gemäß GDPR-Standards können Besucher einer Site (die **betroffenen Personen**) ihr &quot;Recht auf Vergessenheit&quot;von Adobe, dem Datenprozessor, ausüben. Um das Recht zu vergessen, können Sie als Datencontroller herausfordernde Besucher-IDs von einer Benutzeroberfläche oder API zu Adobe hochladen. Weitere Informationen finden Sie in der Dokumentation zum [Adobe Analytics GDPR-Workflow](https://docs.adobe.com/help/en/analytics/admin/data-governance/an-gdpr-workflow.html) , einschließlich des Abschnitts zum [Senden und Löschen von Anforderungen](https://docs.adobe.com/content/help/en/analytics/admin/data-governance/gdpr-submit-access-delete.html) .

>[!NOTE]
>
>Bei anderen Datenquellen ist Ihr Unternehmen dafür verantwortlich, herausfordernde Besucher-IDs aus anderen Protokollquellen wie CRM, POS, IVR und anderen Rohdatenquellen zu bereinigen. Es werden Pakete für benutzerdefinierte Dienste bereitgestellt, um Organisationen zu unterstützen, indem für jede Datenquelle _oder andere benutzerdefinierte Optionen ein vollständiger Dateisatz_ bereitgestellt wird.

## Aktualisieren von DWB für die GDPR-Implementierung

Consulting berät Sie beim passenden Dienstleistungspaket, um bestehende Implementierungen in Übereinstimmung zu bringen. Weitere Informationen erhalten Sie von Ihrem Customer Success Manager (CSM).

Falls erforderlich:

* [Aktualisieren Sie auf die neueste Version](https://docs.adobe.com/content/help/en/data-workbench/using/release-notes/release-notes.html) von Data Workbench. Für höchste Sicherheit wurden in den DWB 6.7-Versionen, die für die GDPR-Integration erforderlich sind, neue Zertifikate und Sicherheitsfunktionen hinzugefügt.
* Wenn Sie ältere TSV Analytics-Ereignis-Protokolle verwenden, aktualisieren Sie auf den [Avro-Datenfeed](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/log-proc-config-file/c-log-sources.html#section-9a824b4c3d5549e7952a7111232035b2).
* Wenn Sie einen veralteten UCP (Unified Customer Process) mit Transform verwenden, um vorhandene Protokolle zu aktualisieren, aktualisieren Sie auf den aktuellen Prozess. Der aktualisierte Vorgang generiert direkt eine Master-Lookup-Datei, um Besucher-IDs über mehrere Quellen hinweg zuzuordnen.
* Standardisieren Sie den Datenfluss, um den GDPR-Dienst aufzunehmen.
* Richten Sie ein kundenspezifisches Dienstleistungspaket ein, um andere Protokollquellen wie CRM, POS, IVR und andere Rohdatenquellen zu verwalten.
* Bestätigen Sie im Analytics-Vertrag eine Speicherdauer von Standarddaten von mindestens 25 Monaten.
