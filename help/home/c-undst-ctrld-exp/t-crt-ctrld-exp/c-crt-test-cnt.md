---
description: Bevor Sie das Experiment konfigurieren, sollten Sie den alternativen Inhalt erstellen, den Sie im Experiment verwenden möchten.
solution: Analytics
title: Erstellen des Testinhalts
uuid: d7996522-38a6-4bb8-9736-d71157c17b45
exl-id: fd46c6af-37e8-452a-880d-147b7d0cfe21
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '164'
ht-degree: 4%

---

# Erstellen des Testinhalts{#creating-the-test-content}

{{eol}}

Bevor Sie das Experiment konfigurieren, sollten Sie den alternativen Inhalt erstellen, den Sie im Experiment verwenden möchten.

Die Kontrollgruppe wird an den ursprünglichen URI gesendet, während die Testgruppe an den neuen, alternativen URI gesendet wird.

Um Verwirrung zu vermeiden, sollten Sie die Namen der Testgruppendateien nicht wiederverwenden. Wenn Sie beispielsweise ein Experiment mit einer Testgruppendatei mit dem Namen [!DNL test2.asp], verwenden Sie nicht [!DNL test2.asp] als Namen für die Testdatei in Ihrem nächsten Experiment.

Für die Hypothese, dass sich das Verschieben des grafischen Links &quot;Demo anfordern&quot;auf Ihrer Homepage auf die Besucherkonversion auswirkt, erstellen wir die alternative Homepage mit dem grafischen Link &quot;Demo anfordern&quot; an der neuen Position. Im folgenden Abschnitt wird beschrieben, wie Sie dann angeben, dass die Kontrollgruppe URI [!DNL index.asp] durch den URI der Testgruppe ersetzt werden. [!DNL index2.asp] für einen bestimmten Prozentsatz von Besuchern.
