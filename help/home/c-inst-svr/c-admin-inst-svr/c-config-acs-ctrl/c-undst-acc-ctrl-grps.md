---
description: Es stehen fünf vordefinierte Zugriffskontrollen zur Verfügung, Sie können jedoch bei Bedarf weitere Gruppen erstellen und verwalten.
title: Grundlagen zu Zugangssteuerungsgruppen
uuid: ff783078-6d2f-4a64-ab11-8083e35d765f
exl-id: 35353b0a-7f08-4215-8a2c-ee1e26d9f5db
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 9%

---

# Grundlagen zu Zugangssteuerungsgruppen{#understanding-access-control-groups}

Es stehen fünf vordefinierte Zugriffskontrollen zur Verfügung, Sie können jedoch bei Bedarf weitere Gruppen erstellen und verwalten.

Sie können die Mitglieder der einzelnen Zugriffskontrollen sowie die Ordner definieren, auf die jede Gruppe Schreibzugriff oder Schreibzugriff hat.

Die vordefinierten Gruppen werden wie folgt definiert:

| Gruppe | Beschreibung |
|---|---|
| Administratoren | Ermöglicht den Zugriff auf alle Ordner und Dateien. Die Standard-IP-Adresse ist 127.0.0.1 (lokaler Host). |
| Sensoren | Ermöglicht den Zugriff auf nur die Dateien, die von [!DNL Sensor] zum Übertragen von Daten verwendet werden. |
| Benutzer | Ermöglicht schreibgeschützten Zugriff auf die Elemente, die erforderlich sind, damit ein [!DNL Insight]-Benutzer grundlegende Aufgaben der Analyse durchführen kann. |
| Power-Benutzer | Ermöglicht schreibgeschützten Zugriff auf die Elemente, die erforderlich sind, damit ein [!DNL Insight]-Benutzer grundlegende Aufgaben zur Analyse durchführt, sowie Lese- und Schreibzugriff auf den Ordner [!DNL Profiles] zum Ändern von Profilen. |
| Clusterserver | Ermöglicht Zugriff auf [!DNL Insight Servers], die als Clusterserver bezeichnet sind. |
| Berichtsserver | Ermöglicht den Zugriff auf [!DNL Report]-Computer, die eine Verbindung mit [!DNL Insight Server] herstellen. |

Mitglieder einer Zugriffskontrolle werden mithilfe ihrer IP-Adressen oder SSL-Zertifikatsinformationen definiert.

Wenn kein SSL-Zertifikat verfügbar ist, kann eine IP-Adresse verwendet werden, um ein Gruppenmitglied zu definieren. Die typische Installation von [!DNL Insight] enthält ein SSL-Zertifikat, während die Verwendung von Zertifikaten für [!DNL Sensor(s)] optional ist. Für [!DNL Insight Server] werden Cluster-Server mit IP-Adressen anstelle von SSL-Zertifikaten definiert.

Die folgenden Codes können zur Definition von Gruppenmitgliedern verwendet werden:

| Zugriffsart-Code | Definition |
|---|---|
| O | Organisation |
| CN | Allgemeiner Name |
| L | Örtlichkeit |
| ST | Bundesland oder Bundesland |
| C | Country |
| OU | Organisationseinheit |
| E-Mail | E-Mail Adresse |
