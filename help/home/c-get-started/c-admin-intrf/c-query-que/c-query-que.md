---
description: Normalerweise beantwortet der Data Workbench-Server eingehende Benutzerabfragen beim Empfang und stellt weiterhin Ergebnisse und Echtzeitaktualisierungen bereit, bis der  diese nicht mehr anfordert.
title: Abfragewarteschlange
uuid: 4d64bc89-b664-4532-9f17-be11812d36d4
exl-id: 5d9b20bf-9396-4016-beed-cee8f533f3ea
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '417'
ht-degree: 0%

---

# Abfragewarteschlange{#query-queue}

{{eol}}

Normalerweise beantwortet der Data Workbench-Server eingehende Benutzerabfragen beim Empfang und stellt weiterhin Ergebnisse und Echtzeitaktualisierungen bereit, bis der  diese nicht mehr anfordert.

Manchmal benötigt die Anzahl der aktiven Abfragen mehr Systemressourcen, insbesondere auf Systemen mit vielen Data Workbenchs. [!DNL Query Queue] ermöglicht es dem Server, einige Abfragen vorübergehend auszusetzen, bis die Ressourcen verfügbar sind, die für die Beantwortung benötigt werden. Die [!DNL Query Queue] bietet außerdem Funktionen zur Priorisierung von Abfragen anhand verschiedener Parameter, sodass bei Ressourcenkonflikten Abfragen mit höherer Priorität zuerst beantwortet werden.

Abfragen von einem einzelnen Client oder Berichtsserver werden in einem Batch platziert und als Einheit geplant. Sie können Ressourcenmonitore konfigurieren, um die Anzahl bestimmter Systemressourcen zu begrenzen, die von Abfragen verwendet werden. Wenn die überwachten Ressourcen die Planung eines weiteren Abfragevorgangs zulassen, wird der Start mit der höchsten Priorität geplant. Benutzer, deren Abfragen aufgrund von Ressourcenbeschränkungen noch nicht geplant sind, erhalten keinen Fehler, werden jedoch darüber informiert, dass ihre Abfragen in die Warteschlange gestellt werden. Der Benutzer kann weiterhin an dem lokalen Beispiel arbeiten.

Die Standardkonfiguration umfasst eine einfache Konfiguration für die [!DNL Query Queue], bleibt jedoch deaktiviert. Administratoren können die [!DNL Query Queue], konfigurieren Sie Ressourcenmonitore, um zu bestimmen, wie viel von verschiedenen Ressourcen für Abfragen verwendet wird, und konfigurieren Sie komplexe Richtlinien zur Priorisierung für verschiedene Benutzer.

**So konfigurieren Sie die Datei &quot;Server.cfg&quot;für[!DNL Query Queuing]**

1. Öffnen [!DNL Server.cfg] durch Klicken auf **[!UICONTROL Admin]** > **[!UICONTROL Profile Manager]** > **[!UICONTROL Dataset]**.
1. Rechtsklick **[!UICONTROL Server.cfg]** und lokalisieren sie für die Bearbeitung.
1. Erweitern [!DNL Query Queue].

   ![](assets/queryqueue1.png)

1. Konfigurieren Sie die folgenden Parameter:

   * **Benutzergruppen:** Ermöglicht die Konfiguration von Richtlinien, Benutzern und der Warteschlangenpriorität. Siehe [Benutzergruppen für die Abfragewarteschlange](../../../../home/c-get-started/c-admin-intrf/c-query-que/c-query-que-user-grps.md#concept-5555f51402ed49419c067d61738474c1) für Definitionen.

   * **Aktiv:** (Vektor) Aktiviert oder deaktiviert die [!DNL Query Queue]. Gültige Werte sind &quot;true&quot;oder &quot;false&quot;. Die Standardeinstellung ist &quot;false&quot;.

   * **Standardbenutzergruppe:** (String) Geben Sie einen Namen für die Benutzergruppe ein, der Benutzer hinzugefügt werden, wenn sie nicht in einer Benutzergruppe aufgeführt sind.
   * **Ressourcenüberwachung:** (Vektor) Klicken Sie mit der rechten Maustaste, um einen Ressourcenmonitor hinzuzufügen. Sie können festlegen, ob die [!DNL Query Queue] überwacht Speicher oder die Anzahl der Abfragen. Rechtsklick **[!UICONTROL Resource Monitor]** zur Auswahl von Memory Budget Monitor oder Number of Queries Monitor. Siehe [Ressourcenüberwachungen für die Abfragewarteschlange](../../../../home/c-get-started/c-admin-intrf/c-query-que/c-query-que-res-mon.md#concept-0840967b228c4d5ba3b59b4b2759f325) für weitere Informationen.

   * **Unberührbare Priorität:** (Int) Gibt an, dass Bundches mit einer Priorität, die größer oder gleich diesem Wert ist, nie der Planung von Bundches mit höherer Priorität vorausgegangen werden. Wird zusammen mit dem [!DNL Memory Budget Monitor] in [Tabelle der Benutzergruppenparameter](../../../../home/c-get-started/c-admin-intrf/c-query-que/c-query-que-user-grps.md#concept-5555f51402ed49419c067d61738474c1).
