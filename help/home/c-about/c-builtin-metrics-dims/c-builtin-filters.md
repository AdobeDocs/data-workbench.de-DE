---
description: Profilfilter beschränken den Umfang der Daten, die aus einem Datensatz verfügbar sind.
title: Integrierte Profilfilter
uuid: d6854d2c-4643-476e-8a44-f188e18cb115
exl-id: bb167487-415d-44a8-9a0a-9a76d90ba5c0
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '484'
ht-degree: 1%

---

# Integrierte Profilfilter{#built-in-profile-filters}

Profilfilter beschränken den Umfang der Daten, die aus einem Datensatz verfügbar sind.

Zusätzlich zu den Protokollverarbeitungs- und Transformationsfiltern, die vor oder während der Erstellung eines Datensatzes angewendet werden können, stehen weitere Profilfilter zur Verfügung, die den Umfang der Daten beeinflussen, die aus einem Datensatz ausgewählt werden können. In diesem Abschnitt wird nur der zweite Typ von Sonderfiltern beschrieben.

Die folgenden Profilfilter stehen dem Benutzer nach der Erstellung eines Datensatzes zur Verfügung:

* Datenunterteilungsfilter
* defekter Sitzungsfilter

>[!NOTE]
>
>Zusätzliche Filter können erstellt und angewendet werden, indem sie im Verzeichnis &quot;Filter&quot;eines Profils vorhanden sind.

## Datenunterteilung {#section-0defb44315d94254ab6e629ec3d6f420}

Eine Datenuntergruppe dient als Datenfilter, da Sie nur die Dimensionselemente von Daten auswählen können, die für Sie von Interesse sind.

Durch das Erstellen von Datenuntergruppen wird die Zeit verkürzt, die für die Berechnung der genauen Antworten auf Ihre Abfragen erforderlich ist. Wenn die von Ihnen angegebene Datenuntergruppe klein genug ist, kann Data Workbench alle benötigten Daten aus Insight Server abrufen und Fragen zur Teilmenge schnell und präzise beantworten. Dies ist besonders nützlich, wenn Sie wissen, dass beispielsweise die Analyse eines Tages von Daten oder Sitzungen eines bestimmten Referrers mehrere Stunden erfordert.

Benutzer können selbst Datenuntergruppen erstellen oder auf in einem geerbten oder funktionierenden Profil definierte Datenuntergruppen zugreifen. Wenn ein Benutzer eine Teilmenge des Datensatzes erstellt (indem er die gewünschten Daten in Insight auswählt und dann mit der rechten Maustaste in den Arbeitsbereich klickt und auf Daten > Teilmenge klickt), wird im Ordner &quot;Filter&quot;im Ordner &quot;Benutzerprofil&quot;eine Datei &quot;Datenuntergruppe.filter&quot;erstellt. Dieser Filter definiert die ausgewählte Datenuntergruppe und speichert die Teilmenge zur zukünftigen Verwendung.

>[!NOTE]
>
>Sie können mehrere Datenuntergruppen erstellen und sie so umschalten, dass sie verschiedene Teile der Daten anzeigen können. Denken Sie daran, die Datenunterteilung zu deaktivieren, wenn Sie alle Daten anzeigen möchten. Andernfalls sind Ihre Metrikwerte nicht für alle Daten im Datensatz repräsentativ.

## defekter Sitzungsfilter {#section-1608e97da6464b11aea27cbb7f3160e4}

Der Filter &quot;Beschädigte Sitzung&quot;ist eine Metrikformel, die einfach an beliebige Filteranforderungen angepasst werden kann. In den Standard-Site-Profilen ist der Filter &quot;Beschädigte Sitzung&quot;so konfiguriert, dass er alle Besucher mit einer auf 1 festgelegten Kennzeichnung &quot;Besucht&quot;einbezieht. Der Wert 1 zeigt das Vorhandensein eines Tracking-Cookies für diesen Besucher an.

Im Folgenden finden Sie den Text der standardmäßigen Datei &quot;Broken Session Filter.filter&quot;, die von Adobe im Versionspaket für die Site-Profile bereitgestellt wird.

```
entity = derived_filter:
   formula = string: Visitorized_Flag="1"
   model = ref: wdata/model
```

In Arbeitsbereichen wird standardmäßig der Filter &quot;Beschädigte Sitzung&quot;sowohl auf ihre Auswahl als auch auf ihre Benchmarks angewendet. Er kann ein-/ausgeblendet werden, indem Sie mit der rechten Maustaste in den Arbeitsbereich klicken und auf &quot;Daten&quot;> &quot;Beschädigte Sitzungsfilter&quot;klicken.

Der Filter &quot;Beschädigte Sitzung&quot;kann in Filterausdrücken als &quot;Broken_Session_Filter&quot;referenziert werden, auch wenn er für den aktuellen Arbeitsbereich nicht aktiviert ist. Weitere Informationen finden Sie unter [Filterausdrücke](https://experienceleague.adobe.com/docs/data-workbench/using/client/t-open-ins.html#Syntax_for_Identifiers) .
