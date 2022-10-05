---
description: Konzeptinformationen zu Teilmengen.
title: Grundlagen zu Untergruppen
uuid: ed185b63-dbb3-4ed4-9403-cf4dc8be2ff1
exl-id: a75b36f9-d34d-4a4a-8a2c-15ae5461823c
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '333'
ht-degree: 1%

---

# Grundlagen zu Untergruppen{#understanding-subsets}

{{eol}}

Konzeptinformationen zu Teilmengen.

Beachten Sie bei der Verwendung einer Untergruppe Folgendes:

* Alle Benchmarks beziehen sich jetzt auf Ihre Teilmenge und nicht auf den gesamten Datensatz. Dies ist bei der Analyse einer bestimmten Teilmenge viel nützlicher. Siehe [Grundlegendes zu Benchmarks](../../../../home/c-get-started/c-vis/c-ustd-benchmks.md#concept-c7b0f4102e92458096f8c4765cbe2914).
* Die Verwendung einer Teilmenge wirkt sich auf alle Arbeitsbereiche aus, da die Teilmenge global auf die Data Workbench angewendet wird.
* Teilmengen betreffen nur Metriken und denormale Dimensionen, nicht normale Dimensionen.
* Bei Verwendung von [!DNL Report]keine Auswirkungen auf die Daten in Berichten haben, die für andere zur Ansicht veröffentlicht werden.
* Nach der Anwendung wird Ihre Teilmenge für alle nachfolgenden Arbeiten im Profil ausgeführt, einschließlich des nächsten Mal, wenn Sie diese Instanz der Data Workbench öffnen, bis Sie sie entfernen.
* Die einzige Stelle, die anzeigt, dass eine Teilmenge angewendet wurde, ist das Kontextmenü, auf das Sie durch Rechtsklicken in einem Arbeitsbereich zugreifen können.

   ![](assets/mnu_Subset.png)

* Sie müssen online arbeiten, um eine Teilmenge zu ändern oder zu entfernen. Wenn Sie offline arbeiten und eine Teilmenge angewendet haben, können Sie keine Ergebnisse aus dem gesamten Datensatz anzeigen. Siehe [Offline und online arbeiten](../../../../home/c-get-started/c-off-on.md#concept-cef8758ede044b18b3558376c5eb9f54).

   >[!NOTE]
   >
   >Die Größe der Teilmenge ist auf die Datenmenge in Ihrem Filter beschränkt, die auf einem einzigen Data Workbench-Server gespeichert ist. Wenn sich Ihr Datensatz daher über einen Data Workbench-Servercluster erstreckt, stammen die Daten für Ihre Untergruppe nur von einem Data Workbench-Server im Cluster.

Ein Benutzer eines großen Einzelhändlers möchte eine Teilmenge (lokalen Cache) einer bestimmten Arbeitswoche mit Daten erstellen und dann Abfragen nur für diese Datenwoche ausführen. Dazu erstellt der Benutzer eine Teilmenge für die gewünschten Tage.

Das folgende Beispiel zeigt ein Balkendiagramm der Besucher im Zeitverlauf und eine Traffic-Metrik-Legende. Die erste Abbildung enthält keine Auswahlen: alle Daten im Datensatz werden dargestellt. Die zweite Abbildung zeigt Daten aus einer Untergruppe von Tagen = {..} nach Besuchern, wobei Tage auf einer Auswahl der Elemente vom 1. bis 5. April in der Dimension Tag basiert.

![](assets/client-sub1.png)
