---
description: Informationen zur Bewertung und Überwachung der Adressraumlast.
title: Überwachen der Speichernutzung
uuid: e7f1c51b-d874-43f4-a074-1c064b5f298a
exl-id: b8c0b33b-dbec-4947-911b-11c8a83bbc9c
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '581'
ht-degree: 2%

---

# Überwachen der Speichernutzung{#monitoring-memory-usage}

Informationen zur Bewertung und Überwachung der Adressraumlast.

**Überwachen der Adressspeicherlast**

**Empfohlene Häufigkeit:** Täglich

Die Belastung des Adressenraums ist ein Maß für den Anteil des maximalen Adressenraums, den ein ordnungsgemäß konfiguriertes [!DNL Insight Server] verwendet. Selbst wenn die Konfigurationsparameter geändert werden, um die Speichernutzung zu reduzieren, wird dies in der Regel erst reduziert, wenn der [!DNL Insight Server]-Dienst neu gestartet wird.

Eine Sicherheitsmarge wird in die maximale Adressraum-Auslastung integriert, um unerwartete Erhöhungen der Adressenraumauslastung zu berücksichtigen. Sie sollten diese Sicherheitsmarge nie bewusst in die Hand nehmen. Sie ist in Notfällen verfügbar und nicht für die Unterstützung von Funktionen, die zu Ihrer Adobe App hinzugefügt wurden.

>[!NOTE]
>
>Um mehr Adressenspeicher zur Verfügung zu stellen und Fehler bei der Speichererschöpfung zu vermeiden, stellen Sie sicher, dass auf Ihrem Betriebssystem der /3GB-Switch aktiviert ist und dass Low Fragmentation Heap in Betrieb ist.

Fehler, die im Ereignisdatenprotokoll [!DNL Insight Server] protokolliert werden, können Hinweise darauf liefern, dass Probleme mit der Belastung des Adressenraums auftreten:

* Fehler vom Typ &quot;Angeforderter X-Byte-Block ist zu groß&quot;weisen darauf hin, dass sich etwas übermäßig auf die Auslastung des Adressraums, die Leistung und die Netzwerkbandbreite auswirken kann. Solche großen Blöcke können erheblich zur Nutzung von Address Space beitragen, sowohl durch den Einsatz von viel Speicher als auch durch die Anforderung großer zusammenhängender Blöcke von Address Space.

   Um dieses Problem zu beheben, können Sie die Kardinalität Ihrer größten Dimensionen reduzieren, wodurch sich die Auslastung Ihres Adressraums erhöht. Wenn Sie die Kardinalität der Dimensionen nicht reduzieren können, sollten Sie versuchen, die Adressraum-Last so klein wie möglich zu halten, damit Sie eine unerwartete Zunahme verarbeiten können.
* Die Fehler &quot;Speicherbudget überschritten&quot;weisen darauf hin, dass Sie möglicherweise die Speicherbegrenzung für die Abfrage erhöhen müssen. Der von Abfragen verwendete Speicher ist proportional zur Kardinalität der Dimensionen und in einigen Fällen auch zu den Längen der Elementnamen. Wenn Sie die Speicherbegrenzung für die Abfrage erhöhen, erhöhen Sie die Gesamtauslastung des Adressraums und verkleinern Sie die großen Dimensionen.

>[!NOTE]
>
>Standardmäßig ist die Verwendung großer Seiten zulässig und die Suche mit Speicherzuordnung ist deaktiviert. In DWB 6.7 und höher kann dies in der Datensatzkonfiguration geändert werden. Alle Änderungen erfordern einen Neustart des Servers.

**Bewertung der Adressenraumlast**

Um die Auslastung des Adressenraums für Ihr System genau zu bewerten, empfiehlt Adobe, den Datensatz erneut zu verarbeiten, einige normale Abfragen durchzuführen, ohne [!DNL Insight Server] anschließend neu zu starten, und dann die gemessene Auslastung des Adressenraums anzuzeigen, indem Sie diese Schritte ausführen.

Wenn ein [!DNL Insight Server] seit dem letzten Neustart nicht signifikant neu verarbeitet und abgefragt wurde, sollten Sie keine Schlussfolgerungen aus der Adressenraumlast ziehen.

1. Klicken Sie in [!DNL Insight] auf der Registerkarte [!DNL Admin] > [!DNL Dataset and Profile] auf die Miniaturansicht **[!UICONTROL Servers Manager]** , um den Arbeitsbereich &quot;Server Manager&quot;zu öffnen.
1. Klicken Sie mit der rechten Maustaste auf das Symbol des zu konfigurierenden [!DNL Insight Server] und klicken Sie auf **[!UICONTROL Detailed Status]**.
1. Klicken Sie in der Oberfläche für den detaillierten Status auf **[!UICONTROL Memory Status]** , um den Inhalt anzuzeigen. Im Parameter &quot;Adressraum laden&quot;können Sie die Adressspeicherlast als Prozentsatz und eine in Klammern eingeschlossene Beschreibung sehen, die den Status angibt.

   Die folgende Tabelle zeigt Bereiche und Status für die Belastung des Adressenraums. Für jeden Bereich wird eine empfohlene Aktion aufgelistet.

   | Laden des Adressraums (%) | Status | Empfohlene Aktion |
   |---|---|---|
   | 0-15 | Lee und Mittelwert | Keine. |
   | 33.15. | light | Keine. |
   | 33-66 | moderieren | Keine. |
   | 66-100 | schwer | Um Speichererschöpfungsfehler zu vermeiden, fügen Sie keine wesentlichen zusätzlichen Funktionen hinzu oder versuchen Sie nicht, mehr Daten zu verarbeiten. |
   | 100-125 | Ausfallsicherheit | Passen Sie Ihre Datensatzkonfiguration an, um die Auslastung des Adressraums zu reduzieren. |
   | 125 oder höher | Fehlschlag unmittelbar | Passen Sie Ihre Datensatzkonfiguration an, um die Auslastung des Adressraums zu reduzieren. Möglicherweise wird der unmittelbar bevorstehende Fehlerstatus nicht angezeigt, bevor ein Fehler auftritt. |

   Wenn die Belastung des Adressenraums über 100 % liegt, sollten Sie die Konfiguration so bald wie möglich ändern, um die Auslastung des Adressenraums zu reduzieren.
