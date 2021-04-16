---
description: Profil-Filter beschränken den Umfang der in einem Datensatz verfügbaren Daten.
title: Integrierte Profilfilter
uuid: d6854d2c-4643-476e-8a44-f188e18cb115
exl-id: bb167487-415d-44a8-9a0a-9a76d90ba5c0
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '486'
ht-degree: 1%

---

# Integrierte Profilfilter{#built-in-profile-filters}

Profil-Filter beschränken den Umfang der in einem Datensatz verfügbaren Daten.

Zusätzlich zu den Filtern zur Protokollverarbeitung und -transformation, die vor oder während der Erstellung eines Datensatzes angewendet werden können, stehen weitere Profil-Filter zur Verfügung, die sich auf den Umfang der Daten auswirken, die aus einem Datensatz ausgewählt werden können. In diesem Abschnitt werden nur die letztgenannten Filter beschrieben.

Die folgenden Profil-Filter stehen dem Benutzer nach Erstellung eines Datensatzes zur Verfügung:

* Datenunterteilungsfilter
* Filter für ungültige Sitzung

>[!NOTE]
>
>Zusätzliche Filter können durch ihre Präsenz im Verzeichnis der Filter eines Profils erstellt und angewendet werden.

## Datenunterteilung {#section-0defb44315d94254ab6e629ec3d6f420}

Eine Datenuntergruppe fungiert als Datenfilter, da Sie nur die Dimensionselemente auswählen können, die für Sie von Interesse sind.

Durch das Erstellen von Datenuntergruppen wird der Zeitaufwand für die Berechnung der genauen Antworten auf Ihre Abfragen verringert. Wenn die von Ihnen angegebene Datenuntergruppe klein genug ist, kann die Data Workbench alle erforderlichen Daten vom Insight-Server abrufen und Fragen zu der Untergruppe schnell und präzise beantworten. Dies ist besonders dann nützlich, wenn Sie wissen, dass die Analyse eines Tages an Daten oder Sitzungen eines bestimmten Werbers mehrere Stunden in Anspruch nehmen kann.

Benutzer können selbst Datenuntergruppen erstellen oder auf in einem geerbten oder funktionierenden Profil definierte Datenuntergruppen zugreifen. Wenn ein Benutzer eine Untergruppe des Datensatzes erstellt (indem er die gewünschten Daten in Insight auswählt und dann mit der rechten Maustaste in den Arbeitsbereich klickt und auf &quot;Daten&quot;> &quot;Untergruppe&quot;klickt), wird im Ordner &quot;Filter&quot;im Ordner &quot;User Profil&quot;eine Datei der Untergruppe &quot;Data&quot;erstellt. Dieser Filter definiert die ausgewählte Datenuntergruppe und speichert die Untergruppe für die künftige Verwendung.

>[!NOTE]
>
>Sie können mehrere Datenuntergruppen erstellen und sie zur Ansicht verschiedener Datenbereiche umschalten. Denken Sie daran, die Einstellung &quot;Datenunterteilung&quot;zu deaktivieren, wenn alle Daten Ansicht werden sollen. Andernfalls sind Ihre Metrikwerte nicht repräsentativ für alle Daten im Datensatz.

## Unterbrochener Sitzungsfilter {#section-1608e97da6464b11aea27cbb7f3160e4}

Der Filter &quot;Fehlerhafte Sitzung&quot;ist eine Metrikformel, die leicht an beliebige Filteranforderungen angepasst werden kann. In den standardmäßigen Site-Profilen ist der Filter für beschädigte Sitzungen so konfiguriert, dass er alle Besucher mit einer als &quot;1&quot;festgelegten visitorisierten Markierung enthält. Der Wert 1 gibt an, dass für diesen Besucher ein Rückverfolgungscookie vorhanden ist.

Im Folgenden finden Sie den Text der Standarddatei &quot;Broken Session Filter.filter&quot;, die von der Adobe im Versionspaket für die Site-Profil bereitgestellt wird.

```
entity = derived_filter:
   formula = string: Visitorized_Flag="1"
   model = ref: wdata/model
```

In Arbeitsbereichen wird standardmäßig der Filter &quot;Fehlerhafte Sitzung&quot;sowohl auf die Auswahl als auch auf die Benchmarks angewendet. Sie können ein-/ausgeschaltet werden, indem Sie mit der rechten Maustaste in den Arbeitsbereich klicken und auf &quot;Daten&quot;> &quot;Unterbrochener Sitzungsfilter&quot;klicken.

Der Filter &quot;Fehlerhafte Sitzung&quot;kann in Ausdrücken mit Filterfunktion &quot;Broken_Sitzung_Filter&quot;referenziert werden, auch wenn er für den aktuellen Arbeitsbereich nicht aktiviert ist. Weitere Informationen finden Sie unter [Filter-Ausdruck](https://docs.adobe.com/content/help/en/data-workbench/using/client/t-open-ins.html#Syntax_for_Identifiers).
