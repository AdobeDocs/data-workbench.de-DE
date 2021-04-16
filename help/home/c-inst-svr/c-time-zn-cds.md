---
description: Formatieren Sie Anweisungen zu zeitbasierten Parametern in Insight Server.
title: Zeitzonencodes
uuid: dcc8aa15-5846-4f24-8b82-e25ff89871ba
exl-id: d8923b01-24fe-4a70-9800-f2eedf567c6a
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '364'
ht-degree: 5%

---

# Zeitzonencodes{#time-zone-codes}

Formatieren Sie Anweisungen zu zeitbasierten Parametern in Insight Server.

Die meisten zeitbasierten Parameter in [!DNL Insight Server] werden im folgenden Format angegeben:

*Monat TT, JJJJ HH:MM:SS-Zeitzone*

Beispiel: 13. August 2013 22:30:00 EST

Zeitzonen werden in einem systemunabhängigen Zeitzonenformat (Coordinated Universal Time) des folgenden Formats ausgedrückt:

UTC +hmm *Module*

Das Zeichen (+) kann entweder ein Plus- (+) oder ein Minuszeichen (-) und *hmm* der Offset von UTC in Stunden und Minuten sein. Die optionale Variable *dstrules* gibt einen Regelsatz zur Implementierung der Sommerzeit oder einer ähnlichen Richtlinie zum Uhrzeitwechsel an.

Wenn Sie *dstrules* angeben, muss sich eine tabulatorbegrenzte Datei mit dem Namen *&lt;[!DNL dstrules]* [!DNL .dst] im Ordner &quot;Dataset\TimeZone&quot;des Profils &quot;Basis&quot;(für Konfigurationsdateien, die keinem bestimmten Datensatz zugeordnet sind) oder des Profils &quot;Datensatz&quot;(für Konfigurationsdateien, die dataset-spezifisch sind) befinden. Die Datei gibt einen zeitzonenunabhängigen Regelsatz für die Sommerzeit an. Sie können unterschiedliche Regelsätze für verschiedene Jahre verwenden. Die [!DNL DST.dst]-Datei, die von der Adobe im Base-Profil bereitgestellt wird, legt die Standardregeln der USA fest, die im Energy Policy Act von 2005 (in Kraft seit 2007) und in den USA für Vorjahre festgelegt wurden.

Beispiele für Zeitzoneneinträge sind unten aufgeführt:

* Östliche Sommerzeit in den USA: Zeitzone = Zeichenfolge: UTC -0500 DST
* UTC-Zeit ohne Offset und keine *Module* (entspricht GMT): Zeitzone = Zeichenfolge: UTC -0000

Bei Verwendung dieses Formats muss die Systemzeitzone von [!DNL Insight Server]-, [!DNL Insight]- und [!DNL Report]-Computern nicht mit der angegebenen Zeitzone übereinstimmen. Darüber hinaus müssen alle aktiven DataSet-Profil auf einem [!DNL Insight Server]-Computer nicht die gleiche Zeitzoneneinstellung haben.

Die folgende Tabelle enthält die Liste der Codes, mit denen Sie Zeitzonen in zeitbasierten Parametern angeben können.

## Zeitzonencode-Tabelle {#section-3cab225b864f4e54ac4f5bd83ab4ed36}

>[!NOTE]
>
>Wenn Sie die Sommerzeit oder eine ähnliche Richtlinie zur Uhrzeitverschiebung implementieren, müssen Sie die [!DNL .dst]-Datei mit den entsprechenden Regeln auf dem *Profil name*\Dataset\Timezone directory on the [!DNL Insight Server]-Computer speichern.

| Code | Zeitzone | Versatz aus GMT |
|---|---|---|
| gmt | Greenwich-Mittel | 0 |
| est | Eastern Standard | 5 |
| edt | Eastern Daylight | 5 |
| cst | Central Standard | 6 |
| cdt | Central Daylight | 6 |
| mst | Gebirgsstandard | 7 |
| mdt | Mountain Daylight | 7 |
| pst | Pacific Standard | 8 |
| pdt | Pacific Daylight | 8 |
