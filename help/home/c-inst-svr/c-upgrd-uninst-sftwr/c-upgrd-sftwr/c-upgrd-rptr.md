---
description: Anleitung zum Aktualisieren von Repeater mit Insight oder zum Aktualisieren durch Kopieren von Dateien.
title: Upgrade von Repeater
uuid: 2027ed9e-9dd9-40f5-b7e9-2709f8745b5c
exl-id: f81fa79e-f660-48fd-b2ff-419961d49c55
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 1%

---

# Upgrade von Repeater{#upgrading-repeater}

Anleitung zum Aktualisieren von Repeater mit Insight oder zum Aktualisieren durch Kopieren von Dateien.

Sie können eine der folgenden Methoden verwenden, um [!DNL Repeater] von Platform 4.x oder höher zu aktualisieren:

* Wenn Sie eine Verbindung zwischen [!DNL Insight] und [!DNL Repeater] erstellt haben, wie unter [Erstellen einer Verbindung zwischen Insight und Repeater](../../../../home/c-inst-svr/c-rptr-fntly/c-cnfg-rptr-fntly/t-crt-conn-ins-rptr.md#task-785bfe5f0e31484683e4345038add118) beschrieben, können Sie [!DNL Insight] verwenden, um [!DNL Repeater] zu aktualisieren. Siehe [Upgrade von Repeater mit Insight](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-upgrd-rptr.md#section-59c24448fd0f45c08abd0245ad746764).

   -oder-

* Wenn Sie keine Verbindung zwischen [!DNL Insight] und [!DNL Repeater] herstellen konnten oder nicht, müssen Sie die Aktualisierungsdateien direkt auf den Computer [!DNL Repeater] kopieren. Siehe [Aktualisieren von Repeater durch Kopieren von Dateien](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-upgrd-rptr.md#section-202f2209f6604f19a15d96b517ea1bc1).

## Aktualisieren von Repeater mit Insight {#section-59c24448fd0f45c08abd0245ad746764}

1. Kopieren Sie auf dem Computer [!DNL Insight] den Ordner [!DNL bin] aus dem Aktualisierungspaket [!DNL Insight Server] in den Ordner [!DNL Temp] im Verzeichnis, in dem [!DNL Insight] installiert ist.
1. Start [!DNL Insight].
1. Klicken Sie in [!DNL Insight] auf der Registerkarte [!DNL Admin] > [!DNL Dataset and Profile] auf die Miniaturansicht **[!UICONTROL Servers Manager]** , um den Arbeitsbereich &quot;Server Manager&quot;zu öffnen.
1. Klicken Sie mit der rechten Maustaste auf das Symbol [!DNL Repeater], das Sie aktualisieren möchten, und klicken Sie auf **[!UICONTROL Server Files]**.
1. Führen Sie in [!DNL Server Files Manager] die folgenden Schritte aus, um die Aktualisierungsdateien auf den Server hochzuladen:

   1. Suchen Sie den Ordner [!DNL bin] .
   1. Klicken Sie mit der rechten Maustaste auf das Häkchen für den Ordner [!DNL bin] im Temp-Ordner und wählen Sie **[!UICONTROL Save Directory to]** > *&lt;**[!UICONTROL server name]**>* aus.

>[!NOTE]
>
>Es wird eine Meldung angezeigt, die angibt, dass dieser Schritt Dateien mit demselben Namen überschreibt, die auf dem Server vorhanden sind. Klicken Sie auf **[!UICONTROL Yes]** , um fortzufahren.

>[!NOTE]
>
>Wenn Sie zusätzliche Dateien hochladen müssen, um Ihr [!DNL Repeater] Upgrade abzuschließen, stellt Adobe entsprechende Anweisungen bereit.

Nach dem Hochladen der Aktualisierungsdateien auf den Computer [!DNL Repeater] wird [!DNL Repeater] automatisch neu gestartet und die neue Version geladen.

## Aktualisieren von Repeater durch Kopieren der Dateien {#section-202f2209f6604f19a15d96b517ea1bc1}

1. Öffnen Sie die von Adobe bereitgestellte Aktualisierungsdatei. Wahrscheinlich ist diese Datei eine [!DNL .zip]-Datei für die Aktualisierung von [!DNL Insight Server].
1. Wechseln Sie zum Ordner, in dem Sie [!DNL Repeater] installiert haben (z. B. [!DNL D:\Adobe\Repeater]).
1. Kopieren Sie den Ordner [!DNL bin] in die Datei [!DNL .zip] und fügen Sie ihn in das Installationsverzeichnis [!DNL Repeater] ein, um den vorhandenen Ordner [!DNL bin] zu überschreiben.

>[!NOTE]
>
>Wenn Sie zusätzliche Dateien hochladen müssen, um Ihr [!DNL Insight Server] Upgrade abzuschließen, stellt Adobe entsprechende Anweisungen bereit.

Nachdem Sie die Aktualisierungsdateien auf den Computer [!DNL Repeater] kopiert haben, startet [!DNL Repeater] automatisch selbst neu und lädt die neue Version.
