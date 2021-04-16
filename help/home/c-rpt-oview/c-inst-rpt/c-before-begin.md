---
description: Damit einige Funktionen von Report Server funktionieren, müssen Sie vor der Installation Hardware oder Software bereitstellen und konfigurieren.
title: Vorabinformationen
uuid: cb464fb6-3109-4eff-9c95-f0cf1f8a8c66
exl-id: 5c8bb4c3-fe76-4b4e-960d-113a9927ad59
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '328'
ht-degree: 1%

---

# Vorabinformationen{#before-you-begin}

Damit einige Funktionen von Report Server funktionieren, müssen Sie vor der Installation Hardware oder Software bereitstellen und konfigurieren.

## Grundlegende Berichtsserver-Anforderungen {#section-e891eaee79fe4fa98e658426dc3b2777}

Die ausgegebenen Berichte können entweder in Form von PNG-Bildern oder XLS-Tabellen in einem Dateisystem oder als E-Mails erstellt werden. Die Hardwareanforderungen sind mit dem [Data Workbench-Client](https://docs.adobe.com/content/help/en/data-workbench/using/install/c-data-workbench-client-install.html#Data_Workbench_Client_Minimum_System_Requirements) identisch.

Die folgenden Anforderungen gelten für Report Server:

* Zugriff auf Dateisystem für die Ausgabe von Daten (Netzwerkfreigabe oder lokales Laufwerk).
* Zugriff auf den konfigurierten SMTP-Server.
* Microsoft Excel 2010 64-Bit oder höher auf dem [!DNL Report]-Server installiert. Weitere Informationen finden Sie unter [Überlegungen zur serverseitigen Automatisierung von Office](http://support.microsoft.com/kb/257757).

## Zusätzliche Anforderungen {#section-f53d4388656a4dfc90aefe29dfabef89}

* **Installieren Sie einen geeigneten Grafikadapter.** Um Berichte korrekt wiedergeben zu können, muss auf dem Computer, auf dem Sie  [!DNL Report] Server installieren, eine entsprechende Grafikkarte installiert sein.

* **Installieren Sie Microsoft Excel, um Berichte als Excel-Dateien zu erstellen.** Um Berichte als Microsoft Excel-Dateien (  [!DNL .xls] oder  [!DNL .xlsx]) zu erstellen und zu verteilen, muss auf dem Computer, auf dem Sie Report Server installieren, die entsprechende 64-Bit-Version von Microsoft Excel installiert und registriert sein. Wenn Excel nicht registriert wurde und der Berichtsserver versucht, zum ersten Mal darauf zuzugreifen, zeigt Excel ein Registrierungsdialogfeld an. Wenn Sie nicht sicher sind, ob die Kopie registriert ist, Excel manuell bearbeiten und ein Dialogfeld zur Registrierung angezeigt wird, führen Sie den Registrierungsprozess durch.

   >[!NOTE]
   >
   >Wenn Sie Berichte als Excel-Dateien generieren, öffnen Sie eine neue Instanz von Excel. Weitere Informationen zu diesem Vorgang finden Sie unter [http://support.microsoft.com/kb/257757](http://support.microsoft.com/kb/257757).

* **Stellen Sie Zugriff auf einen SMTP-Server bereit, um Berichte per E-Mail zu verteilen.** Wenn Sie Berichte per E-Mail verteilen möchten, muss Report Server eine Verbindung zu einem SMTP-Server herstellen können, und die entsprechenden Anschlüsse zum E-Mail-Weiterleitungsdienst müssen geöffnet werden.
