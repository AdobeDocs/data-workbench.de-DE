---
description: Ein Adobe-Datensatz enthält die Daten, die vom Data Workbench-Server geladen und verarbeitet wurden.
solution: Analytics
title: Grundlagen der Datenblattkonstruktion
topic: Data workbench
uuid: 540d159d-3f72-49dd-9929-107f1fc62b2b
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Grundlagen der Datenblattkonstruktion{#understanding-dataset-construction}

Ein Adobe-Datensatz enthält die Daten, die vom Data Workbench-Server geladen und verarbeitet wurden.

Die Schritte, die beim Laden und Verarbeiten der Daten durch den Data Workbench-Server (InsightServer64.exe) durchgeführt werden, bilden den Prozess der Datensatzerstellung.

>[!NOTE]
>
>Ein Data Workbench-Server, der Daten aus einem Adobe-Datensatz verarbeitet und bereitstellt, wird als Datenverarbeitungseinheit oder DPU bezeichnet. Er wird manchmal auch als Verarbeitungsserver oder Abfrageserver bezeichnet. Data Workbench und [!DNL Report] Clients interagieren direkt mit DPUs.

Während der Datensatzkonstruktion liest der Data Workbench-Server Quelldaten aus Protokollquellen, wendet Transformationen auf bestimmte Datenfelder an und definiert erweiterte Dimensionen, die aus den transformierten Feldern zu erstellen sind. Der Bauvorgang findet in zwei Phasen statt: *Protokollverarbeitung* und *Transformation*. Nachdem der Datensatz erstellt wurde, können Sie die erweiterten Dimensionen des Datensatzes verwenden, um abgeleitete Metriken und Dimensionen für Ihre spezifischen Analysezwecke zu erstellen.

Die Dataset-Konstruktion ist wie ein Herstellungsprozess. Sie wählen die Daten (die Rohstoffe) aus, die zum Erstellen des Datensatzes verwendet werden sollen, und definieren die Datentransformationen (die Prozessschritte), die die in den Daten verfügbaren Informationen bearbeiten, um erweiterte Dimensionen (die hergestellten Produkte) zu erstellen.

<!--
c_log_proc.xml
-->

Die Protokolle werden gefiltert und die Datenfelder, die an die Umwandlungsphase übergeben werden sollen, werden identifiziert. Am Ende der Protokollverarbeitungsphase werden die Daten nach Tracking-ID gruppiert (d. h. alle Protokolleinträge mit derselben Tracking-ID werden gruppiert) und in der Zeit sortiert. Während der Protokollverarbeitung können Sie nicht auf die verarbeiteten Daten zugreifen, die für die Analyse verwendet werden sollen.

## Protokollquellen angeben {#section-75279dd6a7304d469735562796741d0f}

Protokollquellen sind Dateien mit den Daten, die zum Erstellen eines Datensatzes verwendet werden sollen. Die in den Protokollquellen verfügbaren Daten werden als Ereignisdaten bezeichnet, da jeder Datensatz einen Transaktionssatz oder eine einzelne Instanz eines Ereignisses darstellt. Darüber hinaus enthält jeder Datensatz oder Protokolleintrag einen Wert, der als Tracking-ID bezeichnet wird.

>[!NOTE]
>
>Stellen Sie bei der Auswahl der Protokollquellen sicher, dass jeder Protokolleintrag eine Verfolgungs-ID für die Entität enthält, die die höchste Ebene darstellt, auf der Ihre Daten gruppiert werden sollen. Wenn Sie z. B. mit Daten arbeiten, die aus dem Website-Traffic erfasst wurden, wählen Sie mit hoher Wahrscheinlichkeit Besucher als diese Entität aus. Jeder Besucher verfügt über eine eindeutige Tracking-ID, und alle Daten zu einem bestimmten Site-Besucher können gruppiert werden. Wenden Sie sich zwecks Hilfe an Adobe.

Ereignisdaten zu Protokollquellen werden in Echtzeit von Insight Server gesammelt [!DNL Sensors] oder aus archivierten Datenquellen extrahiert. Von Sensoren erfasste Ereignisdaten von HTTP- und Anwendungsservern werden an Insight-Server übertragen, die die Daten in stark komprimierte Protokolldateien ( [!DNL .vsl]) konvertieren. Ereignisdaten, die sich in einer einfachen Datei, XML-Datei oder einer ODBC-Datenquelle befinden, werden von Insight Server gelesen. Insight Server stellt Dekodierer bereit, die Sie definieren, um einen gemeinsamen Satz von Protokollfeldern aus diesen verschiedenen Formaten zu extrahieren.

## Definieren von Transformationen {#section-55a8cdb47379484081e53087f074778d}

Eine Transformation ist ein Satz von Anweisungen, die Sie definieren können, um Informationen in den Ereignisdaten zu extrahieren oder zu manipulieren. Jede von Ihnen definierte Transformation wird auf jeden Ereignisdatensatz (Protokolleintrag) angewendet, um vorhandene Protokollfelder zu aktualisieren oder neue Felder zu erstellen. Die Ergebnisse der Transformationen werden zusammen mit den Protokolleintragungsbedingungen verwendet, um zu bewerten, welche Protokolleinträge während der Protokollverarbeitung aus dem Datensatz herausgefiltert werden.

Nicht alle Arten von Transformationen können während der Protokollbearbeitung des Datensatzentwurfs verwendet werden.

## Filtern von Protokollen {#section-6172ca0fb0eb4177925151bb49fdbc02}

Der Datensatz enthält mehrere Parameter, mit denen die Daten gefiltert werden, die aus den Transformationen abgeleitet werden. Mit der Filterung wird angegeben, welche Protokolleinträge in den nachfolgenden Verarbeitungsschritten verwendet werden. Zum Beispiel können Filter durch den Zeitraum, den Status der Antwort des Servers oder IP-Adresse und Benutzeragenten-Informationen definiert werden. Der [!DNL Log Entry Condition] Filtertest ist anpassbar. Der Test sucht nach bestimmten Bedingungen in den Feldern der einzelnen Protokolleinträge, um festzustellen, ob dieser Eintrag im Datensatzaufbau weitergeführt werden soll. Wenn ein Protokolleintrag die Bedingung nicht erfüllt, wird der Eintrag aus dem Konstruktionsprozess entfernt.

## Felder für Transformationen identifizieren {#section-eef98ca723e54547b887aefdf0514c47}

Wenn ein Datenfeld zur weiteren Verarbeitung von der Protokollverarbeitungsphase zur Transformationsphase übergeben werden soll, müssen Sie es bei der Protokollverarbeitung identifizieren. Diese Anforderung gilt unabhängig davon, ob das Feld aus den Protokollquellen verfügbar ist oder aus Datentransformationen erstellt wurde, die während der Protokollverarbeitung auf die Daten angewendet wurden.

<!--
c_transformation.xml
-->

Während der Umwandlungsphase der Datensatzkonstruktion erfolgt die Verarbeitung der gruppierten und geordneten Daten, die aus der Protokollverarbeitung ausgegeben werden. Es werden zusätzliche Datentransformationen durchgeführt und erweiterte Datendimensionen für die Verwendung in Ihren Analysen erstellt. Während der Transformationsphase können Sie auf ein statistisches Muster der Daten zugreifen, das größer wird, wenn sich die Transformationsphase dem Abschluss nähert.

## Definieren von Transformationen {#section-001b3fd4c1dd4dd38a5536872bc9de68}

Sie können Transformationen definieren, die während der Konvertierungsphase des Datensatzentwurfs verwendet werden sollen, um die Erstellung der erweiterten Dimensionen zu erleichtern. Jede Transformation wird auf jeden Ereignisdatensatz (Protokolleintrag) angewendet, der aus der Protokollverarbeitung übergeben wird.

## Filtern von Protokollen {#section-3fed0a00ca344a719b5e8db363f64f06}

Die Variable [!DNL Log Entry Condition] kann während der Transformation angewendet werden, um nach bestimmten Bedingungen in den Feldern jedes Protokolleintrags zu suchen, der aus der Protokollverarbeitung stammt. Wenn ein Protokolleintrag die Bedingung nicht erfüllt, wird der Eintrag aus dem Konstruktionsprozess entfernt.

## Definieren erweiterter Dimensionen {#section-25efafd0bfc84c86b9717d453a88c91b}

Erweiterte Dimensionen sind die Endprodukte des Dataset-Aufbaus. Sie stellen Beziehungen zwischen den Protokollfeldern in den Daten dar. Sie verwenden sie zum Erstellen von Visualisierungen, zum Erstellen erweiterter Metriken oder zum Durchführen einer Analyse, um die Vorgänge und Probleme zu verstehen, die für Ihr Unternehmen spezifisch sind.
