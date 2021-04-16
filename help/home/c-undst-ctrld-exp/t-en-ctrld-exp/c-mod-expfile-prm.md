---
description: Der Parameter ExpFile verweist auf den Speicherort der Experimentkonfigurationsdatei, die Ihr Experiment definiert.
solution: Analytics,Analytics
title: Bearbeiten des ExpFile-Parameters
uuid: bf146f46-f541-4969-8d90-af1a0c969344
exl-id: 9c527ef9-aeda-4d83-8b98-a7dccbd55fe8
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '220'
ht-degree: 3%

---

# Bearbeiten des ExpFile-Parameters{#modifying-the-expfile-parameter}

Der Parameter ExpFile verweist auf den Speicherort der Experimentkonfigurationsdatei, die Ihr Experiment definiert.

Durch Festlegen dieses Parameters können Sie Experimente ausführen. Anweisungen zum Erstellen der Experimentkonfigurationsdatei finden Sie unter [Konfigurieren und Bereitstellen des Experiments](../../../home/c-undst-ctrld-exp/t-crt-ctrld-exp/c-cnfg-dply-exp.md#concept-50f1de0242904698937bb72b3ea1b429).

Im Folgenden finden Sie ein Beispiel für den Parameter ExpFile:

```
ExpFile /home/experiment.txt
```

Diese tabulatorgetrennte Textdatei ( [!DNL .txt]) kann sich an einer beliebigen Stelle im Ordner [!DNL Sensor] befinden und einen beliebigen bequemen Namen haben.

Vergewissern Sie sich, dass Sie den Speicherort des Experimentverzeichnisses und den Namen der angegebenen Konfigurationsdatei aufzeichnen, da Sie die Experimentkonfigurationsdatei (die später in diesem Handbuch beschrieben wird) unter diesem Namen und in diesem Verzeichnis speichern müssen.

>[!NOTE]
>
>Wenn Sie diesen Parameter nicht identisch auf jedem Computer im Webcluster festlegen, auf dem ein [!DNL Sensor] installiert ist, funktioniert das kontrollierte Experimentieren nicht.

Dieser Eintrag kann vorkonfiguriert werden und in der Konfigurationsdatei [!DNL Sensor] dauerhaft und ohne nachteilige Auswirkungen bleiben. Wenn der angegebene Name der Experimentkonfigurationsdatei nicht von [!DNL Sensor] gefunden wird oder leer ist (das heißt, er existiert, hat aber keinen Inhalt), führt [!DNL Sensor] keinen Versuch durch, protokolliert ein Ereignis mit Fehler auf dem HTTP-Server und funktioniert weiterhin normal in allen anderen Aspekten.
