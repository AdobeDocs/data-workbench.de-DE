---
description: Ein Adobe-Datensatz enthält die Daten, die vom Data Workbench-Server geladen und verarbeitet wurden.
title: Grundlagen zum Aufbau von Datensätzen
uuid: 540d159d-3f72-49dd-9929-107f1fc62b2b
exl-id: 111e98b5-d899-4f79-90ce-70f520d527d6
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '937'
ht-degree: 0%

---

# Grundlagen zum Aufbau von Datensätzen{#understanding-dataset-construction}

Ein Adobe-Datensatz enthält die Daten, die vom Data Workbench-Server geladen und verarbeitet wurden.

Die Schritte beim Laden und Verarbeiten der Daten durch den Data Workbench-Server (InsightServer64.exe) bilden den Prozess der Datensatzerstellung.

>[!NOTE]
>
>Ein Data Workbench-Server, der Daten aus einem Adobe-Datensatz verarbeitet und bereitstellt, wird als Datenverarbeitungseinheit oder DPU bezeichnet. Er wird manchmal auch als Verarbeitungs- oder Abfrageserver bezeichnet. Data Workbench- und [!DNL Report]-Clients interagieren direkt mit DPUs.

Bei der Erstellung von Datensätzen liest der Data Workbench-Server Quelldaten aus Protokollquellen, wendet Transformationen auf bestimmte Datenfelder an und definiert erweiterte Dimensionen, die aus den umgewandelten Feldern erstellt werden sollen. Der Bauvorgang erfolgt in zwei Phasen: *Protokollverarbeitung* und *Umwandlung*. Nachdem der Datensatz erstellt wurde, können Sie die erweiterten Dimensionen des Datensatzes verwenden, um abgeleitete Metriken und Dimensionen für Ihre spezifischen Analysezwecke zu erstellen.

Die Datensatzerstellung ist wie ein Herstellungsprozess. Sie wählen die zum Erstellen des Datensatzes zu verwendenden Daten (die Rohstoffe) aus und definieren die Datenumwandlungen (die Prozessschritte), mit denen die in den Daten verfügbaren Informationen bearbeitet werden, um erweiterte Dimensionen (die hergestellten Produkte) zu erstellen.

<!--
c_log_proc.xml
-->

Die Logs werden gefiltert und die Datenfelder, die an die Umwandlungsphase übergeben werden sollen, werden identifiziert. Am Ende der Protokollverarbeitungsphase werden die Daten nach Tracking-ID gruppiert (d. h. alle Protokolleinträge mit derselben Tracking-ID werden gruppiert) und in der richtigen Zeit angeordnet. Während der Protokollverarbeitungsphase können Sie nicht auf die verarbeiteten Daten zugreifen, die für die Analyse verwendet werden sollen.

## Festlegen von Protokollquellen {#section-75279dd6a7304d469735562796741d0f}

Protokollquellen sind Dateien, die die Daten enthalten, die zum Erstellen eines Datensatzes verwendet werden sollen. Die in den Protokollquellen verfügbaren Daten werden als Ereignisdaten bezeichnet, da jeder Datensatz einen Transaktionsdatensatz oder eine einzelne Instanz eines Ereignisses darstellt. Darüber hinaus enthält jeder Datensatz bzw. jeder Protokolleintrag einen Wert, der als Tracking-ID bezeichnet wird.

>[!NOTE]
>
>Stellen Sie bei der Auswahl von Protokollquellen sicher, dass jeder Protokolleintrag eine Tracking-ID für die Entität enthält, die die höchste Ebene darstellt, auf der Ihre Daten gruppiert werden sollen. Wenn Sie beispielsweise mit Daten arbeiten, die aus dem Website-Traffic erfasst wurden, wählen Sie wahrscheinlich Besucher als diese Entität aus. Jeder Besucher verfügt über eine eindeutige Tracking-ID, und alle Daten zu einem bestimmten Site-Besucher können gruppiert werden. Wenden Sie sich für Unterstützung an die Adobe.

Ereignisdaten aus Protokollquellen werden in Echtzeit von [!DNL Sensors] erfasst oder aus archivierten Datenquellen von Insight Server extrahiert. Von Sensoren von HTTP und Anwendungsservern erfasste Ereignisdaten werden an Insight Server übertragen, die die Daten in hochkomprimierte Protokolldateien ( [!DNL .vsl]) konvertieren. Ereignisdaten, die sich in einer reduzierten Datei, XML-Datei oder einer ODBC-Datenquelle befinden, werden von Insight Server gelesen, der Decoder bereitstellt, die Sie definieren, um einen gemeinsamen Satz von Protokollfeldern aus diesen verschiedenen Formaten zu extrahieren.

