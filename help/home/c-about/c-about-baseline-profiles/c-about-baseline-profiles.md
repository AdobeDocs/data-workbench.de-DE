---
description: Für jede Anwendung wurde ein Satz von Standardprofilen erstellt, mit denen ein oder mehrere Profile gleichzeitig installiert werden können.
title: Standardprofile
uuid: ff76ff7e-ccde-4d99-9109-8612a4a83183
exl-id: f1bd5c1d-5f79-4b8c-9928-97169d553631
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '625'
ht-degree: 0%

---

# Standardprofile{#baseline-profiles}

Für jede Anwendung wurde ein Satz von Standardprofilen erstellt, um die gleichzeitige Installation eines oder mehrerer Profile zu ermöglichen.

Zu diesen Grundlinienprofilen gehören die Definitionen von Standardmetriken, Dimensionen, Filtern, Berichten, Arbeitsbereichen und Dashboards. Adobe aktualisiert diese Profile kontinuierlich und stellt sie seinen Lizenznehmern über das Software Support-Programm zur Verfügung. Darüber hinaus können Anwender von Adobe Apps zusätzliche Profile definieren und diese mit oder anstelle der von Adobe bereitgestellten Profile verwenden.

Das Profilverwaltungssystem ermöglicht das Überschreiben der Konfigurationen eines Profils durch Profile der höheren Ebene. Verwenden Sie diese Funktion, wenn Sie eine der Definitionen überschreiben möchten, die in diesen Profilen enthalten sind, nachdem sie installiert wurden. Durch die Installation neuer Versionen dieser Profile werden alle früheren Versionen überschrieben. Daher würden Änderungen, die direkt an diesen Profilen vorgenommen werden, bei der Installation der neuen Profile überschrieben.

Profile für vertikale Märkte oder bestimmte Arten von Unternehmen oder Branchen können auch bei Adobe ClientCare erhältlich sein. Im Folgenden werden die Grundlinienprofile beschrieben:

* Das **Basisprofil** enthält Konfigurationsdateien, die mit Insight Server geliefert werden. Das Basisprofil sollte vom Benutzer oder Administrator nicht geändert werden. Alle im Basisprofil vorgenommenen Änderungen können überschrieben werden, wenn Adobe eine nächste Version von Insight Server oder einer anderen Softwareanwendung veröffentlicht.
* Das **Traffic-Profil** enthält eine Reihe grundlegender Metriken, Dimensionen und Filter für Webanalysen. Er enthält auch Vorlagen-Arbeitsbereiche, Berichte und Dashboards, die die Analyse, Berichterstellung und das allgemeine Verständnis der gesamten Aktivitätstrends und -muster auf der Website erleichtern. Dieses Profil funktioniert &quot;nativ&quot; mit einer Grundinstallation von Site.
* Das **Werteprofil** enthält eine Reihe von Metriken und Dimensionen sowie Vorlagen-Arbeitsbereichen, Berichten und Dashboards, die mit dem integrierten Site-Geschäftswert und Konversionsmodell verknüpft sind. Mit diesem Profil können Benutzer Wertereignisse auf der Site identifizieren und diesen Ereignissen einen Geldwert zuordnen.

   Dieses Profil erweitert Ihre Site-Analysefunktionen, indem es ein Business Value-Modell bereitstellt, eine erweiterte Methode zur Messung und Verfolgung der von Ihrer Site generierten Wertmenge. Wertereignisse und ihr relativer Wert werden über eine einfache Drag &amp; Drop-Oberfläche innerhalb der Site definiert. Site verwendet diese Definitionen zur Berechnung des von jeder Sitzung generierten Geschäftswerts. Diese Informationen werden wiederum verwendet, um Metriken wie Werte, Wertereignisse, Konversion usw. zu definieren. Mit diesen Metriken können Sie Fragen beantworten, z. B.:

   * Welcher ist der profitabelste Pfad durch die Site?
   * Welcher Referrer oder welche Kampagne hat den höchsten Wert generiert?
   * Wie hoch ist die durchschnittliche Anzahl der Käufe auf der Site pro Tag? (Wie viele Wertereignisse treten im Durchschnitt pro Tag auf?)

   Nachdem Sie ein Geschäftswertmodell in Site definiert haben, können Sie die Wertmetriken und -dimensionen in Ihrer Analyse verwenden.

* Das **Marketing-Profil** umfasst Metriken und Dimensionen sowie Vorlagen-Arbeitsbereiche, Berichte und Dashboards, die mit der Analyse von Internet-Marketing-Kampagnen verknüpft sind, einschließlich Suchanalyse und erweiterter Referrer-Analyse.

Adobe bietet außerdem die folgenden optionalen Profile, die verwendet werden können:

* Das **IP-Geostandortprofil** umfasst Dimensionen und Ebenendateien im Zusammenhang mit der Standortanalyse von Besuchern basierend auf IP-Geostandortdaten, die von Quova, Inc. für die Adobe bereitgestellt und in Data Workbench integriert wurden.
* Das IP-Geo-Intelligenzprofil umfasst Dimensionen und Ebenendateien, die mit der Standortanalyse von Besuchern auf der Grundlage von IP-Geo-Intelligence-Daten verknüpft sind, die der Adobe von Digital Envoy, Inc. bereitgestellt und in Data Workbench integriert wurden.

Informationen zu IP-Geo-Standorten und IP-Geo-Intelligence-Profilen erhalten Sie von Ihrem Support-Mitarbeiter für Adoben. In den folgenden Abschnitten werden die in den einzelnen Basisprofilen definierten Metriken und Dimensionen beschrieben.
