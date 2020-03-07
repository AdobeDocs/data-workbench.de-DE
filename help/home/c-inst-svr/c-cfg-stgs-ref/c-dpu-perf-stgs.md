---
description: Anweisungen zum Einstellen der DPU-Leistung.
solution: Insight
title: DPU-Leistungseinstellungen
uuid: e2b87548-7eb3-4f82-a94e-8ec7c3dc27c2
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# DPU-Leistungseinstellungen{#dpu-performance-settings}

Anweisungen zum Einstellen der DPU-Leistung.

Füllen Sie die folgenden Parameter in der Datei * [!DNL Insight Server] Installationsordner*\Components\DPU.cfg aus.

| Parameter | Beschreibung |
|---|---|
| Stapelzählung der Ausführung | Dies ist ein Abstimmungsparameter. Der Standardwert lautet 65536. Sie können beliebig kleine Ausführungsstapelzahlen angeben. Wenden Sie sich an Adobe, bevor Sie Änderungen an diesem Wert vornehmen. |
| Ausführungsstapel | Dies ist ein Abstimmungsparameter. Der Standardwert lautet 128. Wenden Sie sich an Adobe, bevor Sie Änderungen an diesem Wert vornehmen. |
| Ausführungszeit | Dies ist ein Abstimmungsparameter. Der Standardwert ist 0.100. Wenden Sie sich an Adobe, bevor Sie Änderungen an diesem Wert vornehmen. |
| Feld-Dump bei Fehler | Dieser Parameter kann auf true oder false eingestellt werden. Wenn &quot;true&quot;festgelegt ist, [!DNL Insight Server] wird bei jeder Ausführung von Engine-Fehlern eine Datei mit dem Namen [!DNL Field Dump number.txt] im Trace-Ordner erstellt. Das [!DNL Field Dump] &lt; [!DNL number]> [!DNL .txt] ist zur Fehlerbehebung nützlich. |
| Profilpfad | Speicherort, an dem Dateien für alle Profile gespeichert werden. Der Standardspeicherort ist &quot;Profile\&quot;. |
| Speicherbeschränkung für Abfrage | Speicherkapazität (in Byte), die für die Speicherung der Abfrageergebnisse [!DNL Insight Server] reserviert ist. Der Standardwert ist 100000000 (100 MB). Wenn mehr Speicherplatz für die Abfrageergebnisse erforderlich ist (z. B. um mehr gleichzeitige Benutzer zuzulassen), kann die Einstellung erhöht werden, Sie müssen jedoch die [!DNL Insight Server’s] Speicherlast weiterhin überprüfen. |
| Statuspfad | Speicherort der Systemstatusdateien. Der Standardspeicherort ist State\. |
| Threads | Ein Leistungsoptimierungsparameter für [!DNL Insight Server] Computer mit mehreren Prozessoren. In der Regel sollte dieser Wert für alle n-Core-Systeme auf n eingestellt werden. Der Standardwert ist 1. |
| Benutzerpfad | Speicherort der Dateien autorisierter Benutzer. Der Standardspeicherort ist Benutzer\. |

