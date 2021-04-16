---
description: Mithilfe von Transformationen können Sie verfügbare Informationen in Ihren Datendateien extrahieren und in einem nützlicheren Formular bearbeiten.
title: Über Umwandlungen
uuid: 9366f607-741d-4512-9e1b-4165f4291246
exl-id: 9bd533ef-a87e-400a-9bb0-5af1851cca0a
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '307'
ht-degree: 1%

---

# Über Umwandlungen{#about-transformations}

Mithilfe von Transformationen können Sie verfügbare Informationen in Ihren Datendateien extrahieren und in einem nützlicheren Formular bearbeiten.

Die Transformationen werden auf den Protokolleinträgen (Protokolleinträge sind Datenzeilen) in Ihren Protokollquellen ausgeführt. Für jede Datenzeile nimmt die Transformation den Wert des angegebenen Eingabefelds, führt eine Reihe von Verarbeitungsschritten aus und zeichnet das Ergebnis im angegebenen Ausgabefeld auf. Sie können Transformationen definieren, die entweder während der Protokollverarbeitungs- oder Transformationsphase des Datensatzerstellungsprozesses ausgeführt werden sollen:

* **Während der Protokollverarbeitung: Während der Protokollbearbeitung werden** Transformationen auf jeden Ereignis-Datensatz (Protokolleintrag) angewendet, um vorhandene Protokollfelder zu aktualisieren oder neue  zu erstellen. Die Ergebnisse der Transformationen werden zusammen mit den Protokolleintragungsbedingungen verwendet, um zu bewerten, welche Protokolleinträge während der Protokollverarbeitung aus dem Datensatz herausgefiltert werden.
* **Während der Transformation:** Transformationen, die während der Konvertierungsphase der Datensatzkonstruktion ausgeführt werden, arbeiten mit den Feldern der Daten, die von der Protokollverarbeitung übergeben werden, um erweiterte Dimensionen zu erstellen, die Sie in Ihren Analysen verwenden können. Siehe [Erweiterte Dimensionen](../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md).

>[!NOTE]
>
>Die Dateneingabe zur Konvertierung aus der Protokollverarbeitung wird nach Zeit geordnet und nach der Tracking-ID in den Quelldaten gruppiert. Für mehrere Konvertierungen ist es erforderlich, dass die Daten in diesem Formular vorliegen und nur funktionieren, wenn sie während der Transformation definiert werden.

Änderungen der Transformationen müssen mit Vorsicht vorgenommen werden. Die Transformationen beeinflussen nicht, welche Protokolleinträge in den Dataset-Aufbau fließen, sondern beeinflussen die dargestellten Ergebnisse. Auf diese Weise können Änderungen an der Analyse vorgenommen werden, ohne dass die Daten geändert werden, auf denen die Analyse basiert. Änderungen an Transformationen können jedoch die in Analysen erzeugten Werte grundlegend verändern.
