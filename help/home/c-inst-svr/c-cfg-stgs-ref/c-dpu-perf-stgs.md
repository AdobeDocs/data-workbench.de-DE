---
description: Anweisungen zum Einstellen der DPU-Leistung.
title: Einstellungen für die DPU-Leistung
uuid: e2b87548-7eb3-4f82-a94e-8ec7c3dc27c2
exl-id: 738c3a76-f8b4-4d84-86ee-ce9b99f50dae
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '251'
ht-degree: 6%

---

# Einstellungen für die DPU-Leistung{#dpu-performance-settings}

Anweisungen zum Einstellen der DPU-Leistung.

Füllen Sie die folgenden Parameter in der Datei * [!DNL Insight Server] Installationsordner*\Components\DPU.cfg aus.

| Parameter | Beschreibung |
|---|---|
| Stapelzählung der Ausführung | Dies ist ein Abstimmungsparameter. Der Standardwert lautet 65536. Sie können beliebig kleine Ausführungsstapelzahlen angeben. Bitte kontaktieren Sie Adobe, bevor Sie Änderungen an diesem Wert vornehmen. |
| Ausführungsstapel | Dies ist ein Abstimmungsparameter. Der Standardwert lautet 128. Bitte kontaktieren Sie Adobe, bevor Sie Änderungen an diesem Wert vornehmen. |
| Ausführungszeit | Dies ist ein Abstimmungsparameter. Der Standardwert ist 0.100. Bitte kontaktieren Sie Adobe, bevor Sie Änderungen an diesem Wert vornehmen. |
| Feld-Dump bei Fehler | Dieser Parameter kann auf true oder false eingestellt werden. Bei Festlegung auf &quot;true&quot;erstellt [!DNL Insight Server] im Trace-Ordner eine Datei mit dem Namen [!DNL Field Dump number.txt], wenn Fehler bei der Ausführung von Engine auftreten. Die [!DNL Field Dump] &lt; [!DNL number] [!DNL .txt] ist für die Fehlerbehebung nützlich. |
| Profil-Pfad | Speicherort, an dem Dateien für alle Profil gespeichert werden. Der Standardspeicherort ist Profile\. |
| Speicherbeschränkung für Abfrage | Speichermenge (in Byte), die [!DNL Insight Server] reserviert wird, um die Ergebnisse der Abfrage zu speichern. Der Standardwert ist 100000000 (100 MB). Wenn mehr Speicherplatz für die Abfrage erforderlich ist (z. B. um mehr gleichzeitige Benutzer zuzulassen), kann die Einstellung erhöht werden, Sie müssen jedoch weiterhin die Speicherlast von [!DNL Insight Server’s] überprüfen. |
| Statuspfad | Speicherort der Systemstatusdateien. Der Standardspeicherort ist State\. |
| Threads | Ein Leistungs-Abstimmungsparameter für [!DNL Insight Server]-Computer mit mehreren Prozessoren. In der Regel sollte dieser Wert für alle n-Core-Systeme auf n eingestellt werden. Der Standardwert ist 1. |
| Benutzerpfad | Speicherort der Dateien autorisierter Benutzer. Der Standardspeicherort ist Benutzer\. |
