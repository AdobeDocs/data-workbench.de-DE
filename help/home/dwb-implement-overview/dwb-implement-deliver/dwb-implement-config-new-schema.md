---
description: In diesem Dokument wird beschrieben, wie Sie alle standardmäßigen Schemakonfigurationen ändern, nachdem das neue Data Workbench eingerichtet wurde.
title: Änderung der Konfiguration für ein neues Schema
uuid: 7d59fc28-ce56-49e2-b068-d5e286dcc057
exl-id: 6eb4c7e6-9a1e-4bc3-80f0-623abf7de2f2
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '654'
ht-degree: 1%

---

# Änderung der Konfiguration für ein neues Schema{#configuration-changes-for-new-schema}

{{eol}}

In diesem Dokument wird beschrieben, wie Sie alle standardmäßigen Schemakonfigurationen ändern, nachdem das neue Data Workbench eingerichtet wurde.

## Grundlagen zum Datensatzschema {#section-2ffac5170c894781bc943565af7ad479}

Die Grundlage des Datensatzschemas besteht aus einem wichtigen Satz von Beziehungen, die das Rückgrat des Data Workbench-Webanalyseschemas bilden. Im folgenden Beispiel liefert das typische Webanalyseschema eine Vorstellung von den Beziehungen zwischen einem Besucher, einem Besuch und einer Seitenansicht. ![](assets/dwb_impl_schema_change1.png)

* Jeder Besucher kann einen oder mehrere Besuche haben.
* Jeder Besuch wird von nur einem Besucher generiert.
* Jeder Besuch kann einen oder mehrere Seitenansichten umfassen.
* Jede Seitenansicht gehört nur zu einem Besuch. `<discoiqbr>`

Da sich das Web und die Geschäftswelt im Laufe der Jahre weiterentwickelt haben, haben sich auch die Anforderungen der Web- und Datenanalyse geändert. Webseiten begannen als Orte, an denen Inhalte angesehen werden können. Jetzt können Sie sich Inhalte ansehen. interaktiv über Chats, Videos oder Übermittlungen korrespondieren; Kaufprodukte; und vieles mehr. Darüber hinaus möchten Unternehmen nun ihre Web-Daten mit anderen Datenkanälen in ihr Unternehmen integrieren, um einen besseren Überblick über ihr Geschäft insgesamt zu erhalten. Ein Unternehmen möchte beispielsweise möglicherweise seine Web-, Callcenter-, E-Mail-, Social- und Store- sowie Kundendaten zusammenführen. Mit dieser Integration von Offline- und Online-Kanälen haben sich die Datensatzschemas im Laufe der Jahre weiterentwickelt, in denen keine zwei Datensatzschemas identisch sind.

`<discoiqbr>`Wenn Sie die Online- und Offline-Daten integrieren, erscheint der Begriff &quot;Besucher&quot;nicht immer angemessen. Daher wird manchmal der Begriff &quot;Kunde&quot;anstelle des Besuchers verwendet. ![](assets/dwb_impl_schema_change2.png) ![](assets/dwb_impl_schema_change3.png)

Die Ebene &quot;Interaktion&quot;wird verwendet, um eine einzelne Ansicht der Zeit zu ermöglichen, wenn Sie über Daten aus mehreren Datenquellen verfügen. Angenommen, Sie haben nur eine Datenquelle: E-Commerce-Daten, die von der Besucheraktivität auf Ihrer Website erfasst werden. In diesem Fall zeigt die Besuchsebene die Besuche Ihrer Site von diesen Besuchern an. Beachten Sie, dass Zeitdimensionen - &quot;Tag&quot;, &quot;Woche&quot;, &quot;Monat&quot;usw. - werden normalerweise auf der Ebene &quot;Besuch&quot;erfasst.

Auf ähnliche Weise führt die Ebene &quot;Ereignis&quot;alle Ereignisse (Seitenaufruf, Aufruf an Callcenter usw.) ein, die während einer Interaktion aufgetreten sind. Es kombiniert alle Online- und Offline-Ereignisse für einen Kunden während einer Interaktion.

## Neue zählbare Struktur in DWB {#section-b77638ec04e4441cb51c56fd3d4abeb6}

Die neue Schemastruktur ersetzt Besucher nach Kunde, Besuch nach Interaktion und Treffer nach Ereignis. ![](assets/dwb_impl_schema_change4.png)

## Konfigurationsänderungen gemäß dem neuen Datensatzschema {#section-27135515be5c471ba2ee879d1ef4771f}

Um das Datensatzschema von Besucher zu Kunde zu ändern, müssen Sie die folgenden Konfigurationsdateien ändern:

1. Alle Konfigurationsdateien im Ordner Datensatz , in dem zählbare und erweiterte Dimensionen definiert sind. ![](assets/dwb_impl_schema_change5.png)

1. Konfigurationsdateien im Ordner &quot;Dimension&quot;, in denen &quot;visitor&quot;, &quot;visit&quot;oder &quot;event&quot;als Ebene verwendet werden.

   Beispiel: Datei &quot;Campaign.cfg&quot;. Im SC-Profil der Adobe wird Campaign auf Besuchsebene definiert. ![](assets/dwb_impl_schema_change6.png)

   Im folgenden Beispiel wird die Änderung des übergeordneten Schemas von &quot;Besuch&quot;zu &quot;Interaktion&quot;vorgestellt: ![](assets/dwb_impl_API10.png)

1. Da einige Metriken aus zählbaren Elementen abgeleitet oder erstellt werden, müssen Konfigurationsdateien im Ordner Metriken geändert oder erstellt werden.

   Beispiel: eine neue Metrik erstellen [!DNL Customers.metric with formula = sum(one,customer)] oder als Seitenansichten.metric zu *Definition* auf der Trefferebene. Ändern Sie die Metrik und ändern Sie dann die Ebene in &quot;Ereignis&quot;anstelle von &quot;Treffer&quot;.

   Metrik für Seitenansichten der Adobe SC auf Trefferebene: ![](assets/dwb_impl_API8.png)

   `<discoiqbr>` `<discoiqbr>`Im Folgenden wird die Metrik Seitenansichten gemäß dem neuen Schema dargestellt: ![](assets/dwb_impl_API9.png)

1. Ändern Sie die *order.txt* im Ordner &quot;Metriken&quot;angezeigt, sodass er die neuen oder geänderten Metriken zum Kunden, zur Interaktion und zum Ereignis widerspiegelt.

   Adobe *SC order.txt* -Datei. ![](assets/dwb_impl_API11.png)

   *Order.txt* Datei mit neuen Schemaänderungen: ![](assets/dwb_impl_API12.png)

1. Alle Konfigurationsdateien (.vw) im Ordner &quot;Visualisierung&quot;sollten so geändert werden, dass sie auf neue Ebenen verweisen: Kunden, Interaktion und Ereignis. Beispiel: 2D-Prozesskarte, 3D-Prozesskarte usw.

   Adobe SC default URI.vw für 2D-Prozesszuordnung wird auf Trefferebene und Besuchergruppe wie unten gezeigt definiert: ![](assets/dwb_impl_API14.png)

   Änderungen, die in URI.vw für ein neues Schema vorgenommen werden sollen: ![](assets/dwb_impl_API15.png)
