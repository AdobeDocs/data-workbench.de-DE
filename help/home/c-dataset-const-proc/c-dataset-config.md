---
description: Die Datensatzkonfiguration bezieht sich auf den Prozess der Bearbeitung der Konfigurationsdateien, deren Parameter die Regeln für die Erstellung von Datensätzen bereitstellen.
title: Grundlagen zur Konfiguration von Datensätzen
uuid: 813933d1-f52d-4584-8edd-ce9cd4aed74a
exl-id: 1358d08e-d81c-453d-a3a3-c1f279f38192
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '914'
ht-degree: 7%

---

# Grundlagen zur Konfiguration von Datensätzen{#understanding-dataset-configuration}

{{eol}}

Die Datensatzkonfiguration bezieht sich auf den Prozess der Bearbeitung der Konfigurationsdateien, deren Parameter die Regeln für die Erstellung von Datensätzen bereitstellen.

Der erstellte Datensatz befindet sich physisch in der [!DNL temp.db] auf dem Data Workbench-Servercomputer gespeichert ist, sich die Konfigurationsdateien für den Datensatz jedoch in einem Ordner für ein Profil befinden. Ein Profil enthält eine Reihe von Konfigurationsdateien, die einen Datensatz (einschließlich erweiterter Dimensionen) für einen bestimmten Analysezweck erstellen. Darüber hinaus enthält ein Profil die Definitionen von Entitäten wie Metriken, abgeleitete Dimensionen, Arbeitsbereiche, Berichten und Visualisierungen, die es Analysten ermöglichen, mit dem Datensatz zu interagieren und Informationen aus ihm zu erhalten.

Das Profil, dessen Datensatzkonfigurationsdateien Sie bearbeiten, wird als Datensatzprofil bezeichnet. Ein Datensatzprofil verweist auf mehrere geerbte Profile. Dabei kann es sich um beliebige Adobe-Profile handeln, die Sie erstellen und verwalten. So können Sie Ihre App so konfigurieren, dass sie Ihren Analyseanforderungen am besten entspricht. Ein Datensatzprofil kann auch auf interne Profile verweisen, die mit Ihrer Adobe App bereitgestellt werden, um die Grundlage für alle in Ihrer Anwendung verfügbaren Funktionen zu bilden.

Weitere Informationen zu den verschiedenen Profiltypen, die in Adobe Apps verfügbar sind, finden Sie in der *Data Workbench-Benutzerhandbuch*.

<!--
c_req_config_files.xml
-->

Ein Datensatzprofil für eine Adobe-Anwendung muss die folgenden Konfigurationsdateien auf dem Insight Server-Computer enthalten:

* **profile.cfg:** Listet die geerbten Profile und Verarbeitungsserver für das Profil auf. Verarbeitungsserver sind die Insight Server-DPUs, die die Daten für das Profil verarbeiten. Wenn Sie einen Insight Server-Cluster installiert haben, können Sie mehrere Insight Server-Computer angeben, um ein einzelnes Profil auszuführen.

   Anweisungen zum Hinzufügen geerbter Profile zum Datensatzprofil [!DNL Profile.cfg] -Datei, siehe *Handbuch zur Installation und Verwaltung von Serverprodukten*. Informationen zum Installieren eines Insight Server-Clusters oder zum Konfigurieren eines Datensatzprofils für die Ausführung auf einem Insight Server-Cluster finden Sie in der *Handbuch zur Installation und Verwaltung von Serverprodukten*.

