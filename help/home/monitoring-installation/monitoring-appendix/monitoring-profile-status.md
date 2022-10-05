---
description: Die folgenden Dimensionen können im Profil Profilstatus von Data Workbench verwendet werden.
title: Dimensionen im Data Workbench-Profil zum Profilstatus
uuid: bd84a3e5-d1ea-4768-9dac-62f5dfbad49a
exl-id: 57b3ff16-26db-4292-819b-f6cd8e024c2a
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1047'
ht-degree: 2%

---

# Dimensionen im Data Workbench-Profil zum Profilstatus{#dimensions-in-the-data-workbench-profile-status-profile}

{{eol}}

Die folgenden Dimensionen können im Profil Profilstatus von Data Workbench verwendet werden.

<table id="table_DD143B4F15FF446DAD24BD2473B485B9"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Block</b> </td> 
   <td colname="col2"> Dies ist die einzige zählbare Komponente in dieser Konfiguration und ist der Stamm für alle Dimensionen. Ein Block kann als Server betrachtet werden. Es wird das Feld x-trackingid verwendet. Die Block-ID ist ein Hash des Servernamens plus des Hostnamens, sodass pro Server und Profil etwa ein Block vorhanden ist. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Stand der Verspätungsminuten</b> </td> 
   <td colname="col2"> cs-uri-query(bi) wird in das Feld x-as-of-delay-minutes platziert und auf die nächste Minute gerundet. Ab der Funktion "Minuten verzögern"ist eine numerische Dimension, die die letzte Zeile von x-as-of-delay-Minuten für einen Block annimmt. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Umgebung</b> </td> 
   <td colname="col2"> Der Wert cs-uri-query(c) wird für die Umgebungs-ID verwendet. Die letzte Zeile für einen Block wird als Wert für die Dimension verwendet. Diese einfache Dimension zeigt die Umgebung an, in der Ihre Server ausgeführt werden (sofern sie ordnungsgemäß konfiguriert ist). <p>Dies kann in der Datei insight_monitor_agent.cfg festgelegt werden. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Schneller Input MegaBytes pro Minute</b> </td> 
   <td colname="col2"> Für diese Dimension wird der Wert cs-uri-query(bj) verwendet. Die letzte Zeile eines Blocks wird als Wert für die Dimension verwendet. Wenn der Datensatz in Schnelle Eingabe enthalten ist, zeigt der Wert dieser numerischen Dimension die MB pro Minute an, in die das System Daten eingibt. <p>Hinweis: Diese Dimension ist ausgeblendet, da sie nur nützlich ist, wenn sie in einer Metrik im Durchschnitt dargestellt wird. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Schnelles Zusammenführen von MegaBytes pro Minute</b> </td> 
   <td colname="col2">Für diese Dimension wird der Wert cs-uri-query(bk) verwendet. Die letzte Zeile für einen Block wird als Wert für die Dimension verwendet. Wenn sich der Datensatz in Schneller Zusammenführung befindet, zeigt dieser numerische Dimension-Wert die MB pro Minute an, in der das System zusammengeführt wird. <p>Hinweis: Diese Dimension ist ausgeblendet, da sie nur nützlich ist, wenn sie in einer Metrik im Durchschnitt dargestellt wird. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Field GigaBytes</b> </td> 
   <td colname="col2"> Für diese Dimension wird der Wert cs-uri-query(bg) verwendet. Der Wert wird durch 1000 geteilt und auf die nächste Ganzzahl gerundet. Der Wert dieser numerischen Dimension zeigt den Speicherplatz an, den die Felder im Datensatz verwenden. <p>Hinweis: Diese Dimension ist ausgeblendet, da sie nur nützlich ist, wenn sie in einer Metrik im Durchschnitt dargestellt wird. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Host</b> </td> 
   <td colname="col2"> Für diese Dimension wird der Wert cs-uri-query(b) verwendet. Der Wert der Dimension "Einfach"ist die letzte Zeile eines Blocks. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Letztes Ping</b> </td> 
   <td colname="col2">x-last-ping ist x-unixtime dividiert durch 10 (um Größenbeschränkungen für numerische Dimensionen aufzunehmen). Letztes Ping ist die letzte Zeile für einen bestimmten Block und stellt das letzte Mal dar, dass der Überwachungsagent den Systemzustand protokolliert. <p>Hinweis: Diese Dimension ist ausgeblendet, da sie nur nützlich ist, wenn sie in einer Metrik im Durchschnitt dargestellt wird. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Prozentsatz der Protokolllesung</b> </td> 
   <td colname="col2">wird der Wert cs-uri-query(be) für diese numerische Dimension verwendet. Dies ist die letzte Zeile für einen bestimmten Block. Diese Dimension wird verwendet, um den Prozentsatz der zu lesenden Protokolle zu berechnen. <p>Hinweis: Diese Dimension ist ausgeblendet, da sie nur nützlich ist, wenn sie in einer Metrik im Durchschnitt dargestellt wird. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Verarbeitungsmodus-ID</b> </td> 
   <td colname="col2"> Für diese einfache Dimension wird der Wert cs-uri-query(bb) verwendet. Dies ist die letzte Zeile für einen bestimmten Block. Mit der Verarbeitungsmodus-ID können Sie sehen, in welchem Verarbeitungsmodus sich das System befindet (schnelle Eingabe, schnelle Zusammenführung, Echtzeit). <p>Hinweis: Diese Dimension wird ausgeblendet und dann im clientseitigen Dimensionsverarbeitungsmodus erneut mit benutzerfreundlichen Werten offen gelegt. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Verarbeitung angehalten</b> </td> 
   <td colname="col2"> Das Feld "x-processing-stalled"wird über verschiedene Bedingungen erstellt, um anzugeben, ob das Profil derzeit ausgeführt wird oder nicht. Es ist eine einfache Dimension. <p>Hinweis: Diese Dimension funktioniert am besten, wenn eine große Anzahl von Eingabeprotokollen relativ zwischen den DPUs verteilt werden muss. Wenn beispielsweise nur eine große Datei pro Tag geladen wird, kann Data Workbench für mindestens eine Stunde "anhalten", was zu einer falsch positiven Anzeige dieser Dimension führt. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Profil</b> </td> 
   <td colname="col2"> Der Wert cs-uri-query(ba) wird für diese einfache Dimension verwendet. Diese Dimension zeigt die Namen der Profile an, die derzeit überwacht werden. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Quelle am weitesten hinten</b> </td> 
   <td colname="col2"> Die letzte Zeile von cs-uri-query(bl) wird in das Feld x-source-furthest-after kopiert. Die einfache Dimension verwendet die letzte Zeile für einen bestimmten Block. Diese Dimension zeigt den Zeitpunkt des letzten Kontakts mit einer Datenquelle an. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Prozentsatz der Umwandlungen</b> </td> 
   <td colname="col2"> wird der Wert cs-uri-query(bf) für diese numerische Dimension verwendet. Dies ist die letzte Zeile für einen bestimmten Block. Diese Dimension wird verwendet, um den Prozentsatz der vollständigen Datenumwandlung zu berechnen. <p>Hinweis: Diese Dimension ist ausgeblendet, da sie nur nützlich ist, wenn sie in einer Metrik im Durchschnitt dargestellt wird. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Zeitdimensionen</b> </td> 
   <td colname="col2"> Stunde, Tag, Woche, Monat, Stunde des Tages und Tag der Woche werden alle aus dem Feld x-timestamp abgeleitet. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Gruppe</b> </td> 
   <td colname="col2"> Gruppierungswort, das Ihnen eine andere Möglichkeit bietet, den resultierenden Datensatz zu filtern. Wird in der Datei insight_monitor_agent.cfg festgelegt. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Metriken</b> </td> 
   <td colname="col2"> Im Folgenden werden die Metriken aufgelistet, die im Profil-Monitoring-Profil von Data Workbench enthalten sind, und wie sie abgeleitet werden. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Stand der Verspätungsminuten</b> </td> 
   <td colname="col2"> Diese Metrik ist die Summe der Ausführungsminuten für jeden Block und anschließend durch die Metrik Blöcke geteilt. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Ab Verzögerung in Sekunden</b> </td> 
   <td colname="col2"> Diese Metrik ist die Summe der As Of Delay Seconds für jeden Block und dividiert durch die Gesamtzahl der Blöcke. (Ab Dimension "Sekunden verzögern"nicht vorkonfiguriert) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Blöcke</b> </td> 
   <td colname="col2"> Summe 1 für jeden Block. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Schneller Input MB pro Minute</b> </td> 
   <td colname="col2"> Die Summe der Fast Input MegaBytes pro Minute für jeden Block geteilt durch die Anzahl der Blöcke, wenn Fast Input MegaBytes pro Minute größer als null ist. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Schnelles Zusammenführen von MB pro Minute</b> </td> 
   <td colname="col2"> Die Summe der MegaBytes der schnellen Zusammenführung pro Minute für jeden Block dividiert durch die Anzahl der Blöcke, bei denen die MegaBytes der schnellen Zusammenführung pro Minute größer als null ist. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Field GigaBytes</b> </td> 
   <td colname="col2"> Die Summe der Feld-Gigabyte für jeden Block dividiert durch die Blocks-Metrik. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Letztes Ping-Alter</b> </td> 
   <td colname="col2"> Die Ausführungsdauer abzüglich der letzten Ping-Zeit. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Letzte Ping-Zeit</b> </td> 
   <td colname="col2"> Die Summe des letzten Pings für jeden Block dividiert durch Blöcke, multipliziert mit 10. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Protokolllesen</b> </td> 
   <td colname="col2"> Wenn der Protokollleseprozentsatz größer als null ist, ist die Protokolllesehilfe die Summe des Protokollleseprozentsatzes für jeden Block, dividiert durch die Blockmetrik, die alle durch 10 dividiert wird. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Verarbeitung angehalten</b> </td> 
   <td colname="col2"> Die Summe der verarbeiteten angehaltenen Dimension für jeden Baustein, dividiert durch die Metrik Bausteine . </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Umwandlung</b> </td> 
   <td colname="col2"> Die Summe des Umwandlungsprozentsatzes für jeden Block dividiert durch die Metrik "Blöcke", wenn der Transformationsprozentsatz größer als null ist, geteilt durch 10. </td> 
  </tr> 
 </tbody> 
</table>
