---
description: Identifizieren Sie Mindestanforderungen und Empfehlungen für Data Workbench (ehemals [!DNL Insight])-Serverkomponenten, bevor Sie Ihr System planen und implementieren.
title: Serversystemanforderungen
uuid: c4487c76-03b9-4755-893b-555d451b1e69
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Serversystemanforderungen{#server-system-requirements}

Identifizieren Sie Mindestanforderungen und Empfehlungen für Data Workbench-Serverkomponenten, bevor Sie Ihr System planen und implementieren.

## DPU-Anforderungen{#dpu-requirements}

Die Datenverarbeitungseinheit (Server Data Processing Unit, DPU) ist die Hauptkomponente für die Datenverarbeitung in Data Workbench. Es überwacht Netzwerkverbindungen von Data Workbench, liest Rohquellendaten vom File Server Unit (FSU) und verwendet umfangreiche Computer- und Speicherressourcen.

### Lizenzierte Kapazität {#section-71850e13783443798b3df9eb22cc63dc}

Informationen zur Lizenzkapazität finden Sie in der Dienstbeschreibung im *Adobe[!DNL Data Workbench (Insight)]-Servicevertrag* .

>[!NOTE]
>
>Für den *MS System Center-Endpunktschutz* auf Windows 2012-Servern müssen diese ausführbaren Dateien den ***ausgeschlossenen Prozessen hinzugefügt werden:*** >
>* [!DNL InsightServer64.exe]
>* [!DNL ReportServer.exe]
>* [!DNL ExportIntegration.exe]
>



### Empfehlungen und Anforderungen für das DPU-System {#section-ae30555959bf4a309c76d0fd597b5162}

Adobe bietet Empfehlungen zu einem Data Workbench-Design, das Ihren Geschäftsanforderungen entspricht. Die folgenden Richtlinien sind jedoch nützlich bei der Auswahl des Betriebssystems (Betriebssystem) und der Hardware, da die optimierte Art der DPU-Software spezifische Anforderungen an die Betriebssystem-/Hardwareplattform stellt.

Wenn ein einzelner Datensatz durch die Kapazität oder Geschwindigkeit einer einzelnen DPU begrenzt ist, können Sie ihn gruppieren. Angenommen, Sie haben drei lizenzierte Kopien der DPU-Software, die zusammen verwendet werden, um einen größeren Datensatz schneller auszuführen. Da die Daten gleichmäßig zwischen den Computern aufgeteilt werden, wird die lizenzierte Kapazität des Datensatzes mit drei multipliziert. Darüber hinaus wird die Verarbeitungsgeschwindigkeit pro Zeile dreimal schneller als eine einzelne DPU.

Um die bestmögliche Leistung aus Ihrer DPU-Investition zu erzielen, empfiehlt Adobe die folgenden Hochleistungskomponenten, die in der folgenden Tabelle beschrieben werden:

<table id="table_DA0A60CFBA7D4EF98B5ED5A3D8D6777B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col2" class="entry"> erforderlich </th> 
   <th colname="col3" class="entry"> Empfohlen </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Betriebssystem  </p> </td> 
   <td colname="col2"> <p>Microsoft Windows Server 2008 x64 </p> </td> 
   <td colname="col3"> <p>Microsoft Windows Server 2012 x64 </p> <p> Microsoft Windows Server 2016 x 64 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CPU </p> </td> 
   <td colname="col2"> <p>Siehe Empfehlungen. </p> </td> 
   <td colname="col3"> Die neueste Generation von 4-Kern+-Prozessoren von Intel oder AMD wird empfohlen. Für eine optimale Leistung: 8-Kerne; für einen Kompromiss zwischen Geschwindigkeit und Kosten werden 4-Kern-Werte empfohlen. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>RAM </p> </td> 
   <td colname="col2"> <p>8 GB </p> </td> 
   <td colname="col3"> <p>12 GB </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Arbeitsdatenspeicher </p> </td> 
   <td colname="col2"> <p>1 TB+ logischer Temp-Speicher. </p> <p>Zugriff auf das Festplattenteilsystem mit niedriger Latenz </p> </td> 
   <td colname="col3"> <p>Für temporären Speicher empfiehlt Adobe Folgendes: </p> 
    <ul id="ul_F3D033B90CF94F44A2A773B3F6852283"> 
     <li id="li_B902CF7CC6A44F02838B285ADC725A75">(4 bis 8) * (750 GB oder höher) SATA-Festplatten (3,5"-Achse) </li> 
     <li id="li_A378F4E1443F4BB2B54DC7E8372EE572">(6 bis 10) * (300 GB oder höher) SATA-Festplatten (2,5"-Achse) </li> 
    </ul> <p>Diese sollten in einem JBOD-Array konfiguriert werden. Wenn die Bruttorückkapazität 2 TB übersteigt, kann auch ein Array mit 2-Festplatten-RAID1-Volumes verwendet werden. Konfigurieren Sie beispielsweise sechs Festplatten als 3*(2*750 GB RAID 1-Paar.) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Systemdatenspeicher </p> </td> 
   <td colname="col2"> <p>Darüber hinaus benötigt Adobe hochverfügbare Speichermodule in bescheidener Größe (20 GB) für das Betriebssystem, die DPU-Software und andere Systemsoftware. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Clustering von Hardware </p> </td> 
   <td colname="col2"> <p>Siehe Empfehlungen. </p> </td> 
   <td colname="col3"> <p>Verwenden Sie einen homogenen Serversatz. In einem DPU-Cluster verringert der langsamste Server die Leistung des gesamten Datensatzes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Clustering der Netzwerkleistung </td> 
   <td colname="col2"> Ein Switch-Gigabit-Ethernet-Anschluss oder höher. </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

### Alternative Disk-Subsysteme {#section-6f984eabe8074759aa9deaf17e3a68b7}

Berücksichtigen Sie bei der Prüfung alternativer Disk-Subsysteme für temporäre Speicher die folgenden Faktoren und Richtlinien:

* Die DPU ist ungewöhnlich anspruchsvoll von einem leistungsstarken Festplattensystem, sodass die Einrichtung eines unzureichenden Festplatten-Subsystems Leistungsengpässe verursachen kann.
* Die DPU-Software erstellt eine eigene, leistungsorientierte Datenabfolge über eine Reihe von JBOD-Festplatten. Verwenden Sie RAID nicht, um die Geschwindigkeit zu erhöhen.
* Adobe empfiehlt, dass die DPU über eine zusammengefasste, dauerhafte Bandbreite von 400+ MB/s auf den Festplatten verfügt.
* Durchschnittliche Lesegrößen sind sehr hoch (2 MB+). Aus diesem Grund arbeiten 15K- oder 10K-SAS-Festplatten oft etwas besser (oder schlechter) als SATA-Festplatten mit einem erheblichen Preis- und Kapazitätsausfall.
* Vermeiden Sie die Verwendung einer SAN-Architektur. Die Erfahrung zeigt, dass die Kosten, die mit einem SAN verbunden sind, um auf den erforderlichen Ebenen zu arbeiten, in der Regel extrem hoch sind.
* Das lokale Festplatten-Subsystem wird als Arbeitsspeicherplatz verwendet. Bei einem Festplattenausfall gehen keine Daten dauerhaft verloren. Vermeiden Sie daher kostenintensive, langsamere und hochverfügbare Systeme.

### Geschwindigkeitsüberlegungen {#section-01330be232894e08a526d8d82b7c4eb2}

Adobe kann keine Garantie oder Darstellung hinsichtlich der Geschwindigkeit bieten, mit der Daten von einer konfigurierten Data Workbench verarbeitet werden, da eine Reihe von Faktoren die Verarbeitungsgeschwindigkeit der Daten beeinflussen, unter anderem folgende:

* Anzahl der Datenzeilen
* Anzahl der Dimensionen (Spalten) der Daten
* Anzahl und Komplexität der benutzerdefinierten Verarbeitungsschritte
* Einsatz von Clustering
* Geschwindigkeit der Hardware

## Anforderungen an die Dateiservereinheit{#file-server-unit-requirements}

Die File Serving Unit (FSU) des Servers ist die Hauptkomponente für Datenspeicherung und -verwaltung in Data Workbench. Das FSU fungiert als Dateiserver für Rohquellendaten an die DPU und koordiniert gegebenenfalls das Clustering von DPUs. Jedes FSU ist lizenziert, Quelldaten bis zu fünf (5) DPUs bereitzustellen.

<table id="table_45CF36583DFE4536BB31F6A1F6CC181E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> FSU-Komponenten </th> 
   <th colname="col2" class="entry"> Empfehlungen </th> 
   <th colname="col3" class="entry"> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Betriebssystem, CPU, RAM </p> </td> 
   <td colname="col2"> <p>Diese Anforderungen entsprechen denen der DPU. Für das FSU empfiehlt Adobe jedoch die Verwendung der Mindestanforderungen, anstatt den Empfehlungen zu folgen. </p> </td> 
   <td colname="col3"> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Festplattensystem </p> <p>Das FSU benötigt hochverfügbare, redundante Speicherung für große Datenmengen. Adobe wird mit Ihnen zusammenarbeiten, um Ihre genauen Anforderungen zu ermitteln. </p> </td> 
   <td colname="col1"> <p>Adobe empfiehlt: </p> 
    <ul id="ul_FFEEE5052FFD4876BA9A6476DD096539"> 
     <li id="li_F98750D509D640C68885D53FC691ED43">(12 oder mehr) * (750 GB oder höher) SATA-Festplatten in einer RAID 5/6-Konfiguration. </li> 
     <li id="li_3F84F63F9541476987015C27FDE8251B">Hochleistungsfähige SAN-Verbindung mit 100 MB/s+ dauerhafter Bandbreite. </li> 
    </ul> <p>Da das FSU die Rohquellendaten speichert, wären Verluste nicht rückgängig zu machen, und Adobe empfiehlt, diese Daten regelmäßig zu sichern. </p> </td> 
   <td colname="col2"> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Netzwerkleistung </p> </td> 
   <td colname="col2"> <p>Adobe erfordert die Zusammenarbeit von Switching-Gigabit-Ethernet-Verbindungen zwischen FSUs und DPUs. </p> </td> 
   <td colname="col3"> </td>
  </tr> 
 </tbody> 
</table>

## Sensoranforderungen{#sensor-requirements}

Data Workbench Sensor erfasst Ereignisdaten von Web-, Anwendungs- und Datenerfassungsservern, die an einen beliebigen Server übertragen werden. [!DNL Sensor’s] Die Instrumentierung stellt eine konsistente und genaue Messung von Ereignissen sicher, die in Ihrem Internetkanal auftreten. [!DNL Sensor] unterstützt viele Kombinationen aus Webserver-Software und Betriebssystem.

### Sensor-Systemempfehlungen {#section-0a981c3a47b644c1a1a56974ba033b9c}

In der folgenden Tabelle werden Systemempfehlungen für [!DNL Sensor]folgende Anwendungen beschrieben:

<table id="table_A132E06D6B8146C1B199B82464EA0898"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Funktionen  </th> 
   <th colname="col2" class="entry"> Empfohlen </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Festplattenspeicher </p> </td> 
   <td colname="col2"> <p>Mindestens 512 MB </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>RAM </p> </td> 
   <td colname="col2"> <p>32 MB RAM müssen für <span class="wintitle"> Sensor </span> auf dem HTTP-Server oder einem anderen Server, der seinen Host hat, verfügbar sein. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Netzwerkleistung </p> </td> 
   <td colname="col2"> <p>1 Mbit/s oder mehr Netzwerkverbindung zu einem Repeater-Server oder <span class="keyword"> Data Workbench-Server </span>. <span class="wintitle"> Sensor verbraucht </span> in der Regel deutlich weniger Bandbreite als ein (1) Mbit/s. Ihre Adobe-Berater unterstützen Sie bei der routinemäßigen Schätzung der tatsächlich benötigten Bandbreite. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Netzwerkports und Firewalls </p> </td> 
   <td colname="col2"> <p> <span class="wintitle"> Sensor </span> verbindet sich mit dem <span class="keyword"> Data Workbench-Server </span> mit HTTPS (normalerweise Port 443, obwohl dies konfigurierbar ist) oder HTTP (normalerweise Port 80, obwohl dies konfigurierbar ist). </p> <p>Der entsprechende Anschluss an einer Firewall, die sich zwischen einem <span class="wintitle"> Sensor </span> und dem Ziel- <span class="keyword"> Data-Workbench-Server </span> oder -Repeater-Server befindet, sollte nur zwischen dem jeweiligen <span class="wintitle"> Sensor- </span> Hostcomputer und dem <span class="keyword"> Data Workbench-Server </span> oder -Repeater-Server geöffnet werden, bevor der <span class="wintitle"> Sensor- </span> Installationsprozess beginnt. <span class="wintitle"> Sensor </span> stellt eine unidirektionale HTTPS- oder HTTP-Verbindung zu einem <span class="keyword"> Data Workbench-Server </span> oder Repeater-Server her. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Netzwerkverwaltungssysteme </p> </td> 
   <td colname="col2"> <p>Bestehende Netzwerkmanagementsysteme sollten den Zustand der zugrunde liegenden Computerhardware (z. B. Festplattenspeicher, Netzwerkdienst) und der Netzwerkverbindung sowie das Windows-Ereignisprotokoll oder das UNIX-System überwachen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Serverzeitsynchronisierung </p> </td> 
   <td colname="col2"> <p>Stellen Sie sicher, dass die Zeit des Computersystems auf allen Computern, die als Host für einen <span class="wintitle"> Sensor dienen, kontinuierlich synchronisiert wird </span>. Die von <span class="wintitle"> Sensor überwachten Webserver-Anwendungen und Computer </span> müssen über synchronisierte Systemzeiten verfügen, damit die von ihnen erfassten Ereignisdaten korrekt sind. Anweisungen zum kontinuierlichen Synchronisieren der Systemzeiten mit NTP oder einer anderen Zeitsynchronisierungsanlage finden Sie in der Dokumentation Ihres Betriebssystems. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>DNS-Namensverwendung </p> </td> 
   <td colname="col2"> <p>Adobe empfiehlt, dass <span class="wintitle"> Sensoren </span> einen DNS-Namen (anstelle einer IP-Adresse) verwenden, um die Netzwerkadresse eines <span class="keyword"> Data Workbench-Servers </span> oder -Repeater-Servers aufzulösen. Wenn ein <span class="wintitle"> Sensor einen DNS-Namen </span> verwendet, muss die DNS- oder lokale Hostdatei des Hostwebservers so konfiguriert werden, dass der Name des <span class="keyword"> Data Workbench-Servers </span> oder -Repeater-Servers aufgelöst wird. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Support-Server-Software {#section-d6071706539f49d9a861d87b98e6f382}

In der folgenden Tabelle sind die am häufigsten [!DNL Sensor] unterstützten Kombinationen aufgeführt:

<table id="table_99EA23BBC1A148B49643F4B5E4341C08"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Webserver-Software </th> 
   <th colname="col2" class="entry"> Betriebssystem  </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Apache Server/IBM HTTP Server 2.2 </p> </td> 
   <td colname="col2"> <p>Microsoft Windows Server 2003 oder höher; RedHat Enterprise Linux 6.x oder höher; Sun Solaris 8.x oder höher; IBM AIX 5.1x oder höher. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Apache Server 2.4 </p> </td> 
   <td colname="col2"> <p>RedHat Enterprise Linux 6.x oder höher </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Microsoft IIS </p> </td> 
   <td colname="col2"> <p>Microsoft Windows Server 2003 oder höher </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Java-Anwendungsserver (Tomcat, JBoss, iPlanet, Weblogic) </p> </td> 
   <td colname="col2"> <p>Microsoft Windows Server 2003 oder höher; RedHat Enterprise Linux 6.x oder höher; Sun Solaris 8.x oder höher; IBM AIX 5.1x oder höher. </p> </td> 
  </tr> 
 </tbody> 
</table>

Für andere Server- und Betriebssystemkombinationen informieren Sie sich bitte über die Verfügbarkeit von Adobe. Nicht alle Funktionen von [!DNL Sensor] sind mit allen Kombinationen von Web/Anwendungsserver und Betriebssystem verfügbar. Weitere Informationen zu bestimmten [!DNL Sensor] Versionen erhalten Sie beim Adobe Support.

## Berichtsserveranforderungen{#report-server-requirements}

Data Workbench-Berichtsserver ist die Komponente, die die Ausgabe von terminierten Berichten ermöglicht. Die ausgegebenen Berichte können entweder in Form von PNG-Bildern oder XLS-Tabellen in einem Dateisystem oder als E-Mails erstellt werden. Die Hardware-Anforderungen sind mit denen des [Data Workbench Client](https://docs.adobe.com/content/help/en/data-workbench/using/install/c-data-workbench-client-install.html)identisch.

Für [!DNL report server]die folgenden Anforderungen gelten:

* Zugriff auf Dateisystem für die Ausgabe von Daten (Netzwerkfreigabe oder lokales Laufwerk).
* Zugriff auf den konfigurierten SMTP-Server.
* Microsoft Excel 2003 oder höher auf dem [!DNL report] Server installiert. Weitere Informationen finden Sie unter [Überlegungen zur serverseitigen Automatisierung von Office](http://support.microsoft.com/kb/257757) .

## Netzwerkverwaltung{#network-management}

Adobe empfiehlt, dass vorhandene Netzwerkmanagementsysteme die Hardware und das Netzwerk überwachen, auf die sich die Data Workbench-Plattform stützt.

Darüber hinaus empfiehlt Adobe, die Windows-Ereignisprotokolle der FSUs und DPUs zu überwachen, in die geschrieben wird, wenn ein Fehler auftritt.

>[!NOTE]
>
>Jedes Netzwerk-Speichersystem, das Protokolldateien hostet, muss mindestens 10 MB pro DPU an dauerhafter Bandbreite bereitstellen.

## Datenverfügbarkeit{#data-availability}

Es ist eine übliche und erforderliche Vorgehensweise, dass eine Server-DPU Daten in einem neuen oder aktualisierten Datensatz verarbeitet und weiterverarbeitet.

Dies kann durch Konfigurationsänderungen, Änderungen der Datenquelle, Hardwareänderungen, unangemessene Konfiguration, Hardwarefehler, Softwarefehler, Stromausfall usw. geschehen. Bei einer solchen Verarbeitung oder Wiederaufbereitung müssen alle Daten und Systemdaten sofort für die DPU- und FSU-Komponenten verfügbar sein. Die Nichteinhaltung dieser Anforderung kann zu einer erheblichen und unnötigen Systemausfallzeit führen.

## Probleme mit DPU- und FSU-Netzwerken{#dpu-and-fsu-network-issues}

Überlegungen, die beim Arbeiten mit DPU- und FSU-Netzwerken zu beachten sind.

* Für die Verteilung von Protokolldateien über ein Netzwerk müssen alle Netzwerkspeichersysteme, die Protokolldateien hosten, mindestens 10 MB pro DPU an dauerhafter Bandbreite bereitstellen.
* DPU, FSU und Data Workbench kommunizieren bidirektionell über HTTP oder HTTPS an Port 80 oder 443 (standardmäßig; Anschlüsse können alternativ konfiguriert werden).
* Data Workbench [!DNL Sensor(s)] muss in der Lage sein, eine Verbindung (eine Verbindung) zu den Servern herzustellen.
* Damit die DPU Warnmeldungen über SMTP senden kann, muss sie den konfigurierten SMTP-Server kontaktieren können.
* Adobe empfiehlt, FSUs und DPUs Netzwerknamen wie FSU01.CLIENT.COM zuzuweisen, um eine Neukonfiguration zu vermeiden, wenn sich die IP-Adresse ändert.