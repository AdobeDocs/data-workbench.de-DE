---
description: Liste der Dateien, die mit Insight Server installiert wurden, und der Dateien, die nach der Registrierung vorhanden sind, und zum ersten Mal ausgeführt.
title: Verzeichnisstruktur von Insight Server
uuid: 8339b275-f118-4d5d-937e-4df9f8a56b50
exl-id: 568391d0-e0f7-4a5a-ad71-de33c52968a0
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '499'
ht-degree: 5%

---

# Verzeichnisstruktur von Insight Server{#insight-server-directory-structure}

Liste der Dateien, die mit Insight Server installiert wurden, und der Dateien, die nach der Registrierung vorhanden sind, und zum ersten Mal ausgeführt.

## Im Installationspaket enthaltene Dateien {#section-daec17dab3e34c3c9e1ef65842cb91f1}

Die folgenden Ordner sind im Installationspaket [!DNL Insight Server] enthalten:

<table id="table_CE713A3D671C453A87986E4CD4620EF3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Verzeichnis </th> 
   <th colname="col2" class="entry"> Beschreibung des Ordnerinhalts </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Zugangssteuerung </td> 
   <td colname="col2"> <span class="keyword"> Insight Server- </span> Konfigurationsdatei, die eine Liste von Zugriffsgruppen angibt. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Adressen </td> 
   <td colname="col2"> Adresse(n) für die Kommunikation mit <span class="keyword"> Insight Server </span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Prüfung </td> 
   <td colname="col2"> Tägliche Zugriffsprotokolle mit Details zu allen versuchen Verbindungen zu <span class="keyword"> Insight Server </span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> bin </td> 
   <td colname="col2"> <span class="keyword"> Ausführbare  </span> Programmdateien für Insight Server. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Zertifikate </td> 
   <td colname="col2"> Digitale SSL-Zertifikate. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Komponenten </td> 
   <td colname="col2"> <span class="keyword"> Konfigurationsdateien der Insight Server- </span> Komponenten. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Komponenten für Verarbeitungsserver </td> 
   <td colname="col2"> <span class="keyword"> Insight Server- </span> Komponentenkonfigurationsdateien für die Verarbeitung von  <span class="keyword"> Insight Server  </span> in einem  <span class="keyword"> Insight Server- </span> Cluster. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ereignisse </td> 
   <td colname="col2"> Tägliche Ereignisprotokolle mit detaillierten Ereignisstatusmeldungen, einschließlich Fehlermeldungen. Ereignisse, die von <span class="keyword"> Insight Server </span> erfasst und protokolliert werden, werden auch in der Windows Event Viewer angezeigt. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Protokolle </td> 
   <td colname="col2"> <p>Protokolldateien, erstellt von <span class="wintitle"> Sensor </span>(s). </p> <p>"Protokolle"ist das standardmäßige Protokollierungsverzeichnis, es kann jedoch ein alternatives Verzeichnis in der Datei <span class="filepath"> communication.cfg </span> angegeben worden sein. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Suchen </td> 
   <td colname="col2"> Lookup-Dateien wie Roboter- und Suchmaschinenlisten. <span class="keyword"> Insight Server  </span> muss alle Lookup-Dateien in den Speicher laden. Die Gesamtgröße aller Lookup-Dateien, auf die in Komponentenkonfigurationsdateien verwiesen wird, plus Overhead (z. B. 12 Byte pro Zeile für <span class="filepath"> FlatFileLookup </span>-Dateien) darf den verfügbaren physischen oder virtuellen Speicher nicht überschreiten, der nach dem Laden aller anderen Softwareanwendungen verfügbar ist. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Profile </td> 
   <td colname="col2"> <p>Dateien für jedes Profil (Konfigurations-, Arbeitsbereich- und Visualisierungsdateien). Profile werden durch Daten aus einem Datensatz aufgefüllt. Datensätze enthalten Ereignisdaten ("Protokolldaten"); diese Daten können durch installierte Sensoren <span class="wintitle"> (Sensoren </span>), die von Webbeacons oder Seiten-Tags übertragen werden, oder durch Eingaben aus Data Warehouse erfasst werden. <span class="keyword"> Insight- </span> Benutzer mit Zugriff auf ein bestimmtes Profil können den Satz verarbeiteter Daten für dieses Profil sowie die in diesem Profil definierten Arbeitsbereiche und Visualisierungen verwenden. </p> <p>Arbeitsbereiche sind Arbeitsbereiche für die Systemadministration oder -analyse. Ein Arbeitsbereich kann mehrere Schnittstellen enthalten, die unterschiedliche Details zur Systemleistung anzeigen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Software </td> 
   <td colname="col2"> <span class="keyword"> Aktualisierungen der Insight- </span> Software. Auch Updates der Berichtsoftware werden hier gespeichert. </td> 
  </tr> 
 </tbody> 
</table>

## Verzeichnisse und Dateien, die nach dem Start erstellt wurden {#section-ef7408e8fae64454b326ec07453d4628}

Die folgenden Verzeichnisse werden erstellt, nachdem [!DNL Insight Server] registriert und zum ersten Mal ausgeführt wurde:

<table id="table_89CC9F3E568044C8A0072BF0A6EDCCEF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Verzeichnis </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Bundesland </td> 
   <td colname="col2"> Von <span class="keyword"> Insight Server </span> generierte Verarbeitungsinformationen. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Temp </td> 
   <td colname="col2"> <p>Speicherort der temporären Dateien, die von <span class="keyword"> Insight Server </span> während der Wiederaufbereitung und des Vorgangs verwendet werden. Normalerweise gibt es eine Datei (standardmäßig <span class="filepath"> temp.db </span> genannt) pro physischem Laufwerk. </p> <p> <span class="keyword"> Insight Server  </span> muss für das Schreiben in diesen Ordner konfiguriert werden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Trace </td> 
   <td colname="col2"> Protokoll und Ereignisdaten zu <span class="keyword"> Insight Server </span>. Nützlich für die Fehlerbehebung. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Benutzer </td> 
   <td colname="col2"> Benannte ( <span class="keyword"> Insight </span>) Benutzer mit Zugriff auf die Profile auf dem Server. Ein Verzeichnis für jeden autorisierten benannten Benutzer wird im Verzeichnis Benutzer erstellt\, wenn der Benutzer zum ersten Mal über <span class="keyword"> Insight </span> auf <span class="keyword"> Insight Server </span> zugreift. Das Verzeichnis für jeden benannten Benutzer enthält Verzeichnisse, die allen Profilen entsprechen, auf die der Benutzer über den <span class="keyword"> Insight Server </span> zugegriffen hat, sowie deren lokale Adressdateien. </td> 
  </tr> 
 </tbody> 
</table>
