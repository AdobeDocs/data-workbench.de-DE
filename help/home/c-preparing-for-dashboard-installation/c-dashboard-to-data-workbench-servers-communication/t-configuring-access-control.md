---
description: Für das Dashboard sind bestimmte schreibgeschützte Berechtigungen erforderlich, um auf Ihre Daten in Data Workbench zugreifen und diese anzeigen zu können. Schreibberechtigungen sind nicht erforderlich.
title: Konfigurieren der Zugangssteuerung
uuid: 600b6799-547d-46da-9027-4f64943e2ccd
exl-id: a9ff61bb-c519-4205-8fa8-bfd1986fcd60
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 6%

---

# Konfigurieren der Zugangssteuerung{#configuring-access-control}

Für das Dashboard sind bestimmte schreibgeschützte Berechtigungen erforderlich, um auf Ihre Daten in Data Workbench zugreifen und diese anzeigen zu können. Schreibberechtigungen sind nicht erforderlich.

Das Konfigurieren der Zugriffskontrolle umfasst die Bearbeitung Ihrer [!DNL Access Control.cfg]-Datei in den FSUs und das Hinzufügen einer neuen Gruppe, um dem Data Workbench-Dashboard Berechtigungen zu erteilen:

1. Bearbeiten Sie die Datei [!DNL AccessControl.cfg] (vorzugsweise unter Verwendung der Data Workbench-Workstation).
1. Erstellen Sie eine neue Gruppe mit dem Namen *Insight Dashboard Access*.
1. Fügen Sie unter den Mitgliedern dieser Gruppe die entsprechende KN hinzu, die Sie zu diesem Zweck erhalten haben (Beispiel: CN:INSIGHT-USER01). Wenden Sie sich an die Kundenunterstützung von Adobe für diese KN.
1. Ändern Sie unter schreibgeschützter Zugriff dieser Gruppe die Liste, um Folgendes widerzuspiegeln:

* /Profile/$
* /Profile/
* /Adressen
* /Status/
* /Benutzer/$

1. Entfernen Sie alle Elemente aus dem Bereich Lese- und Schreibzugriff , da für das Dashboard keine Schreibberechtigungen erforderlich sind.
1. Speichern Sie die Änderungen an der Datei [!DNL AccessControl.cfg] auf dem Server, damit die Berechtigungen wirksam werden.
