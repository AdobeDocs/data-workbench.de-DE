---
description: Der Data Workbench-Server (InsightServer64.exe) kann Ereignis-Daten aus jeder SQL-Datenbank lesen (z. B. Oracle oder Microsoft SQL Server), die über einen ODBC 3.0-kompatiblen Treiber verfügt.
title: ODBC-Datenquellen
uuid: 5b37cd41-2d79-472c-8e6d-00ff894991a9
exl-id: b22b1e27-9b6c-4708-b45c-a9605807689a
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1245'
ht-degree: 1%

---

# ODBC-Datenquellen{#odbc-data-sources}

Der Data Workbench-Server (InsightServer64.exe) kann Ereignis-Daten aus jeder SQL-Datenbank lesen (z. B. Oracle oder Microsoft SQL Server), die über einen ODBC 3.0-kompatiblen Treiber verfügt.

Die ODBC-Unterstützung des Data Workbench-Servers ähnelt der vorhandenen Unterstützung für das Laden von Daten von Sensoren oder von Protokolldateien, die von externen Prozessen generiert werden. Es gibt jedoch einige zusätzliche Überlegungen und Einschränkungen:

* Die ODBC-Unterstützung des Data Workbench-Servers ist mit den Clustering-Funktionen kompatibel. Die Daten werden auf allen Verarbeitungsservern verteilt, und alle anschließenden Verarbeitungsvorgänge (einschließlich der Verarbeitung von Abfragen) profitieren vollständig vom Clustering.
* Die ODBC-Unterstützung ist von ODBC-Treibern von Drittanbietern abhängig. Damit ODBC-Unterstützung funktioniert, müssen diese Treiber auf dem Computer konfiguriert werden, auf dem der Data Workbench-Server ausgeführt wird. Dabei müssen Tools verwendet werden, die nicht zur Adobe gehören. Data Workbench-Computer erfordern keine zusätzliche Konfiguration.
* Die Tabelle oder Ansicht, aus der Daten geladen werden, muss über eine wachsende ID-Spalte verfügen. Bei jeder Zeile darf der Wert in dieser Spalte (die eine Spalte in der Tabelle oder ein SQL-Spaltencode sein kann) nicht verringert werden, da neue Zeilen in die Datenbank eingefügt werden. Wenn diese Einschränkung verletzt wird, gehen Daten verloren. Für eine adäquate Leistung ist ein Index für diesen Ausdruck erforderlich.

   >[!NOTE]
   >
   >Es ist möglich, dass mehrere Zeilen denselben Wert in der Spalte [!DNL Increasing ID] haben. Eine Möglichkeit ist eine Zeitstempelspalte mit weniger als perfekter Präzision.

* Der Data Workbench-Server kann keine Spalten mit langen Daten laden (Daten über eine bestimmte Länge, wie von der jeweiligen Datenbankanwendung bestimmt).
* Das Abrufen von Daten aus einer Datenbank ist langsamer als das Lesen aus einer Festplattendatei. Die Verarbeitung von Datensätzen, die Daten aus einer ODBC-Quelle laden (insbesondere bei der Wiederaufbereitung), dauert wesentlich länger als die Verarbeitung von Datensätzen mit äquivalenter Größe, deren Daten von Sensoren oder anderen Festplattendateien stammen.

Weitere Informationen zur erneuten Verarbeitung Ihrer Daten finden Sie unter [Wiederaufbereitung und Verarbeitung](../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).

**So konfigurieren Sie Insight Server für ODBC[!DNL event data]**

Zum Konfigurieren des Data Workbench-Servers zum Laden von Daten aus einer SQL-Datenbank müssen Sie zunächst die folgenden Schritte in der richtigen Reihenfolge ausführen:

1. Installieren Sie die entsprechende Datenbankclient-Software, einschließlich eines ODBC-Treibers, auf dem Datenbasis-Servercomputer, auf dem der Datensatz verarbeitet wird.

   >[!NOTE]
   >
   >Wenn Sie ODBC-Ereignis-Daten zur Verarbeitung auf einem Data Workbench-Servercluster laden, müssen Sie die Datenbankclientsoftware auf allen Verarbeitungsservern im Cluster installieren. Weitere Informationen zum Festlegen von Verarbeitungsservern in einem Cluster finden Sie im *Serverproduktinstallations- und Administrationshandbuch*.

