---
description: Sie können das Erscheinungsbild von Menüs anpassen, einschließlich des Menüs im Arbeitsbereich-Fenster (Zugriff durch Rechtsklick in einem beliebigen Arbeitsbereich) und der Menüs, in denen Metriken, Dimensionen und Zuordnungsebenen aufgelistet werden.
title: Anpassung von Menüs
uuid: 8c409c50-40b3-4de3-8048-a825ef4d75f5
exl-id: 7a377d9c-d339-43d8-a71a-a322416b2e60
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 2%

---

# Anpassung von Menüs{#customize-a-menu}

Sie können das Erscheinungsbild von Menüs anpassen, einschließlich des Menüs im Arbeitsbereich-Fenster (Zugriff durch Rechtsklick in einem beliebigen Arbeitsbereich) und der Menüs, in denen Metriken, Dimensionen und Zuordnungsebenen aufgelistet werden.

Die Hierarchie eines Menüs spiegelt die Struktur des Ordners im [!DNL Profile Manager] wider. Beispielsweise spiegelt das Menü des Arbeitsflächenfensters die Struktur des Menüverzeichnisses wider, und das Menü &quot;Metriken&quot;spiegelt die Struktur des Ordners &quot;Metriken&quot;wider. Für jedes Menü kann der entsprechende Ordner die folgenden Elemente enthalten:

* **Dateien:** Diese Dateien stellen die Visualisierungen, Legenden, Anmerkungen, Verwaltungsschnittstellen, Metriken, Dimensionen oder Zuordnungsebenen dar, die Sie durch Klicken auf das entsprechende Menüelement öffnen können.
* **Eine  [!DNL order.txt] Datei:** Diese Datei gibt an, in welcher Reihenfolge die Elemente im Menü angezeigt werden.
* **Unterordner:** Jeder Unterordner stellt ein Untermenü dar. Jeder Unterordner kann eigene Dateien, Unterordner und [!DNL order.txt]-Dateien enthalten.

Beispielsweise enthält das Menü [!DNL Add Legend] die Menüelemente Metrik, Farbe, Wert und Konfidenz in dieser Reihenfolge. Im Vergleich dazu enthält der Ordner &quot;Menü\Hinzufügen Legende&quot;im Ordner [!DNL Profile Manager] die Dateien [!DNL Color.vw], [!DNL Confidence.vw], [!DNL Metric.vw] und [!DNL Value.vw] in alphabetischer Reihenfolge sowie eine [!DNL order.txt]-Datei, um die Reihenfolge der anderen Dateien zu steuern.
