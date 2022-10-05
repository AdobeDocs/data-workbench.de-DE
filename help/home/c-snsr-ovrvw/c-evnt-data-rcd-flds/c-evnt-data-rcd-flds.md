---
description: Protokolldateien (.vsl) enthalten die Felder von Ereignisdaten, die von Servern von Sensoren erfasst und vom Data Workbench-Server im Prozess der Datensatzerstellung verwendet werden.
title: Ereignisdatensatzfelder (.vsl-Dateien)
uuid: ad9e773c-a128-4094-9e20-45a6de025c8f
exl-id: d48b593f-5a3a-4a4e-9a71-3b91024c9a48
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '141'
ht-degree: 2%

---

# Felder für Ereignisdatensätze{#event-data-record-fields}

{{eol}}

Protokolldateien (.vsl) enthalten die Felder von Ereignisdaten, die von Servern von Sensoren erfasst und vom Data Workbench-Server im Prozess der Datensatzerstellung verwendet werden.

Die Namen der Felder folgen im Allgemeinen der Namenskonvention für das erweiterte W3C-Protokolldateiformat. Viele Felder weisen Präfixe auf, die die Quelle der im Feld enthaltenen Informationen angeben:

* &quot;cs&quot;bedeutet Kommunikation vom Client zum Server
* &quot;sc&quot;bedeutet Kommunikation vom Server zum Client
* &quot;s&quot;zeigt Informationen vom Server an
* &quot;c&quot;gibt Informationen aus dem Client an
* &quot;x&quot;gibt Informationen an, die von einem Adobe-Produkt erstellt werden
