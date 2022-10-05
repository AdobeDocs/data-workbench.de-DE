---
description: Erfassen und beschreiben Sie bei der Implementierung von Data Workbench die Geschäftsfragen, die für Ihre Marketing-Umgebung relevant sind.
title: Ermittlung der Ziele und Anforderungen rund um Data Workbench
uuid: 436f0c32-b4e2-41dd-a8e9-531e0a195276
exl-id: 25cc2940-800a-4ad2-a7bb-c343e3d65500
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '411'
ht-degree: 9%

---

# Ermittlung der Ziele und Anforderungen rund um Data Workbench{#data-workbench-discovery-and-requirements}

{{eol}}

Erfassen und beschreiben Sie bei der Implementierung von Data Workbench die Geschäftsfragen, die für Ihre Marketing-Umgebung relevant sind.

In diesem Abschnitt können Sie Eingaben zu den Fragen und Aufgaben sammeln, die für die Entwicklung von Lösungen in Data Workbench (DWB) erforderlich sind. Diese können diese Fragen präzise, eindeutig und technologieunabhängig beantworten und Verweise auf die Unternehmensterminologie und die Adobe Analytics Premium-Lösung bereitstellen. Dieser Abschnitt enthält Informationen zu diesen Zielen und den damit verbundenen Anforderungen.

## Phase 1: Wichtige Geschäftsziele {#section-bb8f3d6071bf48d9a546ac2b80341e1d}

In den folgenden Tabellen werden Sie aufgefordert, Ihren Kundenstamm zu identifizieren und die Erstellung Ihrer DWB-Implementierung zu analysieren.

* Grundlagen zur Kundenbasis
* Verstehen bestimmter Geschäftsfälle (z. B. Effektivität von Self-Service und anderen Datenkanälen/Offline-Datenquellen)

**Grundlagen zur Kundenbasis**

Erfahren Sie, warum Kunden Ihre Site nutzen, welche Herausforderungen sich Ihnen stellen und wie DWB Ihnen basierend auf Ihrem Geschäftsmodell hilft. So können Sie z. B. Ihre Kunden messen, überwachen und analysieren, um andere Produkte und Dienstleistungen zu vertreiben, die Liste aktiver Benutzer abrufen und die Kontodurchdringung sowie andere Ziele erreichen.

| ID | Geschäftsfrage/Anforderung | Priorität | Phase | Abhängigkeiten |
|---|---|---|---|---|
| 1a | Spezifische geschäftliche Frage 1 | Hoch/Mittel/Niedrig | 1 | Allgemeiner Schlüssel, abhängig von einem anderen Schlüssel usw. |
| 1b | Spezifische geschäftliche Frage 2 | Hoch | 1 | Jegliche Abhängigkeit |

Analyseaufbau

<table id="table_6CA959E521964E27804BB2A65EC4BBDE"> 
 <tbody> 
  <tr> 
   <td colname="col1">Workspace Analysis Data Source(s)</td> 
   <td colname="col2"> Workspace-Namen hinzufügen </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Workspace-Dimensionen und -Metriken erforderlich </p> </td> 
   <td colname="col2"> <p>Dimensionen identifizieren: </p> <p>Identifizieren von Metriken: </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Workspace-Filter, -Flags und -Tools erforderlich </td> 
   <td colname="col2"> <p>Segmente identifizieren: </p> <p>Identifizieren von Tools: </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Welche Aktionen lassen sich aus dieser Analyse ableiten? </td> 
   <td colname="col2"> Verstehen Sie Aufgaben und Inhalte mit bestimmten DWB-Arbeitsbereichen. </td> 
  </tr> 
 </tbody> 
</table>

## Phase 2: Erläuterungen zu bestimmten Geschäftsfällen {#section-309d7ec6f631458c9c9e6bd2cef2fa4c}

Machen Sie sich mit anderen Datenquellen und Kanälen vertraut und erfahren Sie, wie diese mit Ihren Geschäftsfällen in Zusammenhang stehen.

<table id="table_733CCD9F4E9048C2865758B8E8D027DC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ID </th> 
   <th colname="col2" class="entry"> Geschäftsfragen/Anforderungen </th> 
   <th colname="col3" class="entry"> Priorität </th> 
   <th colname="col04" class="entry"> Phase </th> 
   <th colname="col4" class="entry"> Abhängigkeiten </th> 
   <th colname="col5" class="entry"> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 2a </td> 
   <td colname="col2"> Spezifische Geschäftsanforderungen 1 </td> 
   <td colname="col3"> <p>Hoch/Mittel/Niedrig </p> </td> 
   <td colname="col04"> 1 </td> 
   <td colname="col4"> <p>Allgemeiner Schlüssel, abhängig von einem anderen Schlüssel, Kontokennzeichnung/-kennung usw. </p> </td> 
   <td colname="col5"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 2b </td> 
   <td colname="col2"> <p>Spezifische Geschäftsanforderung 2 </p> </td> 
   <td colname="col3"> Hoch/Mittel/Niedrig </td> 
   <td colname="col04"> 1 </td> 
   <td colname="col4"> <p>Jegliche Abhängigkeit </p> </td> 
   <td colname="col5"> </td> 
  </tr> 
 </tbody> 
</table>

**Analyseaufbau**

<table id="table_680C5D257CBF42519EFB8B96A00543C5"> 
 <tbody> 
  <tr> 
   <td colname="col1">Workspace Analysis Data Source(s)
     </td> 
   <td colname="col2">
     Workspace-Beispielname </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Workspace-Dimensionen und -Metriken erforderlich </p> </td> 
   <td colname="col2"> <p>Dimensionen: Definieren Sie erforderliche Dimensionen. </p> <p>Metriken: Definieren Sie die benötigten Metriken. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Workspace-Filter, -Flags und -Tools erforderlich </td> 
   <td colname="col2"> <p>Segmente: Identifizieren Sie Ihre Kundensegmente. </p> <p>Instrumente: Wählen Sie die erforderlichen Tools aus. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Welche Aktionen lassen sich aus dieser Analyse ableiten? </td> 
   <td colname="col2"> Wissenswertes über diesen Arbeitsbereich </td> 
  </tr> 
 </tbody> 
</table>

**Datenquellen**

| Datenquellen  | Priorität | Wie oft werden Daten empfangen? |
|---|---|---|
| Site 1 Name Report Suite (RSID) | 1 | Stündlich |
| Site 2 Name (falls vorhanden) (RSID) | 1 | Stündlich |
| Datenquelle 1 (falls zutreffend) | 2 | Täglich? |
| Datenquelle 2 (falls zutreffend) | 3 | Täglich? |
