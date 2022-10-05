---
description: Wenn Insight mit den angegebenen Einstellungen keine Verbindung zu Insight Server herstellen kann, wird im Server-Manager ein roter Knoten angezeigt.
title: Beheben von Verbindungsproblemen
uuid: 17190cee-da5c-449f-aca5-8e9e35e0a5fd
exl-id: 7938d4d6-e1ab-46d9-9ccb-cf79677c5688
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 2%

---

# Beheben von Verbindungsproblemen{#connection-troubleshooting}

{{eol}}

Wenn Insight mit den angegebenen Einstellungen keine Verbindung zu Insight Server herstellen kann, wird im Server-Manager ein roter Knoten angezeigt.

Dies kann beispielsweise vorkommen, wenn Sie die Verbindung falsch konfigurieren oder nicht über die Berechtigung zum Anzeigen der [!DNL Insight Server’s] Status.

**So legen Sie fest, warum Insight keine Verbindung herstellen kann**

1. Klicken Sie mit der rechten Maustaste auf den roten Serverknoten und klicken Sie auf **[!UICONTROL Detailed Status]**.
1. Im [!DNL Detailed Status] Benutzeroberfläche, klicken Sie auf **[!UICONTROL Network Connections]** und erweitern Sie die nummerierten Elemente. Die [!DNL Status] liefert Informationen darüber, warum Insight keine Verbindung herstellen kann:

   * Ein Statuscode in den 500er Jahren zeigt einen Konfigurationsfehler an.
   * Der Statuscode 403 zeigt normalerweise an, dass Sie nicht über die Berechtigung zum Anzeigen des Serverstatus verfügen.

Sie können zusätzliche Statusinformationen im [!DNL insight.log] -Datei. Diese Protokolldatei befindet sich im [!DNL Trace] in dem Ordner, in dem Sie Insight installiert haben. Um die Datei anzuzeigen, öffnen Sie sie in einem Texteditor wie Notepad.

Wenn Sie Hilfe benötigen, sollten Sie die Informationen im Abschnitt [!DNL insight.log] -Datei, wenden Sie sich zunächst an Ihren Systemadministrator. Wenn Sie weitere Hilfe benötigen, wenden Sie sich an die Kundenunterstützung von Adobe.
