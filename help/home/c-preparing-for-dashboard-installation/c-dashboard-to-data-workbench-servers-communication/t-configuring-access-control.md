---
description: Für das Dashboard sind bestimmte schreibgeschützte Berechtigungen erforderlich, um auf Ihre Daten in Data Workbench zugreifen und diese anzeigen zu können. Schreibberechtigungen sind nicht erforderlich.
title: Konfigurieren der Dashboard-Zugriffssteuerung
uuid: 600b6799-547d-46da-9027-4f64943e2ccd
exl-id: a9ff61bb-c519-4205-8fa8-bfd1986fcd60
source-git-commit: 90b9fff995cb37a62024f454f009e9e0d7b927cd
workflow-type: tm+mt
source-wordcount: '165'
ht-degree: 2%

---

# Konfigurieren der Dashboard-Zugriffssteuerung{#configuring-dashboard-access-control}

{{eol}}

Für das Dashboard sind bestimmte schreibgeschützte Berechtigungen erforderlich, um auf Ihre Daten in Data Workbench zugreifen und diese anzeigen zu können. Schreibberechtigungen sind nicht erforderlich.

Die Konfiguration der Zugriffskontrolle umfasst die Bearbeitung Ihrer [!DNL Access Control.cfg] in die FSUs ein und fügen Sie eine neue Gruppe hinzu, um Berechtigungen für das Data Workbench-Dashboard zu erteilen:

1. Bearbeiten Sie die [!DNL AccessControl.cfg] -Datei (vorzugsweise unter Verwendung der Data Workbench-Workstation).
1. Erstellen Sie eine neue Gruppe mit dem Namen *Zugriff auf Insight Dashboard*.
1. Fügen Sie unter den Mitgliedern dieser Gruppe die entsprechende KN hinzu, die Sie zu diesem Zweck erhalten haben (Beispiel: CN:INSIGHT-USER01). Wenden Sie sich an die Kundenunterstützung von Adobe für diese KN.
1. Ändern Sie unter schreibgeschützter Zugriff dieser Gruppe die Liste, um Folgendes widerzuspiegeln:

* /Profile/$
* /Profile/
* /Adressen
* /Status/
* /Benutzer/$

1. Entfernen Sie alle Elemente aus dem Bereich Lese- und Schreibzugriff , da für das Dashboard keine Schreibberechtigungen erforderlich sind.
1. Speichern Sie die Änderungen in der [!DNL AccessControl.cfg] -Datei auf den Server, damit die Berechtigungen wirksam werden.
