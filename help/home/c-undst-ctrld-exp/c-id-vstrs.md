---
description: Eine typische Konfiguration von Site verwendet Cookies, um Besucher Ihrer Website eindeutig zu identifizieren und ihr Verhalten im Laufe der Zeit zu verfolgen.
solution: Insight,Analytics
title: Wie identifiziert die Site Besucher?
topic: Data workbench
uuid: e1e451b8-e827-4010-bda9-9147c3b09958
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Wie identifiziert die Site Besucher?{#how-does-site-identify-visitors}

Eine typische Konfiguration von Site verwendet Cookies, um Besucher Ihrer Website eindeutig zu identifizieren und ihr Verhalten im Laufe der Zeit zu verfolgen.

Wenn ein bestimmter Browser (als Besucher bezeichnet) zum ersten Mal eine Anforderung Ihrer Website aufstellt, [!DNL Sensor] wird mit Ihrem Webserver ein beständiges Cookie gesetzt (standardmäßig [!DNL cs(cookie)(v1st)]), das intern im System als [!DNL x-trackingid]. Dieses Cookie wird nur einmal gesetzt, und zwar bei der ersten Anforderung, die der Besucher an Ihre Website gesendet hat. Er wird dann jedes Mal, wenn der Browser eine Anforderung (eine Seite oder eine eingebettete Objektanforderung) Ihrer Website stellt, von diesem Besucher erfasst.

Die Annahme eines beständigen Cookies liegt im Ermessen des Browsers. Wenn ein Benutzer sich dafür entscheidet, beständige Cookies zu blockieren, werden seine Seitenansichtenanforderungen weiterhin protokolliert, aber die Messungsdaten aus diesen Anforderungen werden nicht mit einem bestimmten Besucher oder dessen Sitzungen auf der Website korreliert, es sei denn, Sie implementieren eine alternative Methode zur Besucheridentifizierung, z. B. die Hash-Transformation in den Feldern IP und UserAgent.

>[!NOTE]
>
>Site-Experimente können nur in Datasets analysiert werden, bei denen die einzige verwendete Methode zur Besucheridentifizierung die Methode des [!DNL Sensor] festgelegten persistenten Cookies ist. Sensoren, die auf J2EE-Servern (JBoss, Tomcat, WebLogic und WebSphere) ausgeführt werden, unterstützen keine kontrollierte Experimentierung.

Während eines kontrollierten Experiments können Benutzer, die keine Cookies akzeptieren, von einem Klick zum nächsten in verschiedene Experimentgruppen unterteilt werden. Dies wird nur dann zu einem Problem, wenn Sie Ihre Testanalyse durchführen, während der Filter für beschädigte Sitzungen deaktiviert ist [!DNL Insight], was von Adobe nicht empfohlen wird.

Weitere Informationen zum Filter für ungültige Sitzungen finden Sie im * [!DNL Insight] Benutzerhandbuch*.

Wenn ein Besucher das Cookie während eines Experiments löscht, wird dem Besucher ein neues Cookie zugewiesen, das möglicherweise einer anderen Gruppe zugewiesen wird. Da Adobe den Besucher als neu identifiziert, wird das Experiment nicht ungültig.
