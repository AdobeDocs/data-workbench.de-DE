---
description: Im Folgenden finden Sie Anforderungen und Empfehlungen für die Installation der Workstation (Client) in Data Workbench.
title: Workstation-Anforderungen
uuid: 3c4ba2e8-efbc-45fe-8ac1-923d070bc710
exl-id: 35e259e3-3d6d-45c8-a923-2f8de117489d
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 2%

---

# Workstation-Anforderungen{#workstation-requirements}

{{eol}}

Im Folgenden finden Sie Anforderungen und Empfehlungen für die Installation der Workstation (Client) in Data Workbench.

Siehe [Systemanforderungen des Servers](https://experienceleague.adobe.com/docs/data-workbench/using/server-admin-install/c-msr-server.html?lang=en) für zusätzliche Systemanforderungen der Data Workbench.

>[!IMPORTANT]
>
>Die Server-, Report Server- und Client-Komponenten werden aktualisiert, um unter 64-Bit-Windows-Betriebssystemen ausgeführt zu werden.

**Vorabinformationen**

Stellen Sie sicher, dass Sie diese Aufgaben abgeschlossen haben, bevor Sie die Data Workbench Workstation (Client) installieren:

* **Hinzufügen** ***Ausgeschlossene Prozesse*** für *MS System Center Endpoint Protection in Windows 2012-Servern* für die folgenden ausführbaren Dateien:

   * **[!DNL InsightServer64.exe]**
   * **[!DNL ReportServer.exe]**
   * **[!DNL ExportIntegration.exe]**

   Dadurch werden die Berechtigungen der Zulassungsliste für diese miteinander verbundenen ausführbaren Dateien aktiviert.

* **Installieren Sie Microsoft Excel, um Analysedaten zu exportieren.** So exportieren Sie Daten aus Arbeitsbereichen als Microsoft Excel ( [!DNL .xls] oder [!DNL .xlsx]), muss Excel auf dem Computer installiert und registriert sein, auf dem Sie Data Workbench installieren. Wenn Excel nicht registriert wurde und Data Workbench zum ersten Mal darauf zugreifen möchte, zeigt Excel ein Registrierungsdialogfeld an. Wenn Sie nicht sicher sind, ob die Kopie registriert ist, starten Sie Excel manuell und führen Sie den Registrierungsprozess durch, wenn ein Registrierungsdialogfeld angezeigt wird.

   >[!NOTE]
   >
   >Mit der Veröffentlichung von Data Workbench 6.4 wurde die Unterstützung für Excel 2007 eingestellt. Da die Data Workbench nur unter Microsoft Windows für die 64-Bit-Architektur ausgeführt wird, wird empfohlen, auch eine 64-Bit-Version von Microsoft Excel zu installieren.

* **Installieren der Adobe [!DNL Acrobat] zum Drucken skalierter Arbeitsbereiche auf PDF.** Zum Drucken skalierter Arbeitsbereiche im Adobe PDF-Format muss der Computer, auf dem die Data Workbench installiert ist, über Adobe verfügen [!DNL Acrobat] installiert.

* **Zugriff auf einen Drucker zum Drucken von Arbeitsbereichen.** Um Arbeitsbereiche von Data Workbench aus zu drucken, muss der Computer, auf dem Sie Data Workbench installieren, Zugriff auf einen Drucker haben. Data Workbench kann Arbeitsbereiche für Farb- oder Schwarzweißdrucker drucken und erfordert keine PostScript- oder anderen erweiterten Druckerfunktionen. Um optimale Ergebnisse zu erzielen, empfiehlt Adobe, Arbeitsbereiche farbig zu drucken.
* **Durchführung von Sicherheitsmaßnahmen.** Sie sollten die normalen Unternehmenssicherheitsrichtlinien Ihres Unternehmens für Data Workbench-Computer befolgen. Um die Hauptaufgaben zu erfüllen, erfordert die Data Workbench nur die Möglichkeit, eine Verbindung zu einem Server (über die Ports 80 und 443) und zu allen Servern herzustellen, die Daten erfassen. Sie können die Data Workbench-Hardware für jeden anderen Zweck verwenden, solange Sie die Data Workbench-Software verwalten und mindestens 10 GB Speicherplatz für die Data Workbench bereitstellen.
* Um die Visualisierungen korrekt wiederzugeben, muss der Computer, auf dem Sie die Workbench installieren, über eine geeignete **Grafikkarte** installiert (siehe Anforderungen an den Grafikadapter unten).

**Data Workbench-Kundenanforderungen**

**Betriebssystem**

* Microsoft Windows 7 (64 Bit)
* Microsoft Windows 8.1 64 Bit
* Microsoft Windows 10 64 Bit

>[!NOTE]
>
>Windows XP wird für Data Workbench 6.1 und neuere Versionen nicht unterstützt.

**Auflösung**

* Erforderlich: 1024 x 768 (XGA)
* Empfohlen: 1920 x 1200 (WUXGA)

**Grafikadapter**

* Erforderlich: OpenGL-Hardwarebeschleunigung zur Unterstützung von OpenGL 3.2
* Empfohlen: Dedizierter Grafikadapter (z. B. NVIDIA- oder ATI-Adapter)

**Prozessor**

* Erforderlich: Intel oder AMD mit 1,2 GHz oder höher
* Empfohlen: ICore 2 Duo-Klasse

**RAM**

* Erforderlich: 2 GB
* Empfohlen: 4 GB

**Konnektivität**

* Erforderlich: 512 Kbit/s-Link zur DPU
* Empfohlen: Link zur DPU mit mindestens 2 MBit/s

**Dateisystem**

NTFS

**Festplattenspeicher**

Mindestens zehn (10) GB freien Festplattenspeicherplatzes

**Drucken**

Druckerzugriff (Druckfarben oder Graustufendrucker) für Druckarbeitsbereiche und Berichte

**Sonstige**

* Dedizierte Maus
* Niedrige Arbeitsumgebung
* Matte-Surface Monitor
