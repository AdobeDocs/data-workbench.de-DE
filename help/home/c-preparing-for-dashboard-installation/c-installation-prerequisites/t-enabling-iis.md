---
description: Der erste Schritt besteht darin, die IIS-Rolle auf Ihrem Dashboard-Server zu aktivieren.
title: Aktivieren von IIS
uuid: fbd194db-3307-41ae-8ece-05eb261d74ad
exl-id: 0d431302-1e69-49b6-8757-9823fd70a3b4
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '126'
ht-degree: 4%

---

# Aktivieren von IIS{#enabling-iis}

{{eol}}

Der erste Schritt besteht darin, die IIS-Rolle auf Ihrem Dashboard-Server zu aktivieren.

1. under **[!UICONTROL Administrative Tools]**, öffnen Sie die **[!UICONTROL Server Manager]**.
1. Klicken Sie mit der rechten Maustaste auf das Menüelement Rollen im linken Bereich des **[!UICONTROL Server Manager]** Fenster.
1. Auswählen **[!UICONTROL Add Roles]**.
1. Auswählen **[!UICONTROL Web Server (IIS)]** und setzen Sie die **[!UICONTROL Add Roles Wizard]**. Stellen Sie sicher, dass die folgenden Rollendienste aktiviert sind:

   | Allgemeine HTTP-Funktionen |
   |---|
   | Statischer Inhalt |
   | Standarddokument |
   | Directory Browsing |
   | HTTP-Fehler |
   | HTTP-Weiterleitung |

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
   | Anforderungsfilterung |
   | IP- und Domänenbeschränkungen |

   | Management-Tools |
   |---|
   | IIS-Verwaltungskonsole |
   | IIS-Verwaltungsskript und -Tools |
   | Verwaltungsdienst |

1. Folgen Sie dem Assistenten, um die Installation abzuschließen.
