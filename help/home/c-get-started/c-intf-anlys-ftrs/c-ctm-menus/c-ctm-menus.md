---
description: Sie können das Erscheinungsbild von Menüs anpassen, einschließlich des Menüs im Arbeitsbereich-Fenster (Zugriff durch Rechtsklick in einem beliebigen Arbeitsbereich) und der Menüs, in denen Metriken, Dimensionen und Zuordnungsebenen aufgelistet werden.
solution: Analytics
title: Menü anpassen
topic: Data workbench
uuid: 8c409c50-40b3-4de3-8048-a825ef4d75f5
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Menü anpassen{#customize-a-menu}

Sie können das Erscheinungsbild von Menüs anpassen, einschließlich des Menüs im Arbeitsbereich-Fenster (Zugriff durch Rechtsklick in einem beliebigen Arbeitsbereich) und der Menüs, in denen Metriken, Dimensionen und Zuordnungsebenen aufgelistet werden.

Die Hierarchie eines Menüs spiegelt die Struktur seines Ordners im [!DNL Profile Manager]. Beispielsweise spiegelt das Menü des Arbeitsflächenfensters die Struktur des Menüverzeichnisses wider, und das Menü &quot;Metriken&quot;spiegelt die Struktur des Ordners &quot;Metriken&quot;wider. Für jedes Menü kann der entsprechende Ordner die folgenden Elemente enthalten:

* **Dateien:** Diese Dateien stellen die Visualisierungen, Legenden, Anmerkungen, Verwaltungsschnittstellen, Metriken, Dimensionen oder Zuordnungsebenen dar, die Sie öffnen können, indem Sie auf den entsprechenden Menüpunkt klicken.
* **Eine[!DNL order.txt]Datei:** Diese Datei gibt an, in welcher Reihenfolge die Elemente im Menü angezeigt werden.
* **Unterordner:** Jeder Unterordner stellt ein Untermenü dar. Jeder Unterordner kann eigene Dateien, Unterordner und [!DNL order.txt] Dateien enthalten.

Beispielsweise enthält das [!DNL Add Legend] Menü die Menüelemente Metrik, Farbe, Wert und Konfidenz in dieser Reihenfolge. Im Vergleich dazu enthält der Ordner &quot;Menü\Legende hinzufügen&quot;in der [!DNL Profile Manager] Datei die Dateien [!DNL Color.vw], [!DNL Confidence.vw]und [!DNL Metric.vw]die [!DNL Value.vw] Dateien in alphabetischer Reihenfolge sowie eine [!DNL order.txt] Datei zur Steuerung der Reihenfolge der anderen Dateien.