* **Datensatz\Log Processing.cfg:** Steuert die Protokollverarbeitungsphase des Datensatzerstellungsprozesses. Siehe [Protokollverarbeitung](../../home/c-dataset-const-proc/c-dataset-constr.md#concept-8a63892878004dc389c7dad784fcb061). Weitere Informationen zum [!DNL Log Processing.cfg] -Datei, siehe [Konfigurationsdatei für die Protokollverarbeitung](../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md).

* **Datensatz\Transformation.cfg:** Steuert die Umwandlungsphase des Datensatzerstellungsprozesses. Siehe [Umwandlung](../../home/c-dataset-const-proc/c-dataset-constr.md#concept-88f72e0897a744b5bc03df5039264dda). Die [!DNL Transformation.cfg] -Datei konfiguriert normalerweise den Datensatz für die profilspezifische Analyse. Weitere Informationen zum [!DNL Transformation.cfg] -Datei, siehe [Konfigurationsdatei für Umwandlungen](../../home/c-dataset-const-proc/c-trans-config-file/c-abt-trans-config-file.md).

* **Datensatzaufnahme-Dateien:** A [!DNL dataset include] enthält eine Untergruppe der im [!DNL Log Processing.cfg] oder [!DNL Transformation.cfg] -Datei für das Datensatzprofil, wird jedoch in einem geerbten Profil gespeichert und verwaltet. [!DNL Dataset include] -Dateien ergänzen die Hauptkonfigurationsdateien des Datensatzes. Weitere Informationen finden Sie unter [Datensatzaufnahme-Dateien](../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md).

Das Datensatzprofil, das Sie während der Implementierung Ihrer Adobe App erhalten haben, enthält eine Reihe von Datensatzkonfigurationsdateien, die Sie mit der [!DNL Profile Manager].

Informationen zum [!DNL Profile Manager], siehe *Insight-Benutzerhandbuch*.

<!--
c_addl_config_files.xml
-->

Obwohl dies nicht für alle Datensätze erforderlich ist, können Sie mit diesen Dateien andere Aspekte des Prozesses zur Datensatzerstellung steuern:

* **Log Processing Mode.cfg:** Die [!DNL Log Processing Mode.cfg] -Datei können Sie die Datenverarbeitung in einem Datensatz anhalten, Offline-Quellen angeben oder angeben, wie oft der Data Workbench-Server seine Statusdateien speichert. Siehe [Zusätzliche Konfigurationsdateien](../../home/c-dataset-const-proc/c-add-config-files/c-add-config-files.md#concept-1afef4f88f1e467ab4326875fd1d3004).

* **Server.cfg:** Die [!DNL Server.cfg] -Datei gibt die standardmäßige Datencache-Größe (in Byte) für Data Workbench-Computer an, die eine Verbindung zum Data Workbench-Server herstellen. Siehe [Zusätzliche Konfigurationsdateien](../../home/c-dataset-const-proc/c-add-config-files/c-add-config-files.md#concept-1afef4f88f1e467ab4326875fd1d3004).

* **Transform.cfg und Transform Mode.cfg:** Diese Dateien sind nur verfügbar, wenn Sie die Datenumwandlungsfunktion für Ihre Adobe App lizenziert haben. Die [!DNL Transform.cfg] enthält die Parameter, die die Protokollquellen und Datenumwandlungen für die Umwandlungsfunktion definieren. Die von Ihnen definierten Umwandlungen manipulieren die Quelldaten und geben sie in einem von Ihnen angegebenen Format aus. Die [!DNL Insight Transform Mode.cfg] -Datei ermöglicht es Ihnen, die Verarbeitung von Daten in einem Datensatz anzuhalten, Offline-Quellen anzugeben oder anzugeben, wie häufig die Insight Server-Funktion, die die Umwandlung durchführt, seine Statusdateien speichert. Siehe [Umwandlungsfunktion](https://experienceleague.adobe.com/docs/data-workbench/using/server-admin-install/transform/t-config-tfm.html).

<!--
c_next_steps.xml
-->

Informationen zu bestimmten Aufgaben zur Datensatzkonfiguration finden Sie in der unten stehenden Tabelle, um die für Sie wichtigen Aufgaben zu finden und zu lesen:

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
   <td colname="col1"> <p>Ermitteln Sie, welche Protokolleinträge den Datensatz während der Protokollverarbeitung eingeben. </p> </td> 
   <td colname="col2"> <p> <a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d"> Datenfilter</a> </p> <p> <a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-ecaff95cee4e40bc90f81e099c5fc934"> Protokolleintragsbedingung</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Aktivierung der Aufteilung von Tracking-IDs mit großen Mengen von Ereignisdaten </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-64b416bbe42f4d689f90df246f7f7caf"> Schlüsselaufteilung</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Konfigurieren eines Insight Server für die Ausführung als Dateiservereinheit </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d"> Konfigurieren einer Insight Server File Server Unit </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Konfigurieren eines Insight Server für die Ausführung als zentralisierten Normalisierungsserver </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d"> Konfigurieren einer Insight Server File Server Unit </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Legen Sie die Zeitzone fest, die für die Erstellung von Zeitdimensionen und für die Durchführung von Zeitkonversionen verwendet werden soll. </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-trans-config-file/c-spec-trans-param/c-time-zones.md#concept-9cf16b1cb4874f7d85e1dd950fdb4956"> Zeitzonen </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nehmen Sie geringfügige Änderungen an den Datensatzkonfigurationsdateien vor, die mit den von Adobe bereitgestellten internen Profilen enthalten sind. </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077"> Bearbeiten vorhandener Datensatzaufnahme-Dateien </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Geben Sie neue Datenfelder an, die von der Protokollverarbeitung zur Transformation übergeben werden sollen </p> </td> 
   <td colname="col2"> <p> <a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-create-new-dataset-inc-files.md#task-b29f30605c374a6ca747ac843337b06e"> Erstellen neuer Datensatzaufnahme-Dateien </a> </p> <p> <a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab"> Datensatzaufnahme-Dateien zur Protokollverarbeitung </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Transformationen definieren </p> </td> 
   <td colname="col2"> <p> <a href="../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md"> Datenumwandlungen </a> </p> <p> <a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-create-new-dataset-inc-files.md#task-b29f30605c374a6ca747ac843337b06e"> Erstellen neuer Datensatzaufnahme-Dateien </a> </p> <p> <a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace"> Datensatzaufnahme-Dateien zur Umwandlung </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Erweiterte Dimensionen erstellen </p> </td> 
   <td colname="col2"> <p> <a href="../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md"> Erweiterte Dimensionen </a> </p> <p> <a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-create-new-dataset-inc-files.md#task-b29f30605c374a6ca747ac843337b06e"> Erstellen neuer Datensatzaufnahme-Dateien </a> </p> <p> <a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace"> Datensatzaufnahme-Dateien zur Umwandlung </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Definieren von Parametern, die während der Protokollverarbeitung oder Transformation verwendet werden </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-def-param-dataset-inc-files.md#concept-5ad06acc8dc44bf2a99643fafdd56b50"> Definieren von Parametern Datensatzaufnahme-Dateien </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Erfahren Sie mehr über die Insight-Schnittstellen, mit denen Sie Ihren Datensatz überwachen oder verwalten können. </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-int/c-dataset-config-int.md#concept-0ea33a52ce234ec8951e7b4430fbc5ab"> Arbeiten mit den Oberflächen für die Datensatzkonfiguration </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ausblenden bestimmter erweiterter Dimensionen, sodass sie nicht im Dimensionsmenü in Insight angezeigt werden </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-dataset-config-tools/c-hide-dataset-comp/c-hide-dataset-comp.md#concept-50d9a004736f42f6b0aa7cde0d6148ff"> Ausblenden von Datensatzkomponenten </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Überschreiben Sie bestimmte Datensatzkonfigurationsdateien in einem Profil, die Sie nicht ändern können oder möchten </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-dataset-config-tools/c-hide-dataset-comp/c-hide-dataset-comp.md#concept-50d9a004736f42f6b0aa7cde0d6148ff"> Ausblenden von Datensatzkomponenten </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Datensatz erneut verarbeiten </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md"> Wiederaufbereitung und erneute Umwandlung </a> </p> </td> 
  </tr> 
 </tbody> 
</table>
