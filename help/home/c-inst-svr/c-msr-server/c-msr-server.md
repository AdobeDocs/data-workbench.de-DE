---
description: Ermitteln Sie Mindestanforderungen und Empfehlungen für die Serverkomponenten der Data Workbench (ehemals [!DNL Insight]), bevor Sie Ihr System planen und implementieren.
title: Systemanforderungen von Servern
uuid: c4487c76-03b9-4755-893b-555d451b1e69
exl-id: 6dd78331-8370-400e-b580-9b9bad13e62c
source-git-commit: 79981e92dd1c2e552f958716626a632ead940973
workflow-type: tm+mt
source-wordcount: '1683'
ht-degree: 1%

---

# Systemanforderungen von Servern{#server-system-requirements}

Ermitteln Sie Mindestanforderungen und Empfehlungen für Data Workbench-Serverkomponenten, bevor Sie Ihr System planen und implementieren.

## DPU-Anforderungen{#dpu-requirements}

Die DPU (Server Data Processing Unit) ist die wichtigste Datenverarbeitungskomponente von Data Workbench. Es überwacht Netzwerkverbindungen von Data Workbench, liest Rohquelldaten aus der File Server Unit (FSU) und verwendet umfangreiche Computer- und Speicherressourcen.

### Lizenzierte Kapazität {#section-71850e13783443798b3df9eb22cc63dc}

Informationen zur Lizenzkapazität finden Sie unter Dienstbeschreibung in der *Adobe [!DNL Data Workbench (Insight)] Service Agreement* .

>[!NOTE]
>
>Für *MS System Center Endpoint Protection* auf Windows 2012-Servern müssen diese ausführbaren Dateien zu den ***Ausgeschlossenen Prozessen hinzugefügt werden:*** >
>* [!DNL InsightServer64.exe]
>* [!DNL ReportServer.exe]
>* [!DNL ExportIntegration.exe]

>


### Recommendations und Voraussetzungen für das DPU-System {#section-ae30555959bf4a309c76d0fd597b5162}

Adobe bietet Empfehlungen zu einem Data Workbench-Design, das Ihren Geschäftsanforderungen entspricht. Die folgenden Richtlinien sind jedoch bei der Auswahl des Betriebssystems (Betriebssystem) und der Hardware nützlich, da die optimierte Beschaffenheit der DPU-Software bestimmte Anforderungen an die Betriebssystem-/Hardwareplattform stellt.

Wenn ein einzelner Datensatz durch die Kapazität oder Geschwindigkeit einer einzelnen DPU begrenzt ist, können Sie ihn gruppieren. Angenommen, Sie verfügen über drei lizenzierte Kopien der DPU-Software, die zusammen verwendet werden, um einen größeren Datensatz schneller auszuführen. Da die Daten gleichmäßig auf die Computer aufgeteilt werden, wird die lizenzierte Kapazität des Datensatzes mit drei multipliziert. Darüber hinaus wird die Verarbeitungsgeschwindigkeit pro Zeile dreimal schneller als eine einzelne DPU.

