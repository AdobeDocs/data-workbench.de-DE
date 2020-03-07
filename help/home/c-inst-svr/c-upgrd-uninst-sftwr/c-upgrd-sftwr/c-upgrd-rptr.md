---
description: Anweisungen zum Aktualisieren von Repeater mit Insight oder zum Aktualisieren durch Kopieren von Dateien.
solution: Insight
title: Verstärker aktualisieren
uuid: 2027ed9e-9dd9-40f5-b7e9-2709f8745b5c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Verstärker aktualisieren{#upgrading-repeater}

Anweisungen zum Aktualisieren von Repeater mit Insight oder zum Aktualisieren durch Kopieren von Dateien.

Sie können eine der folgenden Methoden verwenden, um eine Aktualisierung [!DNL Repeater] von Plattform 4.x oder höher durchzuführen:

* Wenn Sie eine Verbindung zwischen [!DNL Insight] und [!DNL Repeater] , wie unter [Erstellen einer Verbindung zwischen Insight und Repeater](../../../../home/c-inst-svr/c-rptr-fntly/c-cnfg-rptr-fntly/t-crt-conn-ins-rptr.md#task-785bfe5f0e31484683e4345038add118)beschrieben, erstellt haben, können Sie [!DNL Insight] eine Aktualisierung verwenden [!DNL Repeater]. Siehe [Aktualisieren eines Repeaters mit Insight](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-upgrd-rptr.md#section-59c24448fd0f45c08abd0245ad746764).

   -oder-

* Wenn Sie keine Verbindung zwischen [!DNL Insight] und herstellen konnten oder nicht, müssen [!DNL Repeater]Sie die Aktualisierungsdateien direkt auf den [!DNL Repeater] Computer kopieren. Siehe [Aktualisieren von Repeater durch Kopieren von Dateien](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-upgrd-rptr.md#section-202f2209f6604f19a15d96b517ea1bc1).

## Aktualisieren eines Repeaters mit Insight {#section-59c24448fd0f45c08abd0245ad746764}

1. Kopieren Sie auf dem [!DNL Insight] Computer den [!DNL bin] Ordner aus dem [!DNL Insight Server] Aktualisierungspaket in den [!DNL Temp] Ordner, in dem [!DNL Insight] er installiert ist.
1. Start [!DNL Insight].
1. Klicken Sie [!DNL Insight]auf der Registerkarte [!DNL Admin] > [!DNL Dataset and Profile] auf die **[!UICONTROL Servers Manager]** Miniaturansicht, um den Arbeitsbereich &quot;Server Manager&quot;zu öffnen.
1. Klicken Sie mit der rechten Maustaste auf das Symbol des [!DNL Repeater] Aktualisierungsvorgangs und klicken Sie auf **[!UICONTROL Server Files]**.
1. Führen Sie [!DNL Server Files Manager]folgende Schritte aus, um die Aktualisierungsdateien auf den Server hochzuladen:

   1. Suchen Sie den [!DNL bin] Ordner.
   1. Klicken Sie mit der rechten Maustaste auf das Häkchen für den [!DNL bin] Ordner im Temp-Ordner und wählen Sie **[!UICONTROL Save Directory to]** > *&lt;**[!UICONTROL server name]**>*.

>[!NOTE]
>
>Es wird eine Meldung angezeigt, die angibt, dass bei diesem Schritt Dateien mit demselben Namen überschrieben werden, die auf dem Server vorhanden sind. Click **[!UICONTROL Yes]** to continue.

>[!NOTE]
>
>Wenn Sie zum Abschluss des [!DNL Repeater] Upgrades zusätzliche Dateien hochladen müssen, stellt Adobe entsprechende Anweisungen bereit.

Nachdem Sie die Aktualisierungsdateien auf den [!DNL Repeater] Computer hochgeladen haben, wird [!DNL Repeater] automatisch ein Neustart durchgeführt und die neue Version wird geladen.

## Aktualisieren von Repeater durch Kopieren von Dateien {#section-202f2209f6604f19a15d96b517ea1bc1}

1. Öffnen Sie die von Adobe bereitgestellte Aktualisierungsdatei. Diese Datei ist höchstwahrscheinlich eine [!DNL .zip] Datei, die aktualisiert werden [!DNL Insight Server]kann.
1. Wechseln Sie zu dem Ordner, in dem Sie installiert haben [!DNL Repeater] (z. B. [!DNL D:\Adobe\Repeater]).
1. Kopieren Sie den [!DNL bin] Ordner in die [!DNL .zip] Datei und fügen Sie ihn in Ihren [!DNL Repeater] Installationsordner ein, um den vorhandenen [!DNL bin] Ordner zu überschreiben.

>[!NOTE]
>
>Wenn Sie zum Abschluss des [!DNL Insight Server] Upgrades zusätzliche Dateien hochladen müssen, stellt Adobe entsprechende Anweisungen bereit.

Nachdem Sie die Aktualisierungsdateien auf den [!DNL Repeater] Computer kopiert haben, wird [!DNL Repeater] automatisch ein Neustart durchgeführt und die neue Version wird geladen.
