---
description: Eine typische Konfiguration von Site verwendet Cookies, um Besucher Ihrer Website eindeutig zu identifizieren und ihr Verhalten im Zeitverlauf zu verfolgen.
solution: Analytics
title: Wie werden Besucher durch Site identifiziert?
uuid: e1e451b8-e827-4010-bda9-9147c3b09958
exl-id: 2783ee11-6d6a-463d-86b5-dd63e490201f
source-git-commit: 31f775478b0f0d968310ed10a43ad46791319ee9
workflow-type: tm+mt
source-wordcount: '331'
ht-degree: 3%

---

# Wie werden Besucher durch Site identifiziert?{#how-does-site-identify-visitors}

Eine typische Konfiguration von Site verwendet Cookies, um Besucher Ihrer Website eindeutig zu identifizieren und ihr Verhalten im Zeitverlauf zu verfolgen.

Wenn ein bestimmter Browser (als Besucher betrachtet) zum ersten Mal eine Anforderung für Ihre Website sendet, [!DNL Sensor] arbeitet mit Ihrem Webserver zusammen, um ein persistentes Cookie zu setzen (standardmäßig [!DNL cs(cookie)(v1st)]), die intern im System als [!DNL x-trackingid]. Dieses Cookie wird nur einmal bei der allerersten Anforderung des Besuchers an Ihre Website gesetzt. Er wird dann jedes Mal, wenn der Browser eine Anforderung (entweder eine Seite oder eine eingebettete Objektanforderung) Ihrer Website sendet, von diesem Besucher erfasst.

Das Akzeptieren eines persistenten Cookies liegt im Ermessen des Browsers. Wenn ein Benutzer persistente Cookies blockiert, werden seine Seitenansichtsanforderungen weiterhin protokolliert, aber die Messdaten aus diesen Anforderungen werden nicht mit einem bestimmten Besucher oder dessen Sitzungen auf der Website korreliert, es sei denn, Sie implementieren eine alternative Methode zur Besucheridentifizierung, z. B. die Hash-Transformation in den Feldern IP und UserAgent .

>[!NOTE]
>
>Site-Experimente können nur in Datensätzen analysiert werden, in denen die einzige verwendete Methode zur Besucheridentifizierung die [!DNL Sensor] persistente Cookie-Methode festlegen. Sensoren, die auf J2EE-Servern (JBoss, Tomcat, WebLogic und WebSphere) ausgeführt werden, unterstützen keine kontrollierte Experimentierung.

Während eines kontrollierten Experiments können Benutzer, die keine Cookies akzeptieren, von einem Klick zum nächsten in verschiedenen Experimentgruppen untergebracht werden. Dies wird nur dann zu einem Problem, wenn Sie Ihre Testanalyse durchführen und den Filter &quot;Beschädigte Sitzung&quot;deaktiviert in [!DNL Insight], die Adobe nicht empfohlen wird.

Weitere Informationen zum Filter für fehlerhafte Sitzungen finden Sie unter * [!DNL Insight] Benutzerhandbuch*.

Wenn ein Besucher das Cookie während eines Experiments löscht, wird dem Besucher ein neues Cookie zugewiesen, das möglicherweise einer anderen Gruppe zugewiesen wird. Da Adobe den Besucher als neu identifiziert, wird das Experiment nicht invalidiert.
