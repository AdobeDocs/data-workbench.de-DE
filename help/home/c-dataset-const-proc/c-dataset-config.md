---
description: Die Datensatzkonfiguration bezieht sich auf den Prozess der Bearbeitung der Konfigurationsdateien, deren Parameter die Regeln für die Datensatzerstellung bereitstellen.
title: Grundlagen zur Konfiguration von Datensätzen
uuid: 813933d1-f52d-4584-8edd-ce9cd4aed74a
exl-id: 1358d08e-d81c-453d-a3a3-c1f279f38192
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '916'
ht-degree: 7%

---

# Grundlagen zur Konfiguration von Datensätzen{#understanding-dataset-configuration}

Die Datensatzkonfiguration bezieht sich auf den Prozess der Bearbeitung der Konfigurationsdateien, deren Parameter die Regeln für die Datensatzerstellung bereitstellen.

Der erstellte Datensatz befindet sich physisch in der auf dem Data Workbench-Server-Computer gespeicherten Datei [!DNL temp.db], aber die Konfigurationsdateien für den Datensatz befinden sich in einem Ordner für ein Profil. Ein Profil enthält eine Reihe von Konfigurationsdateien, die ein Dataset (einschließlich erweiterter Dimensionen) für eine bestimmte Analyse erstellen. Darüber hinaus enthält ein Profil die Definitionen von Entitäten wie Metriken, abgeleitete Dimensionen, Arbeitsbereiche, Berichte und Visualisierungen, mit denen Analysten mit dem Datensatz interagieren und Informationen daraus abrufen können.

Das Profil, dessen Datensatzkonfigurationsdateien Sie bearbeiten, wird als Ihr DataSet-Profil bezeichnet. Ein DataSet-Profil verweist auf mehrere geerbte Profil, bei denen es sich um beliebige Profil handeln kann, die Sie erstellen und verwalten, sodass Sie Ihre Adobe so konfigurieren können, dass sie Ihren Anforderungen an die Analyse am besten entspricht. Ein DataSet-Profil kann auch auf interne Profil verweisen, die mit Ihrer Anwendung zur Adobe bereitgestellt werden, um die Grundlage für alle in Ihrer Anwendung verfügbaren Funktionen zu bilden.

Weitere Informationen zu den verschiedenen Typen von Profilen, die mit Adobe-Anwendungen verfügbar sind, finden Sie im *Data Workbench Benutzerhandbuch*.

<!--
c_req_config_files.xml
-->

Ein DataSet-Profil für eine Adobe-Anwendung muss die folgenden Konfigurationsdateien auf dem Insight Server-Computer enthalten:

* **Profil.cfg:** Listen der geerbten Profil und Verarbeitungsserver für das Profil. Verarbeitungsserver sind die Insight Server-DPUs, die die Daten für das Profil verarbeiten. Wenn Sie einen Insight Server-Cluster installiert haben, können Sie mehrere Insight Server-Computer angeben, um ein einzelnes Profil auszuführen.

   Anweisungen zum Hinzufügen geerbter Profil zur [!DNL Profile.cfg]-Datei eines Dataset-Profils finden Sie im *Serverinstallations- und Administrationshandbuch*. Informationen zum Installieren eines Insight Server-Clusters oder zum Konfigurieren eines DataSet-Profils für die Ausführung auf einem Insight Server-Cluster finden Sie im *Handbuch zur Serverinstallation und -verwaltung*.

