---
description: Bevor Sie das Experiment konfigurieren, sollten Sie den alternativen Inhalt erstellen, den Sie im Experiment verwenden möchten.
solution: Analytics,Analytics
title: Erstellen des Testinhalts
topic: Data workbench
uuid: d7996522-38a6-4bb8-9736-d71157c17b45
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '164'
ht-degree: 4%

---


# Erstellen des Testinhalts{#creating-the-test-content}

Bevor Sie das Experiment konfigurieren, sollten Sie den alternativen Inhalt erstellen, den Sie im Experiment verwenden möchten.

Die Kontrollgruppe wird an den ursprünglichen URI gesendet, während die Testgruppe an den neuen alternativen URI gesendet wird.

Um Verwirrung zu vermeiden, sollten Sie die Namen der Testgruppen-Dateien nicht wiederverwenden. Wenn Sie z. B. ein Experiment mit einer Testgruppendatei mit dem Namen [!DNL test2.asp]ausführen, sollten Sie nicht [!DNL test2.asp] als Name für die Testdatei im nächsten Experiment verwenden.

Für die Hypothese, dass sich das Verschieben des grafischen Links &quot;Demo anfordern&quot;auf Ihrer Startseite auf die Besucher-Umrechnung auswirkt, erstellen wir die alternative Startseite, die den grafischen Link &quot;Demo anfordern&quot;in der neuen Position enthält. Im folgenden Abschnitt wird beschrieben, wie Sie dann angeben, dass der URI der Kontrollgruppe für einen bestimmten Prozentsatz von Besuchern durch den URI der Testgruppe ersetzt [!DNL index.asp] werden [!DNL index2.asp] soll.
