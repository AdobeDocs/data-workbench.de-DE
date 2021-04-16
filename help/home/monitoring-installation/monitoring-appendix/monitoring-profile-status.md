---
description: Die folgenden Dimensionen stehen im Data Workbench Profil Status-Profil zur Verfügung.
title: Dimensionen im Data Workbench-Profil zum Profilstatus
uuid: bd84a3e5-d1ea-4768-9dac-62f5dfbad49a
exl-id: 57b3ff16-26db-4292-819b-f6cd8e024c2a
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1047'
ht-degree: 2%

---

# Dimensionen im Data Workbench-Profil zum Profilstatus{#dimensions-in-the-data-workbench-profile-status-profile}

Die folgenden Dimensionen stehen im Data Workbench Profil Status-Profil zur Verfügung.

<table id="table_DD143B4F15FF446DAD24BD2473B485B9"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Block</b> </td> 
   <td colname="col2"> Dies ist die einzige zählbare Datei in dieser Konfiguration und existiert als Stamm für alle Dimensionen. Ein Block kann als Server betrachtet werden. Es verwendet das x-trackingid-Feld. Die Block-ID ist ein Hash des Servernamens und des Hostnamens, sodass pro Profil etwa ein Block vorhanden ist. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Ab Verzögerung Minuten</b> </td> 
   <td colname="col2"> cs-uri-Abfrage(bi) wird in das Feld "x-as-of-delay-minutes"gesetzt und auf die nächste Minute gerundet. Ab Delay Minutes ist eine numerische Dimension, die die letzte Zeile von x-as-of-delay-Minuten für einen Block nimmt. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Umgebung</b> </td> 
   <td colname="col2"> Der Wert "cs-uri-Abfrage(c)"wird für die Umgebung-ID verwendet. Die letzte Zeile für einen Block wird als Wert für die Dimension verwendet. Diese einfache Dimension zeigt die Umgebung an, in der Ihre Server ausgeführt werden (vorausgesetzt, sie ist richtig konfiguriert). <p>Dies kann in der Datei "insight_monitor_agent.cfg"festgelegt werden </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Schnelle Eingabe MegaBytes pro Minute</b> </td> 
   <td colname="col2"> Für diese Dimension wird der Wert "cs-uri-Abfrage(bj)"verwendet. Die letzte Zeile für einen Block wird als Wert für die Dimension verwendet. Wenn sich der Datensatz in "Schnelle Eingabe"befindet, zeigt diese numerische Dimension die MB pro Minute an, in der das System Daten eingibt. <p>Hinweis:  Diese Dimension wird ausgeblendet, da sie nur dann nützlich ist, wenn sie in einer Metrik gemittelt wird. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Schnelles Zusammenführen von MegaBytes pro Minute</b> </td> 
   <td colname="col2">Für diese Dimension wird der Wert "cs-uri-Abfrage(bk)"verwendet. Die letzte Zeile für einen Block wird als Wert für die Dimension verwendet. Wenn sich der Datensatz in "Schnelle Zusammenführung"befindet, zeigt dieser Wert der numerischen Dimension die MB pro Minute an, in der das System zusammengeführt wird. <p>Hinweis:  Diese Dimension wird ausgeblendet, da sie nur dann nützlich ist, wenn sie in einer Metrik gemittelt wird. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Feld GigaBytes</b> </td> 
   <td colname="col2"> Für diese Dimension wird der Wert "cs-uri-Abfrage(bg)"verwendet. Der Wert wird durch 1000 dividiert und auf die nächste ganze Zahl gerundet. Der Wert dieser numerischen Dimension zeigt den Platz an, den die Felder im Datensatz verwenden. <p>Hinweis:  Diese Dimension wird ausgeblendet, da sie nur dann nützlich ist, wenn sie in einer Metrik gemittelt wird. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Host</b> </td> 
   <td colname="col2"> Für diese Dimension wird der Wert "cs-uri-Abfrage(b)"verwendet. Der Wert der Dimension "Einfach"ist die letzte Zeile für einen Block. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Letztes Ping</b> </td> 
   <td colname="col2">x-last-ping wird durch x-unixtime dividiert durch 10 (um Größenbeschränkungen für numerische Dimensionen aufzunehmen). Letztes Ping ist die letzte Zeile für einen bestimmten Block und stellt das letzte Mal dar, dass der Überwachungsagenten den Systemstatus protokolliert. <p>Hinweis:  Diese Dimension wird ausgeblendet, da sie nur dann nützlich ist, wenn sie in einer Metrik gemittelt wird. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Prozentsatz der Protokolllesung</b> </td> 
   <td colname="col2">der Wert cs-uri-Abfrage(be) für diese numerische Dimension verwendet wird. Es ist die letzte Zeile für einen bestimmten Block. Diese Dimension wird verwendet, um den Prozentsatz der zu lesenden Protokolle zu berechnen. <p>Hinweis:  Diese Dimension wird ausgeblendet, da sie nur dann nützlich ist, wenn sie in einer Metrik gemittelt wird. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Verarbeitungsmodus-ID</b> </td> 
   <td colname="col2"> Für diese einfache Dimension wird der Wert "cs-uri-Abfrage(bb)"verwendet. Es ist die letzte Zeile für einen bestimmten Block. Mit der Verarbeitungsmodus-ID können Sie sehen, in welchem Verarbeitungsmodus das System verarbeitet wird (schnelle Eingabe, schnelle Zusammenführung, Echtzeit). <p>Hinweis:  Diese Dimension wird ausgeblendet und dann mit benutzerfreundlichen Werten im clientseitigen Dimensionsverarbeitungsmodus erneut offen gelegt. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Verarbeitung angehalten</b> </td> 
   <td colname="col2"> Das angehaltene Feld "x-processing-stalled"wird unter verschiedenen Bedingungen erstellt, um anzugeben, ob das Profil derzeit ausgeführt wird oder nicht. Es ist eine einfache Dimension. <p>Hinweis:  Diese Dimension funktioniert am besten, wenn es eine große Anzahl von Eingabeprotokollen gibt, die fair unter den DPU verteilt werden sollen. Wenn z. B. nur eine große Datei pro Tag geladen wird, kann die Data Workbench eine Stunde oder länger "anhalten", was zu einer falsch positiven Anzeige aus dieser Dimension führt. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Profil</b> </td> 
   <td colname="col2"> Für diese einfache Dimension wird der Wert "cs-uri-Abfrage(ba)"verwendet. Diese Dimension zeigt die Namen der Profil an, die derzeit überwacht werden. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Quelle am weitesten hinten</b> </td> 
   <td colname="col2"> Die letzte Zeile von cs-uri-Abfrage(bl) wird in das x-source-furthest-behind-Feld kopiert. Die Dimension "Einfach"verwendet die letzte Zeile für einen bestimmten Block. Diese Dimension zeigt an, wann der letzte Kontakt mit einer Datenquelle aufgetreten ist. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Transformationsprozentsatz</b> </td> 
   <td colname="col2"> der Wert cs-uri-Abfrage(bf) für diese numerische Dimension verwendet wird. Es ist die letzte Zeile für einen bestimmten Block. Diese Dimension wird zur Berechnung des Prozentsatzes der vollständigen Datenumwandlung verwendet. <p>Hinweis:  Diese Dimension wird ausgeblendet, da sie nur dann nützlich ist, wenn sie in einer Metrik gemittelt wird. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Zeitdimensionen</b> </td> 
   <td colname="col2"> Stunde, Tag, Woche, Monat, Stunde des Tages und Wochentag werden alle aus dem Feld "x-timestamp"abgeleitet. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Gruppe</b> </td> 
   <td colname="col2"> Gruppieren von Wörtern, die Ihnen eine andere Möglichkeit bieten, den resultierenden Datensatz zu filtern. Wird in der Datei "insight_monitor_agent.cfg"festgelegt. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Metriken</b> </td> 
   <td colname="col2"> Mit den folgenden Listen werden die Metriken, die im Data Workbench Profil Monitoring-Profil enthalten sind, und ihre Ableitung behandelt. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Ab Verspätungsminuten</b> </td> 
   <td colname="col2"> Diese Metrik ist die Summe der Ausführungsminuten für jeden Block und anschließend dividiert durch die Metrik Blöcke. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Ab Verzögerung Sekunden</b> </td> 
   <td colname="col2"> Diese Metrik ist die Summe der "Ausführungsdauer"für jeden Block und dividiert durch die Gesamtanzahl der Blöcke. (Ab Delay Seconds Dimension nicht standardmäßig konfiguriert) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Blöcke</b> </td> 
   <td colname="col2"> Summe 1 für jeden Block. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Schnelle Eingabe MB pro Minute</b> </td> 
   <td colname="col2"> Die Summe der schnellen Eingabe MegaBytes pro Minute für jeden Block dividiert durch die Anzahl der Blöcke, wenn die schnelle Eingabe MegaBytes pro Minute größer als null ist. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Schnelle Zusammenführung MB pro Minute</b> </td> 
   <td colname="col2"> Die Summe der MegaBytes pro Minute für jeden Block geteilt durch die Anzahl der Blöcke, wenn die MegaBytes für die schnelle Zusammenführung größer als null sind. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Feld GigaBytes</b> </td> 
   <td colname="col2"> Die Summe der Field-Gigabyte für jeden Block dividiert durch die Blocks-Metrik. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Letztes Seitenalter</b> </td> 
   <td colname="col2"> Die Ausführungszeit minus letzte Ping-Zeit. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Letzte Ping-Zeit</b> </td> 
   <td colname="col2"> Die Summe des letzten Pings für jeden Block dividiert durch Blöcke und dann mit 10 multipliziert. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Protokolllesen</b> </td> 
   <td colname="col2"> Wenn der Protokollleseprozentsatz größer als null ist, ist "Protokolllesen"die Summe des Protokollleseprozentsatzes für jeden Block, geteilt durch die Blockmetrik, die alle durch 10 dividiert wird. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Verarbeitung angehalten</b> </td> 
   <td colname="col2"> Die Summe der Dimension "Verarbeitung angehalten"für jeden Block dividiert durch die Metrik "Blöcke". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Umwandlung</b> </td> 
   <td colname="col2"> Die Summe der Transformationsprozentsätze für jeden Block dividiert durch die Metrik Blöcke, wenn der Transformationsprozentsatz größer als null ist, alle dividiert durch 10. </td> 
  </tr> 
 </tbody> 
</table>
