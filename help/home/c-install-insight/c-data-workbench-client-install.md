---
description: Die folgenden Anforderungen und Empfehlungen gelten für die Installation der Workstation (Client) in Data Workbench.
solution: Analytics
title: Anforderungen an Workstations
topic: Data workbench
uuid: 3c4ba2e8-efbc-45fe-8ac1-923d070bc710
translation-type: tm+mt
source-git-commit: 2930bd3ae06e700e75144221fc993efdd6bd1e85
workflow-type: tm+mt
source-wordcount: '524'
ht-degree: 1%

---


# Anforderungen an Workstations{#workstation-requirements}

Die folgenden Anforderungen und Empfehlungen gelten für die Installation der Workstation (Client) in Data Workbench.

Weitere Informationen zu den Systemanforderungen für Data Workbench finden Sie unter [Serversystemanforderungen](https://docs.adobe.com/help/en/data-workbench/using/server-admin-install/c-msr-server.html) .

>[!IMPORTANT]
>
>Server-, Berichtsserver- und Client-Komponenten werden aktualisiert, um auf 64-Bit-Windows-Betriebssystemen ausgeführt zu werden.

**Vorabinformationen**

Vergewissern Sie sich, dass Sie die folgenden Aufgaben abgeschlossen haben, bevor Sie die Data Workstation (Client) installieren:

* **Hinzufügen** ***Ausgeschlossene Prozesse*** für den *MS System Center-Endpunktschutz in Windows 2012-Servern* für die folgenden ausführbaren Dateien:

   * **[!DNL InsightServer64.exe]**
   * **[!DNL ReportServer.exe]**
   * **[!DNL ExportIntegration.exe]**
   Dadurch werden die zulässigen Rechte für diese miteinander verbundenen ausführbaren Dateien aktiviert.

* **Installieren Sie Microsoft Excel, um Analysen zu exportieren.** Um Daten aus Arbeitsbereichen als Microsoft Excel-Dateien ( [!DNL .xls] oder [!DNL .xlsx]) zu exportieren, muss Excel auf dem Computer, auf dem Sie Data Workbench installieren, installiert und registriert sein. Wenn Excel nicht registriert wurde und Data Workbench versucht, zum ersten Mal darauf zuzugreifen, zeigt Excel ein Registrierungsdialogfeld an. Wenn Sie nicht sicher sind, ob die Kopie registriert ist, Excel manuell erstellen und ein Dialogfeld zur Registrierung angezeigt wird, führen Sie den Registrierungsprozess durch.

   >[!NOTE]
   >
   >Mit der Veröffentlichung von Data Workbench 6.4 wurde die Unterstützung für Excel 2007 eingestellt. Da Data Workbench außerdem nur für 64-Bit-Architektur unter Microsoft Windows ausgeführt wird, wird empfohlen, auch eine 64-Bit-Version von Microsoft Excel zu installieren.

* **Installieren von Adobe[!DNL Acrobat]zum Drucken von skalierten Arbeitsbereichen als PDF.** Um skalierte Arbeitsbereiche auf das Adobe PDF-Format zu drucken, muss Adobe auf dem Computer, auf dem Data Workbench installiert ist, installiert [!DNL Acrobat] sein.

* **Zugriff auf einen Drucker zum Drucken von Arbeitsbereichen.** Zum Drucken von Arbeitsbereichen aus Data Workbench muss der Computer, auf dem Sie Data Workbench installieren, Zugriff auf einen Drucker haben. Data Workbench kann Arbeitsflächen auf Farb- oder Schwarzweißdruckern drucken und benötigt keine PostScript- oder andere erweiterte Druckerfunktionen. Um optimale Ergebnisse zu erzielen, empfiehlt Adobe, Arbeitsbereiche farbig zu drucken.
* **Durchführung von Sicherheitsmaßnahmen.** Sie sollten die für Ihre Firma geltenden Richtlinien zur Unternehmenssicherheit für Data Workbench-Computer befolgen. Zur Erfüllung ihrer Hauptaufgaben erfordert Data Workbench nur die Möglichkeit, eine Verbindung zu einem Server (über die Ports 80 und 443) und zu allen Servern, die Daten erfassen, herzustellen. Sie können die Data Workbench-Hardware für jeden anderen Zweck verwenden, solange Sie die Data Workbench-Software verwalten und mindestens 10 GB Datenspeicherung für Data Workbench zuweisen.
* Zur korrekten Darstellung der Visualisierungen muss auf dem Computer, auf dem Sie die Workbench installieren, ein entsprechender **Grafikadapter** installiert sein (siehe Anforderungen für Grafikadapter unten).

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

