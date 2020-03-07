---
description: Die folgenden Dimensionen sind im Historic-Profil der Data Workbench verfügbar.
solution: Analytics
title: Dimensionen im historischen Profil von Data Workbench
topic: Data workbench
uuid: 6d93fba4-986b-46a4-9479-aeb54853dff5
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Dimensionen im historischen Profil von Data Workbench{#dimensions-in-the-data-workbench-historic-profile}

Die folgenden Dimensionen sind im Historic-Profil der Data Workbench verfügbar.

## Dimensionen im historischen Profil von Data Workbench {#section-96f1b64f5cb84411b630f97f227d888d}

Die folgenden Dimensionen sind im Historic-Profil der Data Workbench verfügbar.

<table id="table_3EAEA68E73BE431D841F7F2E83EDD6AC"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Block</b> </td> 
   <td colname="col2">Dies ist die einzige zählbare Konfiguration in dieser Konfiguration, es ist die Wurzel für alle Dimensionen. Ein Block kann als Server betrachtet werden. Es verwendet das x-trackingid-Feld. <p>Hinweis:  Die Block-ID ist ein Hash des Servernamens und des Hostnamens, sodass pro Server-Profil etwa ein Block vorhanden ist. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Ping</b> </td> 
   <td colname="col2"> Dies ist eine zählbare Dimension, die aus der Zählung "Block"erstellt wurde. Jede Datenzeile im Profil ist ein Ping vom Überwachungsagenten. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Warnungskritisch</b> </td> 
   <td colname="col2"> Numerische Dimension, die aus dem Wert cs-uri-query(ad) erstellt wurde. Es wird auf Ping-Ebene erstellt, vorausgesetzt, dass cs-uri-query(a) mit "1"übereinstimmt. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Warnung nach unten</b> </td> 
   <td colname="col2"> Numerische Dimension basierend auf dem Wert cs-uri-query(ac). Es wird auf Ping-Ebene erstellt, vorausgesetzt, dass cs-uri-query(a) mit "1"übereinstimmt. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Warnung</b> </td> 
   <td colname="col2"> Numerische Dimension basierend auf dem Wert cs-uri-query(ae). Es wird auf Ping-Ebene erstellt, vorausgesetzt, dass cs-uri-query(a) mit "1"übereinstimmt. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Beliebige Profilwiederverarbeitung</b> </td> 
   <td colname="col2"> Numerische Dimension basierend auf dem Wert cs-uri-query(aa). Es wird auf Ping-Ebene erstellt, vorausgesetzt, dass cs-uri-query(a) mit "1"übereinstimmt und cs-uriquery(k) nicht leer ist. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Ab Verzögerung Minuten</b> </td> 
   <td colname="col2"> cs-uri-query(bi) wird in das Feld x-as-of-delay-minuten platziert und auf die nächste Minute gerundet. Es wird auf Ping-Ebene erstellt, vorausgesetzt, dass cs-uri-query(a) mit "1"übereinstimmt. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Prozentsatz der Kapazitätenzeile</b> </td> 
   <td colname="col2"> Numerische Dimension basierend auf dem Wert cs-uri-query(r). Es wird auf Ping-Ebene erstellt, vorausgesetzt, dass cs-uri-query(a) mit "1"übereinstimmt und cs-uriquery(k) nicht leer ist. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Kapazitätsgrößenprozentsatz</b> </td> 
   <td colname="col2"> Numerische Dimension basierend auf dem Wert cs-uri-query(n). Es wird auf Ping-Ebene erstellt, vorausgesetzt, dass cs-uri-query(a) mit "1"übereinstimmt und cs-uriquery(k) nicht leer ist. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Komponentenprüfung erfolgreich</b> </td> 
   <td colname="col2"> Einfache Dimension erstellt aus dem Wert cs-uri-query(v). Es wird auf Ping-Ebene erstellt und konditioniert, dass cs-uri-query(a) mit "1"übereinstimmt. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Komponenten im Fehler</b> </td> 
   <td colname="col2"> cs-uri-query(ao) wird durch das Trennzeichen "|"getrennt und in das Feld x-components-in-error kopiert. Viele bis Viele Dimensionen, die aus dem Fehlerfeld x-components-in-error erstellt wurden. Baut auf Ping-Ebene. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Detaillierte Prüfung in Sekunden</b> </td> 
   <td colname="col2"> Numerische Dimension basierend auf dem Wert cs-uri-query(l). Es wird auf Ping-Ebene erstellt, vorausgesetzt, dass cs-uri-query(k) nicht leer ist. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Detaillierter Prüferfolg</b> </td> 
   <td colname="col2"> Einfache Dimension erstellt aus dem Wert cs-uri-query(k). Es wird auf Ping-Ebene erstellt, vorausgesetzt, dass cs-uri-query(a) mit "1"übereinstimmt. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Dimension GigaBytes</b> </td> 
   <td colname="col2"> cs-uri-query(bc) wird in das Feld x-dimension-Gigabytes kopiert. Das Feld x-dimension-Gigabytes ist Benutzer für diese einfache Dimension, bedingt durch cs-uri-query(a) passend zu "2". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Verwendeter Festplattenprozentsatz "x"</b> </td> 
   <td colname="col2"> Diese numerischen Dimensionen werden aus den Werten "cs-uri-query(ah, ai, aj, ak, al)"konfiguriert. Sie werden auf Ping-Ebene erstellt und auf cs-uri-query(a) stimmt mit "1"überein und cs-uri-query(k) ist nicht leer. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Geschätzte Sweep-Dekaseconds</b> </td> 
   <td colname="col2"> In dieser numerischen Dimension wird das Feld x-schätzung-sweep-dekaseconds verwendet. Dies ist die geschätzte Sweep-Zeit der Server geteilt durch zehn (reduzierte Auflösung der Sweep-Messung, um die Größe zu vergrößern). <p>Hinweis:  Diese Dimension wird ausgeblendet, da sie nur dann nützlich ist, wenn sie in einer Metrik gemittelt wird. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Schnelle Eingabe MegaBytes pro Minute</b> </td> 
   <td colname="col2"> Für diese Dimension wird der Wert "cs-uri-query(bj)"verwendet. Die letzte Zeile für einen Block wird als Wert für die Dimension verwendet. Wenn sich der Datensatz in "Schnelle Eingabe"befindet, zeigt dieser Wert der numerischen Dimension die MB pro Minute an, in der das System Daten eingibt. <p>Hinweis:  Diese Dimension wird ausgeblendet, da sie nur dann nützlich ist, wenn sie in einer Metrik gemittelt wird. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Schnelles Zusammenführen von MegaBytes pro Minute</b> </td> 
   <td colname="col2">Für diese Dimension wird der Wert "cs-uri-query(bk)"verwendet. Die letzte Zeile für einen Block wird als Wert für die Dimension verwendet. Wenn sich der Datensatz in "Schnelle Zusammenführung"befindet, zeigt dieser Wert der numerischen Dimension die MB pro Minute an, in der das System zusammengeführt wird. <p><p>Hinweis:  Diese Dimension wird ausgeblendet, da sie nur dann nützlich ist, wenn sie in einer Metrik gemittelt wird. </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Feld GigaBytes</b> </td> 
   <td colname="col2">Für diese Dimension wird der Wert cs-uri-query(bg) verwendet. Der Wert wird durch 1000 dividiert und auf die nächste ganze Zahl gerundet. Der Wert dieser numerischen Dimension zeigt den Platz an, den die Felder im Datensatz verwenden. <p>Hinweis:  Diese Dimension wird ausgeblendet, da sie nur dann nützlich ist, wenn sie in einer Metrik gemittelt wird. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Gruppe</b> </td> 
   <td colname="col2"> Einfache Dimension, die auf Ping-Ebene aus dem Wert cs-uri-query(x) erstellt wurde. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Host</b> </td> 
   <td colname="col2"> Für diese Dimension wird der Wert cs-uri-query(b) verwendet. Der Wert der Dimension "Einfach"ist die letzte Zeile für einen Block. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Letztes Ping</b> </td> 
   <td colname="col2"> Das x-unixtime-Feld wird in x-last-ping kopiert und durch 10 dividiert, um die Kardinalität zu reduzieren. Die numerische Dimension wird auf Blockebene erstellt und verwendet das Feld "x-last-ping". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Lastendurchschnitt</b> </td> 
   <td colname="col2"> Hierbei handelt es sich um eine numerische Dimension, bei der die letzte Zeile für den cs-uri-query(i)-Wert eines bestimmten Servers verwendet wird. Es ist davon abhängig, dass cs-uri-query(k) nicht leer ist. Diese Dimension wird verwendet, um die durchschnittliche Belastung der Server im überwachten System zu berechnen. <p><p>Hinweis:  Diese Dimension wird ausgeblendet, da sie nur dann nützlich ist, wenn sie in einer Metrik gemittelt wird. </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Prozentsatz der Protokolllesung</b> </td> 
   <td colname="col2">der Wert cs-uri-query(be) wird für diese numerische Dimension verwendet, die auf Ping-Ebene erstellt wurde. Diese Dimension wird verwendet, um den Prozentsatz der zu lesenden Protokolle zu berechnen. <p>Hinweis:  Diese Dimension wird ausgeblendet, da sie nur dann nützlich ist, wenn sie in einer Metrik gemittelt wird. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Dateiprozentsatz der Speicherseite</b> </td> 
   <td colname="col2"> Dies ist eine numerische Dimension mit dem Wert cs-uri-query(o), der auf Ping-Ebene erstellt wurde. Es ist davon abhängig, dass cs-uri-query(k) nicht leer und cs-uri-query(a) mit "1"übereinstimmen. Diese Dimension wird verwendet, um den Prozentsatz der Speicherbelegung der Seitendatei zu berechnen. <p>Hinweis:  Diese Dimension wird ausgeblendet, da sie nur dann nützlich ist, wenn sie in einer Metrik gemittelt wird. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Physikalische MegaBytes insgesamt</b> </td> 
   <td colname="col2">Dies ist eine numerische Dimension mit dem Wert cs-uri-query(ag), der auf Ping-Ebene erstellt wurde. Es ist davon abhängig, dass cs-uri-query(k) nicht leer ist und cs-uri-query(a) mit "1"übereinstimmen. <p>Hinweis:  Diese Dimension wird ausgeblendet, da sie nur dann nützlich ist, wenn sie in einer Metrik gemittelt wird. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Physikalischer Speicherprozentsatz</b> </td> 
   <td colname="col2">Dies ist eine numerische Dimension mit dem Wert cs-uri-query(ag), der auf Ping-Ebene erstellt wurde. Es ist davon abhängig, dass cs-uri-query(k) nicht leer ist und cs-uri-query(a) mit "1"übereinstimmen. Diese Dimension wird verwendet, um den Prozentsatz der physischen Speicherbelegung jedes Servers zu berechnen. <p>Hinweis:  Diese Dimension wird ausgeblendet, da sie nur dann nützlich ist, wenn sie in einer Metrik gemittelt wird. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Speicherabfrageprozentsatz</b> </td> 
   <td colname="col2"> Hierbei handelt es sich um eine numerische Dimension mit dem Wert cs-uri-query(s) auf Ping-Ebene. Es ist davon abhängig, dass cs-uri-query(k) nicht leer ist und cs-uri-query(a) mit "1 übereinstimmen. Diese Dimension wird verwendet, um den Prozentsatz der Speichernutzung der Abfrage auf jedem Server zu berechnen. <p>Hinweis:  Diese Dimension wird ausgeblendet, da sie nur dann nützlich ist, wenn sie in einer Metrik gemittelt wird. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Netzwerkverbindungen</b> </td> 
   <td colname="col2"> Dies ist eine numerische Dimension mit dem Wert cs-uri-query(q), der auf Ping-Ebene erstellt wurde. Es ist davon abhängig, dass cs-uri-query(k) nicht leer ist und cs-uri-query(a) mit "1 übereinstimmen. Dies wird verwendet, um die Anzahl der Netzwerkverbindungen anzuzeigen, die für einen bestimmten Server vorhanden sind. <p>Hinweis:  Diese Dimension wird ausgeblendet, da sie nur dann nützlich ist, wenn sie in einer Metrik gemittelt wird. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Ausgabezeilen</b> </td> 
   <td colname="col2"> cs-uri-query(bh) Wert wird durch 100000 geteilt und in das Feld x-output-rows kopiert, um die Größe der Dimension zu reduzieren. X-Output-Zeilen werden in einer numerischen Dimension verwendet, die auf Ping-Ebene erstellt wurde, vorausgesetzt, dass cs-uri-query(a) mit "2"übereinstimmt. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Ping-Typ-ID</b> </td> 
   <td colname="col2"> Einfache Dimension erstellt mit dem Wert cs-uri-query(a) auf Ping-Ebene. Dies zeigt, was für eine Art Ping aufgezeichnet wurde. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Wartezeit bei Umfragen in Sekunden</b> </td> 
   <td colname="col2">Der Wert "cs-uri-query(m)"wird durch 10 dividiert, um die Dimensionsgröße zu reduzieren, und in das Feld "x-poll-latency-centiseconds"kopiert. Dies ist eine numerische Dimension, die auf Ping-Ebene erstellt wurde, vorausgesetzt, dass cs-uri-query(k) nicht leer ist und cs-uri-query(a) mit "1"übereinstimmt. Diese Dimension wird zur Berechnung der Abruflatenz verwendet. <p>Hinweis:  Diese Dimension wird ausgeblendet, da sie nur dann nützlich ist, wenn sie in einer Metrik gemittelt wird. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Verarbeitungsmodus-ID</b> </td> 
   <td colname="col2"> Der Wert cs-uri-query(bb) wird für diese einfache Dimension verwendet, die auf Ping-Ebene erstellt wurde. Es ist davon abhängig, dass cs-uri-query(bb) nicht leer ist und dass cs-uri-query(a) mit "2"-Verarbeitungs-Modus-ID übereinstimmt, kann man sehen, in welchem Modus das System verarbeitet wird (schnelle Eingabe, schnelle Zusammenführung, Echtzeit). <p>Hinweis:  Diese Dimension wird ausgeblendet und dann mit benutzerfreundlichen Werten im clientseitigen Dimensionsverarbeitungsmodus erneut offen gelegt. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Profil</b> </td> 
   <td colname="col2"> Der Wert cs-uri-query(ba) wird für diese einfache Dimension verwendet, er wird auf Ping-Ebene erstellt. Diese Dimension zeigt die Namen der Profile an, die derzeit überwacht werden. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Schnellprüfung in Sekunden</b> </td> 
   <td colname="col2"> Der Wert cs-uri-query(h) wird für diese numerische Dimension verwendet. Es wird auf Ping-Ebene erstellt, vorausgesetzt, dass cs-uri-query(a) mit "1"übereinstimmt. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Schnelle Prüfung erfolgreich</b> </td> 
   <td colname="col2"> Dies ist eine einfache Dimension, die aus dem Wert cs-uri-query(g) auf Ping-Ebene erstellt wurde. Sie wird zur Berechnung der Schnellprüfungsmetrik verwendet. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Echtzeitverarbeitungsprozentsatz</b> </td> 
   <td colname="col2"> Numerische Dimension unter Verwendung des Werts cs-uri-query(t), der auf Ping-Ebene erstellt wurde. Es ist davon abhängig, dass cs-uri-query(a) mit "1"übereinstimmt. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Quelle am weitesten hinten</b> </td> 
   <td colname="col2"> Einfache Dimension erstellt aus dem auf Ping-Ebene erstellten Wert cs-uri-query(bl). Diese Dimension zeigt an, wann der letzte Kontakt mit einer Datenquelle aufgetreten ist. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Temp DB Space Prozentwert</b> </td> 
   <td colname="col2">Numerische Dimension, die mithilfe des Werts cs-uri-query(an) erstellt wurde, der auf Ping-Ebene erstellt wurde. Es wird vorausgesetzt, dass cs-uri-query(k) nicht leer ist und cs-uri-query(a) mit "1"übereinstimmt. Es wird zur Berechnung des Prozentsatzes des verwendeten Temp DB-Speichers auf einem bestimmten Server verwendet. <p>Hinweis:  Diese Dimension wird ausgeblendet, da sie nur dann nützlich ist, wenn sie in einer Metrik gemittelt wird. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Transformationsprozentsatz</b> </td> 
   <td colname="col2">der Wert cs-uri-query(bf) für diese numerische Dimension verwendet wird. Es ist auf der Ping-Ebene gebaut. Diese Dimension wird zur Berechnung des Prozentsatzes der vollständigen Datenumwandlung verwendet. <p><p>Hinweis:  Diese Dimension wird ausgeblendet, da sie nur dann nützlich ist, wenn sie in einer Metrik gemittelt wird. </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Data Workbench-Version</b> </td> 
   <td colname="col2"> Für diese einfache Dimension wird der Wert cs-uri-query(ab) verwendet. Es wird auf Ping-Ebene erstellt und konditioniert, dass cs-uri-query(ab) nicht leer ist und cs-uri-query(a) mit "1"übereinstimmt. Dies zeigt die Version(en) des Data Workbench-Servers an, der auf jedem Server ausgeführt wird. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Data Workbench Version Major</b> </td> 
   <td colname="col2"> Der Wert cs-uri-query(ab) wird aufgeteilt und der Hauptveröffentlichungswert wird in das Feld x-insight-version-major kopiert. Es handelt sich dabei um eine einfache Dimension, die auf Ping-Ebene erstellt wurde und bedingt ist, dass x-insight-version-major nicht leer ist und cs-uri-query(a) mit "1"übereinstimmt. </td> 
  </tr> 
 </tbody> 
</table>

<!-- <a id="section_76D8A4B07BB947558EBED1123EA203D5"></a> -->

