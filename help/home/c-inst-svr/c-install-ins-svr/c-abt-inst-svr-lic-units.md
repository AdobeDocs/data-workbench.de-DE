---
description: Insight Server ist unter zwei Lizenztypen verfügbar.
solution: Insight
title: Info zu Insight Server-Lizenzeinheiten
uuid: e6a48b00-4dc1-416c-9039-01c01b86abbf
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Info zu Insight Server-Lizenzeinheiten{#about-insight-server-license-units}

Insight Server ist unter zwei Lizenztypen verfügbar.

Die folgenden beiden Lizenztypen sind verfügbar:

* [Datenverarbeitungseinheit (DPU)](../../../home/c-inst-svr/c-install-ins-svr/c-abt-inst-svr-lic-units.md#section-bf589e13cf5c43a58f8f85a457de6f65)
* [Dateiservereinheit (FSU)](../../../home/c-inst-svr/c-install-ins-svr/c-abt-inst-svr-lic-units.md#section-8f3a5c8521a34913bbed10f5794b1a0a)

## Datenverarbeitungseinheit (DPU) {#section-bf589e13cf5c43a58f8f85a457de6f65}

Diese Art von Daten [!DNL Insight Server] kann Daten aus einem Adobe-Datensatz verarbeiten, speichern und bereitstellen. Sie kann optional die Protokolldateien speichern, die die Quelldaten enthalten, aus denen der Datensatz erstellt wird, oder sie können diese Daten von einer [!DNL Insight Server] Dateiservereinheit (FSU) empfangen. Eine DPU ist die Art der direkten Interaktion [!DNL Insight Server] von Kunden [!DNL Insight] und [!DNL Report] Kunden.

Wenn Sie eine [!DNL Insight Server] DPU installieren, lesen Sie die [Installationsanweisungen für eine Insight Server-DPU](../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-install-proc-inst-svr-dpu.md#task-ce1ac85294604467ab750b24176d25bc).

## Dateiservereinheit (FSU) {#section-8f3a5c8521a34913bbed10f5794b1a0a}

Dieser Servertyp ist so konfiguriert, dass er Ereignisdaten von einer oder mehreren Instanzen zur Datenreplikation [!DNL Sensor] oder Ereignisreplikation ( [!DNL Repeater] Funktionen mit einer speziellen Anwenderlizenz) empfängt und speichert und die Daten an eine oder mehrere [!DNL Insight Server] Datenverarbeitungseinheiten (DPUs) für die Erstellung von Adobe-Datensätzen weiterleitet. DPUs kommunizieren mit einem FSU mit einem Protokoll, das die Übertragung von Ereignisdaten an die DPU optimiert und wesentlich schneller ist als die Verwaltung von Protokolldateien auf normalen Dateiservern. Die Verwendung eines FSU senkt außerdem die Hardwarekosten, da Protokolldaten auf kostengünstigerer Speicherhardware gespeichert werden können und dadurch die administrative Komplexität verringert wird, da mehrere Daten [!DNL Sensors] auf eine einzige verweisen können [!DNL Insight Server].

Wenn Sie eine [!DNL Insight Server] FSU installieren, lesen Sie [Installationsanweisungen für eine Insight Server-FSU](../../../home/c-inst-svr/c-install-ins-svr/t-inst-proc-fsu.md#task-e4a4a791b6694119ba45b36f3e573016).
