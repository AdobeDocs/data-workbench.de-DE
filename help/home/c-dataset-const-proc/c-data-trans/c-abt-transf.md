---
description: Mithilfe von Transformationen können Sie verfügbare Informationen in Ihren Datendateien extrahieren und in einem nützlicheren Formular bearbeiten.
solution: Analytics
title: Grundlagen zu Transformationen
topic: Data workbench
uuid: 9366f607-741d-4512-9e1b-4165f4291246
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Grundlagen zu Transformationen{#about-transformations}

Mithilfe von Transformationen können Sie verfügbare Informationen in Ihren Datendateien extrahieren und in einem nützlicheren Formular bearbeiten.

Die Transformationen werden auf den Protokolleinträgen (Protokolleinträge sind Datenzeilen) in Ihren Protokollquellen ausgeführt. Für jede Datenzeile nimmt die Transformation den Wert des angegebenen Eingabefelds, führt eine Reihe von Verarbeitungsschritten aus und zeichnet das Ergebnis im angegebenen Ausgabefeld auf. Sie können Transformationen definieren, die entweder während der Protokollverarbeitungs- oder Transformationsphase des Datensatzerstellungsprozesses ausgeführt werden sollen:

* **Während der Protokollverarbeitung:** Transformationen, die während der Protokollverarbeitungsphase der Datensatzkonstruktion ausgeführt werden, werden auf jeden Ereignisdatensatz (Protokolleintrag) angewendet, um vorhandene Protokollfelder zu aktualisieren oder neue Felder zu erzeugen. Die Ergebnisse der Transformationen werden zusammen mit den Protokolleintragungsbedingungen verwendet, um zu bewerten, welche Protokolleinträge während der Protokollverarbeitung aus dem Datensatz herausgefiltert werden.
* **Während der Transformation:** Transformationen, die während der Umwandlungsphase der Datensatzkonstruktion ausgeführt werden, werden auf den Feldern der Daten ausgeführt, die von der Protokollverarbeitung übergeben werden, um erweiterte Dimensionen zu erstellen, die Sie in Ihren Analysen verwenden können. Siehe [Erweiterte Dimensionen](../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md).

>[!NOTE]
>
>Die Dateneingabe zur Konvertierung aus der Protokollverarbeitung wird nach Zeit geordnet und nach der Tracking-ID in den Quelldaten gruppiert. Für mehrere Konvertierungen ist es erforderlich, dass die Daten in diesem Formular vorliegen und nur funktionieren, wenn sie während der Transformation definiert werden.

Änderungen der Transformationen müssen mit Vorsicht vorgenommen werden. Die Transformationen beeinflussen nicht, welche Protokolleinträge in den Dataset-Aufbau fließen, sondern beeinflussen die dargestellten Ergebnisse. Auf diese Weise können Änderungen an der Analyse vorgenommen werden, ohne dass die Daten, auf denen die Analyse basiert, geändert werden. Änderungen an Transformationen können jedoch die in Analysen erzeugten Werte grundlegend verändern.
