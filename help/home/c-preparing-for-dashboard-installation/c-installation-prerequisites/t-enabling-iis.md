---
description: Der erste Schritt besteht darin, die IIS-Rolle auf dem Dashboard-Server zu aktivieren.
title: Aktivieren von IIS
uuid: fbd194db-3307-41ae-8ece-05eb261d74ad
exl-id: 0d431302-1e69-49b6-8757-9823fd70a3b4
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '126'
ht-degree: 4%

---

# Aktivieren von IIS{#enabling-iis}

Der erste Schritt besteht darin, die IIS-Rolle auf dem Dashboard-Server zu aktivieren.

1. Öffnen Sie unter **[!UICONTROL Administrative Tools]** **[!UICONTROL Server Manager]** die
1. Klicken Sie mit der rechten Maustaste auf das Menüelement Rollen im linken Bereich des Fensters **[!UICONTROL Server Manager]**.
1. Auswählen **[!UICONTROL Add Roles]**.
1. Wählen Sie **[!UICONTROL Web Server (IIS)]** und fahren Sie mit **[!UICONTROL Add Roles Wizard]** fort. Stellen Sie sicher, dass die folgenden Rollendienste aktiviert sind:

   | Allgemeine HTTP-Funktionen |
   |---|
   | Statischer Inhalt |
   | Standard-Dokument |
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
