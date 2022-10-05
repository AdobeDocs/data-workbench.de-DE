---
description: Der Data Workbench-Server (InsightServer64.exe) kann Ereignisdaten aus jeder SQL-Datenbank lesen (z. B. Oracle oder Microsoft SQL Server), die über einen ODBC-3.0-kompatiblen Treiber verfügt.
title: ODBC-Datenquellen
uuid: 5b37cd41-2d79-472c-8e6d-00ff894991a9
exl-id: b22b1e27-9b6c-4708-b45c-a9605807689a
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1245'
ht-degree: 1%

---

# ODBC-Datenquellen{#odbc-data-sources}

{{eol}}

Der Data Workbench-Server (InsightServer64.exe) kann Ereignisdaten aus jeder SQL-Datenbank lesen (z. B. Oracle oder Microsoft SQL Server), die über einen ODBC-3.0-kompatiblen Treiber verfügt.

Die ODBC-Unterstützung des Data Workbench-Servers ähnelt der vorhandenen Unterstützung für das Laden von Daten von Sensoren oder von Protokolldateien, die von externen Prozessen generiert wurden. Es gibt jedoch einige zusätzliche Aspekte und Einschränkungen:

* Die ODBC-Unterstützung des Data Workbench-Servers ist mit den Clustering-Funktionen kompatibel. Die Daten werden auf alle Verarbeitungsserver verteilt, und die anschließende Verarbeitung (einschließlich der Abfrageverarbeitung) profitiert vollständig vom Clustering.
* Die ODBC-Unterstützung hängt von ODBC-Treibern von Drittanbietern ab. Damit die ODBC-Unterstützung funktioniert, müssen diese Treiber auf dem Computer konfiguriert werden, auf dem der Data Workbench-Server ausgeführt wird. Dazu müssen Tools verwendet werden, die nicht zur Adobe-Plattform gehören. Für Data Workbench-Computer ist keine zusätzliche Konfiguration erforderlich.
* Die Tabelle oder Ansicht, aus der Daten geladen werden, muss über eine Spalte mit zunehmender ID verfügen. Für jede Zeile darf der Wert in dieser Spalte (d. h. eine tatsächliche Spalte in der Tabelle oder ein SQL-Spaltenausdruck) nicht abnehmen, da neue Zeilen in die Datenbank eingefügt werden. Wenn diese Einschränkung verletzt wird, gehen Daten verloren. Für eine angemessene Leistung ist ein Index für diesen Spalten- oder Spaltenausdruck erforderlich.

   >[!NOTE]
   >
   >Es ist möglich, dass mehrere Zeilen denselben Wert im [!DNL Increasing ID] Spalte. Eine Möglichkeit ist eine Zeitstempelspalte mit weniger als perfekter Genauigkeit.

* Der Data Workbench-Server kann keine Spalten mit langen Daten laden (Daten über eine bestimmte Länge, die von der verwendeten spezifischen Datenbankanwendung bestimmt wird).
* Das Abrufen von Daten aus einer Datenbank ist langsamer als das Lesen aus einer Festplattendatei. Datensätze, die Daten aus einer ODBC-Quelle laden, benötigen bei der Verarbeitung viel mehr Zeit (insbesondere bei der Wiederaufbereitung) als Datensätze gleicher Größe, deren Daten aus Sensoren oder anderen Festplattendateien stammen.

Informationen zur erneuten Verarbeitung Ihrer Daten finden Sie unter [Wiederaufbereitung und erneute Umwandlung](../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).

**Konfigurieren von Insight Server für ODBC[!DNL event data]**

Zum Konfigurieren des Data Workbench-Servers für das Laden von Daten aus einer SQL-Datenbank müssen Sie zunächst die folgenden Schritte in der richtigen Reihenfolge ausführen:

1. Installieren Sie die entsprechende Datenbank-Client-Software, einschließlich eines ODBC-Treibers, auf dem Data Workbench-Servercomputer, auf dem der Datensatz verarbeitet wird.

   >[!NOTE]
   >
   >Wenn Sie ODBC-Ereignisdaten zur Verarbeitung auf einem Data Workbench-Servercluster laden, müssen Sie die Datenbank-Client-Software auf allen Verarbeitungsservern im Cluster installieren. Informationen zum Festlegen von Verarbeitungsservern in einem Cluster finden Sie in der *Handbuch zur Installation und Verwaltung von Serverprodukten*.

