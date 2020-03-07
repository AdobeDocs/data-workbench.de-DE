---
description: Der erste Schritt besteht darin, die IIS-Rolle auf Ihrem Dashboard-Server zu aktivieren.
solution: Analytics
title: Aktivieren von IIS
topic: Data workbench
uuid: fbd194db-3307-41ae-8ece-05eb261d74ad
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Aktivieren von IIS{#enabling-iis}

Der erste Schritt besteht darin, die IIS-Rolle auf Ihrem Dashboard-Server zu aktivieren.

1. Öffnen Sie **[!UICONTROL Administrative Tools]** die **[!UICONTROL Server Manager]**.
1. Klicken Sie mit der rechten Maustaste auf das Menüelement Rollen im linken Bereich des **[!UICONTROL Server Manager]** Fensters.
1. Auswählen **[!UICONTROL Add Roles]**.
1. Wählen Sie **[!UICONTROL Web Server (IIS)]** die Option und fahren Sie mit **[!UICONTROL Add Roles Wizard]**. Stellen Sie sicher, dass die folgenden Rollendienste aktiviert sind:

   | Allgemeine HTTP-Funktionen |
   |---|
   | Statischer Inhalt |
   | Standarddokument |
   | Directory Browsing |
   | HTTP-Fehler |
   | HTTP-Umleitung |

   | Anwendungsentwicklung |
   |---|
   | ASP.NET |
   | .NET-Erweiterbarkeit |
   | ISAPI-Erweiterungen |
   | ISAPI-Filter |

   | Gesundheit und Diagnose |
   |---|
   | HTTP-Protokollierung |
   | Protokollierungswerkzeuge |
   | Anforderungsmonitor |
   | Ablaufverfolgung |
   | Benutzerdefinierte Protokollierung |

   | Sicherheit |
   |---|
   | Grundlegende Authentifizierung |
   | Windows-Authentifizierung |
   | URL-Authentifizierung |
   | Anforderungsfilter |
   | IP- und Domänenbeschränkungen |

   | Verwaltungstools |
   |---|
   | IIS Management Console |
   | IIS-Verwaltungsskript und -Tools |
   | Verwaltungsdienst |

1. Folgen Sie dem Assistenten, um die Installation abzuschließen.
