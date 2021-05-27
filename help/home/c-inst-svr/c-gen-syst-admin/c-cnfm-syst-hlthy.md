---
description: Sie müssen sicherstellen, dass die Computer, auf denen Adobe Server-Produkte installiert sind, die im Dokument mit den Mindestsystemanforderungen definierten Systemanforderungen erfüllen.
title: Prüfen des Zustands der Systeme
uuid: 6d132865-36ab-40fc-be24-e031f356fce2
exl-id: 543f7592-dd3c-47ba-b174-5f12e9586378
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '169'
ht-degree: 5%

---

# Prüfen des Zustands der Systeme{#confirming-your-systems-are-healthy}

Sie müssen sicherstellen, dass die Computer, auf denen Adobe Server-Produkte installiert sind, die im Dokument mit den Mindestsystemanforderungen definierten Systemanforderungen erfüllen.

**Empfohlene Häufigkeit:** Alle 5-10 Minuten

Außerdem müssen Sie Ihre Systeme entsprechend den Best Practices für den Betrieb dieser bestimmten Hardware überwachen, einschließlich, aber nicht beschränkt auf die Überwachung folgender Punkte:

* CPU-Auslastung
* Speicherplatz
* Hardwaresystemnachrichten
* Innere Systemtemperatur
* Speichernutzung
* Netzteilbedingungen
* Leistung des RAID- oder Datenträger-Controllers und Fehler

Adobe empfiehlt, dass Sie Ihr Verwaltungstool so konfigurieren, dass es Administratoren warnt, wenn ein Systemparameter auf einem Servercomputer den festgelegten Schwellenwert überschreitet.

Bei [!DNL Insight Server]-Computern empfiehlt Adobe außerdem, dass Sie jedes [!DNL Insight Server] so konfigurieren, dass angegeben wird, wann der festgelegte Mindestspeicherplatz erreicht ist. Weitere Informationen zu diesen Warnhinweisen finden Sie unter [Konfigurieren administrativer Warnhinweise](../../../home/c-inst-svr/c-admin-inst-svr/t-config-adm-alrts.md#task-0858f588da4941aa9d4952f6592681aa).
