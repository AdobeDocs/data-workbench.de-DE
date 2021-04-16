---
description: Normalerweise beantwortet der Data Workbench-Server eingehende Abfragen beim Empfang und stellt weiterhin Ergebnisse und Aktualisierungen in Echtzeit bereit, bis der Benutzer sie nicht mehr anfordert.
title: Abfragewarteschlange
uuid: 4d64bc89-b664-4532-9f17-be11812d36d4
exl-id: 5d9b20bf-9396-4016-beed-cee8f533f3ea
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '417'
ht-degree: 1%

---

# Abfragewarteschlange{#query-queue}

Normalerweise beantwortet der Data Workbench-Server eingehende Abfragen beim Empfang und stellt weiterhin Ergebnisse und Aktualisierungen in Echtzeit bereit, bis der Benutzer sie nicht mehr anfordert.

Manchmal, besonders auf Systemen mit vielen Data Workbenchs, erfordert die Anzahl der aktiven Abfragen mehr Systemressourcen, als vom Server zur Verfügung stehen. [!DNL Query Queue] erlaubt es dem Server, einige Abfragen vorübergehend zu warten, bis die erforderlichen Ressourcen zur Verfügung stehen. Das [!DNL Query Queue] bietet außerdem Funktionen, mit denen Abfragen anhand verschiedener Parameter priorisiert werden können, sodass Abfragen mit höherer Priorität bei Ressourcenstreitigkeiten zuerst beantwortet werden.

Abfragen von einem einzigen Client oder Berichtsserver werden in einen Bunch gesetzt und als Einheit eingeplant. Sie können Ressourcenmonitore konfigurieren, um die Anzahl bestimmter Systemressourcen zu begrenzen, die von Abfragen verwendet werden. Wenn die überwachten Ressourcen die Planung eines weiteren Abfragen-Bunch zulassen, wird der Bunch mit der höchsten Priorität geplant. Benutzer, deren Abfragen aufgrund von Ressourcenbeschränkungen noch nicht geplant sind, erhalten keinen Fehler, werden aber darüber informiert, dass ihre Abfragen in die Warteschlange gestellt sind und der Benutzer weiterhin am lokalen Beispiel arbeiten kann.

Die Standardkonfiguration beinhaltet eine einfache Konfiguration für das [!DNL Query Queue], lässt sie jedoch deaktiviert. Administratoren können die [!DNL Query Queue]-Variablen aktivieren oder deaktivieren, Ressourcenmonitore konfigurieren, um zu bestimmen, wie viel der verschiedenen Ressourcen für die Abfrage verwendet wird, und komplexe Priorisierungsrichtlinien für verschiedene Benutzer konfigurieren.

**So konfigurieren Sie die Datei &quot;Server.cfg&quot;für[!DNL Query Queuing]**

1. Öffnen Sie [!DNL Server.cfg], indem Sie auf **[!UICONTROL Admin]** > **[!UICONTROL Profile Manager]** > **[!UICONTROL Dataset]** klicken.
1. Klicken Sie mit der rechten Maustaste auf **[!UICONTROL Server.cfg]** und wählen Sie die Option &quot;Lokal zur Bearbeitung&quot;.
1. Erweitern [!DNL Query Queue].

   ![](assets/queryqueue1.png)

1. Konfigurieren Sie die folgenden Parameter:

   * **Benutzergruppen:** Hiermit können Sie Richtlinien, Benutzer und die Warteschlangenpriorität konfigurieren. Definitionen finden Sie unter [Benutzergruppen in der Abfrage](../../../../home/c-get-started/c-admin-intrf/c-query-que/c-query-que-user-grps.md#concept-5555f51402ed49419c067d61738474c1).

   * **Aktiv:** (Vector) Aktiviert oder deaktiviert den  [!DNL Query Queue]. Gültige Werte sind true oder false. Die Standardeinstellung ist &quot;false&quot;.

   * **Standard-Benutzergruppe:** (Zeichenfolge) Geben Sie einen Namen der Benutzergruppe ein, der Benutzer hinzugefügt werden, sofern sie nicht in einer Benutzergruppe aufgeführt sind.
   * **Ressourcenmonitore:** (Vector) Klicken Sie mit der rechten Maustaste, um einen Ressourcenmonitor hinzuzufügen. Sie können angeben, ob das [!DNL Query Queue] den Speicher oder die Anzahl der Abfragen überwacht. Klicken Sie mit der rechten Maustaste auf **[!UICONTROL Resource Monitor]**, um Memory Budget Monitor oder Anzahl der Abfragen Monitor auszuwählen. Weitere Informationen finden Sie unter [Abfrage Queue Resource Monitors](../../../../home/c-get-started/c-admin-intrf/c-query-que/c-query-que-res-mon.md#concept-0840967b228c4d5ba3b59b4b2759f325).

   * **Unberührbare Priorität:** (Int) Legt fest, dass Bundches mit einer Priorität größer als oder gleich diesem Wert nie der Planung von Bundches mit höherer Priorität vorgreifen. Wird in Verbindung mit dem [!DNL Memory Budget Monitor] verwendet, das in der Tabelle [Benutzergruppenparameter](../../../../home/c-get-started/c-admin-intrf/c-query-que/c-query-que-user-grps.md#concept-5555f51402ed49419c067d61738474c1) beschrieben ist.
