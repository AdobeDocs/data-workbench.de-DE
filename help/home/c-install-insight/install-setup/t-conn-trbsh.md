---
description: Wenn Insight mit den angegebenen Einstellungen keine Verbindung zu den Insight-Servern herstellen kann, wird im Server Manager ein roter Knoten angezeigt.
title: Verbindungsproblem
uuid: 17190cee-da5c-449f-aca5-8e9e35e0a5fd
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Verbindungsproblem{#connection-troubleshooting}

Wenn Insight mit den angegebenen Einstellungen keine Verbindung zu den Insight-Servern herstellen kann, wird im Server Manager ein roter Knoten angezeigt.

Dies kann beispielsweise vorkommen, wenn Sie die Verbindung falsch konfigurieren oder nicht berechtigt sind, den [!DNL Insight Server’s] Status anzuzeigen.

**So bestimmen Sie, warum Insight keine Verbindung herstellen kann**

1. Klicken Sie mit der rechten Maustaste auf den roten Serverknoten und klicken Sie auf **[!UICONTROL Detailed Status]**.
1. Klicken Sie in der [!DNL Detailed Status] Benutzeroberfläche auf die nummerierten Elemente **[!UICONTROL Network Connections]** und erweitern Sie sie. Der [!DNL Status] Parameter enthält Informationen darüber, warum Insight keine Verbindung herstellen kann:

   * Ein Statuscode in den 500ern gibt einen Konfigurationsfehler an.
   * Der Statuscode 403 gibt normalerweise an, dass Sie nicht berechtigt sind, den Serverstatus anzuzeigen.

Sie können weitere Statusinformationen in der [!DNL insight.log] Datei anzeigen. Diese Protokolldatei befindet sich im [!DNL Trace] Ordner, in dem Sie Insight installiert haben. Um die Datei anzuzeigen, öffnen Sie sie in einem Texteditor wie Notepad.

Wenn Sie Hilfe beim Verständnis der Informationen in der [!DNL insight.log] Datei benötigen, wenden Sie sich zuerst an Ihren Systemadministrator. Wenn Sie weitere Unterstützung benötigen, wenden Sie sich an den Adobe-Kundendienst.
