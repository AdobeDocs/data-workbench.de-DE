---
description: Die folgenden Dimensionen sind im Datenbasis-Serverstatusprofil von Workbench verfügbar.
solution: Analytics
title: Dimensionen im Data Workbench-Serverstatusprofil
topic: Data workbench
uuid: 4cfe882a-2797-4af9-bd6d-75bc31ee909c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Dimensionen im Data Workbench-Serverstatusprofil{#dimensions-in-the-data-workbench-server-status-profile}

Die folgenden Dimensionen sind im Datenbasis-Serverstatusprofil von Workbench verfügbar.

<table id="table_10DFAD7A0C5946B0A2458F6C08D04FC5"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Server</b> </td> 
   <td colname="col2"> Diese zählbare Dimension wurde aus dem Feld x-trackingid erstellt und stellt die Server dar, auf denen derzeit Data Workbench ausgeführt wird. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Agentenversion</b> </td> 
   <td colname="col2"> Der Wert cs-uri-query(af) wird für diese einfache Dimension verwendet. Dies ist der Wert "Zuletzt nicht leer"für einen Server. Dies zeigt das Builddatum und die Uhrzeit für die Version(en) des/der Überwachungsagenten an. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Beliebige Profilwiederverarbeitung</b> </td> 
   <td colname="col2"> Das Feld cs-uri-query(aa) wird für diese numerische Dimension verwendet, es ist der Wert der letzten Zeile für einen bestimmten Server, bedingt durch cs-uri-query(k) ist nicht leer. Diese Dimension wird verwendet, um anzugeben, ob Profile neu verarbeitet werden. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Prozentsatz der Kapazitätenzeile</b> </td> 
   <td colname="col2"> Das Feld cs-uri-query(r) wird für diese numerische Dimension verwendet, es ist der Wert der letzten Zeile für einen bestimmten Server, bedingt durch cs-uri-query(k) ist nicht leer. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Kapazitätsgrößenprozentsatz</b> </td> 
   <td colname="col2"> Das Feld cs-uri-query(n) wird für diese numerische Dimension verwendet, es ist der Wert der letzten Zeile für einen bestimmten Server, bedingt durch cs-uri-query(k) ist nicht leer. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Allgemeiner Name</b> </td> 
   <td colname="col2"> Das Feld sc-ur-query(am) wird für diese einfache Dimension verwendet. Es ist der Wert des Werts Last Nonblank für einen bestimmten Server. Es zeigt den gemeinsamen Namen der überwachten Server an. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Komponentenprüfung erfolgreich</b> </td> 
   <td colname="col2"> Das Feld cs-uri-query(v) wird für diese einfache Dimension verwendet. Es ist der Wert der letzten Zeile für einen bestimmten Server. Diese Dimension überprüft die Komponenten des Servers, um sicherzustellen, dass sie ordnungsgemäß funktionieren. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Komponenten im Fehler</b> </td> 
   <td colname="col2"> Eine Transformation über mehrere Zeilen nimmt den Wert der letzten Zeile der cs-uri-query(ao) und kopiert ihn in das Feld x-components-in-error. Diese Dimension Viele bis Viele zeigt alle Komponenten an, die auf den überwachten Servern fehlerhaft sind. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Umgebung</b> </td> 
   <td colname="col2">Der Wert cs-uri-query(c) wird für die Umgebungs-ID verwendet. Die letzte Zeile für einen Block wird als Wert für die Dimension verwendet. Diese einfache Dimension zeigt die Umgebung an, in der Ihre Server ausgeführt werden (sofern sie ordnungsgemäß konfiguriert ist). <p><p>Hinweis:  Diese Dimension wird in insight_monitor_agent.cfg festgelegt. </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Geschätzte Sweep-Dekaseconds</b> </td> 
   <td colname="col2"> In dieser numerischen Dimension wird das Feld x-schätzung-sweep-dekaseconds verwendet. Dies ist die geschätzte Sweep-Zeit der Server geteilt durch zehn (reduzierte Auflösung der Sweep-Messung, um die Größe zu vergrößern). <p><p>Hinweis:  Diese Dimension wird ausgeblendet, da sie nur dann nützlich ist, wenn sie in einer Metrik gemittelt wird. </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Host</b> </td> 
   <td colname="col2"> Für diese Dimension wird der Wert cs-uri-query(b) verwendet. Der Wert der Dimension "Einfach"ist die letzte Zeile für einen Block. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Letztes Ping</b> </td> 
   <td colname="col2"> x-last-ping wird durch x-unixtime dividiert durch 10 (um Größenbeschränkungen für numerische Dimensionen aufzunehmen). Letztes Ping ist die letzte Zeile für einen bestimmten Block und stellt das letzte Mal dar, dass der Überwachungsagenten den Systemstatus protokolliert. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Lastendurchschnitt</b> </td> 
   <td colname="col2"> Hierbei handelt es sich um eine numerische Dimension, bei der die letzte Zeile für den cs-uri-query(i)-Wert eines bestimmten Servers verwendet wird. Es ist davon abhängig, dass cs-uri-query(k) nicht leer ist. Diese Dimension wird verwendet, um die durchschnittliche Belastung der Server im überwachten System zu berechnen. <p>Hinweis:  Diese Dimension wird ausgeblendet, da sie nur dann nützlich ist, wenn sie in einer Metrik gemittelt wird. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Dateiprozentsatz der Speicherseite</b> </td> 
   <td colname="col2"> Hierbei handelt es sich um eine numerische Dimension, bei der die letzte Zeile für den cs-uri-query(o)-Wert eines bestimmten Servers verwendet wird. Es ist davon abhängig, dass cs-uri-query(k) nicht leer ist. Diese Dimension wird verwendet, um den Prozentsatz der Speicherbelegung der Seitendatei zu berechnen. <p>Hinweis:  Diese Dimension wird ausgeblendet, da sie nur dann nützlich ist, wenn sie in einer Metrik gemittelt wird. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Physikalische MegaBytes insgesamt</b> </td> 
   <td colname="col2"> Hierbei handelt es sich um eine numerische Dimension, bei der die letzte Zeile für den cs-uri-query(ag)-Wert eines bestimmten Servers verwendet wird. Es ist davon abhängig, dass cs-uri-query(k) nicht leer ist. <p>Hinweis:  Diese Dimension wird ausgeblendet, da sie nur dann nützlich ist, wenn sie in einer Metrik gemittelt wird. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Physikalischer Speicherprozentsatz</b> </td> 
   <td colname="col2"> Hierbei handelt es sich um eine numerische Dimension, bei der die letzte Zeile für den cs-uri-query(ag)-Wert eines bestimmten Servers verwendet wird. Es ist davon abhängig, dass cs-uri-query(k) nicht leer ist. Diese Dimension wird verwendet, um den Prozentsatz der physischen Speicherbelegung jedes Servers zu berechnen. <p>Hinweis:  Diese Dimension wird ausgeblendet, da sie nur dann nützlich ist, wenn sie in einer Metrik gemittelt wird. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Speicherabfrageprozentsatz</b> </td> 
   <td colname="col2"> Hierbei handelt es sich um eine numerische Dimension, bei der die letzte Zeile für den (die) Wert (s) cs-uri-query(s) des Servers verwendet wird. Es ist davon abhängig, dass cs-uri-query(k) nicht leer ist. Diese Dimension wird verwendet, um den Prozentsatz der Speichernutzung der Abfrage auf jedem Server zu berechnen. <p>Hinweis:  Diese Dimension wird ausgeblendet, da sie nur dann nützlich ist, wenn sie in einer Metrik gemittelt wird. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Netzwerkverbindungen</b> </td> 
   <td colname="col2"> Hierbei handelt es sich um eine numerische Dimension, bei der die letzte Zeile für den cs-uri-query(q)-Wert eines bestimmten Servers verwendet wird. Es ist davon abhängig, dass cs-uri-query(k) nicht leer ist. Dies wird verwendet, um die Anzahl der Netzwerkverbindungen anzuzeigen, die für einen bestimmten Server vorhanden sind. <p>Hinweis:  Diese Dimension wird ausgeblendet, da sie nur dann nützlich ist, wenn sie in einer Metrik gemittelt wird. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Wartezeit bei Umfragen in Sekunden</b> </td> 
   <td colname="col2"> Diese Dimension wird zur Berechnung der Abfragenlatenz verwendet. Der Wert "cs-uri-query(m)"wird durch 10 dividiert, um die Dimensionsgröße zu reduzieren, und in das Feld "x-poll-latency-centiseconds"kopiert. Dies ist eine numerische Dimension, die die letzte Zeile für einen bestimmten Server akzeptiert. <p>Hinweis:  Diese Dimension wird ausgeblendet, da sie nur dann nützlich ist, wenn sie in einer Metrik gemittelt wird. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Schnelle Prüfung erfolgreich</b> </td> 
   <td colname="col2"> Dies ist eine einfache Dimension, die aus dem Wert cs-uri-query(g) der letzten Zeile für einen bestimmten Server erstellt wurde. Sie wird zur Berechnung der Schnellprüfungsmetrik verwendet. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Temp DB Space Prozentwert</b> </td> 
   <td colname="col2"> Die letzte Zeile des Werts cs-uri-query(an) wird in das Feld x-temp-db-space-percent kopiert. Dies ist eine numerische Dimension, die verwendet wird, um den Prozentsatz des verwendeten Temp DB-Speichers auf einem bestimmten Server zu berechnen. <p>Hinweis:  Diese Dimension wird ausgeblendet, da sie nur dann nützlich ist, wenn sie in einer Metrik gemittelt wird. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Insight-Version</b> </td> 
   <td colname="col2"> Für diese einfache Dimension wird der Wert cs-uri-query(ab) verwendet. Dies ist der Wert "Zuletzt nicht leer"für einen Server. Dies zeigt die Version(en) des Data Workbench-Servers an, der auf jedem Server ausgeführt wird. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Gruppe</b> </td> 
   <td colname="col2"> Gruppieren von Wörtern, die Ihnen eine andere Möglichkeit bieten, den resultierenden Datensatz zu filtern. <p>Hinweis:  Diese Dimension wird in insight_monitor_agent.cfg festgelegt. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Metriken</b> </td> 
   <td colname="col2"> Im Folgenden werden die Metriken aufgelistet, die im Profil-Monitoring-Profil von Data Workbench enthalten sind und wie sie abgeleitet werden. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Kapazität insgesamt</b> </td> 
   <td colname="col2"> Dies ist die Metrik "Kapazitätsgröße"mit dem Zweifachen plus der Metrik "Kapazitätszeile"geteilt durch "3". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Kapazitätszeile</b> </td> 
   <td colname="col2"> Dies ist die Summe des Kapazitäts-Zeilenprozentsatzes für jeden Server geteilt durch die Metrik Server. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Kapazitätsgröße</b> </td> 
   <td colname="col2"> Dies ist die Summe des Prozentsatzes der Kapazitätsgröße für jeden Server geteilt durch die Metrik Server. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Komponentenprüfung</b> </td> 
   <td colname="col2"> Dies ist die Anzahl der Server, bei denen Component Check Success gleich eins ist, geteilt durch den Server, bei dem Service DPU oder FSU ist, alle multipliziert mit 100 (um es zu einem Prozentsatz). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Disk "x"</b> </td> 
   <td colname="col2"> Die Disk-Metriken werden berechnet, indem die Summe des verwendeten Festplattenprozentsatzes für jeden Server, geteilt durch die Metrik Server, berechnet wird. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Geschätzte Sweep-Minuten</b> </td> 
   <td colname="col2"> Dies ist die Summe der geschätzten Sweep-Dekaseconds für jeden Server, geteilt durch die Metrik Server, bei der geschätzte Sweep-Dekaseconds größer als null sind, alle geteilt durch 6. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Letzte Ping-Zeit</b> </td> 
   <td colname="col2"> Die Summe des letzten Pings für jeden Block dividiert durch Blöcke und dann mit 10 multipliziert. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Load</b> </td> 
   <td colname="col2"> Dies ist die Summe des Lastendurchschnitts für jeden Server geteilt durch die Metrik Server. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Speicherseitendatei</b> </td> 
   <td colname="col2"> Dies ist die Summe des Dateiprozentsatzes der Speicherseite für jeden Server geteilt durch die Metrik Server. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Physikalischer Speicher</b> </td> 
   <td colname="col2"> Dies ist die Summe des physikalischen Prozentsatzes des Speichers für jeden Server geteilt durch die Metrik Server. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Speicherabfrage</b> </td> 
   <td colname="col2"> Dies ist die Summe des Prozentsatzes der Speicherabfrage für jeden Server geteilt durch die Metrik Server. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Netzwerkverbindungen</b> </td> 
   <td colname="col2"> Dies ist die Summe der Netzwerkverbindungen für jeden Server geteilt durch die Metrik Server. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Umfragelatenz in Millisekunden</b> </td> 
   <td colname="col2"> Dies ist die Summe der Zentisekunden der Umfrage für jeden Server geteilt durch die Metrik Server, die alle mit 10 multipliziert wird. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Schnellprüfung</b> </td> 
   <td colname="col2"> Dies ist die Anzahl der Server, bei denen Quick Check Success gleich 1 ist, geteilt durch die Metrik Server, die alle mit 100 multipliziert wird. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Server</b> </td> 
   <td colname="col2"> Dies ist die Summe von 1 für jeden Server oder die Gesamtzahl der überwachten Server. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Temp DB</b> </td> 
   <td colname="col2"> Dies ist die Summe des Temp DB Space Percentage für jeden Server geteilt durch die Metrik Server. </td> 
  </tr> 
 </tbody> 
</table>

