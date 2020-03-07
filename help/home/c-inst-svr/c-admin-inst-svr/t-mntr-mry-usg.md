---
description: Informationen zur Bewertung und Überwachung der Adressraumlast.
solution: Insight
title: Speichernutzung überwachen
uuid: e7f1c51b-d874-43f4-a074-1c064b5f298a
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Speichernutzung überwachen{#monitoring-memory-usage}

Informationen zur Bewertung und Überwachung der Adressraumlast.

**Überwachen des Ladevorgangs des Adressraums**

**Empfohlene Häufigkeit:** Täglich

Die Adressraumlast ist ein Maß für den Anteil des maximalen Adressraums, den ein ordnungsgemäß konfigurierter Benutzer [!DNL Insight Server] verwendet. Selbst wenn die Konfigurationsparameter geändert werden, um die Speicherbelegung zu reduzieren, wird sie in der Regel erst nach einem Neustart des [!DNL Insight Server] Dienstes verringert.

Eine Sicherheitsmarge ist in der maximalen Adressenraumlast integriert, um unerwartete Erhöhungen der Adressenraumnutzung zu berücksichtigen. Sie sollten diese Sicherheitsmarge niemals bewusst eingrenzen. Es ist in Notfällen verfügbar und nicht für die Unterstützung von Funktionen, die zu Ihrer Adobe-Anwendung hinzugefügt wurden.

>[!NOTE]
>
>Um mehr Adressraum verfügbar zu machen und Speichererschöpfungsfehler zu vermeiden, stellen Sie sicher, dass auf Ihrem Betriebssystem der /3GB-Switch aktiviert ist und dass Low-Fragmentation Heap in Betrieb ist.

Fehler, die im [!DNL Insight Server] Ereignisdatenprotokoll protokolliert werden, können Hinweise darauf bieten, dass Probleme bei der Belastung mit dem Adressraum auftreten:

* Die Fehler &quot;Der angeforderte X-Byteblock ist zu groß&quot;deuten darauf hin, dass sich etwas übermäßig auf die Adressraumlast, Leistung und Netzwerkbandbreite auswirkt. Solche großen Blöcke können erheblich zur Nutzung des Address Space beitragen, sowohl durch den Einsatz von viel Speicher als auch durch die Notwendigkeit großer zusammenhängender Blöcke des Address Space.

   Um dieses Problem zu beheben, können Sie die Kardinalität Ihrer größten Dimensionen reduzieren, wodurch sich die Belastung des Adressraums erhöht. Wenn Sie die Kardinalität der Dimensionen nicht reduzieren können, sollten Sie versuchen, die Belastung des Adressraums so gering wie möglich zu halten, dass Sie eine unerwartete Erhöhung bewältigen können.
* Die Fehler &quot;Speicherbudget überschritten&quot;deuten möglicherweise darauf hin, dass Sie die Abfragespeichergrenze erhöhen müssen. Der von Abfragen verwendete Arbeitsspeicher ist proportional zur Dimensionskardinalität und in einigen Fällen auch zur Länge der Elementnamen. Wenn Sie die Einstellung für den Abfragespeicher erhöhen, erhöhen Sie die Gesamtlast des Adressraums und verringern Sie die Größe.

>[!NOTE]
>
>Standardmäßig ist die Verwendung großer Seiten zulässig und die Suche mit Speicherzuordnung ist deaktiviert. In DWB 6.7 und höher kann dies in der Datensatzkonfiguration geändert werden. Änderungen erfordern einen Neustart des Servers.

**So bewerten Sie die Auslastung des Adressraums**

Um die Adressenraumlast für Ihr System genau zu bewerten, empfiehlt Adobe die Neuverarbeitung des Datensatzes, einige normale Abfragen ohne anschließenden Neustart durchzuführen [!DNL Insight Server]und dann die gemessene Adressraumlast anzuzeigen, indem Sie die folgenden Schritte ausführen.

Wenn eine Datei [!DNL Insight Server] seit dem letzten Neustart nicht signifikant neu verarbeitet und abgefragt wurde, sollten Sie keine Schlussfolgerungen aus der Adressraumladung ziehen.

1. Klicken Sie [!DNL Insight]auf der Registerkarte [!DNL Admin] > [!DNL Dataset and Profile] auf die **[!UICONTROL Servers Manager]** Miniaturansicht, um den Arbeitsbereich &quot;Server Manager&quot;zu öffnen.
1. Klicken Sie mit der rechten Maustaste auf das Symbol des zu konfigurierenden [!DNL Insight Server] Objekts und klicken Sie auf **[!UICONTROL Detailed Status]**.
1. Klicken Sie in der Oberfläche für den Detailstatus auf , **[!UICONTROL Memory Status]** um den Inhalt anzuzeigen. Im Parameter &quot;Adressraum laden&quot;können Sie die Adressraumlast als Prozentsatz und eine in Klammern eingeschlossene Beschreibung als Status anzeigen.

   In der folgenden Tabelle sind die Bereiche und der Status für die Belastung mit dem Adressraum aufgeführt. Für jeden Bereich wird eine empfohlene Aktion angezeigt.

   | Adressraum-Ladevorgang (%) | Status | Empfohlene Aktion |
   |---|---|---|
   | 0-15 | Muskel- und Mittelwert | Keine. |
   | 15-33 | light | Keine. |
   | 33-66 | mäßig | Keine. |
   | 66-100 | schwer | Fügen Sie zur Vermeidung von Fehlern bei der Speichererschöpfung keine zusätzlichen Funktionen hinzu oder versuchen Sie nicht, weitere Daten zu verarbeiten. |
   | 100-125 | Zuverlässigkeit beeinträchtigt | Passen Sie Ihre Datensatzkonfiguration an, um die Belastung mit dem Adressraum zu verringern. |
   | 125 oder höher | Fehler unmittelbar | Passen Sie Ihre Datensatzkonfiguration an, um die Belastung mit dem Adressraum zu verringern. Möglicherweise wird der sofortige Status des Fehlers nicht angezeigt, bevor ein Fehler auftritt. |

   Wenn Sie einen Adressraum von über 100 % haben, sollten Sie die Konfiguration so bald wie möglich ändern, um die Verwendung des Adressraums zu reduzieren.

