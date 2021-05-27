---
description: Sie können das Erscheinungsbild der Menüs anpassen, einschließlich des Arbeitsbereichfensters (Zugriff durch Rechtsklick in einem beliebigen Arbeitsbereich) und der Menüs, die Metriken, Dimensionen und Zuordnungsebenen auflisten.
title: Anpassung von Menüs
uuid: 8c409c50-40b3-4de3-8048-a825ef4d75f5
exl-id: 7a377d9c-d339-43d8-a71a-a322416b2e60
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 2%

---

# Anpassung von Menüs{#customize-a-menu}

Sie können das Erscheinungsbild der Menüs anpassen, einschließlich des Arbeitsbereichfensters (Zugriff durch Rechtsklick in einem beliebigen Arbeitsbereich) und der Menüs, die Metriken, Dimensionen und Zuordnungsebenen auflisten.

Die Hierarchie eines Menüs spiegelt die Struktur seines Verzeichnisses im [!DNL Profile Manager] wider. Beispielsweise spiegelt das Menü im Arbeitsbereich-Fenster die Struktur des Menüverzeichnisses wider und das Menü &quot;Metriken&quot;spiegelt die Struktur des Ordners Metriken wider. Für jedes Menü kann der entsprechende Ordner die folgenden Elemente enthalten:

* **Dateien:** Diese Dateien stellen die Visualisierungen, Legenden, Anmerkungen, Verwaltungsschnittstellen, Metriken, Dimensionen oder Zuordnungsebenen dar, die Sie öffnen können, indem Sie auf das entsprechende Menüelement klicken.
* **Eine  [!DNL order.txt] Datei:**  Diese Datei gibt an, in welcher Reihenfolge die Elemente im Menü angezeigt werden.
* **Unterverzeichnisse:** Jedes Unterverzeichnis stellt ein Untermenü dar. Jedes Unterverzeichnis kann eigene Dateien, Unterverzeichnisse und die Datei [!DNL order.txt] enthalten.

Beispielsweise enthält das Menü [!DNL Add Legend] die Menüelemente Metrik, Farbe, Wert und Konfidenz in dieser Reihenfolge. Im Vergleich dazu enthält das Verzeichnis Menu\Add Legend im Ordner [!DNL Profile Manager] die Dateien [!DNL Color.vw], [!DNL Confidence.vw], [!DNL Metric.vw] und [!DNL Value.vw] in alphabetischer Reihenfolge sowie die Datei [!DNL order.txt], um die Reihenfolge der anderen Dateien zu steuern.
