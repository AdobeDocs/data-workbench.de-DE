---
description: Der Parameter ExpFile verweist auf den Speicherort der Experimentkonfigurationsdatei, die Ihr Experiment definiert.
solution: Insight,Analytics
title: Ändern des ExpFile-Parameters
topic: Data workbench
uuid: bf146f46-f541-4969-8d90-af1a0c969344
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Ändern des ExpFile-Parameters{#modifying-the-expfile-parameter}

Der Parameter ExpFile verweist auf den Speicherort der Experimentkonfigurationsdatei, die Ihr Experiment definiert.

Durch Festlegen dieses Parameters können Sie Experimente ausführen. Anweisungen zum Erstellen der Experimentkonfigurationsdatei finden Sie unter [Konfigurieren und Bereitstellen des Experiments](../../../home/c-undst-ctrld-exp/t-crt-ctrld-exp/c-cnfg-dply-exp.md#concept-50f1de0242904698937bb72b3ea1b429).

Im Folgenden finden Sie ein Beispiel für den Parameter ExpFile:

```
ExpFile /home/experiment.txt
```

Diese tabulatorgetrennte Textdatei ( [!DNL .txt]) kann sich an einer beliebigen Stelle im [!DNL Sensor] Ordner befinden und einen beliebigen Namen haben.

Vergewissern Sie sich, dass Sie den Speicherort des Experimentverzeichnisses und den Namen der angegebenen Konfigurationsdatei aufzeichnen, da Sie die Experimentkonfigurationsdatei (die später in diesem Handbuch beschrieben wird) unter diesem Namen und in diesem Verzeichnis speichern müssen.

>[!NOTE]
>
>Wenn Sie diesen Parameter nicht auf allen Computern im Webcluster, auf denen ein Webcluster installiert [!DNL Sensor] ist, identisch einstellen, funktioniert das kontrollierte Experimentieren nicht.

Dieser Eintrag kann vorkonfiguriert werden und dauerhaft in der [!DNL Sensor] Konfigurationsdatei bleiben, ohne dass dies negative Auswirkungen hat. Wenn der angegebene Name der Experimentkonfigurationsdatei nicht von gefunden wird [!DNL Sensor] oder leer ist (d. h., er existiert, hat aber keinen Inhalt), führt das Experiment [!DNL Sensor] nicht durch, protokolliert ein Fehlerereignis auf dem HTTP-Server und funktioniert in jeder anderen Hinsicht normal weiter.
