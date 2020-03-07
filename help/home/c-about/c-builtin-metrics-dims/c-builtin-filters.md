---
description: Profilfilter beschränken den Umfang der in einem Datensatz verfügbaren Daten.
solution: Analytics
title: Integrierte Profilfilter
topic: Data workbench
uuid: d6854d2c-4643-476e-8a44-f188e18cb115
translation-type: tm+mt
source-git-commit: 2e4991206394ca0c463210990ea44dfb700341a5

---


# Integrierte Profilfilter{#built-in-profile-filters}

Profilfilter beschränken den Umfang der in einem Datensatz verfügbaren Daten.

Zusätzlich zu den Protokollverarbeitungs- und Transformationsfiltern, die vor oder während der Erstellung eines Datensatzes angewendet werden können, stehen weitere Profilfilter zur Verfügung, die sich auf den Umfang der Daten auswirken, die aus einem Datensatz ausgewählt werden können. In diesem Abschnitt wird nur der letzte Typ von Spezialfiltern beschrieben.

Die folgenden Profilfilter stehen dem Benutzer nach der Erstellung eines Datensatzes zur Verfügung:

* Datenunterteilungsfilter
* Filter für ungültige Sitzung

>[!NOTE]
>
>Zusätzliche Filter können erstellt und über ihre Präsenz im Filterverzeichnis eines Profils angewendet werden.

## Datenunterteilung {#section-0defb44315d94254ab6e629ec3d6f420}

Eine Datenuntergruppe fungiert als Datenfilter, da Sie nur die Dimensionselemente auswählen können, die für Sie von Interesse sind.

Das Erstellen von Datenuntergruppen verringert die Zeit, die für die Berechnung der genauen Antworten auf Ihre Abfragen benötigt wird. Wenn die von Ihnen angegebene Datenuntergruppe klein genug ist, kann Data Workbench alle benötigten Daten vom Insight Server abrufen und Fragen zu der Untergruppe schnell und präzise beantworten. Dies ist besonders nützlich, wenn Sie wissen, dass die Analyse eines Tages mit Daten oder Sitzungen einer bestimmten verweisenden Stelle mehrere Stunden in Anspruch nehmen kann.

Benutzer können selbst Datenuntergruppen erstellen oder auf Datenuntergruppen zugreifen, die in einem geerbten oder funktionierenden Profil definiert sind. Wenn ein Benutzer eine Untergruppe des Datensatzes erstellt (indem er die gewünschten Daten in Insight auswählt und dann mit der rechten Maustaste in den Arbeitsbereich klickt und auf &quot;Daten&quot;> &quot;Untergruppe&quot;klickt), wird im Ordner &quot;Filter&quot;im Ordner &quot;Benutzerprofil&quot;eine Datei &quot;Data Subset.filter&quot;erstellt. Dieser Filter definiert die ausgewählte Datenuntergruppe und speichert die Untergruppe für die künftige Verwendung.

>[!NOTE]
>
>Sie können mehrere Datenuntergruppen erstellen und sie umschalten, um verschiedene Teile der Daten anzuzeigen. Denken Sie daran, die Datenunterteilung zu deaktivieren, wenn Sie alle Daten anzeigen möchten. Andernfalls sind Ihre Metrikwerte nicht repräsentativ für alle Daten im Datensatz.

## Filter für ungültige Sitzung {#section-1608e97da6464b11aea27cbb7f3160e4}

Der Filter &quot;Fehlerhafte Sitzung&quot;ist eine Metrikformel, die leicht an beliebige Filteranforderungen angepasst werden kann. In den Standard-Site-Profilen ist der Filter &quot;Fehlerhafte Sitzung&quot;so konfiguriert, dass er alle Besucher einbezieht, die eine als &quot;Besuch&quot;festgelegte Markierung haben. Der Wert 1 gibt an, dass für diesen Besucher ein Rückverfolgungs-Cookie vorhanden ist.

Im Folgenden finden Sie den Text der Standarddatei &quot;Broken Session Filter.filter&quot;, die Adobe im Release-Paket für die Site-Profile bereitgestellt hat.

```
entity = derived_filter:
   formula = string: Visitorized_Flag="1"
   model = ref: wdata/model
```

In Arbeitsbereichen wird standardmäßig der Filter &quot;Fehlerhafte Sitzung&quot;sowohl auf die Auswahl als auch auf die Benchmarks angewendet. Sie können ein-/ausgeschaltet werden, indem Sie mit der rechten Maustaste in den Arbeitsbereich klicken und auf &quot;Daten&quot;> &quot;Unterbrochener Sitzungsfilter&quot;klicken.

Der Filter &quot;Fehlerhafte Sitzung&quot;kann in Filterausdrücken als &quot;Broken_Sitzung_Filter&quot;referenziert werden, auch wenn er für den aktuellen Arbeitsbereich nicht aktiviert ist. Weitere Informationen finden Sie unter [Filterausdrücke](https://docs.adobe.com/content/help/en/data-workbench/using/client/t-open-ins.html#Syntax_for_Identifiers) .
