---
description: Für jede Anwendung wurde eine Reihe von Standardanwendungen erstellt, damit ein oder mehrere Profil jederzeit installiert werden können.
title: Standardprofile
uuid: ff76ff7e-ccde-4d99-9109-8612a4a83183
exl-id: f1bd5c1d-5f79-4b8c-9928-97169d553631
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '625'
ht-degree: 0%

---

# Standardprofile{#baseline-profiles}

Für jede Anwendung wurde eine Reihe von Standardanwendungen erstellt, damit ein oder mehrere Profil jederzeit installiert werden können.

Zu diesen Profilen gehören die Definitionen von Standardmetriken, Dimensionen, Filtern, Berichten, Arbeitsbereichen und Dashboards. Adobe aktualisiert diese Profil kontinuierlich und stellt sie ihren Lizenznehmern über ihr Software Support-Programm zur Verfügung. Darüber hinaus können Anwender von Adobe-Anwendungen zusätzliche Profil definieren und mit oder anstelle der von der Adobe bereitgestellten Profil verwenden.

Das Profil-Management-System ermöglicht die Außerkraftsetzung der Konfigurationen eines Profils durch Profil auf höherer Ebene. Verwenden Sie diese Funktion, wenn Sie eine der in diesen Profilen enthaltenen Definitionen überschreiben möchten, nachdem sie installiert wurden. Bei der Installation neuer Versionen dieser Profil werden alle früheren Versionen überschrieben. Änderungen, die direkt an diesen Profilen vorgenommen wurden, würden daher bei der Installation der neuen Profil überschrieben.

Profil für vertikale Märkte oder bestimmte Firmen oder Branchen stehen auch bei Adobe ClientCare zur Verfügung. Im Folgenden werden die grundlegenden Profil beschrieben:

* Das **Base-Profil** enthält Konfigurationsdateien, die im Lieferumfang von Insight Server enthalten sind. Das Base-Profil sollte vom Benutzer oder Administrator nicht geändert werden. Änderungen, die im Base-Profil vorgenommen werden, können überschrieben werden, wenn Adobe eine nächste Version von Insight Server oder einer anderen Softwareanwendung veröffentlicht.
* Das **Traffic-Profil** enthält einen Satz fundamentaler Metriken, Dimensionen und Filter für Webanalysen. Er umfasst auch Vorlagenarbeitsbereiche, Berichte und Dashboard, die die Analyse, den Berichte und das allgemeine Verständnis der Trends und Aktivitäten der Internetseite insgesamt erleichtern. Dieses Profil funktioniert standardmäßig mit einer Basisinstallation von Site.
* Das **Value-Profil** umfasst einen Satz von Metriken und Dimensionen sowie Vorlagenarbeitsbereiche, Berichte und Dashboard, die mit dem integrierten Site-Geschäftswert und dem Konversionsmodell verknüpft sind. Mit diesem Profil können Benutzer Wertewerte auf der Site identifizieren und diesen Ereignissen einen Geldwert zuordnen.

   Dieses Profil erweitert Ihre Site-Analyse um ein Geschäftswertmodell, eine erweiterte Methode zur Messung und Verfolgung der von Ihrer Site generierten Wertschöpfung. Ereignis mit Werten und deren relativer Wert werden über eine einfache Drag &amp; Drop-Oberfläche innerhalb der Site definiert. Site verwendet diese Definitionen, um den Geschäftswert zu berechnen, der von jeder Sitzung generiert wurde. Diese Informationen werden wiederum verwendet, um Metriken wie Werte, Ereignis, Konversion usw. zu definieren. Mit diesen Metriken können Sie Fragen wie die folgenden beantworten:

   * Welcher ist der rentabelste Pfad durch die Site?
   * Welcher Werber oder welche Kampagne hat den meisten Wert generiert?
   * Wie hoch ist die durchschnittliche Anzahl der Käufe auf der Site pro Tag? (Wie viele Ereignis werden durchschnittlich pro Tag angezeigt?)

   Nachdem Sie ein Geschäftswertmodell in der Site definiert haben, können Sie die Wertmetriken und Dimensionen in Ihrer Analyse verwenden.

* Das **Marketing-Profil** umfasst Metriken und Dimensionen sowie Vorlagenarbeitsbereiche, Berichte und Dashboard, die mit der Analyse von Internet-Marketing-Kampagnen verknüpft sind, einschließlich der Analyse der Suche und der Analyse erweiterter Werber.

Die Adobe bietet außerdem die folgenden optionalen Profil:

* Das **IP-Geo-Position-Profil** enthält Dimensionen- und Ebenendateien, die sich auf die Analyse der Standorte der Besucher beziehen, basierend auf IP-Geo-Standortdaten, die von Quova, Inc. zur Adobe bereitgestellt und in Data Workbench integriert wurden.
* Das IP-Geo-Intelligence-Profil umfasst Dimensionen und Ebenendateien, die mit der Analyse der Standorte des Besuchers zusammenhängen, basierend auf IP-Geo-Intelligence-Daten, die von Digital Envoy, Inc. zur Adobe bereitgestellt und in Data Workbench integriert wurden.

Informationen zu IP-Geolocation und IP-Geo-Intelligence-Profilen erhalten Sie von Ihrem Adobe Support-Team. Die folgenden Abschnitte beschreiben die in den einzelnen Profilen definierten Metriken und Dimensionen.
