---
description: Liste der Dateien, die mit Insight Server installiert wurden, und der Dateien, die nach der Registrierung vorhanden sind, und die zum ersten Mal ausgeführt werden.
solution: Insight
title: Insight Server Directory Structure
uuid: 8339b275-f118-4d5d-937e-4df9f8a56b50
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Insight Server Directory Structure{#insight-server-directory-structure}

Liste der Dateien, die mit Insight Server installiert wurden, und der Dateien, die nach der Registrierung vorhanden sind, und die zum ersten Mal ausgeführt werden.

## Im Installationspaket enthaltene Dateien {#section-daec17dab3e34c3c9e1ef65842cb91f1}

Die folgenden Ordner sind im [!DNL Insight Server] Installationspaket enthalten:

<table id="table_CE713A3D671C453A87986E4CD4620EF3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Verzeichnis </th> 
   <th colname="col2" class="entry"> Beschreibung des Ordnerinhalts </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Zugriffssteuerung </td> 
   <td colname="col2"> <span class="keyword"> Insight Server- </span> Konfigurationsdatei, die eine Liste der Zugriffsgruppen angibt. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Adressen </td> 
   <td colname="col2"> Adresse(n) für die Kommunikation mit <span class="keyword"> Insight Server </span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Prüfung </td> 
   <td colname="col2"> Protokolle mit täglichem Zugriff mit Details zu allen versuchten Verbindungen zu <span class="keyword"> Insight Server </span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> bin </td> 
   <td colname="col2"> <span class="keyword"> Programmdateien </span> mit ausführbaren Insight-Servern. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Zertifikate </td> 
   <td colname="col2"> Digitale SSL-Zertifikate. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Komponenten </td> 
   <td colname="col2"> <span class="keyword"> Konfigurationsdateien für Insight Server- </span> Komponenten. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Komponenten für Verarbeitungsserver </td> 
   <td colname="col2"> <span class="keyword"> Konfigurationsdateien für Insight Server- </span> Komponenten zur Verarbeitung von <span class="keyword"> Insight-Servern </span> in einem <span class="keyword"> Insight Server- </span> Cluster. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ereignisse </td> 
   <td colname="col2"> Tägliche Ereignisprotokolle mit detaillierten Ereignisstatusmeldungen, einschließlich Fehlermeldungen. Ereignisse, die von <span class="keyword"> Insight Server erfasst und protokolliert werden, </span> werden auch in der Windows-Ereignisanzeige angezeigt. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Protokolle </td> 
   <td colname="col2"> <p>Protokolldateien, die von <span class="wintitle"> Sensor </span>(en) erstellt wurden. </p> <p>"Protokolle"ist der Standardordner für die Protokollierung, es wurde jedoch möglicherweise ein anderer Ordner in der <span class="filepath"> Datei "communication.cfg" </span> angegeben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Suchen </td> 
   <td colname="col2"> Suchdateien, z. B. Roboter- und Suchmaschinenlisten. <span class="keyword"> Insight Server </span> muss alle Lookup-Dateien in den Speicher laden. Die Gesamtgröße aller Lookup-Dateien, auf die in den Komponentenkonfigurationsdateien verwiesen wird, plus Overhead (z. B. 12 Byte pro Zeile für <span class="filepath"> FlatFileLookup- </span> Dateien), darf den verfügbaren physischen oder virtuellen Speicher nicht überschreiten, der verfügbar ist, nachdem alle anderen Softwareanwendungen geladen wurden. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Profile </td> 
   <td colname="col2"> <p>Dateien für jedes Profil (Konfigurations-, Arbeitsbereich- und Visualisierungsdateien). Profile werden durch Daten aus einem Datensatz gefüllt. Datensätze enthalten Ereignisdaten ("Protokolldaten"); Diese Daten können von installierten <span class="wintitle"> Sensoren erfasst </span>, von Web-Beacons oder Seiten-Tags übertragen oder von Data Warehouse-Daten eingegeben werden. <span class="keyword"> Insight- </span> Benutzer mit Zugriff auf ein bestimmtes Profil können den Satz verarbeiteter Daten für dieses Profil sowie die in diesem Profil definierten Arbeitsbereiche und Visualisierungen verwenden. </p> <p>Arbeitsbereiche sind Arbeitsbereiche für die Systemverwaltung oder -analyse. Ein Arbeitsbereich kann mehrere Schnittstellen enthalten, die unterschiedliche Details zur Systemleistung anzeigen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Software </td> 
   <td colname="col2"> <span class="keyword"> Updates </span> der Insight-Software. Aktualisierungen der Berichtsoftware werden auch hier gespeichert. </td> 
  </tr> 
 </tbody> 
</table>

## Nach dem Start erstellte Verzeichnisse und Dateien {#section-ef7408e8fae64454b326ec07453d4628}

Die unten aufgeführten Ordner werden nach der Registrierung erstellt und zum ersten Mal ausgeführt: [!DNL Insight Server]

<table id="table_89CC9F3E568044C8A0072BF0A6EDCCEF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Verzeichnis </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Land </td> 
   <td colname="col2"> Von <span class="keyword"> Insight Server generierte Informationen werden verarbeitet </span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Temp </td> 
   <td colname="col2"> <p>Speicherort der temporären Dateien, die von <span class="keyword"> Insight Server </span> während der Wiederaufbereitung und des Vorgangs verwendet werden. Es gibt normalerweise eine Datei (standardmäßig <span class="filepath"> temp.db genannt) pro physischem Laufwerk </span> . </p> <p> <span class="keyword"> Insight Server </span> muss für das Schreiben in diesen Ordner konfiguriert sein. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Trace </td> 
   <td colname="col2"> Protokoll- und Ereignisdaten zu <span class="keyword"> Insight Server </span>. Nützlich für die Fehlerbehebung. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Benutzer </td> 
   <td colname="col2"> Benannte ( <span class="keyword"> Insight </span>) Benutzer mit Zugriff auf die Profile auf dem Server. Ein Ordner für jeden autorisierten benannten Benutzer wird im Ordner "Benutzer"erstellt,\ wenn der Benutzer zum ersten Mal <span class="keyword"> Insight Server </span> über <span class="keyword"> Insight aufruft </span>. Der Ordner für jeden benannten Benutzer enthält Ordner, die allen Profilen entsprechen, auf die der Benutzer auf diesem <span class="keyword"> Insight Server zugegriffen hat, </span> sowie deren lokale Adressdateien. </td> 
  </tr> 
 </tbody> 
</table>

