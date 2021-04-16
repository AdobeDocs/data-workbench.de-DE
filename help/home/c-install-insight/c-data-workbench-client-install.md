---
description: Die folgenden Anforderungen und Empfehlungen gelten für die Installation der Workstation (Client) in der Data Workbench.
title: Workstation-Anforderungen
uuid: 3c4ba2e8-efbc-45fe-8ac1-923d070bc710
exl-id: 35e259e3-3d6d-45c8-a923-2f8de117489d
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '524'
ht-degree: 2%

---

# Workstation-Anforderungen{#workstation-requirements}

Die folgenden Anforderungen und Empfehlungen gelten für die Installation der Workstation (Client) in der Data Workbench.

Weitere Systemanforderungen für die Data Workbench finden Sie unter [Serversystemanforderungen](https://docs.adobe.com/help/en/data-workbench/using/server-admin-install/c-msr-server.html).

>[!IMPORTANT]
>
>Server-, Berichtsserver- und Client-Komponenten werden aktualisiert, um auf 64-Bit-Windows-Betriebssystemen ausgeführt zu werden.

**Vorabinformationen**

Vergewissern Sie sich, dass Sie die folgenden Aufgaben abgeschlossen haben, bevor Sie die Data Workbench Workstation (Client) installieren:

* **** ***AddExcluded-*** Prozesse für den  *MS System Center-Endpunktschutz in Windows 2012-* Servern für die folgenden ausführbaren Dateien:

   * **[!DNL InsightServer64.exe]**
   * **[!DNL ReportServer.exe]**
   * **[!DNL ExportIntegration.exe]**

   Dadurch werden Zulassungslisten-Rechte für diese miteinander verbundenen ausführbaren Dateien aktiviert.

* **Installieren Sie Microsoft Excel, um Analysen zu exportieren.** Um Daten aus Arbeitsbereichen als Microsoft Excel-Dateien (  [!DNL .xls] oder  [!DNL .xlsx]) zu exportieren, muss Excel auf dem Computer, auf dem Sie die Data Workbench installieren, installiert und registriert sein. Wenn Excel nicht registriert wurde und Data Workbench zum ersten Mal darauf zugreifen möchte, zeigt Excel ein Registrierungsdialogfeld an. Wenn Sie nicht sicher sind, ob die Kopie registriert ist, Excel manuell erstellen und ein Dialogfeld zur Registrierung angezeigt wird, führen Sie den Registrierungsprozess durch.

   >[!NOTE]
   >
   >Mit der Veröffentlichung von Data Workbench 6.4 wurde die Excel 2007-Unterstützung eingestellt. Da die Data Workbench nur unter Microsoft Windows für die 64-Bit-Architektur ausgeführt wird, sollten Sie auch eine 64-Bit-Version von Microsoft Excel installieren.

* **Installieren der Adobe  [!DNL Acrobat] zum Drucken von skalierten Arbeitsbereichen als PDF.** Um skalierte Arbeitsflächen im Adobe PDF-Format zu drucken, muss auf dem Computer, auf dem die Data Workbench installiert ist, Adobe  [!DNL Acrobat] installiert sein.

* **Zugriff auf einen Drucker zum Drucken von Arbeitsbereichen.** Um Arbeitsbereiche von der Data Workbench aus zu drucken, muss der Computer, auf dem Sie die Data Workbench installieren, Zugriff auf einen Drucker haben. Data Workbench kann Arbeitsbereiche auf Farb- oder Schwarzweißdruckern drucken und erfordert keine PostScript- oder andere erweiterte Druckerfunktionen. Um optimale Ergebnisse zu erzielen, empfiehlt Adobe, Arbeitsbereiche farbig zu drucken.
* **Durchführung von Sicherheitsmaßnahmen.** Sie sollten die für Ihre Firma geltenden Richtlinien zur Unternehmenssicherheit für Data Workbenchs befolgen. Zur Erfüllung ihrer Hauptaufgaben erfordert die Data Workbench nur die Möglichkeit, eine Verbindung zu einem Server (über die Ports 80 und 443) und zu allen Servern, die Daten erfassen, herzustellen. Sie können die Data Workbench für jeden anderen Zweck verwenden, solange Sie die Data Workbench-Software verwalten und mindestens 10 GB Datenspeicherung für die Data Workbench bereitstellen.
* Um Visualisierungen genau darzustellen, muss auf dem Computer, auf dem Sie die Workbench installieren, ein geeigneter **Grafikadapter** installiert sein (siehe Anforderungen für Grafikadapter unten).

**Data Workbench-Client-Anforderungen**

**Betriebssystem**

* Microsoft Windows 7 64-Bit
* Microsoft Windows 8.1 64 Bit
* Microsoft Windows 10 64 Bit

>[!NOTE]
>
>Windows XP wird für Data Workbench 6.1 und höher nicht unterstützt.

**Auflösung**

* Erforderlich: 1024 x 768 (XGA)
* Empfohlen: 1920 x 1200 (WUXGA)

**Grafikadapter**

* Erforderlich: OpenGL-Hardwarebeschleunigung zur Unterstützung von OpenGL 3.2
* Empfohlen: Dedizierte Grafikkarte (z. B. NVIDIA- oder ATI-Adapter)

**Prozessor**

* Erforderlich: Intel oder AMD mit 1,2 GHz oder höher
* Empfohlen: ICore 2 Duo-Klasse

**RAM**

* Erforderlich: 2 GB
* Empfohlen: 4 GB

**Konnektivität**

* Erforderlich: 512 Kbit/s-Verbindung zur DPU
* Empfohlen: Verknüpfung mit der DPU mit mindestens 2 Mbit/s

**Dateisystem**

NTFS

**Disk-Datenspeicherung**

Mindestens zehn (10) GB freier Festplattenspeicherplatz

**Drucken**

Druckerzugriff (Drucker mit Farb- oder Graustufen) für den Druck von Arbeitsbereichen und Berichten

**Sonstige**

* Dedizierte Maus
* Umgebung für Arbeitskräfte mit niedrigem Blinddruck
* Matte-Surface-Monitor
