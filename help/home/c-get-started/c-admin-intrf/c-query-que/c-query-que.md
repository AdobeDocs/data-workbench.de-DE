---
description: Normalerweise beantwortet der Data Workbench-Server eingehende Benutzerabfragen beim Empfang und stellt weiterhin Ergebnisse und Aktualisierungen in Echtzeit bereit, bis der Benutzer sie nicht mehr anfordert.
solution: Analytics
title: Abfragewarteschlange
topic: Data workbench
uuid: 4d64bc89-b664-4532-9f17-be11812d36d4
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Abfragewarteschlange{#query-queue}

Normalerweise beantwortet der Data Workbench-Server eingehende Benutzerabfragen beim Empfang und stellt weiterhin Ergebnisse und Aktualisierungen in Echtzeit bereit, bis der Benutzer sie nicht mehr anfordert.

Manchmal, besonders auf Systemen mit vielen Data Workbench-Benutzern, erfordert die Anzahl der aktiven Abfragen mehr Systemressourcen, als vom Server zur Verfügung stehen. [!DNL Query Queue] erlaubt es dem Server, einige Abfragen zeitweise zu unterbrechen, bis die Ressourcen zur Verfügung stehen, die für die Beantwortung benötigt werden. Die [!DNL Query Queue] bietet außerdem Funktionen zur Priorisierung von Abfragen, die auf einer Vielzahl von Parametern basieren, sodass bei Ressourcenstreitigkeiten zuerst Abfragen mit höherer Priorität beantwortet werden.

Abfragen von einem einzelnen Client oder Berichtsserver werden in einem Stapel abgelegt und als Einheit geplant. Sie können Ressourcenmonitore konfigurieren, um die Menge bestimmter Systemressourcen zu begrenzen, die von Abfragen verwendet werden. Wenn die überwachten Ressourcen die Planung einer weiteren Abfrage zulassen, wird der Bunch mit der höchsten Priorität geplant. Benutzer, deren Abfragen aufgrund von Ressourcenbeschränkungen noch nicht geplant sind, erhalten keinen Fehler, werden jedoch darüber informiert, dass ihre Abfragen in die Warteschlange gestellt wurden und der Benutzer weiterhin an dem lokalen Beispiel arbeiten kann.

Die Standardkonfiguration beinhaltet eine einfache Konfiguration für den [!DNL Query Queue]Bericht, lässt ihn jedoch deaktiviert. Administratoren können den [!DNL Query Queue]Ressourcenmonitor aktivieren oder deaktivieren, den Umfang der verschiedenen Ressourcen für die Abfrage festlegen und komplexe Priorisierungsrichtlinien für verschiedene Benutzer konfigurieren.

**So konfigurieren Sie die Datei &quot;Server.cfg&quot;für[!DNL Query Queuing]**

1. Öffnen Sie [!DNL Server.cfg] durch Klicken auf **[!UICONTROL Admin]** > **[!UICONTROL Profile Manager]** > **[!UICONTROL Dataset]**.
1. Klicken Sie mit der rechten Maustaste **[!UICONTROL Server.cfg]** und wählen Sie Lokalisierung zur Bearbeitung aus.
1. Erweitern [!DNL Query Queue].

   ![](assets/queryqueue1.png)

1. Konfigurieren Sie die folgenden Parameter:

   * **Benutzergruppen:** Ermöglicht die Konfiguration von Richtlinien, Benutzern und der Warteschlangenpriorität. Definitionen finden Sie unter [Abfragewarteschlangen-Benutzergruppen](../../../../home/c-get-started/c-admin-intrf/c-query-que/c-query-que-user-grps.md#concept-5555f51402ed49419c067d61738474c1) .

   * **Aktiv:** (Vector) Aktiviert oder deaktiviert den [!DNL Query Queue]. Gültige Werte sind true oder false. Die Standardeinstellung ist &quot;false&quot;.

   * **StandardBenutzergruppe:** (Zeichenfolge) Geben Sie einen Namen für die Benutzergruppe ein, der Benutzer hinzugefügt werden, sofern sie nicht in einer Benutzergruppe aufgeführt sind.
   * **Ressourcenmonitore:** (Vektor) Klicken Sie mit der rechten Maustaste, um einen Ressourcenmonitor hinzuzufügen. Sie können festlegen, ob der Arbeitsspeicher des Monitors oder die Anzahl der Abfragen [!DNL Query Queue] überwacht werden soll. Klicken Sie mit der rechten Maustaste, **[!UICONTROL Resource Monitor]** um die Option &quot;Speicherbudgetmonitor&quot;oder &quot;Anzahl der Abfragen&quot;auszuwählen. Weitere Informationen finden Sie unter [Abfragewarteschlangen-Ressourcenmonitore](../../../../home/c-get-started/c-admin-intrf/c-query-que/c-query-que-res-mon.md#concept-0840967b228c4d5ba3b59b4b2759f325) .

   * **Unberührbare Priorität:** (Int) Legt fest, dass Bundches mit einer Priorität größer als oder gleich diesem Wert niemals der Planung von Bundches mit höherer Priorität vorgreifen. Wird in Verbindung mit dem [!DNL Memory Budget Monitor] , der in der Tabelle &quot; [Benutzergruppenparameter&quot;beschrieben ist, verwendet](../../../../home/c-get-started/c-admin-intrf/c-query-que/c-query-que-user-grps.md#concept-5555f51402ed49419c067d61738474c1).

