---
description: Insight Server ist unter zwei Lizenztypen verfügbar.
title: Über Insight Server License Units
uuid: e6a48b00-4dc1-416c-9039-01c01b86abbf
exl-id: 82d6fa29-d36e-480d-a975-f5a5e60a32d2
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
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

Dieser Typ von [!DNL Insight Server] kann Daten aus einem Adobe-Datensatz verarbeiten, speichern und bereitstellen. Sie kann optional die Protokolldateien speichern, die die Quelldaten enthalten, aus denen der Datensatz erstellt wird, oder sie können diese Daten von einer [!DNL Insight Server] File Server Unit (FSU) empfangen. Eine DPU ist der Typ von [!DNL Insight Server], mit dem [!DNL Insight]- und [!DNL Report]-Clients direkt interagieren.

Wenn Sie eine [!DNL Insight Server] DPU installieren, finden Sie weitere Informationen unter [Installationsanweisungen für eine Insight Server-DPU](../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-install-proc-inst-svr-dpu.md#task-ce1ac85294604467ab750b24176d25bc).

## File Server Unit (FSU) {#section-8f3a5c8521a34913bbed10f5794b1a0a}

Dieser Servertyp ist so konfiguriert, dass er Ereignis-Daten von einer oder mehreren [!DNL Sensor]- oder Ereignis-Datenreplikationsinstanzen ( [!DNL Repeater]-Funktion mit einer speziellen Anwendungslizenz) empfängt und speichert und die Daten an ein oder mehrere [!DNL Insight Server] Datenverarbeitungseinheiten (DPUs) für die Erstellung von Adobe-Datasets streamen kann. DPUs kommunizieren mit einem FSU mit einem Protokoll, das die Übertragung von Ereignis-Daten an die DPU optimiert und wesentlich schneller ist als die Verwaltung von Protokolldateien auf normalen Dateiservern. Die Verwendung einer FSU senkt außerdem die Hardwarekosten, indem Protokolldaten auf kostengünstigeren Datenspeicherung gespeichert werden können, und verringert die administrative Komplexität, da mehrere [!DNL Sensors] auf ein einzelnes [!DNL Insight Server] verweisen können.

Wenn Sie eine [!DNL Insight Server]-FSU installieren, lesen Sie [Installationsanweisungen für eine Insight Server-FSU](../../../home/c-inst-svr/c-install-ins-svr/t-inst-proc-fsu.md#task-e4a4a791b6694119ba45b36f3e573016).
