---
description: Ein Adobe-Datensatz enthält die Daten, die vom Data Workbench-Server geladen und verarbeitet wurden.
title: Grundlagen zum Aufbau von Datensätzen
uuid: 540d159d-3f72-49dd-9929-107f1fc62b2b
exl-id: 111e98b5-d899-4f79-90ce-70f520d527d6
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '937'
ht-degree: 0%

---

# Grundlagen zum Aufbau von Datensätzen{#understanding-dataset-construction}

Ein Adobe-Datensatz enthält die Daten, die vom Data Workbench-Server geladen und verarbeitet wurden.

Die Schritte, die beim Laden und Verarbeiten der Daten durch den Data Workbench-Server (InsightServer64.exe) durchgeführt werden, bilden den Prozess der Datensatzerstellung.

>[!NOTE]
>
>Ein Data Workbench-Server, der Daten aus einem Adobe-Datensatz verarbeitet und bereitstellt, wird als Datenverarbeitungseinheit oder DPU bezeichnet. Er wird manchmal auch als Verarbeitungsserver oder Abfrage-Server bezeichnet. Data Workbench- und [!DNL Report]-Clients interagieren direkt mit DPUs.

Während der Datensatzkonstruktion liest der Data Workbench-Server Quelldaten aus Protokollquellen, wendet Transformationen auf bestimmte Datenfelder an und definiert erweiterte Dimensionen, die aus den transformierten Feldern zu erstellen sind. Der Bauvorgang findet in zwei Phasen statt: *Protokollverarbeitung* und *Transformation*. Nachdem der Datensatz erstellt wurde, können Sie die erweiterten Dimensionen des Datensatzes verwenden, um abgeleitete Metriken und Dimensionen für Ihre spezifischen Analysen zu erstellen.

Die Dataset-Konstruktion ist wie ein Herstellungsprozess. Sie wählen die Daten (die Rohstoffe) aus, die zum Erstellen des Datensatzes verwendet werden sollen, und definieren die Datentransformationen (die Prozessschritte), die die in den Daten verfügbaren Informationen bearbeiten, um erweiterte Dimensionen (die hergestellten Produkte) zu erstellen.

<!--
c_log_proc.xml
-->

Die Protokolle werden gefiltert und die Datenfelder, die an die Umwandlungsphase übergeben werden sollen, werden identifiziert. Am Ende der Protokollverarbeitungsphase werden die Daten nach Tracking-ID gruppiert (d. h. alle Protokolleinträge mit derselben Tracking-ID werden gruppiert) und in der Zeit sortiert. Während der Protokollverarbeitung können Sie nicht auf die verarbeiteten Daten zugreifen, die für die Analyse verwendet werden sollen.

## Protokollquellen {#section-75279dd6a7304d469735562796741d0f} angeben

Protokollquellen sind Dateien mit den Daten, die zum Erstellen eines Datensatzes verwendet werden sollen. Die in den Protokollquellen verfügbaren Daten werden als Ereignis-Daten bezeichnet, da jeder Datensatz einen Transaktionssatz oder eine Instanz eines Ereignisses darstellt. Darüber hinaus enthält jeder Datensatz oder Protokolleintrag einen Wert, der als Tracking-ID bezeichnet wird.

>[!NOTE]
>
>Stellen Sie bei der Auswahl der Protokollquellen sicher, dass jeder Protokolleintrag eine Verfolgungs-ID für die Entität enthält, die die höchste Ebene darstellt, auf der Ihre Daten gruppiert werden sollen. Wenn Sie z. B. mit Daten arbeiten, die aus dem Website-Traffic gesammelt wurden, wählen Sie wahrscheinlich Besucher als solche aus. Jeder Besucher verfügt über eine eindeutige Tracking-ID, und alle Daten zu einem bestimmten Site-Besucher können gruppiert werden. Wenden Sie sich zwecks Hilfe an die Adobe.

Ein Ereignis aus Protokollquellen wird in Echtzeit von [!DNL Sensors] oder aus archivierten Datenquellen von Insight Server extrahiert. Von Sensoren erfasste Ereignis-Daten von HTTP- und Anwendungsservern werden an Insight-Server übertragen, die die Daten in hochkomprimierte Protokolldateien ( [!DNL .vsl]) konvertieren. Ereignis-Daten, die sich in einer einfachen Datei, XML-Datei oder einer ODBC-Datenquelle befinden, werden von Insight Server gelesen. Insight Server stellt Dekodierer bereit, die Sie definieren, um einen gemeinsamen Satz von Protokollfeldern aus diesen verschiedenen Formaten zu extrahieren.

