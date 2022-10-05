---
description: Mithilfe von Umwandlungen können Sie die in Ihren Datendateien verfügbaren Informationen extrahieren und in ein nützlicheres Formular umwandeln.
title: Über Umwandlungen
uuid: 9366f607-741d-4512-9e1b-4165f4291246
exl-id: 9bd533ef-a87e-400a-9bb0-5af1851cca0a
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '307'
ht-degree: 1%

---

# Über Umwandlungen{#about-transformations}

{{eol}}

Mithilfe von Umwandlungen können Sie die in Ihren Datendateien verfügbaren Informationen extrahieren und in ein nützlicheres Formular umwandeln.

Umwandlungen beziehen sich auf die Protokolleinträge (Sie können sich Protokolleinträge als Datenzeilen vorstellen) in Ihren Protokollquellen. Für jede Datenzeile nimmt die Umwandlung den Wert des angegebenen Eingabefelds an, führt eine Reihe von Verarbeitungsschritten durch und zeichnet das Ergebnis im von Ihnen angegebenen Ausgabefeld auf. Sie können Umwandlungen definieren, die entweder während der Protokollverarbeitungs- oder Transformationsphase des Datensatzerstellungsprozesses ausgeführt werden sollen:

* **Während der Protokollverarbeitung:** Während der Protokollverarbeitungsphase der Datensatzerstellung ausgeführte Umwandlungen werden auf jeden Ereignisdatensatz (Protokolleintrag) angewendet, um vorhandene Protokollfelder zu aktualisieren oder neue Felder zu erstellen. Die Ergebnisse der Transformationen werden zusammen mit den Protokolleintragsbedingungen verwendet, um zu bewerten, welche Protokolleinträge während der Protokollverarbeitung aus dem Datensatz herausgefiltert werden.
* **Während der Umwandlung:** Umwandlungen, die während der Umwandlungsphase der Datensatzerstellung ausgeführt werden, beziehen sich auf die von der Protokollverarbeitung übergebenen Datenfelder, um erweiterte Dimensionen zu erstellen, die Sie in Ihren Analysen verwenden können. Siehe [Erweiterte Dimensionen](../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md).

>[!NOTE]
>
>Die Dateneingabe zur Transformation aus der Protokollverarbeitung wird nach Zeit geordnet und nach der Tracking-ID in Ihren Quelldaten gruppiert. Bei mehreren Umwandlungen müssen die Daten in diesem Formular vorliegen und nur funktionieren, wenn sie während der Transformation definiert wurden.

Änderungen an Transformationen müssen mit Vorsicht vorgenommen werden. Umwandlungen beeinflussen nicht, welche Protokolleinträge in den Prozess der Datensatzerstellung fließen, sondern beeinflussen die angezeigten Ergebnisse. Dadurch können Änderungen an dem, was analysiert wird, vorgenommen werden, ohne die Daten zu ändern, auf denen die Analyse basiert. Änderungen bei Umwandlungen können jedoch die in Analysen erzeugten Werte grundlegend verändern.
