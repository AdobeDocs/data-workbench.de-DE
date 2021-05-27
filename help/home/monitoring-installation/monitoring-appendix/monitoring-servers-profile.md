---
description: Die folgenden Dimensionen können im Data Workbench-Profil zum Server-Status verwendet werden.
title: Dimensionen im Data Workbench-Profil zum Server-Status
uuid: 4cfe882a-2797-4af9-bd6d-75bc31ee909c
exl-id: 002f6b95-f151-41d9-ae28-9c01c1f621ee
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1366'
ht-degree: 1%

---

# Dimensionen im Data Workbench-Profil zum Server-Status{#dimensions-in-the-data-workbench-server-status-profile}

Die folgenden Dimensionen können im Data Workbench-Profil zum Server-Status verwendet werden.

<table id="table_10DFAD7A0C5946B0A2458F6C08D04FC5"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Server</b> </td> 
   <td colname="col2"> Diese zählbare Dimension, die aus dem Feld x-trackingid erstellt wurde, stellt die Server dar, auf denen Data Workbench derzeit ausgeführt wird. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Agent-Version</b> </td> 
   <td colname="col2"> Der Wert cs-uri-query(af) wird für diese einfache Dimension verwendet. Dies ist der letzte nicht leere Wert für einen Server. Dadurch werden das Build-Datum und die Uhrzeit für die Version(en) des ausgeführten Überwachungsagenten angezeigt. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Jegliche erneute Verarbeitung eines Profils</b> </td> 
   <td colname="col2"> Das Feld cs-uri-query(aa) wird für diese numerische Dimension verwendet. Es ist der Wert der letzten Zeile für einen bestimmten Server, bedingt durch cs-uri-query(k) ist nicht leer. Diese Dimension wird verwendet, um anzugeben, ob Profile erneut verarbeitet werden. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Prozentsatz der Kapazitätszeile</b> </td> 
   <td colname="col2"> Das Feld cs-uri-query(r) wird für diese numerische Dimension verwendet. Es ist der Wert der letzten Zeile für einen bestimmten Server, bedingt durch cs-uri-query(k) ist nicht leer. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Kapazitätsgröße Prozentsatz</b> </td> 
   <td colname="col2"> Das Feld cs-uri-query(n) wird für diese numerische Dimension verwendet. Es ist der Wert der letzten Zeile für einen bestimmten Server, bedingt durch cs-uri-query(k) ist nicht leer. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Gebrauchsname</b> </td> 
   <td colname="col2"> Das Feld sc-ur-query(am) wird für diese einfache Dimension verwendet. Es ist der Wert des Wertes Letztes Nicht leer für einen bestimmten Server. Er zeigt den allgemeinen Namen der überwachten Server an. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Komponentenprüfung erfolgreich</b> </td> 
   <td colname="col2"> Das Feld cs-uri-query(v) wird für diese einfache Dimension verwendet. Es ist der Wert der letzten Zeile für einen bestimmten Server. Diese Dimension überprüft die Komponenten des Servers, um sicherzustellen, dass sie ordnungsgemäß funktionieren. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Komponenten im Fehler</b> </td> 
   <td colname="col2"> Bei einer Umwandlung über mehrere Zeilen wird der Wert der letzten Zeile der cs-uri-query(ao) übernommen und in das Feld x-components-in-error kopiert. Diese Dimension Viele bis Viele zeigt alle fehlerhaften Komponenten auf Servern an, die überwacht werden. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Umgebung</b> </td> 
   <td colname="col2">Der Wert cs-uri-query(c) wird für die Umgebungs-ID verwendet. Die letzte Zeile für einen Block wird als Wert für die Dimension verwendet. Diese einfache Dimension zeigt die Umgebung an, in der Ihre Server ausgeführt werden (sofern sie ordnungsgemäß konfiguriert ist). <p><p>Hinweis:  Diese Dimension wird in insight_monitor_agent.cfg festgelegt. </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Geschätzte Sweep-Dekaseconds</b> </td> 
   <td colname="col2"> Das Feld x-estimated-sweep-dekaseconds wird in dieser numerischen Dimension verwendet. Dies ist die geschätzte Sweep-Zeit der Server geteilt durch zehn (reduzierte Auflösung der Sweep-Messung, um die Größe der Dimension zu vergrößern). <p><p>Hinweis:  Diese Dimension ist ausgeblendet, da sie nur nützlich ist, wenn sie in einer Metrik im Durchschnitt dargestellt wird. </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Host</b> </td> 
   <td colname="col2"> Für diese Dimension wird der Wert cs-uri-query(b) verwendet. Der Wert der Dimension "Einfach"ist die letzte Zeile eines Blocks. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Letztes Ping</b> </td> 
   <td colname="col2"> x-last-ping ist x-unixtime dividiert durch 10 (um Größenbeschränkungen für numerische Dimensionen aufzunehmen). Letztes Ping ist die letzte Zeile für einen bestimmten Block und stellt das letzte Mal dar, dass der Überwachungsagent den Systemzustand protokolliert. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Durchschnitt laden</b> </td> 
   <td colname="col2"> Dies ist eine numerische Dimension, die die letzte Zeile für den cs-uri-query(i) -Wert eines bestimmten Servers verwendet. Dies ist davon abhängig, dass cs-uri-query(k) nicht leer ist. Diese Dimension wird verwendet, um die durchschnittliche Auslastung der Server im überwachten System zu berechnen. <p>Hinweis:  Diese Dimension ist ausgeblendet, da sie nur nützlich ist, wenn sie in einer Metrik im Durchschnitt dargestellt wird. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Dateiprozentsatz der Speicherseite</b> </td> 
   <td colname="col2"> Dies ist eine numerische Dimension, die die letzte Zeile für den cs-uri-query(o) -Wert eines bestimmten Servers verwendet. Dies ist davon abhängig, dass cs-uri-query(k) nicht leer ist. Diese Dimension wird verwendet, um den Prozentsatz der Speichernutzung der Seitendatei zu berechnen. <p>Hinweis:  Diese Dimension ist ausgeblendet, da sie nur nützlich ist, wenn sie in einer Metrik im Durchschnitt dargestellt wird. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Physikalische MegaBytes insgesamt</b> </td> 
   <td colname="col2"> Dies ist eine numerische Dimension, die die letzte Zeile für den cs-uri-query(ag) -Wert eines bestimmten Servers verwendet. Dies ist davon abhängig, dass cs-uri-query(k) nicht leer ist. <p>Hinweis:  Diese Dimension ist ausgeblendet, da sie nur nützlich ist, wenn sie in einer Metrik im Durchschnitt dargestellt wird. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Physikalischer Speicherprozentsatz</b> </td> 
   <td colname="col2"> Dies ist eine numerische Dimension, die die letzte Zeile für den cs-uri-query(ag) -Wert eines bestimmten Servers verwendet. Dies ist davon abhängig, dass cs-uri-query(k) nicht leer ist. Diese Dimension wird verwendet, um den Prozentsatz der Speichernutzung jedes Servers zu berechnen. <p>Hinweis:  Diese Dimension ist ausgeblendet, da sie nur nützlich ist, wenn sie in einer Metrik im Durchschnitt dargestellt wird. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Prozentsatz der Speicherabfrage</b> </td> 
   <td colname="col2"> Dies ist eine numerische Dimension, die die letzte Zeile für den cs-uri-Abfragewert(e) eines bestimmten Servers verwendet. Dies ist davon abhängig, dass cs-uri-query(k) nicht leer ist. Diese Dimension wird verwendet, um den Prozentsatz der Speichernutzung der Abfrage für jeden Server zu berechnen. <p>Hinweis:  Diese Dimension ist ausgeblendet, da sie nur nützlich ist, wenn sie in einer Metrik im Durchschnitt dargestellt wird. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Netzwerkverbindungen</b> </td> 
   <td colname="col2"> Dies ist eine numerische Dimension, die die letzte Zeile für den cs-uri-query(q) -Wert eines bestimmten Servers verwendet. Dies ist davon abhängig, dass cs-uri-query(k) nicht leer ist. Damit wird die Anzahl der Netzwerkverbindungen angezeigt, die für einen bestimmten Server vorhanden sind. <p>Hinweis:  Diese Dimension ist ausgeblendet, da sie nur nützlich ist, wenn sie in einer Metrik im Durchschnitt dargestellt wird. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Umfragelatenz in Sekunden</b> </td> 
   <td colname="col2"> Diese Dimension wird verwendet, um die Abfragelatenz zu berechnen. Der Wert cs-uri-query(m) wird durch 10 dividiert, um die Dimensionsgröße zu reduzieren, und in das Feld x-poll-latency-centiseconds kopiert. Dies ist eine numerische Dimension, die die letzte Zeile für einen bestimmten Server akzeptiert. <p>Hinweis:  Diese Dimension ist ausgeblendet, da sie nur nützlich ist, wenn sie in einer Metrik im Durchschnitt dargestellt wird. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Schnellprüfungserfolg</b> </td> 
   <td colname="col2"> Dies ist eine einfache Dimension, die aus dem Wert cs-uri-query(g) der letzten Zeile für einen bestimmten Server erstellt wurde. Sie wird zur Berechnung der Schnellprüfungsmetrik verwendet. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Temp DB Space Prozentwert</b> </td> 
   <td colname="col2"> Die letzte Zeile des Werts cs-uri-query(a) wird in das Feld x-temp-db-space-percent kopiert. Dies ist eine numerische Dimension, die verwendet wird, um den Prozentsatz des verwendeten Temp DB-Speicherplatzes auf einem bestimmten Server zu berechnen. <p>Hinweis:  Diese Dimension ist ausgeblendet, da sie nur nützlich ist, wenn sie in einer Metrik im Durchschnitt dargestellt wird. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Insight-Version</b> </td> 
   <td colname="col2"> Der Wert cs-uri-query(ab) wird für diese einfache Dimension verwendet. Dies ist der letzte nicht leere Wert für einen Server. Dadurch werden die auf den einzelnen Servern ausgeführten Versionen des Data Workbench-Servers angezeigt. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Gruppe</b> </td> 
   <td colname="col2"> Gruppierungswort, das Ihnen eine andere Möglichkeit bietet, den resultierenden Datensatz zu filtern. <p>Hinweis:  Diese Dimension wird in insight_monitor_agent.cfg festgelegt. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Metriken</b> </td> 
   <td colname="col2"> Im Folgenden werden die Metriken aufgelistet, die im Profil-Monitoring-Profil von Data Workbench enthalten sind, und wie sie abgeleitet werden. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Gesamtkapazität</b> </td> 
   <td colname="col2"> Dies ist die Metrik Kapazitätsgröße zweimal plus der Metrik Kapazitätszeile dividiert durch 3. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Kapazitätszeile</b> </td> 
   <td colname="col2"> Dies ist die Summe des Prozentsatzes der Kapazitätszeilen für jeden Server dividiert durch die Metrik Server . </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Kapazitätsgröße</b> </td> 
   <td colname="col2"> Dies ist die Summe des Prozentsatzes der Kapazitätsgröße für jeden Server geteilt durch die Metrik Server . </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Komponentenprüfung</b> </td> 
   <td colname="col2"> Dies ist die Anzahl der Server, bei denen die Komponentenüberprüfung erfolgreich gleich eins ist, geteilt durch den Server, bei dem der Dienst DPU oder FSU ist, alle multipliziert mit 100 (um einen Prozentsatz zu erhalten). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Disk "x"</b> </td> 
   <td colname="col2"> Die Festplattenmetriken werden berechnet, indem sie die Summe ihres verwendeten Festplattenprozentsatzes für jeden Server, geteilt durch die Server-Metrik, berechnen. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Geschätzte Sweep-Minutes</b> </td> 
   <td colname="col2"> Dies ist die Summe der geschätzten Sweep-Dekasekonds für jeden Server, geteilt durch die Server-Metrik, bei der geschätzte Sweep-Dekasekonds größer als null ist, alle geteilt durch 6. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Letzte Ping-Zeit</b> </td> 
   <td colname="col2"> Die Summe des letzten Pings für jeden Block dividiert durch Blöcke, multipliziert mit 10. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Load</b> </td> 
   <td colname="col2"> Dies ist die Summe des Lastdurchschnitts für jeden Server dividiert durch die Metrik Server . </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Speicherseitendatei</b> </td> 
   <td colname="col2"> Dies ist die Summe des Dateiprozentsatzes der Speicherseite für jeden Server, geteilt durch die Metrik Server . </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Physikalische Speicher</b> </td> 
   <td colname="col2"> Dies ist die Summe des physischen Prozentsatzes des Arbeitsspeichers für jeden Server geteilt durch die Metrik Server . </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Speicherabfrage</b> </td> 
   <td colname="col2"> Dies ist die Summe des Speicherabfrageprozentsatzes für jeden Server geteilt durch die Server-Metrik. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Netzwerkverbindungen</b> </td> 
   <td colname="col2"> Dies ist die Summe der Netzwerkverbindungen für jeden Server geteilt durch die Metrik Server . </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Umfragelatenz in Millisekunden</b> </td> 
   <td colname="col2"> Dies ist die Summe der Umfrage-Latenzzeiten in Sekunden für jeden Server, geteilt durch die Server-Metrik, die alle mit 10 multipliziert wird. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Schnellprüfung</b> </td> 
   <td colname="col2"> Dies ist die Anzahl der Server, bei denen der Erfolg der Schnellprüfung gleich 1 ist, geteilt durch die Metrik Server , die alle mit 100 multipliziert wird. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Server</b> </td> 
   <td colname="col2"> Dies ist die Summe von 1 für jeden Server oder die Gesamtzahl der überwachten Server. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Temp DB</b> </td> 
   <td colname="col2"> Dies ist die Summe des Temp DB Space Prozentsatzes für jeden Server geteilt durch die Server-Metrik. </td> 
  </tr> 
 </tbody> 
</table>
