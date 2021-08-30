---
description: Damit einige Funktionen von Report Server funktionieren, müssen Sie vor der Installation Hardware oder Software bereitstellen und konfigurieren.
title: Vorabinformationen
uuid: cb464fb6-3109-4eff-9c95-f0cf1f8a8c66
exl-id: 5c8bb4c3-fe76-4b4e-960d-113a9927ad59
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '326'
ht-degree: 1%

---

# Vorabinformationen{#before-you-begin}

Damit einige Funktionen von Report Server funktionieren, müssen Sie vor der Installation Hardware oder Software bereitstellen und konfigurieren.

## Grundlegende Anforderungen an Report Server {#section-e891eaee79fe4fa98e658426dc3b2777}

Die Berichte, die ausgegeben werden, können entweder in Form von PNG-Bildern oder .XLS-Tabellen in einem Dateisystem oder in Form von E-Mails erstellt werden. Die Hardwareanforderungen sind mit dem [Data Workbench-Client](https://experienceleague.adobe.com/docs/data-workbench/using/install/c-data-workbench-client-install.html#Data_Workbench_Client_Minimum_System_Requirements) identisch.

Die folgenden Anforderungen sind für Report Server vorhanden:

* Zugriff auf das Dateisystem für die Ausgabe von Daten (Netzwerkfreigabe oder lokales Laufwerk).
* Zugriff auf den konfigurierten SMTP-Server.
* Microsoft Excel 2010 (64 Bit oder höher), installiert auf [!DNL Report] Server. Weitere Informationen finden Sie unter [Überlegungen zur serverseitigen Automatisierung von Office](http://support.microsoft.com/kb/257757) .

## Zusätzliche Anforderungen {#section-f53d4388656a4dfc90aefe29dfabef89}

* **Installieren Sie einen geeigneten Grafikadapter.** Um Berichte ordnungsgemäß zu rendern, muss auf dem Computer, auf dem Sie den  [!DNL Report] Server installieren, eine entsprechende Grafikkarte installiert sein.

* **Installieren Sie Microsoft Excel, um Berichte als Excel-Dateien zu erstellen.** Um Berichte als Microsoft Excel-Dateien (  [!DNL .xls] oder  [!DNL .xlsx]) zu generieren und zu verteilen, muss auf dem Computer, auf dem Sie Report Server installieren, die entsprechende Version von Microsoft Excel 64 Bit installiert und registriert sein. Wenn Excel nicht registriert wurde und Report Server zum ersten Mal versucht, darauf zuzugreifen, wird in Excel ein Registrierungsdialogfeld angezeigt. Wenn Sie nicht sicher sind, ob die Kopie registriert ist, starten Sie Excel manuell und führen Sie den Registrierungsprozess durch, wenn ein Registrierungsdialogfeld angezeigt wird.

   >[!NOTE]
   >
   >Wenn Sie Berichte als Excel-Dateien generieren, öffnen Sie eine neue Instanz von Excel. Weitere Informationen zu diesem Prozess finden Sie unter [http://support.microsoft.com/kb/257757](http://support.microsoft.com/kb/257757).

* **Gewähren Sie Zugriff auf einen SMTP-Server, um Berichte per E-Mail zu verteilen.** Wenn Sie Berichte in E-Mails verteilen möchten, muss Report Server eine Verbindung zu einem SMTP-Server herstellen können und die entsprechenden Anschlüsse an den E-Mail-Weiterleitungsdienst müssen geöffnet werden.
