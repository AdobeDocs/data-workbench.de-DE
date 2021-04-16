---
description: Eine typische Site-Konfiguration verwendet Cookies, um Besucher Ihrer Website eindeutig zu identifizieren und deren Verhalten im Laufe der Zeit zu verfolgen.
solution: Analytics,Analytics
title: Wie werden Besucher durch Site identifiziert?
uuid: e1e451b8-e827-4010-bda9-9147c3b09958
exl-id: 2783ee11-6d6a-463d-86b5-dd63e490201f
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '331'
ht-degree: 3%

---

# Wie werden Besucher durch Site identifiziert?{#how-does-site-identify-visitors}

Eine typische Site-Konfiguration verwendet Cookies, um Besucher Ihrer Website eindeutig zu identifizieren und deren Verhalten im Laufe der Zeit zu verfolgen.

Wenn ein bestimmter Browser (als Besucher bezeichnet) zum ersten Mal eine Anforderung Ihrer Website ausgibt, arbeitet [!DNL Sensor] mit Ihrem Webserver, um ein beständiges Cookie zu setzen (standardmäßig [!DNL cs(cookie)(v1st)]), das intern im System als [!DNL x-trackingid] interpretiert wird. Dieses Cookie wird nur einmal gesetzt, und zwar bei der ersten Anforderung, die der Besucher an Ihre Website gesendet hat. Er wird dann jedes Mal, wenn der Browser eine Anforderung (eine Seite oder eine eingebettete Objektanforderung) Ihrer Website aufnimmt, von diesem Besucher erfasst.

Die Annahme eines beständigen Cookies liegt im Ermessen des Browsers. Wenn ein Benutzer sich dafür entscheidet, beständige Cookies zu blockieren, werden die Seitenanfrageanforderungen weiterhin protokolliert, die Messungsdaten aus diesen Ansichten werden jedoch nicht mit einem bestimmten Besucher oder dessen Sitzungen auf der Website korreliert, es sei denn, Sie implementieren eine alternative Methode zur Identifizierung des Besuchers, z. B. die Hash-Transformation in den Feldern IP und UserAgent.

>[!NOTE]
>
>Site-Experimente können nur in Datasets analysiert werden, bei denen die einzige verwendete Methode zur Identifizierung des Besuchers die Methode [!DNL Sensor] zum Festlegen eines persistenten Cookies ist. Sensoren, die auf J2EE-Servern (JBoss, Tomcat, WebLogic und WebSphere) ausgeführt werden, unterstützen keine kontrollierte Experimentierung.

Während eines kontrollierten Experiments können Benutzer, die keine Cookies akzeptieren, von einem Klick zum nächsten in verschiedene Experimentgruppen unterteilt werden. Dies wird nur dann zu einem Problem, wenn Sie Ihre Test-Analyse durchführen, während der Filter für beschädigte Sitzungen in [!DNL Insight] deaktiviert ist. Diese Adobe wird nicht empfohlen.

Weitere Informationen zum Filter &quot;Fehlerhafte Sitzung&quot;finden Sie im * [!DNL Insight] Benutzerhandbuch*.

Wenn ein Besucher das Cookie während eines Experiments löscht, wird dem Besucher ein neues Cookie zugewiesen, das möglicherweise einer anderen Gruppe zugewiesen wird. Da die Adobe den Besucher als neu identifiziert, ist das Experiment nicht ungültig.
