---
description: Data Workbench umfasst integrierte Metriken.
title: Integrierte Metriken
uuid: 1e4d91dc-0130-4296-8395-fd2ddb03f6ef
exl-id: a8a2a8dd-dc13-4eb3-92ce-09f02252ecf0
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '310'
ht-degree: 1%

---

# Integrierte Metriken{#built-in-metrics}

Data Workbench umfasst integrierte Metriken.

In der folgenden Tabelle sind die verfügbaren integrierten Metriken für Data Workbench aufgeführt:

| Integrierte Metrik | Beschreibung |
|---|---|
| als | Die Ausführungszeit des Datensatzes in 100 Nanosekunden-Intervallen seit dem 1. Januar 1600 00:00 UTC. Der Ausführungszeitstempel ist die neueste Zeit im Datensatz, für die definitiv alle Daten verarbeitet wurden. |
| Log Bytes Read | Die Gesamtmenge der komprimierten Daten (in Byte), die während der Protokollverarbeitungsphase bisher verarbeitet wurde. |
| Protokollbyte insgesamt | Die Gesamtmenge der komprimierten Daten (in Byte) in Protokolldateien, die den konfigurierten Kriterien für Protokollquellen und dem Start- und Enddatumsbereich des Datensatzes entsprechen. Wenn die Protokollverarbeitung in der Konfigurationsdatei für den Protokollverarbeitungsmodus angehalten wurde, entspricht die Gesamtsumme der Protokollbyte-Dateien der Anzahl der Lesevorgänge für Protokollbyte. |
| Fortschritt der Protokollverarbeitung | Der prozentuale Abschluss der Protokollverarbeitungsphase der Insight Server-Datenverarbeitung. |
| Dekodierte Protokolleinträge gesamt | Die Anzahl der Einträge in den Protokolldateien, die im Rahmen der Protokollverarbeitungsphase der Datenverarbeitung mit Insight Server erfolgreich dekodiert wurden. |
| Gefilterte Protokolleinträge gesamt | Die Anzahl der Einträge in den Protokolldateien, die nach der Dekodierung vom Roboterfilter akzeptiert wurden, sowie die Protokolleintragsbedingungen und anderen Filter, die als Teil der Protokollverarbeitungsphase der Datenverarbeitung von Insight Server angewendet werden. |
| Protokolleinträge gesamt | Die Anzahl der Einträge in den Protokolldateien, die bisher in der Protokollverarbeitungsphase der Datenverarbeitung mit Insight Server verarbeitet wurden. |
| Verarbeitete Protokolleinträge gesamt | Die Anzahl der gefilterten Protokolleinträge, die in den Adobe-Datensatz integriert wurden. |
| Umwandlungsfortschritt | Der prozentuale Abschluss der Transformationsphase der Datenverarbeitung mit Insight Server. |
| Unkomprimierte Protokollbyte lesen | Die gesamte Menge unkomprimierter Daten (in Byte), die während der Protokollverarbeitungsphase bisher verarbeitet wurde. |
