---
description: In diesem Abschnitt wird das Erstellen von Zeitstempeln für einen Data Workbench-Datensatz beschrieben.
title: Einrichten der Ereigniszeit
uuid: 0230154d-05a2-44cf-9456-0a27e55f58ef
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Einrichten der Ereigniszeit{#setting-up-event-time}

In diesem Abschnitt wird das Erstellen von Zeitstempeln für einen Data Workbench-Datensatz beschrieben.

## Die Ereigniszeit {#section-e10ef2b5b6244dc5b215836e3c77d663}

Die Ereigniszeit ist das Datum und die Uhrzeit, zu der die Anforderung (oder das Ereignis) eintritt.

Normalerweise wird für Online-Daten *x_hit_time_gmt* als Zeitstempelfeld verwendet. Die Uhrzeit des Aufrufs kann als Zeitstempel für Offlinedaten (z. B. Call-Center-Daten) verwendet werden. Dieses Feld ist ein Pflichtfeld und alle Datenquellen sollten ein Feld enthalten, das als Zeitstempel verwendet werden kann. Diese Informationen sollten von Ihrer Organisation bereitgestellt werden.

In DWB erfassen die folgenden vordefinierten Variablen den Zeitstempel:

<table id="table_C24BD56CEB4E42F68D645EBB65585D16"> 
 <tbody> 
  <tr> 
   <td colname="col1"><i>x-timestamp</i> </td> 
   <td colname="col2"> <p> Datum und Uhrzeit (GMT), zu der die Anforderung beim Server einging. Die Zeit wird als die Anzahl von 100 Nanosekunden seit dem 1. Januar 1600 ausgedrückt. </p> <p>Beispiel: 127710989320000000 wäre der <i>x-timestamp</i> -Wert für 11:28:52.00000000 am Dienstag, 13. September 2005. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><i>x-timestring</i> </td> 
   <td colname="col2"> <i>x-timestamp</i> im Format JJJJJ-MM-TT HH:MM:SS.mmm. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><i>x-unixtime</i> </td> 
   <td colname="col2"> <i>x-unixtime</i> ist die Epoche, die die Anzahl der Sekunden seit dem 1. Januar 1970 um 00:00:01 darstellt. </td> 
  </tr> 
 </tbody> 
</table>

Basierend auf dem Format des Datumsfelds wird x-timestamp oder x-unixtime oder x-timestring verwendet. Wenn die eingehenden Daten beispielsweise das Format JJJJ-MM-TT haben, ist eine x-timestring-Zeichenfolge zu verwenden.

Der Zeitstempel wird in einem der Formate definiert und DWB generiert intern die anderen beiden Formate. Außerdem handelt es sich hierbei um vordefinierte DWB-Felder, und der gleiche Name sollte nicht für andere Felder verwendet werden.

## In DWB definierte Zeitzonen {#section-3cdd12254342442b917376661e1d9c9f}

Wenn das Datumsfeld eine der unten genannten Zeitzonen enthält, berücksichtigt DWB die gesamte Zeile in dieser bestimmten Zeitzone. Beispiel: Eine Datei hat das Datum definiert als 2015-01-01 00:00:00 gmtt und eine andere Datei hat den Wert 2015-01-01 00:00:00 cst, dann wird das Datum der ersten Datei in GMT-Zeitzone berücksichtigt, während das Datum der zweiten Datei in CST-Zeitzone.

| Code | Zeitzone |
|---|---|
| gmt | Greenwich-Mittel |
| est | Eastern Standard |
| edt | Eastern Daylight |
| cst | Central Standard |
| cdt | Central Daylight |
| mst | Gebirgsstandard |
| mdt | Mountain Daylight |
| pst | Pacific Standard |
| pdt | Pacific Daylight |

>[!NOTE]
>
>DWB verarbeitet nur die oben genannten Zeitzonen.

## Festlegen benutzerdefinierter Zeitzonen {#section-7c351921f22b439b81c73f40d5b47536}

DWB verarbeitet den Offset in der Zeitzone nicht. Um den Offset in der Zeitzone zu berücksichtigen, sollten die Daten in dieser Zeitzone formatiert werden.

Beispiel: Um das Datumsformat in der CST-Zeitzone zu berücksichtigen, sollten die Daten im Format JJJJ-MM-TT HH:MM:SS UTC +/-HHMM vom Client stammen.

2015-10-18 05:00:00 UTC -0200

## Festlegen der Ereigniszeit/des Zeitstempels {#section-81507080f0b44ae6b83d3650ba019812}

Basierend auf dem Datumsfeldformat wird die Variable *x-timestamp, x-unixtime* oder *x-timestring* verwendet. Im folgenden Beispiel wird, da *x-hit_time_gmt* im Unix Epoc-Format vorliegt, *x-unixtime* verwendet.

Verwenden Sie in der DWB- [!DNL foundation.cfg] Datei (oder einer anderen Konfigurationsdatei im Ordner für die Verarbeitung des Datensatzprotokolls) die Kopiertransformation, um die Ereigniszeit wie folgt festzulegen:

Basierend auf dem Datumsfeldformat wird die Variable &quot;x-timestamp&quot;, &quot;x-unixtime&quot;oder &quot;x-timestring&quot;verwendet. Im folgenden Beispiel wird x-unixtime verwendet, da x-hit_time_gmt im Unix Epoc-Format vorliegt.

Verwenden Sie in der Datei &quot;insight foundation.cfg&quot;(oder einer anderen Konfiguration unter &quot;Datasetà log processing&quot;) die Option &quot;Copy transform&quot;, um die Ereigniszeit wie unten gezeigt festzulegen: ![](assets/dwb_impl_timestamp1.png)

Ist das Datum im Format JJJJ-MM-TT HH:MM:SS.mmm angegeben, wird eine x-timestring-Zeichenfolge verwendet. ![](assets/dwb_impl_timestamp2.png)Beispiel: Wenn das Datumsfeld in einem anderen als dem in DWB definierten Format wie JJJJ/MM/TT vorliegt, formatieren Sie es zunächst in einem vom DWB akzeptierten Zeitstempelformat und weisen Sie es dann der entsprechenden Variablen zu. Im folgenden Screenshot wird das Datum zunächst in das Format JJJJ-MM-TT konvertiert und dann *x-timestring *der Variablen zugewiesen. ![](assets/dwb_impl_timestamp3.png)

