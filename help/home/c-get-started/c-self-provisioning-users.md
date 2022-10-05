---
description: Verwenden Sie Workstation, um Ihre Data Workbench-Benutzer zu verwalten.
title: Selbstbereitstellung von Benutzern
uuid: e3c10bc4-2fa0-4368-9952-e38a4794aee9
exl-id: fba916bf-66a1-4b69-a1c0-cad5b27bbbba
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '596'
ht-degree: 3%

---

# Selbstbereitstellung von Benutzern{#self-provisioning-of-users}

{{eol}}

Verwenden Sie Workstation, um Ihre Data Workbench-Benutzer zu verwalten.

Sie können Workstation verwenden, um eine Verbindung zum Data Workbench-Server herzustellen, indem Sie das erforderliche Zertifikat von Adobe aus einrichten. Dieses Zertifikat unterstützt sowohl die SSL-Kommunikation als auch die Autorisierung zur Verwendung der lizenzierten Ressourcen und Funktionen. Bei der zertifikatbasierten Authentifizierung müssen Sie mehrere Zertifikate erwerben und einrichten, damit Sie die Workstation auf mehreren Computern verwenden können. Die Benutzerbereitstellung und -berechtigungen werden außerdem von Adobe verwaltet. Sie müssen sich an die Adobe wenden, um neue Zertifikate oder Zertifikatsperrungen zu erhalten.

Ab DWB 6.7 unterstützt die Workstation die Benutzerauthentifizierung über Benutzernamen und Kennwort.

Während die zertifikatbasierte Authentifizierung/-Autorisierung weiterhin für Ihre Einrichtung funktioniert, wird dringend empfohlen, zur neueren authentifizierungsbasierten Authentifizierung zu migrieren. Im neueren Ansatz authentifizieren sich Ihre Workstation-Benutzer selbst über das Adobe Identity Management System (IMS). Bevor sie die Workstation verwenden können, müssen sie über die [Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=de) durch den Administrator der Organisation.

Das neue Authentifizierungs- und Benutzerbereitstellungsmodell hilft bei Folgendem:

* Selbstbereitstellung von Benutzern und Gruppen durch Admin Console. Sie müssen sich nicht an die Adobe wenden, um Lizenzberechtigungen für Benutzer hinzuzufügen, zu entfernen oder zu ändern.
* Zugreifen auf Workstation von mehreren Computern aus, ohne den Konfigurationsstatus zu verlieren, indem Sie sich mit Anmeldeinformationen anmelden. Der lokale Cache wird beim Abmelden gelöscht, das aktuelle Profil wird geschlossen und das Konfigurationsprofil wird aktiv.

## Erste Schritte

Bevor Sie beginnen, wenden Sie sich an die Adobe, um Ihre Organisation zur Admin Console hinzuzufügen. Abhängig von den von Ihnen erworbenen Dienstleistungen stellt Adobe die Organisation für Sie bereit. Unternehmen können beispielsweise Zugriff auf den Attributionsdienst, die Beta-Builds oder beides haben. Sobald eine Organisation konfiguriert ist, kann der Organisationsadministrator Benutzer und Gruppen hinzufügen. Siehe [Verwalten von Experience Cloud-Benutzern und -produkten](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html) in Experience Cloud für weitere Informationen. Der Organisationsadministrator kann abhängig von seinen Rollen auch Nutzungsbeschränkungen für verschiedene Benutzer konfigurieren. Beispielsweise benötigen Benutzer ohne Vorabversion keinen Zugriff auf die Beta-Builds.

Jeder bereitgestellte Benutzer, der dieser Organisation über die Admin Console hinzugefügt wird, hat Zugriff auf die Data Workbench. Die Unterdienste können je nach Produktzugriff nur für jeden Benutzer aktiviert oder deaktiviert werden. Wenn ein Benutzer vom Zertifikat auf IMS aktualisiert wird, werden alle lokalen Daten in das neue IMS-Benutzerverzeichnis kopiert.

>[!NOTE]
>
>Eine Sitzung dauert 6 Stunden auf dem Server und 23 Stunden auf dem Client, es sei denn, das Zugriffstoken wird aktualisiert. Wenn das Token aktualisiert wird, können Sie den Client verwenden, ohne sich erneut anzumelden.

Es muss mindestens eine Konfiguration auf Produktebene vom Administrator in Admin Console erstellt werden, bevor einem Benutzer Zugriff gewährt wird.

Die boolesche Kennzeichnung **IMS verwenden** kann hinzugefügt werden zu [!DNL Insight.cfg] , um in den Zertifikatmodus zurückzukehren. Informationen zum Konfigurieren der Zugriffskontrolle für IMS-Benutzer finden Sie unter [Aktualisieren der Datei &quot;Zugriffskontrolle&quot;](https://experienceleague.adobe.com/docs/data-workbench/using/server-admin-install/install-servers/insight-server-dpu/c-updt-accss-ctrl-file.html).

## Konfliktbeilegung

Wenn ein Benutzer auf mehreren Computern mit demselben IMS-Konto für dasselbe Profil angemeldet ist und sich auf einem der Computer im Offline-Modus befindet, wird ein `.conflict` können sich bilden und Sie werden von einem Popup-Fenster informiert. Dies tritt auf, wenn sich der Inhalt von Dateien (Arbeitsbereichen, Dimensionen, Filtern usw.) unterscheidet. auf beiden Computern synchronisiert werden in [!DNL User\Profile\] auf dem Server und Client . Eine Sicherung wird im `.conflict` und keine Daten verloren gehen. Eine boolesche Kennzeichnung in [!DNL Insight.cfg] bietet Ihnen die Möglichkeit, dieses Konflikt-Popup zu deaktivieren.

Markierung: Konfliktbenachrichtigungen

Dies gilt für Arbeitsbereiche, Metriken, Dimensionen usw. im Benutzerordner.
