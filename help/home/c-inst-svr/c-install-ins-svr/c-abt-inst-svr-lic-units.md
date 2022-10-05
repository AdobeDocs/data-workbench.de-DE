---
description: Insight Server ist unter zwei Lizenztypen verfügbar.
title: Über Insight Server License Units
uuid: e6a48b00-4dc1-416c-9039-01c01b86abbf
exl-id: 82d6fa29-d36e-480d-a975-f5a5e60a32d2
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 7%

---

# Über Insight Server License Units{#about-insight-server-license-units}

{{eol}}

Insight Server ist unter zwei Lizenztypen verfügbar.

Die beiden Lizenztypen lauten wie folgt:

* [Datenverarbeitungseinheit (DPU)](../../../home/c-inst-svr/c-install-ins-svr/c-abt-inst-svr-lic-units.md#section-bf589e13cf5c43a58f8f85a457de6f65)
* [File Server Unit (FSU)](../../../home/c-inst-svr/c-install-ins-svr/c-abt-inst-svr-lic-units.md#section-8f3a5c8521a34913bbed10f5794b1a0a)

## Datenverarbeitungseinheit (DPU) {#section-bf589e13cf5c43a58f8f85a457de6f65}

Diese Art von [!DNL Insight Server] kann Daten aus einem Adobe-Datensatz verarbeiten, speichern und bereitstellen. Optional kann es die Protokolldateien speichern, die die Quelldaten enthalten, aus denen der Datensatz erstellt wird, oder diese Daten von einem [!DNL Insight Server] File Server Unit (FSU). Eine DPU ist der Typ [!DNL Insight Server] mit [!DNL Insight] und [!DNL Report] Clients interagieren direkt.

Wenn Sie eine [!DNL Insight Server] DPU, siehe [Installationsverfahren für eine Insight Server-DPU](../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-install-proc-inst-svr-dpu.md#task-ce1ac85294604467ab750b24176d25bc).

## File Server Unit (FSU) {#section-8f3a5c8521a34913bbed10f5794b1a0a}

Dieser Servertyp ist so konfiguriert, dass Ereignisdaten von einem oder mehreren [!DNL Sensor] oder Ereignisdatenreplikationsinstanzen ( [!DNL Repeater] -Funktion, die mit einer speziellen Nutzungslizenz bereitgestellt wird) und das Streamen der Daten an eine oder mehrere [!DNL Insight Server] Datenverarbeitungseinheiten (DPUs) zum Erstellen von Adobe-Datensätzen. DPUs kommunizieren mit einer FSU mithilfe eines Protokolls, das die Übertragung von Ereignisdaten an die DPU optimiert und deutlich schneller ist als die Wartung von Protokolldateien auf normalen Dateiservern. Die Verwendung einer FSU senkt auch die Hardware-Kosten, da sie die Speicherung von Protokolldaten auf kostengünstigeren Speicher-Hardware ermöglicht und die administrative Komplexität verringert, da mehrere [!DNL Sensors] , um auf eine einzelne [!DNL Insight Server].

Wenn Sie eine [!DNL Insight Server] FSU, siehe [Installationsverfahren für eine Insight Server-FSU](../../../home/c-inst-svr/c-install-ins-svr/t-inst-proc-fsu.md#task-e4a4a791b6694119ba45b36f3e573016).
