---
description: Bevor Sie das Experiment konfigurieren, sollten Sie den alternativen Inhalt erstellen, den Sie im Experiment verwenden möchten.
solution: Insight,Analytics
title: Testinhalt erstellen
topic: Data workbench
uuid: d7996522-38a6-4bb8-9736-d71157c17b45
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Testinhalt erstellen{#creating-the-test-content}

Bevor Sie das Experiment konfigurieren, sollten Sie den alternativen Inhalt erstellen, den Sie im Experiment verwenden möchten.

Die Kontrollgruppe wird an den ursprünglichen URI gesendet, während die Testgruppe an den neuen alternativen URI gesendet wird.

Um Verwirrung zu vermeiden, sollten Sie die Namen der Testgruppen-Dateien nicht wiederverwenden. Wenn Sie z. B. ein Experiment mit einer Testgruppendatei mit dem Namen [!DNL test2.asp]ausführen, sollten Sie nicht [!DNL test2.asp] als Name für die Testdatei im nächsten Experiment verwenden.

Für die Hypothese, dass das Verschieben des grafischen Links &quot;Anforderung einer Demo&quot;auf Ihrer Homepage die Besucherumrechnung beeinflusst, erstellen wir die alternative Homepage, die den grafischen Link &quot;Anforderung einer Demo&quot;an der neuen Position enthält. Im folgenden Abschnitt wird beschrieben, wie Sie dann angeben, dass die Regelgruppen-URI durch den Test-Gruppen-URI [!DNL index.asp] [!DNL index2.asp] für einen bestimmten Prozentsatz der Besucher ersetzt werden soll.
