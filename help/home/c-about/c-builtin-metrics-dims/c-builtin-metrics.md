---
description: Data Workbench umfasst integrierte Metriken.
solution: Analytics
title: Integrierte Metriken
topic: Data workbench
uuid: 1e4d91dc-0130-4296-8395-fd2ddb03f6ef
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Integrierte Metriken{#built-in-metrics}

Data Workbench umfasst integrierte Metriken.

In der folgenden Tabelle sind die verfügbaren integrierten Metriken für Data Workbench aufgeführt:

| Integrierte Metrik | Beschreibung |
|---|---|
| as | Die Ausführungszeit des Datensatzes in 100 Nanosekunden-Intervallen seit dem 1. Januar 1600 00:00 UTC. Der Ausführungszeitstempel ist das letzte Mal im Datensatz, für das alle Daten definitiv verarbeitet wurden. |
| Gelesene Protokollbyte | Die Gesamtsumme der komprimierten Daten (in Byte), die bisher während der Protokollverarbeitungsphase verarbeitet wurden. |
| Protokollbyte insgesamt | Die Gesamtmenge der komprimierten Daten (in Byte) in Protokolldateien, die den konfigurierten Kriterien für Protokollquellen und dem Start- und Enddatumsbereich des Datensatzes entsprechen. Wenn die Protokollverarbeitung in der Konfigurationsdatei des Protokollverarbeitungsmodus angehalten wird, ist die Gesamtanzahl der Protokollbyten identisch mit der Anzahl der gelesenen Byte. |
| Fortschritt der Protokollverarbeitung | Der prozentuale Abschluss der Protokollverarbeitungsphase der Insight Server-Datenverarbeitung. |
| Dekodierte Protokolleinträge gesamt | Die Anzahl der Einträge in den Protokolldateien, die im Rahmen der Protokollverarbeitungsphase der Insight Server-Datenverarbeitung erfolgreich dekodiert wurden. |
| Gefilterte Protokolleinträge gesamt | Die Anzahl der Einträge in den Protokolldateien, die nach der Dekodierung vom Roboterfilter akzeptiert wurden, sowie die Logeintragungsbedingungen und andere Filter, die als Teil der Protokollverarbeitungsphase der Insight Server-Datenverarbeitung angewendet werden. |
| Protokolleinträge gesamt | Die Anzahl der Einträge in den Protokolldateien, die bisher in der Protokollverarbeitungsphase der Datenverarbeitung mit Insight Server verarbeitet wurden. |
| Verarbeitete Protokolleinträge gesamt | Die Anzahl der gefilterten Protokolleinträge, die in den Adobe-Datensatz integriert wurden. |
| Transformationsfortschritt | Der prozentuale Abschluss der Transformationsphase der Insight Server-Datenverarbeitung. |
| Unkomprimierte Protokollbyte gelesen | Die gesamte Menge nicht komprimierter Daten (in Byte), die bisher während der Protokollverarbeitungsphase verarbeitet wurden. |

