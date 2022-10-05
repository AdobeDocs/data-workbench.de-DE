---
description: Sie können das Erscheinungsbild der Menüs anpassen, einschließlich des Arbeitsbereichfensters (Zugriff durch Rechtsklick in einem beliebigen Arbeitsbereich) und der Menüs, die Metriken, Dimensionen und Zuordnungsebenen auflisten.
title: Anpassung von Menüs
uuid: 8c409c50-40b3-4de3-8048-a825ef4d75f5
exl-id: 7a377d9c-d339-43d8-a71a-a322416b2e60
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 2%

---

# Anpassung von Menüs{#customize-a-menu}

{{eol}}

Sie können das Erscheinungsbild der Menüs anpassen, einschließlich des Arbeitsbereichfensters (Zugriff durch Rechtsklick in einem beliebigen Arbeitsbereich) und der Menüs, die Metriken, Dimensionen und Zuordnungsebenen auflisten.

Die Hierarchie eines Menüs spiegelt die Struktur seines Verzeichnisses im [!DNL Profile Manager]. Beispielsweise spiegelt das Menü im Arbeitsbereich-Fenster die Struktur des Menüverzeichnisses wider und das Menü &quot;Metriken&quot;spiegelt die Struktur des Ordners Metriken wider. Für jedes Menü kann der entsprechende Ordner die folgenden Elemente enthalten:

* **Dateien:** Diese Dateien stellen die Visualisierungen, Legenden, Anmerkungen, Verwaltungsschnittstellen, Metriken, Dimensionen oder Zuordnungsebenen dar, die Sie durch Klicken auf das entsprechende Menüelement öffnen können.
* **Ein [!DNL order.txt] Datei:** Diese Datei gibt an, in welcher Reihenfolge das Menü seine Elemente anzeigt.
* **Unterverzeichnisse:** Jedes Unterverzeichnis stellt ein Untermenü dar. Jedes Unterverzeichnis kann eigene Dateien, Unterverzeichnisse und [!DNL order.txt] -Datei.

Beispiel: die [!DNL Add Legend] enthält die Menüelemente Metrik, Farbe, Wert und Konfidenz in dieser Reihenfolge. Im Vergleich dazu befindet sich im Ordner Menü\Legende hinzufügen im [!DNL Profile Manager] enthält die Dateien [!DNL Color.vw], [!DNL Confidence.vw], [!DNL Metric.vw]und [!DNL Value.vw] Dateien in alphabetischer Reihenfolge sowie eine [!DNL order.txt] -Datei, um die Reihenfolge der anderen Dateien zu steuern.