Um die bestmögliche Leistung Ihrer DPU-Investition zu erzielen, empfiehlt Adobe die folgenden Hochleistungskomponenten, die in der folgenden Tabelle beschrieben werden:

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
   <td colname="col1"> <p>Betriebssystem </p> </td>
   <td colname="col2"> <p>Microsoft Windows Server 2008 x 64 </p> </td>
   <td colname="col3"> <p>Microsoft Windows Server 2012 x 64 </p> <p> Microsoft Windows Server 2016 x 64 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>CPU </p> </td>
   <td colname="col2"> <p>Siehe Empfehlungen. </p> </td>
   <td colname="col3"> Es wird empfohlen, 4-Core+-Prozessoren der neuesten Generation von Intel oder AMD zu verwenden. für optimale Leistung 8-Kerne; für einen Kompromiss zwischen Geschwindigkeit und Kosten werden 4 Kerne empfohlen. </td>
  </tr>
  <tr>
   <td colname="col1"> <p>RAM </p> </td>
   <td colname="col2"> <p>8 GB </p> </td>
   <td colname="col3"> <p>12 GB </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>Arbeitsdatenspeicher </p> </td>
   <td colname="col2"> <p>1 TB+ des gesamten logischen temporären Speichers. </p> <p>Geringe Latenz beim Zugriff auf das Festplattenuntersystem </p> </td>
   <td colname="col3"> <p>Für die temporäre Speicherung empfiehlt die Adobe Folgendes: </p>
    <ul id="ul_F3D033B90CF94F44A2A773B3F6852283">
     <li id="li_B902CF7CC6A44F02838B285ADC725A75">(4 bis 8) * (750 GB oder höher) SATA-Festplatten (3,5" Spindel) </li>
     <li id="li_A378F4E1443F4BB2B54DC7E8372EE572">(6 bis 10) * (300 GB oder höher) SATA-HDDs (2,5"-Spindel) </li>
    </ul> <p>Diese sollten in einem JBOD-Array konfiguriert werden. Wenn die Brutto-Festplattenkapazität 2 TB überschreitet, kann alternativ ein Array von 2-Festplatten-RAID1-Volumes verwendet werden. Konfigurieren Sie beispielsweise sechs Festplatten als 3*(2*750GB RAID 1-Paar). </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>Systemdatenspeicher </p> </td>
   <td colname="col2"> <p>Darüber hinaus erfordert die Adobe einen hochverfügbaren Speicher von bescheidener Größe (20 GB) für Betriebssystem, DPU-Software und andere Systemsoftware. </p> </td>
   <td colname="col3"> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>Clustering-Hardware </p> </td>
   <td colname="col2"> <p>Siehe Empfehlungen. </p> </td>
   <td colname="col3"> <p>Verwenden Sie einen homogenen Satz von Servern. In einem DPU-Cluster reduziert der langsamste Server die Leistung des gesamten Datensatzes. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> Clustering der Netzwerkleistung </td>
   <td colname="col2"> Switch-Gigabit-Ethernet-Verbindung oder höher. </td>
   <td colname="col3"> </td>
  </tr>
 </tbody>
</table>

### Alternative Datenträger-Subsysteme {#section-6f984eabe8074759aa9deaf17e3a68b7}

Beachten Sie bei der Erwägung alternativer Festplattenuntersysteme für temporäre Speicher die folgenden Faktoren und Richtlinien:

* Die DPU fordert ein leistungsfähiges Festplattensystem ungewöhnlich, sodass die Einrichtung eines unzureichenden Festplatten-Subsystems Leistungsengpässe verursachen kann.
* Die DPU-Software führt ihr eigenes leistungsorientiertes Daten-Striping über eine Reihe von JBOD-Festplatten aus. Verwenden Sie RAID nicht, um die Geschwindigkeit zu erhöhen.
* Adobe empfiehlt, dass die DPU über eine aggregierte, nachhaltige Bandbreite von 400 MB/s auf den Festplatten verfügt.
* Durchschnittliche Lesegrößen sind sehr hoch (2 MB+). Aus diesem Grund schneiden 15-K- oder 10-K-SAS-Festplatten häufig etwas besser (oder schlechter) als SATA-Festplatten bei erheblichen Kosten- und Kapazitätskosten.
* Vermeiden Sie die Verwendung einer SAN-Architektur. Die Erfahrung zeigt, dass die Kosten für die Durchführung eines SAN auf den erforderlichen Ebenen normalerweise extrem sind.
* Das Teilsystem &quot;Lokale Festplatte&quot;wird als Kratzspeicher verwendet. Bei einem Festplattenfehler gehen keine Daten dauerhaft verloren. Vermeiden Sie daher kostspielige, langsamere und hochverfügbare Systeme.

### Geschwindigkeitsüberlegungen {#section-01330be232894e08a526d8d82b7c4eb2}

Adobe kann keine Garantie oder Darstellung hinsichtlich der Geschwindigkeit der Datenverarbeitung durch eine konfigurierte Data Workbench bieten, da eine Vielzahl von Faktoren die Datenverarbeitungsgeschwindigkeit beeinflusst, unter anderem, aber nicht beschränkt auf Folgendes:

* Anzahl der Datenzeilen
* Anzahl der Datendimensionen (Spalten)
* Anzahl und Komplexität der benutzerdefinierten Verarbeitungsschritte
* Clustering
* Geschwindigkeit der Hardware

## Anforderungen an Dateiservereinheiten{#file-server-unit-requirements}

Die File Serving Unit (FSU) des Servers ist die wichtigste Datenspeicherungs- und Verwaltungskomponente von Data Workbench. Das FSU fungiert als Dateiserver für Rohquelldaten an die DPU und koordiniert gegebenenfalls das Clustering von DPUs. Jede FSU ist lizenziert, Quelldaten für bis zu fünf (5) DPUs bereitzustellen.

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
   <td colname="col2"> <p>Diese Anforderungen entsprechen denen der DPU. Für das FSU empfiehlt Adobe jedoch, die Mindestanforderungen zu verwenden, anstatt die Empfehlungen zu befolgen. </p> </td>
   <td colname="col3"> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>Datenträgersystem </p> <p>Das FSU benötigt hochverfügbare, redundante Datenspeicherung für große Datenmengen. Adobe wird mit Ihnen zusammenarbeiten, um Ihre Anforderungen genau zu bestimmen. </p> </td>
   <td colname="col1"> <p>Adobe empfiehlt: </p>
    <ul id="ul_FFEEE5052FFD4876BA9A6476DD096539">
     <li id="li_F98750D509D640C68885D53FC691ED43">(12 oder mehr) * (750 GB oder höher) SATA-Festplatten in einer RAID 5/6-Konfiguration. </li>
     <li id="li_3F84F63F9541476987015C27FDE8251B">Hochleistungsfähige SAN-Verbindung mit 100 MB/s+ nachhaltiger Bandbreite. </li>
    </ul> <p>Da das FSU die Rohquellendaten speichert, wäre jeder Verlust nicht rückgängig zu machen, und die Adobe legt nahe, diese Daten regelmäßig zu sichern. </p> </td>
   <td colname="col2"> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>Netzwerkleistung </p> </td>
   <td colname="col2"> <p>Für die Adobe sind Switch-Gigabit-Ethernet-Verbindungen zwischen FSUs und DPUs erforderlich, die zusammenarbeiten. </p> </td>
   <td colname="col3"> </td>
  </tr>
 </tbody>
</table>

## Sensoranforderungen{#sensor-requirements}

Data Workbench Sensor erfasst Ereignisdaten von Web-, Anwendungs- und Datenerfassungsservern, die an einen beliebigen Server übertragen werden. [!DNL Sensor’s] Die Instrumentierung stellt eine konsistente und genaue Messung von Ereignissen sicher, die in Ihrem Internetkanal auftreten. [!DNL Sensor] unterstützt viele Kombinationen von Webserver-Software und Betriebssystem.

### Sensor System Recommendations {#section-0a981c3a47b644c1a1a56974ba033b9c}

In der folgenden Tabelle werden Systemempfehlungen für [!DNL Sensor] beschrieben:

<table id="table_A132E06D6B8146C1B199B82464EA0898">
 <thead>
  <tr>
   <th colname="col1" class="entry"> Funktionen </th>
   <th colname="col2" class="entry"> Empfohlen </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> <p>Festplattenspeicher </p> </td>
   <td colname="col2"> <p>Mindestens 512 MB. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>RAM </p> </td>
   <td colname="col2"> <p>32 MB RAM müssen für <span class="wintitle"> Sensor </span> auf dem HTTP- oder anderen Servercomputer verfügbar sein, der der Host ist. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>Netzwerkleistung </p> </td>
   <td colname="col2"> <p>1 MBit/s oder eine größere Netzwerkverbindung zu einem Repeater-Server oder <span class="keyword"> Data Workbench-Server </span>. <span class="wintitle"> Der Sensor verbraucht  </span> in der Regel deutlich weniger Bandbreite als ein (1) MBit/s. Ihre Adobe-Berater helfen Ihnen dabei, die tatsächlich benötigte Bandbreite routinemäßig abzuschätzen. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>Netzwerkports und Firewalls </p> </td>
   <td colname="col2"> <p> <span class="wintitle"> Sensor  </span> stellt eine Verbindung zum  <span class="keyword"> Data Workbench-Server  </span> über HTTPS (normalerweise Port 443, obwohl dies konfigurierbar ist) oder HTTP (normalerweise Port 80, obwohl dies konfigurierbar ist) her. </p> <p>Der entsprechende Anschluss in einer beliebigen Firewall, die zwischen einem <span class="wintitle"> Sensor </span> und dem <span class="keyword"> Data Workbench-Server </span> oder Repeater-Server der Zielgruppe <span class="wintitle"> oder des Hostcomputers </span> und dem <span class="keyword"> Data Workbench-Server </span> oder Repeater-Server vor Beginn des <span class="wintitle"> Sensors </span> befindet, sollte geöffnet werden. Installationsprozess. <span class="wintitle"> Sensor  </span> führt eine unidirektionale HTTPS- oder HTTP-Verbindung zu einem  <span class="keyword"> Data Workbench-Server  </span> oder Repeater-Server durch. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>Netzwerkverwaltungssysteme </p> </td>
   <td colname="col2"> <p>Bestehende Netzwerkverwaltungssysteme sollten den Zustand der zugrunde liegenden Computerhardware (z. B. Festplattenspeicher, Netzwerkdienst) und die Netzwerkverbindung sowie das Windows-Ereignisprotokoll oder das UNIX-Syslog überwachen. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>Serverzeitsynchronisierung </p> </td>
   <td colname="col2"> <p>Stellen Sie sicher, dass die Systemzeit des Computers kontinuierlich auf allen Computern synchronisiert wird, die einen <span class="wintitle"> Sensor </span> hosten. Die Webserver-Anwendungen und Computer, die von <span class="wintitle"> Sensor </span> überwacht werden, müssen über synchronisierte Systemzeiten verfügen, damit die von ihnen erfassten Ereignisdaten präzise sind. Anweisungen zum kontinuierlichen Synchronisieren der Systemzeiten mit NTP oder einer anderen solchen Zeitsynchronisierungsfunktion finden Sie in der Dokumentation Ihres Betriebssystems . </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>Nutzung des DNS-Namens </p> </td>
   <td colname="col2"> <p>Adobe empfiehlt, dass <span class="wintitle"> Sensoren </span> einen DNS-Namen (anstelle einer IP-Adresse) verwenden, um die Netzwerkadresse eines <span class="keyword"> Data Workbench-Servers </span> oder Repeater-Servers aufzulösen. Wenn ein <span class="wintitle"> Sensor </span> einen DNS-Namen verwendet, muss die DNS- oder lokale Hostdatei des Host-Webservers so konfiguriert werden, dass der Name des <span class="keyword"> Data Workbench-Servers </span> oder Repeater-Servers aufgelöst wird. </p> </td>
  </tr>
 </tbody>
</table>

### Support-Server-Software {#section-d6071706539f49d9a861d87b98e6f382}

In der folgenden Tabelle sind die häufigsten Kombinationen aufgeführt, die [!DNL Sensor] unterstützt:

<table id="table_99EA23BBC1A148B49643F4B5E4341C08">
 <thead>
  <tr>
   <th colname="col1" class="entry"> Webserver-Software </th>
   <th colname="col2" class="entry"> Betriebssystem </th>
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

Für andere Server- und Betriebssystemkombinationen konsultieren Sie bitte die Adobe bezüglich der Verfügbarkeit. Nicht alle Funktionen von [!DNL Sensor] sind für alle Kombinationen von Web/Application Server und Betriebssystem verfügbar. Weitere Informationen zu bestimmten [!DNL Sensor]-Versionen erhalten Sie beim Support für Adoben.

## Anforderungen an Berichtsserver{#report-server-requirements}

Der Data Workbench-Berichtsserver ist die Komponente, die die Ausgabe geplanter Berichte ermöglicht. Die Berichte, die ausgegeben werden, können entweder in Form von PNG-Bildern oder .XLS-Tabellen in einem Dateisystem oder in Form von E-Mails erstellt werden. Die Hardwareanforderungen sind mit dem [Data Workbench Client](https://experienceleague.adobe.com/docs/data-workbench/using/install/c-data-workbench-client-install.html?lang=de) identisch.

Die folgenden Anforderungen sind für [!DNL report server] vorhanden:

* Zugriff auf das Dateisystem für die Ausgabe von Daten (Netzwerkfreigabe oder lokales Laufwerk).
* Zugriff auf den konfigurierten SMTP-Server.
* Microsoft Excel 2003 oder höher auf dem [!DNL report]-Server installiert. Weitere Informationen finden Sie unter [Überlegungen zur serverseitigen Automatisierung von Office](https://support.microsoft.com/kb/257757) .

## Netzwerkverwaltung{#network-management}

Adobe empfiehlt, dass bestehende Netzwerkverwaltungssysteme die Hardware und das Netzwerk überwachen, auf die sich die Data Workbench-Plattform stützt.

Darüber hinaus empfiehlt Adobe, die Windows-Ereignisprotokolle der FSUs und DPUs zu überwachen, die in geschrieben werden, wenn ein Fehler auftritt.

>[!NOTE]
>
>Jedes Netzwerkspeichersystem, auf dem Protokolldateien gehostet werden, muss mindestens 10 MB pro DPU an nachhaltiger Bandbreite bereitstellen.

## Datenverfügbarkeit{#data-availability}

Es ist eine normale und erforderliche Vorgehensweise für eine Server-DPU, Daten in neuen oder aktualisierten Datensätzen zu verarbeiten und erneut zu verarbeiten.

Dies kann durch Konfigurationsänderungen, Änderungen der Datenquelle, Änderungen der Hardware, unangemessene Konfiguration, Hardwarefehler, Softwarefehler, Stromausfall usw. geschehen. Wenn eine solche Verarbeitung oder Wiederaufbereitung erfolgt, müssen alle Datensatz- und Systemdaten sofort für die DPU- und FSU-Komponenten verfügbar sein. Wird diese Anforderung nicht erfüllt, kann dies zu erheblichen und unnötigen Systemausfallzeiten führen.

## Netzwerkprobleme mit der DPU und der FSU{#dpu-and-fsu-network-issues}

Überlegungen zum Arbeiten mit DPU- und FSU-Netzwerken sollten beachtet werden.

* Für die Verteilung von Netzwerkprotokolldateien muss jedes Netzwerkspeichersystem, auf dem Protokolldateien gehostet werden, mindestens 10 MB pro DPU an nachhaltiger Bandbreite bereitstellen.
* DPU, FSU und Data Workbench kommunizieren bidirektional über HTTP oder HTTPS an Port 80 oder 443 (standardmäßig). -Anschlüsse können alternativ konfiguriert werden).
* Die Data Workbench [!DNL Sensor(s)] muss eine Verbindung (unidirektionale Verbindung) zu den Servern herstellen können.
* Damit die DPU Warnmeldungen über SMTP senden kann, muss sie den konfigurierten SMTP-Server kontaktieren können.
* Adobe empfiehlt, FSUs und DPUs Netzwerknamen wie FSU01.CLIENT.COM zu geben, um eine Neukonfiguration zu vermeiden, falls sich die IP-Adresse ändert.