## Definieren von Umwandlungen {#section-55a8cdb47379484081e53087f074778d}

Eine Transformation ist eine Reihe von Anweisungen, die Sie definieren können, um Informationen in den Ereignisdaten zu extrahieren oder zu bearbeiten. Jede von Ihnen definierte Umwandlung wird auf jeden Ereignisdatensatz (Protokolleintrag) angewendet, um vorhandene Protokollfelder zu aktualisieren oder neue Felder zu erstellen. Die Ergebnisse der Transformationen werden zusammen mit den Protokolleintragsbedingungen verwendet, um zu bewerten, welche Protokolleinträge während der Protokollverarbeitung aus dem Datensatz herausgefiltert werden.

Nicht alle Arten von Umwandlungen können während der Protokollverarbeitungsphase des Datensatzerstellungsprozesses verwendet werden.

## Filterprotokolle {#section-6172ca0fb0eb4177925151bb49fdbc02}

Der Datensatz enthält mehrere Parameter, die zum Filtern der aus den Transformationen stammenden Daten verwendet werden. Mit der Filterung können Sie angeben, welche Protokolleinträge in nachfolgenden Verarbeitungsschritten verwendet werden. Beispielsweise können Filter nach dem Zeitbereich, dem Status der Antwort des Servers oder nach IP-Adresse und Benutzeragenten-Informationen definiert werden. [!DNL Log Entry Condition] ist ein anpassbarer Filtertest. Der Test sucht in den Feldern jedes Protokolleintrags nach bestimmten Bedingungen, um zu bestimmen, ob dieser Eintrag im Prozess der Datensatzerstellung weiter verwendet werden soll. Wenn ein Protokolleintrag die Bedingung nicht erfüllt, wird der Eintrag aus dem Umwandlungsprozess entfernt.

## Identifizieren von Feldern für Umwandlungen {#section-eef98ca723e54547b887aefdf0514c47}

Wenn ein Datenfeld zur weiteren Verarbeitung von der Protokollverarbeitungsphase an die Umwandlungsphase übergeben werden soll, müssen Sie es während der Protokollverarbeitung identifizieren. Diese Anforderung gilt unabhängig davon, ob das Feld aus den Protokollquellen verfügbar ist oder aus Datenumwandlungen erstellt wurde, die während der Protokollverarbeitung auf die Daten angewendet werden.

<!--
c_transformation.xml
-->

Während der Umwandlungsphase der Datensatzerstellung erfolgt die Verarbeitung der gruppierten und geordneten Daten, die aus der Protokollverarbeitung ausgegeben werden. Es werden zusätzliche Datenumwandlungen durchgeführt und erweiterte Datendimensionen für die Verwendung in Ihren Analysen erstellt. Während der Transformationsphase können Sie auf eine statistische Stichprobe der Daten zugreifen, die größer wird, wenn sich die Transformationsphase dem Abschluss nähert.

## Definieren von Umwandlungen {#section-001b3fd4c1dd4dd38a5536872bc9de68}

Sie können Umwandlungen definieren, die während der Umwandlungsphase des Datensatzerstellungsprozesses verwendet werden sollen, um die Erstellung der erweiterten Dimensionen zu erleichtern. Jede Umwandlung wird auf jeden Ereignisdatensatz (Protokolleintrag) angewendet, der von der Protokollverarbeitung übergeben wird.

## Filterprotokolle {#section-3fed0a00ca344a719b5e8db363f64f06}

[!DNL Log Entry Condition] kann während der Transformation angewendet werden, um in den Feldern jedes Protokolleintrags, der aus der Protokollverarbeitung stammt, nach bestimmten Bedingungen zu suchen. Wenn ein Protokolleintrag die Bedingung nicht erfüllt, wird der Eintrag aus dem Umwandlungsprozess entfernt.

## Definieren erweiterter Dimensionen {#section-25efafd0bfc84c86b9717d453a88c91b}

Erweiterte Dimensionen sind die Endprodukte des Datensatzerstellungsprozesses. Sie stellen Beziehungen zwischen den Protokollfeldern in den Daten dar. Sie können sie verwenden, um Visualisierungen zu erstellen, erweiterte Metriken zu erstellen oder Analysen durchzuführen, um die unternehmensspezifischen Vorgänge und Probleme zu verstehen.
