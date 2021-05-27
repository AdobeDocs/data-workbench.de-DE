---
description: Normalerweise beantwortet der Data Workbench-Server eingehende Benutzerabfragen beim Empfang und stellt weiterhin Ergebnisse und Echtzeitaktualisierungen bereit, bis der  diese nicht mehr anfordert.
title: Abfragewarteschlange
uuid: 4d64bc89-b664-4532-9f17-be11812d36d4
exl-id: 5d9b20bf-9396-4016-beed-cee8f533f3ea
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '417'
ht-degree: 1%

---

# Abfragewarteschlange{#query-queue}

Normalerweise beantwortet der Data Workbench-Server eingehende Benutzerabfragen beim Empfang und stellt weiterhin Ergebnisse und Echtzeitaktualisierungen bereit, bis der  diese nicht mehr anfordert.

Manchmal benötigt die Anzahl der aktiven Abfragen mehr Systemressourcen, insbesondere auf Systemen mit vielen Data Workbenchs. [!DNL Query Queue] ermöglicht es dem Server, einige Abfragen vorübergehend auszusetzen, bis die Ressourcen verfügbar sind, die für die Beantwortung benötigt werden. Der [!DNL Query Queue] bietet außerdem Funktionen zur Priorisierung von Abfragen anhand verschiedener Parameter, sodass bei Ressourcenkonflikten Abfragen mit höherer Priorität zuerst beantwortet werden.

Abfragen von einem einzelnen Client oder Berichtsserver werden in einem Batch platziert und als Einheit geplant. Sie können Ressourcenmonitore konfigurieren, um die Anzahl bestimmter Systemressourcen zu begrenzen, die von Abfragen verwendet werden. Wenn die überwachten Ressourcen die Planung eines weiteren Abfragevorgangs zulassen, wird der Start mit der höchsten Priorität geplant. Benutzer, deren Abfragen aufgrund von Ressourcenbeschränkungen noch nicht geplant sind, erhalten keinen Fehler, werden jedoch darüber informiert, dass ihre Abfragen in die Warteschlange gestellt werden. Der Benutzer kann weiterhin an dem lokalen Beispiel arbeiten.

Die Standardkonfiguration enthält eine einfache Konfiguration für [!DNL Query Queue], lässt sie jedoch deaktiviert. Administratoren können die [!DNL Query Queue] aktivieren oder deaktivieren, Ressourcenmonitore konfigurieren, um zu bestimmen, wie viele verschiedene Ressourcen für Abfragen verwendet werden, und komplexe Richtlinien zur Priorisierung für verschiedene Benutzer konfigurieren.

**So konfigurieren Sie die Datei &quot;Server.cfg&quot;für[!DNL Query Queuing]**

1. Öffnen Sie [!DNL Server.cfg], indem Sie auf **[!UICONTROL Admin]** > **[!UICONTROL Profile Manager]** > **[!UICONTROL Dataset]** klicken.
1. Klicken Sie mit der rechten Maustaste auf **[!UICONTROL Server.cfg]** und wählen Sie diese für die Bearbeitung lokal aus.
1. Erweitern [!DNL Query Queue].

   ![](assets/queryqueue1.png)

1. Konfigurieren Sie die folgenden Parameter:

   * **Benutzergruppen:** Hier können Sie Richtlinien, Benutzer und die Priorität der Warteschlange konfigurieren. Definitionen finden Sie unter [Benutzergruppen für die Abfragewarteschlange](../../../../home/c-get-started/c-admin-intrf/c-query-que/c-query-que-user-grps.md#concept-5555f51402ed49419c067d61738474c1) .

   * **Aktiv:**  (Vektor) Aktiviert oder deaktiviert  [!DNL Query Queue]. Gültige Werte sind &quot;true&quot;oder &quot;false&quot;. Die Standardeinstellung ist &quot;false&quot;.

   * **Standardbenutzergruppe:**  (String) Geben Sie einen Namen für die Benutzergruppe ein, der Benutzer hinzugefügt werden, wenn sie nicht in einer Benutzergruppe aufgeführt sind.
   * **Ressourcenmonitore:**  (Vektor) Klicken Sie mit der rechten Maustaste, um einen Ressourcenmonitor hinzuzufügen. Sie können angeben, ob der [!DNL Query Queue] Speicher oder die Anzahl der Abfragen überwacht. Klicken Sie mit der rechten Maustaste auf **[!UICONTROL Resource Monitor]**, um Memory Budget Monitor oder Number of Queries Monitor auszuwählen. Weitere Informationen finden Sie unter [Ressourcenüberwachungen der Abfragewarteschlange](../../../../home/c-get-started/c-admin-intrf/c-query-que/c-query-que-res-mon.md#concept-0840967b228c4d5ba3b59b4b2759f325) .

   * **Unberührbare Priorität:**  (Integer) Legt fest, dass Bundches mit einer Priorität, die größer oder gleich diesem Wert ist, nie der Planung von Bundches mit höherer Priorität vorausgegangen werden. Wird zusammen mit dem [!DNL Memory Budget Monitor] verwendet, der in der [Tabelle der Benutzergruppenparameter](../../../../home/c-get-started/c-admin-intrf/c-query-que/c-query-que-user-grps.md#concept-5555f51402ed49419c067d61738474c1) beschrieben ist.