1. Konfigurieren Sie eine Datenquelle mit dem ODBC-Datenquellenadministrator für Windows.

   Beachten Sie, dass der Data Workbench-Server (InsightServer64.exe) als Windows-Dienst ausgeführt wird. Daher muss die Datenquelle normalerweise als System-DSN und nicht als Benutzer-DSN konfiguriert werden, damit der Data Workbench-Server sie verwenden kann. Weitere Informationen zu diesem Konfigurationsschritt finden Sie in der Dokumentation für Ihre Datenbanksoftware.

Nachdem Sie die Datenbank-Client-Software auf dem entsprechenden Data Workbench-Server-Computer installiert haben, können Sie den Datensatz für die Verwendung der ODBC-Datenquelle konfigurieren, indem Sie die entsprechenden Parameter im [!DNL Log Processing] Konfigurationsdatei für das gewünschte Profil.

## Parameter {#section-15c0218d93364693a565f2609a12f73e}

Für Daten aus Datenbanken, die den ODBC-Standard (Open Database Connectivity) verwenden, stehen die folgenden Parameter zur Verfügung:

<table id="table_606D8A90DA4A43C29F2C6130F8C753F8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Name </td> 
   <td colname="col2"> Die Kennung für die ODBC-Quelle. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Datenquellenname </td> 
   <td colname="col2"> Ein DSN, das von einem Administrator des Data Workbench-Servercomputers bereitgestellt wird, auf dem der Datensatz verarbeitet wird, und sich auf die Datenbank bezieht, aus der Daten geladen werden sollen. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Datenbankkennwort </td> 
   <td colname="col2"> Das Kennwort für die Verbindung mit der Datenbank. Wenn ein Kennwort für das DSN im <span class="wintitle"> Datenquellenadministrator</span>, kann dies leer gelassen werden. Jedes hier angegebene Kennwort setzt das für das DSN konfigurierte Kennwort im <span class="wintitle"> Datenquellenadministrator</span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Benutzer-ID der Datenbank </td> 
   <td colname="col2"> Die Benutzer-ID, die beim Herstellen einer Verbindung zur Datenbank verwendet wird. Wenn eine Benutzer-ID für das DSN im <span class="wintitle"> Datenquellenadministrator</span>, kann dies leer gelassen werden. Jede hier bereitgestellte Benutzer-ID setzt die Benutzer-ID außer Kraft, die für das DSN in der <span class="wintitle"> Datenquellenadministrator</span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Felder </td> 
   <td colname="col2"> Ein Vektor von Spaltenobjekten, der eine Zuordnung von Datenspalten in der Datenbank zu Datenfeldern in der Ausführungsengine des Data Workbench-Servers angibt. Jede Spalte enthält Einträge <span class="wintitle"> Spaltenname</span> und <span class="wintitle"> Feldname</span>. <span class="wintitle"> Spaltenname</span> ist ein SQL-Spaltenausdruck, der im Kontext der Tabelle gültig sein muss, die durch <span class="wintitle"> Tabellenkennung</span> weiter oben beschrieben. Es kann sich um einen Spaltennamen oder einen SQL-Ausdruck handeln, der auf einer beliebigen Anzahl von Spalten in der Tabelle basiert. Eine Formatierungsfunktion kann erforderlich sein, um Werte bestimmter Datentypen in Zeichenfolgen so zu konvertieren, dass die Genauigkeit nicht verloren geht. Alle Daten werden implizit mithilfe der standardmäßigen Formatierungsmethode der Datenbank in Zeichenfolgen konvertiert, was bei einigen Spaltendatentypen (z. B. Datums-/Uhrzeitdatentypen) zu Datenverlust führen kann, wenn keine expliziten Formatierungsausdrücke verwendet werden. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ID-Spalte erhöhen </td> 
   <td colname="col2"> <p>Ein Spaltenname oder SQL-Spaltenausdruck, der das Kriterium erfüllt, dass er beim Hinzufügen neuer Zeilen erhöht (oder zumindest nicht verringert) wird. Das heißt, wenn Zeile B zu einem späteren Zeitpunkt als Zeile A zur Tabelle hinzugefügt wird, muss der Wert dieser Spalte (oder des Spaltenausdrucks) in Zeile B größer sein (entsprechend der nativen Sortierreihenfolge der Datenbank) als der entsprechende Wert in Zeile A. </p> <p> 
     <ul id="ul_EBF6AEE4746B41B3B5BB6CC74194DAED"> 
      <li id="li_A5C9BE52B01649DE9726ECEC68B99828"> Die <span class="wintitle"> ID-Spalte erhöhen </span>name kann mit dem Namen einer vorhandenen Spalte übereinstimmen, muss jedoch nicht angegeben werden. </li> 
      <li id="li_CF69EAB4AFB14F4894F7A5CDCAF06947"> Es wird angenommen, dass dieser Ausdruck einen SQL-Zeichendatentyp aufweist. Wenn die tatsächlich zunehmende ID-Spalte einen anderen Datentyp aufweist, muss dieser Wert ein Spaltenausdruck sein, um ihn in eine Zeichenfolge zu konvertieren. Da dies in der Regel bedeutet, dass Vergleiche lexikografisch sind (Zeichen für Zeichen), ist es wichtig, den Wert sorgfältig zu formatieren. </li> 
      <li id="li_58977431962E48039C898CFC47C53323"> Der Ausdruck wird in SQL ORDER BY -Klauseln verwendet und in SQL WHERE -Klauseln mit verglichen. Es ist von entscheidender Bedeutung, dass ein Index auf dem exakten Spaltenausdruck aufbaut, der verwendet wird. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Protokollquellen-ID </td> 
   <td colname="col2"> <p>Der Wert dieses Parameters kann eine beliebige Zeichenfolge sein. Wenn ein Wert angegeben wird, können Sie mit diesem Parameter Protokolleinträge von verschiedenen Protokollquellen für die Quellidentifizierung oder die gezielte Verarbeitung unterscheiden. Das Feld x-log-source-id wird mit einem Wert gefüllt, der die Protokollquelle für jeden Protokolleintrag angibt. Wenn Sie beispielsweise Protokolleinträge aus einer ODBC-Quelle namens ODBCSource01 identifizieren möchten, können Sie <span class="filepath"> von ODBCSource01.</span> und diese Zeichenfolge an das Feld x-log-source-id für jeden Protokolleintrag aus dieser Quelle übergeben wird. </p> <p> Weitere Informationen zum Feld x-log-source-id finden Sie unter <a href="../../../home/c-dataset-const-proc/c-ev-data-rec-fields.md#concept-06bda4be1a4649a2905a4422e9e6c42f"> Felder für Ereignisdatensätze</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Auf Server ausführen </td> 
   <td colname="col2"> Indexwert in der <span class="filepath"> profile.cfg</span> -Datei des Verarbeitungsservers, der die ODBC-Abfragen durchführt, um Daten aus der Datenbank abzurufen. (Der Parameter für Verarbeitungsserver im <span class="filepath"> profile.cfg</span> -Datei listet alle Verarbeitungsserver für den Datensatz auf und jeder Server hat einen Indexwert, wobei der erste 0 ist.) Der Standardwert lautet 0. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tabellenkennung </td> 
   <td colname="col2"> Ein SQL-Ausdruck, der die Tabelle oder Ansicht benennt, aus der Daten geladen werden sollen. Eine typische Tabellenkennung ist vom Formular SCHEMA.TABLE. </td> 
  </tr> 
 </tbody> 
</table>

Dieses Beispiel zeigt die [!DNL Log Processing] Konfigurationsfenster in Data Workbench mit einer ODBC-Datenquelle. Diese Datenquelle entnimmt Daten aus einer Tabelle mit dem Namen [!DNL VISUAL.VSL] in einer Datenbank mit [!DNL Data Source Name] &quot;VSTestO.&quot; Fünf (5) Spaltenobjekte ( [!DNL Fields]) ordnen Daten aus den Datenspalten in der Datenbank dem Data Workbench-Server zu.

![](assets/cfg_LogProcessing_LogSources_ODBC.png)