1. Konfigurieren Sie eine Datenquelle mit dem ODBC-Datenquellenadministrator für Windows.

   Beachten Sie, dass der Data Workbench-Server (InsightServer64.exe) als Windows-Dienst ausgeführt wird. Daher muss die Datenquelle normalerweise als System-DSN und nicht als User-DSN konfiguriert werden, damit der Data Workbench-Server sie verwenden kann. Weitere Informationen zu diesem Konfigurationsschritt finden Sie in der Dokumentation zu Ihrer Datenbanksoftware.

Nachdem Sie die Datenbankclient-Software auf dem entsprechenden Datenbasis-Servercomputer installiert haben, können Sie den Datensatz für die Verwendung der ODBC-Datenquelle konfigurieren, indem Sie die entsprechenden Parameter in der Konfigurationsdatei [!DNL Log Processing] für das gewünschte Profil bearbeiten.

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
   <td colname="col2"> Der Bezeichner für die ODBC-Quelle. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Datenquellenname </td> 
   <td colname="col2"> Ein DSN, das von einem Administrator des Data Workbench-Servercomputers, auf dem der Datensatz verarbeitet wird, bereitgestellt wird und sich auf die Datenbank bezieht, aus der Daten geladen werden sollen. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Datenbankkennwort </td> 
   <td colname="col2"> Das Kennwort, das beim Herstellen einer Verbindung zur Datenbank verwendet wird. Wenn im Ordner <span class="wintitle"> Data Source Administrator</span> ein Kennwort für das DSN konfiguriert wurde, kann dies leer bleiben. Jedes hier bereitgestellte Kennwort setzt das für das DSN konfigurierte Kennwort in <span class="wintitle"> Datenquellen-Administrator</span> außer Kraft. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Benutzer-ID der Datenbank </td> 
   <td colname="col2"> Die beim Herstellen einer Verbindung zur Datenbank zu verwendende Benutzer-ID. Wenn im Ordner <span class="wintitle"> Data Source Administrator</span> eine Benutzer-ID für das DSN konfiguriert wurde, kann dies leer bleiben. Jede hier bereitgestellte Benutzer-ID setzt die Benutzer-ID außer Kraft, die für das DSN im Ordner <span class="wintitle"> Data Source Administrator</span> konfiguriert wurde. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Felder </td> 
   <td colname="col2"> Ein Vektor von Spaltenobjekten, der eine Zuordnung von Datenspalten in der Datenbank zu Datenfeldern in der Datenbasis-Server-Ausführungsengine angibt. Jede Spalte enthält die Einträge <span class="wintitle"> Spaltenname</span> und <span class="wintitle"> Feldname</span>. <span class="wintitle"> Spalte </span> Name ist ein SQL-Spaltenname, der im Kontext der oben beschriebenen Tabelle gültig sein muss, die mit der  <span class="wintitle"> Tabellenkennung </span> gekennzeichnet ist. Dabei kann es sich um einen Spaltennamen oder einen SQL-Ausdruck handeln, der auf einer beliebigen Spaltenanzahl in der Tabelle basiert. Eine Formatierungsfunktion kann erforderlich sein, um Werte bestimmter Datentypen so in Zeichenfolgen zu konvertieren, dass keine Präzision verloren geht. Sämtliche Daten werden implizit mithilfe der Standardformatierungsmethode der Datenbank in Zeichenfolgen konvertiert, was bei einigen Spaltendatentypen (z. B. Datums-/Uhrzeitdatentypen) zu Datenverlusten führen kann, wenn keine expliziten Ausdruck zur Formatierung verwendet werden. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ID-Spalte vergrößern </td> 
   <td colname="col2"> <p>Ein Spaltenname oder SQL-Spaltenname, der das Kriterium erfüllt, dass er beim Hinzufügen neuer Zeilen erhöht (oder zumindest nicht verringert) wird. Das heißt, wenn Zeile B zu einem späteren Zeitpunkt als Zeile A der Tabelle hinzugefügt wird, muss der Wert dieser Spalte (oder des Ausdrucks der Spalte) in Zeile B größer sein (gemäß der systemeigenen Sortierreihenfolge der Datenbank) als der entsprechende Wert in Zeile A. </p> <p> 
     <ul id="ul_EBF6AEE4746B41B3B5BB6CC74194DAED"> 
      <li id="li_A5C9BE52B01649DE9726ECEC68B99828"> Der Name der Spalte <span class="wintitle"> Inkrementieren der ID </span>kann mit dem Namen einer vorhandenen Spalte übereinstimmen, muss jedoch nicht angegeben werden. </li> 
      <li id="li_CF69EAB4AFB14F4894F7A5CDCAF06947"> Es wird angenommen, dass dieser Ausdruck einen SQL-Zeichendatentyp hat. Wenn die tatsächlich zunehmende ID-Spalte von einem anderen Datentyp stammt, muss dieser Ausdruck ein Spaltenwert sein, um ihn in eine Zeichenfolge zu konvertieren. Da dies in der Regel bedeutet, dass Vergleiche lexikografisch sind (Zeichen nach Zeichen), ist es wichtig, den Wert sorgfältig zu formatieren. </li> 
      <li id="li_58977431962E48039C898CFC47C53323"> Der Ausdruck wird in SQL ORDER BY-Klauseln verwendet und mit SQL WO-Klauseln verglichen. Es ist äußerst wichtig, dass ein Index auf dem exakten Spaltencode basiert, der verwendet wird. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Protokollquelle-ID </td> 
   <td colname="col2"> <p>Der Wert dieses Parameters kann eine beliebige Zeichenfolge sein. Wenn ein Wert angegeben wird, können Sie mit diesem Parameter Protokolleinträge von verschiedenen Protokollquellen zur Quellidentifizierung oder gezielten Verarbeitung unterscheiden. Das Feld x-log-source-id wird mit einem Wert gefüllt, der die Protokollquelle für jeden Protokolleintrag identifiziert. Wenn Sie beispielsweise Protokolleinträge aus einer ODBC-Quelle mit dem Namen ODBCSource01 identifizieren möchten, können Sie <span class="filepath"> aus ODBCSource01 eingeben.</span> und diese Zeichenfolge an das Feld x-log-source-id für jeden Protokolleintrag aus dieser Quelle übergeben wird. </p> <p> Weitere Informationen zum Feld x-log-source-id finden Sie unter <a href="../../../home/c-dataset-const-proc/c-ev-data-rec-fields.md#concept-06bda4be1a4649a2905a4422e9e6c42f"> Ereignis Data Record Fields</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ausführen auf Server </td> 
   <td colname="col2"> Indexwert in der Datei <span class="filepath"> Profil.cfg</span> des Verarbeitungsservers, der die ODBC-Abfragen ausführt, um Daten aus der Datenbank abzurufen. (Der Parameter "Verarbeitungsserver"in der Datei "<span class="filepath">"Profil.cfg</span>"Liste alle Verarbeitungsserver für den Datensatz, wobei jeder Server einen Indexwert hat, wobei der erste 0 ist.) Der Standardwert lautet 0. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tabellenkennung </td> 
   <td colname="col2"> Ein SQL-Ausdruck, der die Tabelle oder Ansicht benennt, aus der Daten geladen werden sollen. Eine typische Tabellenkennung ist das form SCHEMA.TABLE. </td> 
  </tr> 
 </tbody> 
</table>

Dieses Beispiel zeigt das Konfigurationsfenster [!DNL Log Processing] in der Data Workbench mit einer ODBC-Datenquelle. Diese Datenquelle nimmt Daten aus einer Tabelle mit dem Namen [!DNL VISUAL.VSL] in einer Datenbank mit [!DNL Data Source Name] &quot;VSTestO&quot;. Fünf (5) Spaltenobjekte ( [!DNL Fields]) ordnen Daten aus den Datenspalten in der Datenbank dem Data Workbench-Server zu.

![](assets/cfg_LogProcessing_LogSources_ODBC.png)
