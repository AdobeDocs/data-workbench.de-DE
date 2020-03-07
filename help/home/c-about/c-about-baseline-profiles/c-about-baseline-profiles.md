---
description: Für jede Anwendung wurde eine Reihe von Standardprofilen erstellt, damit ein oder mehrere Profile jederzeit installiert werden können.
solution: Analytics
title: Ausgangsprofile
topic: Data workbench
uuid: ff76ff7e-ccde-4d99-9109-8612a4a83183
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Ausgangsprofile{#baseline-profiles}

Für jede Anwendung wurde eine Reihe von Standardprofilen erstellt, damit eines oder mehrere Profile jederzeit installiert werden können.

Zu diesen Grundprofilen gehören die Definitionen von Standardmetriken, Dimensionen, Filtern, Berichten, Arbeitsbereichen und Dashboards. Adobe aktualisiert diese Profile kontinuierlich und stellt sie seinen Lizenznehmern über das Software Support-Programm zur Verfügung. Außerdem können Benutzer von Adobe-Anwendungen zusätzliche Profile definieren und mit oder anstelle der von Adobe bereitgestellten Profile verwenden.

Das Profil-Management-System ermöglicht das Überschreiben der Profilkonfigurationen durch Profile mit höherer Ebene. Verwenden Sie diese Funktion, wenn Sie eine der in diesen Profilen enthaltenen Definitionen überschreiben möchten, nachdem sie installiert wurden. Bei der Installation neuer Versionen dieser Profile werden alle früheren Versionen überschrieben. Daher würden Änderungen, die direkt an diesen Profilen vorgenommen werden, bei der Installation der neuen Profile überschrieben.

Profile für vertikale Märkte oder bestimmte Arten von Unternehmen oder Branchen stehen möglicherweise auch bei Adobe ClientCare zur Verfügung. Im Folgenden werden die Grundlinienprofile beschrieben:

* Das **Basisprofil** enthält Konfigurationsdateien, die im Lieferumfang von Insight Server enthalten sind. Das Basisprofil sollte vom Benutzer oder Administrator nicht geändert werden. Änderungen, die im Basisprofil vorgenommen wurden, können überschrieben werden, wenn Adobe eine nächste Version von Insight Server oder einer anderen Softwareanwendung veröffentlicht.
* Das **Traffic-Profil** umfasst eine Reihe grundlegender Metriken, Dimensionen und Filter für Webanalyse. Er enthält außerdem Vorlagen-Arbeitsbereiche, Berichte und Dashboards, die die Analyse, Berichterstellung und ein allgemeines Verständnis der Aktivitätstrends und -muster auf der Website insgesamt erleichtern. Dieses Profil funktioniert &quot;standardmäßig&quot; bei einer Basisinstallation von Site.
* Das **Value-Profil** umfasst einen Satz von Metriken und Dimensionen sowie Vorlagen-Arbeitsbereiche, Berichte und Dashboards, die mit dem integrierten Site-Geschäftswert und dem Konversionsmodell verknüpft sind. Dieses Profil ermöglicht es Benutzern, Wertereignisse auf der Site zu identifizieren und diesen Ereignissen einen Geldwert zuzuordnen.

   Dieses Profil erweitert Ihre Site-Analysefunktionen um ein Geschäftswertmodell, eine erweiterte Methode zur Messung und Verfolgung der von Ihrer Site generierten Wertschöpfung. Wertereignisse und ihr relativer Wert werden über eine einfache Drag &amp; Drop-Oberfläche innerhalb der Site definiert. Site verwendet diese Definitionen, um den von jeder Sitzung generierten Geschäftswert zu berechnen. Diese Informationen werden wiederum verwendet, um Metriken wie Werte, Wertereignisse, Konversion usw. zu definieren. Mit diesen Metriken können Sie Fragen wie die folgenden beantworten:

   * Welcher ist der rentabelste Pfad durch die Site?
   * Welche verweisende Stelle oder welche Kampagne hat den meisten Wert generiert?
   * Wie hoch ist die durchschnittliche Anzahl der Käufe auf der Site pro Tag? (Wie viele Wertereignisse treten durchschnittlich pro Tag auf?)
   Nachdem Sie ein Geschäftswertmodell in der Site definiert haben, können Sie die Wertmetriken und Dimensionen in Ihrer Analyse verwenden.

* Das **Marketing-Profil** umfasst Metriken und Dimensionen sowie Vorlagen-Arbeitsbereiche, Berichte und Dashboards, die mit der Analyse von Internetmarketingkampagnen verknüpft sind, einschließlich Suchanalyse und erweiterter Referrer-Analyse.

Adobe stellt außerdem die folgenden optionalen Profile zur Verfügung:

* Das **IP-Geo-Positionsprofil** umfasst Dimensionen und Ebenendateien, die mit der Analyse der Standorte von Besuchern auf der Grundlage der IP-Geo-Standortdaten zusammenhängen, die Adobe von Quova, Inc. bereitgestellt und in Data Workbench integriert wurden.
* Das IP-Geo-Intelligence-Profil umfasst Dimensionen und Ebenendateien, die sich auf die Analyse der Standorte des Besuchers beziehen, basierend auf IP-Geo-Intelligence-Daten, die Adobe von Digital Envoy, Inc. bereitgestellt und in Data Workbench integriert werden.

Informationen zu IP-Geo-Standorten und IP-Geo-Intelligence-Profilen erhalten Sie von Ihrem Adobe-Supportpersonal. Die folgenden Abschnitte beschreiben die Metriken und Dimensionen, die in den einzelnen Baseline-Profilen definiert werden.
