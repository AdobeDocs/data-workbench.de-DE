---
description: Insight Server ist unter zwei Lizenztypen verfügbar.
solution: Analytics
title: Über Insight Server License Units
uuid: e6a48b00-4dc1-416c-9039-01c01b86abbf
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 7%

---


# Über Insight Server License Units{#about-insight-server-license-units}

Insight Server ist unter zwei Lizenztypen verfügbar.

Die folgenden beiden Lizenztypen sind verfügbar:

* [Datenverarbeitungseinheit (DPU)](../../../home/c-inst-svr/c-install-ins-svr/c-abt-inst-svr-lic-units.md#section-bf589e13cf5c43a58f8f85a457de6f65)
* [File Server Unit (FSU)](../../../home/c-inst-svr/c-install-ins-svr/c-abt-inst-svr-lic-units.md#section-8f3a5c8521a34913bbed10f5794b1a0a)

## Datenverarbeitungseinheit (DPU) {#section-bf589e13cf5c43a58f8f85a457de6f65}

Diese Art von Daten [!DNL Insight Server] kann Daten aus einem Adobe-Datensatz verarbeiten, speichern und bereitstellen. It optionally can store the log files that contain the source data from which the dataset is constructed, or it can receive that data from an [!DNL Insight Server] File Server Unit (FSU). Eine DPU ist die Art der direkten Interaktion [!DNL Insight Server] von Kunden [!DNL Insight] und [!DNL Report] Kunden.

Wenn Sie eine [!DNL Insight Server] DPU installieren, lesen Sie die [Installationsanweisungen für eine Insight Server-DPU](../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-install-proc-inst-svr-dpu.md#task-ce1ac85294604467ab750b24176d25bc).

## File Server Unit (FSU) {#section-8f3a5c8521a34913bbed10f5794b1a0a}

Dieser Servertyp ist so konfiguriert, dass er Ereignis-Daten von einer oder mehreren Instanzen der Datenreplikation [!DNL Sensor] oder des Ereignisses (Funktionen mit einer speziellen Anwenderlizenz) empfängt und speichert und die Daten an einen oder mehrere Datenverarbeitungseinheiten ( [!DNL Repeater] [!DNL Insight Server] Data Processing Units, DPUs) für die Erstellung von Adobe-Datasets weiterleitet. DPUs kommunizieren mit einem FSU mit einem Protokoll, das die Übertragung von Ereignis-Daten an die DPU optimiert und wesentlich schneller ist als die Verwaltung von Protokolldateien auf normalen Dateiservern. The use of an FSU also reduces hardware costs by enabling log data to be stored on lower cost storage hardware and reduces administrative complexity by allowing multiple [!DNL Sensors] to point to a single [!DNL Insight Server].

Wenn Sie eine [!DNL Insight Server] FSU installieren, lesen Sie [Installationsanweisungen für eine Insight Server-FSU](../../../home/c-inst-svr/c-install-ins-svr/t-inst-proc-fsu.md#task-e4a4a791b6694119ba45b36f3e573016).