* **DataSet\Log Processing.cfg:** Steuert die Protokollierungsphase des Datensatzerstellungsprozesses. Siehe [Protokollverarbeitung](../../home/c-dataset-const-proc/c-dataset-constr.md#concept-8a63892878004dc389c7dad784fcb061). Weitere Informationen zur Datei [!DNL Log Processing.cfg] finden Sie unter [Konfigurationsdatei für die Protokollverarbeitung](../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md).

* **DataSet\Transformation.cfg:** Steuert die Umwandlungsphase des Datensatzerstellungsprozesses. Siehe [Transformation](../../home/c-dataset-const-proc/c-dataset-constr.md#concept-88f72e0897a744b5bc03df5039264dda). Die [!DNL Transformation.cfg]-Datei konfiguriert den Datensatz in der Regel für die Profil-spezifische Analyse. Weitere Informationen zur Datei [!DNL Transformation.cfg] finden Sie unter [Transformationskonfigurationsdatei](../../home/c-dataset-const-proc/c-trans-config-file/c-abt-trans-config-file.md).

* **Datensatz einschließlich Dateien:** Eine  [!DNL dataset include] Datei enthält eine Untergruppe der Parameter, die in der  [!DNL Log Processing.cfg] oder- [!DNL Transformation.cfg] Datei für das DataSet-Profil enthalten sind, jedoch in einem geerbten Profil gespeichert und verwaltet werden. [!DNL Dataset include] Dateien ergänzen die Hauptdataset-Konfigurationsdateien. Weitere Informationen finden Sie unter [Dateninklusive Dateien](../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md).

Das DataSet-Profil, das Sie während der Implementierung Ihrer Adobe erhalten, enthält eine Reihe von DataSet-Konfigurationsdateien, die Sie mit dem Befehl [!DNL Profile Manager] öffnen, bearbeiten und speichern können.

Informationen zum [!DNL Profile Manager] finden Sie im *Insight-Benutzerhandbuch*.

<!--
c_addl_config_files.xml
-->

Diese Dateien sind zwar nicht für alle Datensätze erforderlich, ermöglichen Ihnen jedoch die Steuerung anderer Aspekte des Datensatzerstellungsprozesses:

* **Protokollverarbeitungsmodus.cfg:** Die  [!DNL Log Processing Mode.cfg] Datei ermöglicht Ihnen, die Verarbeitung von Daten in einem Datensatz anzuhalten, Offlinequellen anzugeben oder anzugeben, wie oft der Data Workbench-Server seine Statusdateien speichert. Siehe [Zusätzliche Konfigurationsdateien](../../home/c-dataset-const-proc/c-add-config-files/c-add-config-files.md#concept-1afef4f88f1e467ab4326875fd1d3004).

* **Server.cfg:** Die  [!DNL Server.cfg] Datei gibt die standardmäßige Datencache-Größe (in Byte) für Datenbasis-Computer an, die eine Verbindung zum Data Workbench-Server herstellen. Siehe [Zusätzliche Konfigurationsdateien](../../home/c-dataset-const-proc/c-add-config-files/c-add-config-files.md#concept-1afef4f88f1e467ab4326875fd1d3004).

* **Transform.cfg und Transform Mode.cfg:** Diese Dateien sind nur verfügbar, wenn Sie die Datenkonvertierungsfunktion für die Verwendung mit Ihrer Adobe lizenziert haben. Die Datei [!DNL Transform.cfg] enthält die Parameter, die die Protokollquellen und Datentransformationen für die Transformation definieren. Die von Ihnen definierten Konvertierungen manipulieren die Quelldaten und geben sie in einem von Ihnen angegebenen Format aus. Mit der Datei [!DNL Insight Transform Mode.cfg] können Sie die Verarbeitung von Daten in einem Datensatz anhalten, Offlinequellen angeben oder die Häufigkeit angeben, mit der die Konvertierungsfunktion des Insight-Servers die Statusdateien speichert. Siehe [Transformationsfunktionalität](https://docs.adobe.com/content/help/en/data-workbench/using/server-admin-install/transform/t-config-tfm.html).

<!--
c_next_steps.xml
-->

Informationen zu bestimmten Aufgaben der Datenaset-Konfiguration finden Sie in der folgenden Tabelle, um die Aufgaben von Interesse zu suchen und zu lesen:

<table id="table_394CFB5135274545B5DA37952EC6943E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Wenn Sie möchten... </th> 
   <th colname="col2" class="entry"> Siehe... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Protokollquellen definieren </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-6714c720fac044cbb9af003bf401b2ea"> Quellen für die Protokollierung </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Bestimmen Sie, welche Protokolleinträge während der Protokollverarbeitung in den Datensatz eingegeben werden. </p> </td> 
   <td colname="col2"> <p> <a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d"> Data Filters</a> </p> <p> <a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-ecaff95cee4e40bc90f81e099c5fc934"> Protokolleintragsbedingung</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Aktivieren der Aufteilung von Tracking-IDs mit großen Mengen von Ereignis-Daten </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-64b416bbe42f4d689f90df246f7f7caf"> Schlüsselaufteilung</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Konfigurieren eines Insight-Servers für die Ausführung als Dateiservereinheit </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d"> Konfigurieren einer Insight Server File Server-Einheit  </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Konfigurieren eines Insight-Servers für die Ausführung als zentralisierter Normalisierungsserver </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d"> Konfigurieren einer Insight Server File Server-Einheit  </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Legen Sie die Zeitzone fest, die für die Erstellung von Zeitdimensionen und für die Durchführung von Zeitkonvertierungen verwendet werden soll </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-trans-config-file/c-spec-trans-param/c-time-zones.md#concept-9cf16b1cb4874f7d85e1dd950fdb4956"> Zeitzonen </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nehmen Sie geringfügige Änderungen an den Konfigurationsdateien des Datensatzes vor, die in den internen Profilen enthalten sind, die von der Adobe bereitgestellt werden </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077"> Bearbeiten vorhandener Datensatzaufnahme-Dateien </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Geben Sie neue Datenfelder an, die von der Protokollverarbeitung zur Konvertierung übergeben werden sollen </p> </td> 
   <td colname="col2"> <p> <a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-create-new-dataset-inc-files.md#task-b29f30605c374a6ca747ac843337b06e"> Erstellen neuer Datensatzaufnahme-Dateien </a> </p> <p> <a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab"> Datensatzaufnahme-Dateien zur Protokollverarbeitung </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Definieren von Transformationen </p> </td> 
   <td colname="col2"> <p> <a href="../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md"> Datenumwandlungen </a> </p> <p> <a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-create-new-dataset-inc-files.md#task-b29f30605c374a6ca747ac843337b06e"> Erstellen neuer Datensatzaufnahme-Dateien </a> </p> <p> <a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace"> Datensatzaufnahme-Dateien zur Umwandlung </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Erweiterte Dimensionen erstellen </p> </td> 
   <td colname="col2"> <p> <a href="../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md"> Erweiterte Dimensionen </a> </p> <p> <a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-create-new-dataset-inc-files.md#task-b29f30605c374a6ca747ac843337b06e"> Erstellen neuer Datensatzaufnahme-Dateien </a> </p> <p> <a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace"> Datensatzaufnahme-Dateien zur Umwandlung </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Definieren von Parametern, die während der gesamten Protokollverarbeitung oder Transformation verwendet werden </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-def-param-dataset-inc-files.md#concept-5ad06acc8dc44bf2a99643fafdd56b50"> Definieren von Parametern Datensatzaufnahme-Dateien </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Informieren Sie sich über die Insight-Schnittstellen, mit denen Sie Ihr Dataset überwachen oder verwalten können </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-int/c-dataset-config-int.md#concept-0ea33a52ce234ec8951e7b4430fbc5ab"> Arbeiten mit den Oberflächen für die Datensatzkonfiguration </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ausblenden bestimmter erweiterter Dimensionen, sodass sie nicht im Dimensionsmenü in Insight angezeigt werden </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-dataset-config-tools/c-hide-dataset-comp/c-hide-dataset-comp.md#concept-50d9a004736f42f6b0aa7cde0d6148ff"> Ausblenden von Datensatzkomponenten </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Überschreiben bestimmter Datensatzkonfigurationsdateien in einem Profil, das Sie nicht ändern können oder möchten </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-dataset-config-tools/c-hide-dataset-comp/c-hide-dataset-comp.md#concept-50d9a004736f42f6b0aa7cde0d6148ff"> Ausblenden von Datensatzkomponenten </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Datensatz neu verarbeiten </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md"> Wiederaufbereitung und erneute Umwandlung </a> </p> </td> 
  </tr> 
 </tbody> 
</table>
