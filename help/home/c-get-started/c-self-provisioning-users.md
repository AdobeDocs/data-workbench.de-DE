---
description: Verwenden Sie Workstation, um Ihre Data Workbench-Benutzer zu verwalten.
title: Selbstbereitstellung von Benutzern
uuid: e3c10bc4-2fa0-4368-9952-e38a4794aee9
translation-type: tm+mt
source-git-commit: cb3ca4b3b993f5f04f6b6cee25850600ff3d8986

---


# Selbstbereitstellung von Benutzern{#self-provisioning-of-users}

Verwenden Sie Workstation, um Ihre Data Workbench-Benutzer zu verwalten.

Sie können Workstation verwenden, um eine Verbindung zum Data Workbench-Server herzustellen, indem Sie das erforderliche Zertifikat von Adobe einrichten. Dieses Zertifikat unterstützt sowohl die SSL-Kommunikation als auch die Autorisierung zur Verwendung der lizenzierten Ressourcen und Funktionen. Bei der zertifikatbasierten Authentifizierung müssen Sie mehrere Zertifikate erwerben und einrichten, um die Workstation auf mehreren Computern zu verwenden. Außerdem werden Benutzerbereitstellungen und Berechtigungen von Adobe verwaltet und Sie müssen sich für neue Zertifikate oder Zertifikatsperrungen an Adobe wenden.

Ab DWB 6.7 unterstützt die Workstation die Benutzerauthentifizierung über Benutzernamen und Kennwort.

Während die zertifikatbasierte Authentifizierung/Autorisierung für Ihre Einrichtung weiterhin funktioniert, wird eine Migration zur neueren, berechtigungsbasierten Authentifizierung dringend empfohlen. Bei neueren Methoden authentifizieren sich Ihre Workstation-Benutzer über das Adobe Identity Management System (IMS). Bevor sie die Workstation verwenden können, müssen sie vom Administrator des Unternehmens über die [Admin-Konsole](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/admin-getting-started.html) Zugriff auf die Funktionen erhalten.

Das neue Authentifizierungs- und Benutzerbereitstellungsmodell hilft bei Folgendem:

* Selbstbereitstellung von Benutzern und Gruppen über die Admin-Konsole. Sie müssen sich nicht an Adobe wenden, um Lizenzberechtigungen für Benutzer hinzuzufügen, zu entfernen oder zu ändern.
* Zugriff auf Workstation von mehreren Computern aus, ohne den Konfigurationsstatus zu verlieren, indem Sie sich mit den Anmeldeinformationen anmelden. Der lokale Cache wird beim Abmelden gelöscht, das aktuelle Profil wird geschlossen und das Konfigurationsprofil wird aktiv.

## Erste Schritte

Wenden Sie sich zunächst an Adobe, um Ihre Organisation in der Admin-Konsole hinzuzufügen. Je nachdem, welche Dienste Sie erworben haben, stellt Adobe die Organisation für Sie bereit. Organisationen können beispielsweise Zugriff auf den Zuordnungs-Dienst oder auf Beta-Builds haben. Sobald eine Organisation konfiguriert ist, kann der Unternehmensadministrator Benutzer und Gruppen hinzufügen. Weitere Informationen finden Sie unter [Verwalten von Experience Cloud-Benutzern und -Produkten](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/admin-getting-started.html) in Experience Cloud. Der Organisationsadministrator kann außerdem je nach Rollen Nutzungsbeschränkungen für verschiedene Benutzer konfigurieren. Beispielsweise benötigen Benutzer ohne Vorabversion keinen Zugriff auf die Beta-Builds.

Jeder bereitgestellte Benutzer, der dieser Organisation über die Admin-Konsole hinzugefügt wird, hat Zugriff auf die Data Workbench. Die Unterdienste können je nach Produktzugriff nur für jeden Benutzer aktiviert oder deaktiviert werden. Wenn ein Benutzer vom Zertifikat auf das IMS aktualisiert wird, werden alle lokalen Daten in das neue IMS-Benutzerverzeichnis kopiert.

>[!NOTE]
>
>Eine Sitzung dauert 6 Stunden auf dem Server und 23 Stunden auf dem Client, es sei denn, das Zugriffstoken wird aktualisiert. Wenn das Token aktualisiert wird, können Sie den Client verwenden, ohne sich erneut anzumelden.

Der Administrator muss mindestens eine Konfiguration auf Produktebene in der Admin-Konsole erstellen, bevor er Zugriff auf einen beliebigen Benutzer erhält.

Das boolesche Flag IMS **verwenden** kann zum Ausweichmodus [!DNL Insight.cfg] des Zertifikats hinzugefügt werden. Informationen zum Konfigurieren der Zugriffssteuerung für IMS-Benutzer finden Sie unter [Aktualisieren der Zugriffssteuerungsdatei](https://docs.adobe.com/content/help/en/data-workbench/using/server-admin-install/install-servers/insight-server-dpu/c-updt-accss-ctrl-file.html).

## Konfliktlösung

Wenn ein Benutzer auf mehreren Computern mit demselben IMS-Konto im selben Profil angemeldet ist und sich auf einem der Computer im Offlinemodus befindet, werden Sie von einem `.conflict` möglichen Formular und einem Popup-Fenster in Kenntnis gesetzt. Dies tritt auf, wenn sich der Inhalt von Dateien (Arbeitsbereiche, Dimensionen, Filter usw.) unterscheidet. auf beiden Computern in [!DNL User\Profile\] auf Server und Client synchronisiert. Es wird eine Sicherung in der `.conflict` Datei erstellt und es gehen keine Daten verloren. Eine boolesche Flag in [!DNL Insight.cfg] gibt Ihnen die Möglichkeit, dieses Konflikt-Popup zu deaktivieren.

Markierung: Konfliktbenachrichtigungen

Dies gilt für Arbeitsbereiche, Metriken, Dimensionen usw. im Benutzerordner.
