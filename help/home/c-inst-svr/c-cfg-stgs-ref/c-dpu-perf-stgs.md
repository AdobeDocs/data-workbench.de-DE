---
description: Anweisungen zur Optimierung der DPU-Leistung.
title: Einstellungen für die DPU-Leistung
uuid: e2b87548-7eb3-4f82-a94e-8ec7c3dc27c2
exl-id: 738c3a76-f8b4-4d84-86ee-ce9b99f50dae
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '251'
ht-degree: 7%

---

# Einstellungen für die DPU-Leistung{#dpu-performance-settings}

{{eol}}

Anweisungen zur Optimierung der DPU-Leistung.

Füllen Sie die folgenden Parameter im * aus [!DNL Insight Server] Installationsverzeichnis*\Components\DPU.cfg-Datei.

| Parameter | Beschreibung |
|---|---|
| Stapelanzahl der Ausführungen | Dies ist ein Tuning-Parameter. Der Standardwert lautet 65536. Sie können beliebig kleine Ausführungs-Batch-Zählungen angeben. Wenden Sie sich an die Adobe, bevor Sie Änderungen an diesem Wert vornehmen. |
| Ausführungs-Batches | Dies ist ein Tuning-Parameter. Der Standardwert lautet 128. Wenden Sie sich an die Adobe, bevor Sie Änderungen an diesem Wert vornehmen. |
| Durchführungszeit | Dies ist ein Tuning-Parameter. Der Standardwert ist 0,100. Wenden Sie sich an die Adobe, bevor Sie Änderungen an diesem Wert vornehmen. |
| Feld-Dump bei Fehler | Dieser Parameter kann auf true oder false gesetzt werden. Wenn auf &quot;true&quot;gesetzt, [!DNL Insight Server] erstellt eine Datei mit dem Namen [!DNL Field Dump number.txt] in seinem Trace-Verzeichnis, wenn Fehler bei der Ausführungsmaschine auftreten. Die [!DNL Field Dump] &lt; [!DNL number]> [!DNL .txt] ist für die Fehlerbehebung nützlich. |
| Profilpfad | Speicherort, an dem Dateien für alle Profile gespeichert werden sollen. Der Standardspeicherort ist Profile\. |
| Speicherbegrenzung für Abfrage | Menge an Speicher (in Byte), die [!DNL Insight Server] reserviert, um Abfrageergebnisse zu speichern. Der Standardwert ist 100000000 (100 MB). Wenn mehr Platz für Abfrageergebnisse erforderlich ist (z. B. um mehr gleichzeitige Benutzer zu ermöglichen), kann die Einstellung erhöht werden. Sie müssen jedoch weiterhin die [!DNL Insight Server’s] Speicherlast. |
| Statuspfad | Speicherort der Systemstatusdateien. Der Standardspeicherort ist Status\. |
| Threads | Ein Leistungsparameter für [!DNL Insight Server] Maschinen mit mehreren Prozessoren. Im Allgemeinen sollte dieser Wert für jedes N-Core-System auf n gesetzt werden. Der Standardwert ist 1. |
| Benutzerpfad | Speicherort der Dateien autorisierter Benutzer. Der Standardspeicherort ist Benutzer\. |
