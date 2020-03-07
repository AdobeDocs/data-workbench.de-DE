---
description: Konzeptbezogene Informationen zu Untergruppen.
solution: Analytics
title: Grundlagen zu Untergruppen
topic: Data workbench
uuid: ed185b63-dbb3-4ed4-9403-cf4dc8be2ff1
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Grundlagen zu Untergruppen{#understanding-subsets}

Konzeptbezogene Informationen zu Untergruppen.

Beachten Sie bei der Verwendung einer Untergruppe Folgendes:

* Alle Benchmarks beziehen sich jetzt auf Ihre Untergruppe und nicht auf den gesamten Datensatz. Dies ist bei der Analyse einer bestimmten Untergruppe viel nützlicher. Siehe [Benchmarks](../../../../home/c-get-started/c-vis/c-ustd-benchmks.md#concept-c7b0f4102e92458096f8c4765cbe2914).
* Die Verwendung einer Untergruppe wirkt sich auf alle Arbeitsbereiche aus, da die Untergruppe global auf Data Workbench angewendet wird.
* Untergruppen wirken sich nur auf Metriken und denormale Dimensionen aus, nicht auf normale Dimensionen.
* Bei der Verwendung [!DNL Report]wirken sich Untergruppen nicht auf die Daten in Berichten aus, die für andere zur Ansicht veröffentlicht wurden.
* Nach der Anwendung ist Ihre Untergruppe für alle weiteren Arbeiten im Profil gültig, einschließlich des nächsten Zeitpunkts, an dem Sie diese Instanz von Data Workbench öffnen, bis Sie sie entfernen.
* Die einzige Stelle, die angibt, dass eine Untergruppe angewendet wurde, ist das Kontextmenü, auf das Sie mit der rechten Maustaste in einem Arbeitsbereich klicken.

   ![](assets/mnu_Subset.png)

* Sie müssen online arbeiten, um eine Untergruppe zu ändern oder zu entfernen. Wenn Sie offline arbeiten und eine Untergruppe angewendet haben, können Sie keine Ergebnisse aus dem gesamten Datensatz anzeigen. Siehe [Offline- und Online-Arbeit](../../../../home/c-get-started/c-off-on.md#concept-cef8758ede044b18b3558376c5eb9f54).

   >[!NOTE]
   >
   >Die Größe der Untergruppe ist auf die Datenmenge in Ihrem Filter beschränkt, die sich auf einem einzelnen Data Workbench-Server befindet. Wenn Ihr Datensatz daher einen Data Workbench-Servercluster umfasst, stammen die Daten für Ihre Untergruppe von nur einem Data Workbench-Server im Cluster.

Ein Benutzer eines großen Einzelhändlers möchte eine Teilmenge (lokalen Cache) einer bestimmten Arbeitswoche mit Daten erstellen und dann Abfragen nur für diese Datenwoche ausführen. Dazu erstellt der Benutzer eine Untergruppe für die interessanten Tage.

Das folgende Beispiel zeigt ein Balkendiagramm der Besucher im Zeitverlauf und eine Traffic-Metriklegende. Die erste Abbildung enthält keine Auswahl: alle Daten im Datensatz dargestellt werden. Die zweite Abbildung zeigt Daten zu einer Untergruppe von Tagen = {...} nach Besuchern, wobei Tage auf einer Auswahl der Elemente vom 1. April bis zum 5. April in der Dimension &quot;Tag&quot;basieren.

![](assets/client-sub1.png)