## Definieren von Transformationen {#section-55a8cdb47379484081e53087f074778d}

Eine Transformation ist ein Satz von Anweisungen, die Sie definieren können, um Informationen in den Ereignis-Daten zu extrahieren oder zu manipulieren. Jede von Ihnen definierte Transformation wird auf jeden Ereignis-Datensatz (Protokolleintrag) angewendet, um vorhandene Protokollfelder zu aktualisieren oder neue  zu erstellen. Die Ergebnisse der Transformationen werden zusammen mit den Protokolleintragungsbedingungen verwendet, um zu bewerten, welche Protokolleinträge während der Protokollverarbeitung aus dem Datensatz herausgefiltert werden.

Nicht alle Arten von Transformationen können während der Protokollbearbeitung des Datensatzentwurfs verwendet werden.

## Filtern von Protokollen {#section-6172ca0fb0eb4177925151bb49fdbc02}

Der Datensatz enthält mehrere Parameter, mit denen die Daten gefiltert werden, die aus den Transformationen abgeleitet werden. Mit der Filterung wird angegeben, welche Protokolleinträge in den nachfolgenden Verarbeitungsschritten verwendet werden. Filter können beispielsweise durch Angabe des Zeitraums, des Serverstatus oder der IP-Adresse und der Benutzeragenten-Informationen definiert werden. Das [!DNL Log Entry Condition] ist ein anpassbarer Filtertest. Der Test sucht nach bestimmten Bedingungen in den Feldern der einzelnen Protokolleinträge, um festzustellen, ob dieser Eintrag im Datensatzaufbau weitergeführt werden soll. Wenn ein Protokolleintrag die Bedingung nicht erfüllt, wird der Eintrag aus dem Konstruktionsprozess entfernt.

## Identifizieren von Feldern für Transformationen {#section-eef98ca723e54547b887aefdf0514c47}

Wenn ein Datenfeld zur weiteren Verarbeitung von der Protokollverarbeitungsphase zur Transformationsphase übergeben werden soll, müssen Sie es bei der Protokollverarbeitung identifizieren. Diese Anforderung gilt unabhängig davon, ob das Feld aus den Protokollquellen verfügbar ist oder aus Datentransformationen erstellt wurde, die während der Protokollverarbeitung auf die Daten angewendet wurden.

<!--
c_transformation.xml
-->

Während der Umwandlungsphase der Datensatzkonstruktion erfolgt die Verarbeitung der gruppierten und geordneten Daten, die aus der Protokollverarbeitung ausgegeben werden. Es werden zusätzliche Datentransformationen durchgeführt und erweiterte Datendimensionen für die Verwendung in Ihren Analysen erstellt. Während der Transformationsphase können Sie auf ein statistisches Muster der Daten zugreifen, das größer wird, wenn sich die Transformationsphase dem Abschluss nähert.

## Definieren von Transformationen {#section-001b3fd4c1dd4dd38a5536872bc9de68}

Sie können Transformationen definieren, die während der Konvertierungsphase des Datensatzentwurfs verwendet werden sollen, um die Erstellung der erweiterten Dimensionen zu erleichtern. Jede Transformation wird auf jeden Ereignis-Datensatz (Protokolleintrag) angewendet, der aus der Protokollverarbeitung weitergeleitet wird.

## Filtern von Protokollen {#section-3fed0a00ca344a719b5e8db363f64f06}

Das [!DNL Log Entry Condition] kann während der Transformation angewendet werden, um nach bestimmten Bedingungen in den Feldern jedes Protokolleintrags zu suchen, der aus der Protokollverarbeitung stammt. Wenn ein Protokolleintrag die Bedingung nicht erfüllt, wird der Eintrag aus dem Konstruktionsprozess entfernt.

## Definieren erweiterter Dimensionen {#section-25efafd0bfc84c86b9717d453a88c91b}

Erweiterte Dimensionen sind die Endprodukte des Dataset-Aufbaus. Sie stellen Beziehungen zwischen den Protokollfeldern in den Daten dar. Sie verwenden sie zum Erstellen von Visualisierungen, zum Erstellen erweiterter Metriken oder zum Durchführen einer Analyse, um die Vorgänge und Probleme zu verstehen, die für Ihr Unternehmen spezifisch sind.
