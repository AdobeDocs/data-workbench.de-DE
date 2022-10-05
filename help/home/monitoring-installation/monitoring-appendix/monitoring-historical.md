---
description: Die folgenden Dimensionen können im Data Workbench-Profil zur Historie verwendet werden.
title: Dimensionen im Data Workbench-Profil zur Historie
uuid: 6d93fba4-986b-46a4-9479-aeb54853dff5
exl-id: 9df1f317-a985-4132-b32e-f2263e0c23b2
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1698'
ht-degree: 1%

---

# Dimensionen im Data Workbench-Profil zur Historie{#dimensions-in-the-data-workbench-historic-profile}

{{eol}}

Die folgenden Dimensionen können im Data Workbench-Profil zur Historie verwendet werden.

## Dimensionen im Data Workbench-Profil zur Historie {#section-96f1b64f5cb84411b630f97f227d888d}

Die folgenden Dimensionen können im Data Workbench-Profil zur Historie verwendet werden.

<table id="table_3EAEA68E73BE431D841F7F2E83EDD6AC"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Block</b> </td> 
   <td colname="col2">Dies ist die einzige zählbare Konfiguration in dieser Konfiguration. Es ist die Wurzel für alle Dimensionen. Ein Block kann als Server betrachtet werden. Es wird das Feld x-trackingid verwendet. <p>Hinweis: Die Block-ID ist ein Hash des Servernamens plus des Hostnamens, sodass pro Server und Profil etwa ein Block vorhanden ist. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Ping</b> </td> 
   <td colname="col2"> Dies ist eine zählbare Dimension, die auf der Blockzählung basiert. Jede Datenzeile im Profil ist ein Ping vom Überwachungsagenten. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Warnungskritisch</b> </td> 
   <td colname="col2"> Numerische Dimension, die aus dem cs-uri-query(ad) -Wert erstellt wird. Es wird auf der Ping-Ebene erstellt, sofern cs-uri-query(a) mit "1"übereinstimmt. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Warnhinweis nach unten</b> </td> 
   <td colname="col2"> Numerische Dimension basierend auf dem Wert cs-uri-query(ac) . Es wird auf Ping-Ebene erstellt, vorausgesetzt, dass cs-uri-query(a) mit "1"übereinstimmt. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Warnhinweis</b> </td> 
   <td colname="col2"> Numerische Dimension, die aus dem Wert cs-uri-query(ae) erstellt wurde. Es wird auf der Ping-Ebene erstellt, sofern cs-uri-query(a) mit "1"übereinstimmt. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Jegliche erneute Verarbeitung eines Profils</b> </td> 
   <td colname="col2"> Numerische Dimension basierend auf dem cs-uri-query(aa) -Wert. Es wird auf Ping-Ebene erstellt, sofern cs-uri-query(a) mit "1"übereinstimmt und cs-uriquery(k) nicht leer ist. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Stand der Verspätungsminuten</b> </td> 
   <td colname="col2"> cs-uri-query(bi) wird in das Feld x-as-of-delay-minutes platziert und auf die nächste Minute gerundet. Es wird auf der Ping-Ebene erstellt, sofern cs-uri-query(a) mit "1"übereinstimmt. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Prozentsatz der Kapazitätszeile</b> </td> 
   <td colname="col2"> Numerische Dimension basierend auf dem Wert cs-uri-query(r) . Es wird auf Ping-Ebene erstellt, sofern cs-uri-query(a) mit "1"übereinstimmt und cs-uriquery(k) nicht leer ist. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Kapazitätsgröße Prozentsatz</b> </td> 
   <td colname="col2"> Numerische Dimension basierend auf dem Wert cs-uri-query(n) . Es wird auf Ping-Ebene erstellt, sofern cs-uri-query(a) mit "1"übereinstimmt und cs-uriquery(k) nicht leer ist. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Komponentenprüfung erfolgreich</b> </td> 
   <td colname="col2"> Einfache Dimension basierend auf dem Wert cs-uri-query(v) . Sie wird auf Ping-Ebene erstellt und ist konditioniert, dass cs-uri-query(a) mit "1"übereinstimmt. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Komponenten im Fehler</b> </td> 
   <td colname="col2"> cs-uri-query(ao) wird durch das Trennzeichen "|"aufgeteilt und in das Feld x-components-in-error kopiert. Viele bis viele Dimensionen wurden aus dem Fehlerfeld x-components-in-error erstellt. Erstellt auf Ping-Ebene. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Detaillierte Prüfung in Sekunden</b> </td> 
   <td colname="col2"> Numerische Dimension basierend auf dem Wert cs-uri-query(l) . Es wird auf Ping-Ebene erstellt, sofern cs-uri-query(k) nicht leer ist. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Detaillierte Prüfung erfolgreich</b> </td> 
   <td colname="col2"> Einfache Dimension, die aus dem Wert cs-uri-query(k) erstellt wurde. Es wird auf der Ping-Ebene erstellt, sofern cs-uri-query(a) mit "1"übereinstimmt. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Dimension GigaBytes</b> </td> 
   <td colname="col2"> cs-uri-query(bc) wird in das Feld x-dimension-Gigabytes kopiert. Das Feld x-dimension-Gigabytes ist Benutzer für diese einfache Dimension, abhängig von cs-uri-query(a), die mit "2"übereinstimmt. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Verwendeter Festplattenprozentsatz "x"</b> </td> 
   <td colname="col2"> Diese numerischen Dimensionen werden über die Werte cs-uri-query(ah, ai, aj, ak, all) konfiguriert. Sie werden auf der Ping-Ebene erstellt und davon abhängig gemacht, dass cs-uri-query(a) mit "1"übereinstimmt und cs-uri-query(k) nicht leer ist. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Geschätzte Sweep-Dekaseconds</b> </td> 
   <td colname="col2"> Das Feld x-estimated-sweep-dekaseconds wird in dieser numerischen Dimension verwendet. Dies ist die geschätzte Sweep-Zeit der Server geteilt durch zehn (reduzierte Auflösung der Sweep-Messung, um die Größe der Dimension zu vergrößern). <p>Hinweis: Diese Dimension ist ausgeblendet, da sie nur nützlich ist, wenn sie in einer Metrik im Durchschnitt dargestellt wird. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Schneller Input MegaBytes pro Minute</b> </td> 
   <td colname="col2"> Für diese Dimension wird der Wert cs-uri-query(bj) verwendet. Die letzte Zeile eines Blocks wird als Wert für die Dimension verwendet. Wenn der Datensatz in Schnelle Eingabe enthalten ist, zeigt der Wert dieser numerischen Dimension die MB pro Minute an, in die das System Daten eingibt. <p>Hinweis: Diese Dimension ist ausgeblendet, da sie nur nützlich ist, wenn sie in einer Metrik im Durchschnitt dargestellt wird. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Schnelles Zusammenführen von MegaBytes pro Minute</b> </td> 
   <td colname="col2">Für diese Dimension wird der Wert cs-uri-query(bk) verwendet. Die letzte Zeile für einen Block wird als Wert für die Dimension verwendet. Wenn sich der Datensatz in Schneller Zusammenführung befindet, zeigt dieser numerische Dimension-Wert die MB pro Minute an, in der das System zusammengeführt wird. <p><p>Hinweis: Diese Dimension ist ausgeblendet, da sie nur nützlich ist, wenn sie in einer Metrik im Durchschnitt dargestellt wird. </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Field GigaBytes</b> </td> 
   <td colname="col2">Für diese Dimension wird der Wert cs-uri-query(bg) verwendet. Der Wert wird durch 1000 geteilt und auf die nächste Ganzzahl gerundet. Der Wert dieser numerischen Dimension zeigt den Speicherplatz an, den die Felder im Datensatz verwenden. <p>Hinweis: Diese Dimension ist ausgeblendet, da sie nur nützlich ist, wenn sie in einer Metrik im Durchschnitt dargestellt wird. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Gruppe</b> </td> 
   <td colname="col2"> Einfache Dimension, die auf Ping-Ebene aus dem Wert cs-uri-query(x) erstellt wird. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Host</b> </td> 
   <td colname="col2"> Für diese Dimension wird der Wert cs-uri-query(b) verwendet. Der Wert der Dimension "Einfach"ist die letzte Zeile eines Blocks. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Letztes Ping</b> </td> 
   <td colname="col2"> das Feld x-unixtime wird in x-last-ping kopiert und durch 10 geteilt, um die Kardinalität zu reduzieren. Die numerische Dimension wird auf Blockebene erstellt und verwendet das X-Last-Ping-Feld. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Durchschnitt laden</b> </td> 
   <td colname="col2"> Dies ist eine numerische Dimension, die die letzte Zeile für den cs-uri-query(i) -Wert eines bestimmten Servers verwendet. Dies ist davon abhängig, dass cs-uri-query(k) nicht leer ist. Diese Dimension wird verwendet, um die durchschnittliche Auslastung der Server im überwachten System zu berechnen. <p><p>Hinweis: Diese Dimension ist ausgeblendet, da sie nur nützlich ist, wenn sie in einer Metrik im Durchschnitt dargestellt wird. </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Prozentsatz der Protokolllesung</b> </td> 
   <td colname="col2">der Wert cs-uri-query(be) wird für diese numerische Dimension verwendet, die auf Ping-Ebene erstellt wird. Diese Dimension wird verwendet, um den Prozentsatz der zu lesenden Protokolle zu berechnen. <p>Hinweis: Diese Dimension ist ausgeblendet, da sie nur nützlich ist, wenn sie in einer Metrik im Durchschnitt dargestellt wird. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Dateiprozentsatz der Speicherseite</b> </td> 
   <td colname="col2"> Dies ist eine numerische Dimension, die mithilfe des Werts cs-uri-query(o) auf Ping-Ebene erstellt wird. Dies ist davon abhängig, dass cs-uri-query(k) nicht leer ist und cs-uri-query(a) mit "1" übereinstimmt. Diese Dimension wird verwendet, um den Prozentsatz der Speichernutzung der Seitendatei zu berechnen. <p>Hinweis: Diese Dimension ist ausgeblendet, da sie nur nützlich ist, wenn sie in einer Metrik im Durchschnitt dargestellt wird. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Physikalische MegaBytes insgesamt</b> </td> 
   <td colname="col2">Dies ist eine numerische Dimension mit dem Wert cs-uri-query(ag) , der auf Ping-Ebene erstellt wurde. Dies ist davon abhängig, dass cs-uri-query(k) nicht leer ist und cs-uri-query(a) mit "1. <p>Hinweis: Diese Dimension ist ausgeblendet, da sie nur nützlich ist, wenn sie in einer Metrik im Durchschnitt dargestellt wird. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Physikalischer Speicherprozentsatz</b> </td> 
   <td colname="col2">Dies ist eine numerische Dimension mit dem Wert cs-uri-query(ag) , der auf Ping-Ebene erstellt wurde. Dies ist davon abhängig, dass cs-uri-query(k) nicht leer ist und cs-uri-query(a) mit "1. Diese Dimension wird verwendet, um den Prozentsatz der Speichernutzung jedes Servers zu berechnen. <p>Hinweis: Diese Dimension ist ausgeblendet, da sie nur nützlich ist, wenn sie in einer Metrik im Durchschnitt dargestellt wird. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Prozentsatz der Speicherabfrage</b> </td> 
   <td colname="col2"> Dies ist eine numerische Dimension, die den Wert der cs-uri-Abfrage(en) auf Ping-Ebene verwendet. Dies ist davon abhängig, dass cs-uri-query(k) nicht leer ist und cs-uri-query(a) mit "1. Diese Dimension wird verwendet, um den Prozentsatz der Speichernutzung der Abfrage für jeden Server zu berechnen. <p>Hinweis: Diese Dimension ist ausgeblendet, da sie nur nützlich ist, wenn sie in einer Metrik im Durchschnitt dargestellt wird. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Netzwerkverbindungen</b> </td> 
   <td colname="col2"> Dies ist eine numerische Dimension, die den auf Ping-Ebene erstellten cs-uri-query(q) -Wert verwendet. Dies ist davon abhängig, dass cs-uri-query(k) nicht leer ist und cs-uri-query(a) mit "1. Damit wird die Anzahl der Netzwerkverbindungen angezeigt, die für einen bestimmten Server vorhanden sind. <p>Hinweis: Diese Dimension ist ausgeblendet, da sie nur nützlich ist, wenn sie in einer Metrik im Durchschnitt dargestellt wird. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Ausgabezeilen</b> </td> 
   <td colname="col2"> cs-uri-query(bh) wird durch 100000 dividiert und in das Feld x-output-rows kopiert, um die Größe der Dimension zu reduzieren. X-Ausgabe-Zeilen werden in einer numerischen Dimension verwendet, die auf Ping-Ebene erstellt wird, vorausgesetzt, dass cs-uri-query(a) mit "2"übereinstimmt. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Ping Type ID</b> </td> 
   <td colname="col2"> Einfache Dimension, die mit dem Wert cs-uri-query(a) auf Ping-Ebene erstellt wurde. Dies zeigt, welche Art von Ping aufgezeichnet wurde. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Umfragelatenz in Sekunden</b> </td> 
   <td colname="col2">Der Wert cs-uri-query(m) wird durch 10 dividiert, um die Dimensionsgröße zu reduzieren, und in das Feld x-poll-latency-centiseconds kopiert. Dies ist eine numerische Dimension, die auf Ping-Ebene erstellt wird, sofern cs-uri-query(k) nicht leer ist und cs-uri-query(a) mit "1"übereinstimmt. Diese Dimension wird verwendet, um die Abfragelatenz zu berechnen. <p>Hinweis: Diese Dimension ist ausgeblendet, da sie nur nützlich ist, wenn sie in einer Metrik im Durchschnitt dargestellt wird. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Verarbeitungsmodus-ID</b> </td> 
   <td colname="col2"> Der Wert cs-uri-query(bb) wird für diese einfache Dimension verwendet, die auf Ping-Ebene erstellt wurde. Es ist davon abhängig, dass cs-uri-query(bb) nicht leer ist und dass cs-uri-query(a) mit "2" Verarbeitungsmodus-ID übereinstimmt, um zu sehen, in welchem Verarbeitungsmodus sich das System befindet (schnelle Eingabe, schnelle Zusammenführung, Echtzeit). <p>Hinweis: Diese Dimension wird ausgeblendet und dann im clientseitigen Dimensionsverarbeitungsmodus erneut mit benutzerfreundlichen Werten offen gelegt. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Profil</b> </td> 
   <td colname="col2"> Der Wert cs-uri-query(ba) wird für diese einfache Dimension verwendet und auf Ping-Ebene erstellt. Diese Dimension zeigt die Namen der Profile an, die derzeit überwacht werden. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Schnellprüfung in Sekunden</b> </td> 
   <td colname="col2"> Der Wert cs-uri-query(h) wird für diese numerische Dimension verwendet. Es wird auf der Ping-Ebene erstellt, sofern cs-uri-query(a) mit "1"übereinstimmt. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Schnellprüfungserfolg</b> </td> 
   <td colname="col2"> Dies ist eine einfache Dimension, die aus dem auf Ping-Ebene erstellten cs-uri-query(g) -Wert erstellt wurde. Sie wird zur Berechnung der Schnellprüfungsmetrik verwendet. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Prozentsatz für die Echtzeitverarbeitung</b> </td> 
   <td colname="col2"> Numerische Dimension mit dem Wert cs-uri-query(t) , der auf Ping-Ebene erstellt wurde. Es ist davon abhängig, dass cs-uri-query(a) mit "1"übereinstimmt. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Quelle am weitesten hinten</b> </td> 
   <td colname="col2"> Einfache Dimension, die aus dem auf Ping-Ebene erstellten cs-uri-query(bl)-Wert erstellt wurde. Diese Dimension zeigt den Zeitpunkt des letzten Kontakts mit einer Datenquelle an. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Temp DB Space Prozentwert</b> </td> 
   <td colname="col2">Numerische Dimension, die mit dem Wert cs-uri-query(an) erstellt wurde und auf Ping-Ebene erstellt wurde. Es wird davon ausgegangen, dass cs-uri-query(k) nicht leer ist und cs-uri-query(a) mit "1"übereinstimmt. Sie wird verwendet, um den Prozentsatz des verwendeten Temp DB-Speicherplatzes auf einem bestimmten Server zu berechnen. <p>Hinweis: Diese Dimension ist ausgeblendet, da sie nur nützlich ist, wenn sie in einer Metrik im Durchschnitt dargestellt wird. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Prozentsatz der Umwandlungen</b> </td> 
   <td colname="col2">wird der Wert cs-uri-query(bf) für diese numerische Dimension verwendet. Er wird auf Ping-Ebene erstellt. Diese Dimension wird verwendet, um den Prozentsatz der vollständigen Datenumwandlung zu berechnen. <p><p>Hinweis: Diese Dimension ist ausgeblendet, da sie nur nützlich ist, wenn sie in einer Metrik im Durchschnitt dargestellt wird. </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Data Workbench Version</b> </td> 
   <td colname="col2"> Der Wert cs-uri-query(ab) wird für diese einfache Dimension verwendet. Es wird auf Ping-Ebene erstellt und unter der Bedingung erstellt, dass cs-uri-query(ab) nicht leer ist und cs-uri-query(a) mit "1"übereinstimmt. Dadurch werden die auf den einzelnen Servern ausgeführten Versionen des Data Workbench-Servers angezeigt. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Data Workbench Version Major</b> </td> 
   <td colname="col2"> Der Wert cs-uri-query(ab) wird aufgeteilt und der Hauptveröffentlichungswert wird in das Feld x-insight-version-major kopiert. Es handelt sich dabei um eine einfache Dimension, die auf Ping-Ebene erstellt wurde und davon abhängig ist, dass x-insight-version-major nicht leer ist und cs-uri-query(a) mit "1"übereinstimmt. </td> 
  </tr> 
 </tbody> 
</table>

<!-- <a id="section_76D8A4B07BB947558EBED1123EA203D5"></a> -->
