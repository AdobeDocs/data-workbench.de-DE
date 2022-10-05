---
description: Anleitung zum Aktualisieren von Repeater mit Insight oder zum Aktualisieren durch Kopieren von Dateien.
title: Upgrade von Repeater
uuid: 2027ed9e-9dd9-40f5-b7e9-2709f8745b5c
exl-id: f81fa79e-f660-48fd-b2ff-419961d49c55
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 1%

---

# Upgrade von Repeater{#upgrading-repeater}

{{eol}}

Anleitung zum Aktualisieren von Repeater mit Insight oder zum Aktualisieren durch Kopieren von Dateien.

Sie können eine der folgenden Methoden zum Aktualisieren verwenden [!DNL Repeater] von Platform 4.x oder höher:

* Wenn Sie eine Verbindung zwischen [!DNL Insight] und [!DNL Repeater] wie in [Erstellen einer Verbindung zwischen Insight und Repeater](../../../../home/c-inst-svr/c-rptr-fntly/c-cnfg-rptr-fntly/t-crt-conn-ins-rptr.md#task-785bfe5f0e31484683e4345038add118)können Sie [!DNL Insight] zum Upgrade [!DNL Repeater]. Siehe [Upgrade von Repeater mithilfe von Insight](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-upgrd-rptr.md#section-59c24448fd0f45c08abd0245ad746764).

   -oder-

* Wenn Sie keine Verbindung zwischen [!DNL Insight] und [!DNL Repeater]müssen Sie die Aktualisierungsdateien direkt in die [!DNL Repeater] Maschine. Siehe [Aktualisieren von Repeater durch Kopieren von Dateien](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-upgrd-rptr.md#section-202f2209f6604f19a15d96b517ea1bc1).

## Upgrade von Repeater mithilfe von Insight {#section-59c24448fd0f45c08abd0245ad746764}

1. Im [!DNL Insight] Computer, kopieren Sie die [!DNL bin] Ordner aus dem [!DNL Insight Server] Upgrade-Paket auf [!DNL Temp] Ordner im Verzeichnis, in dem [!DNL Insight] installiert ist.
1. Starten [!DNL Insight].
1. In [!DNL Insight]auf [!DNL Admin] > [!DNL Dataset and Profile] klicken Sie auf die **[!UICONTROL Servers Manager]** Miniaturansicht, um den Arbeitsbereich &quot;Server Manager&quot;zu öffnen.
1. Klicken Sie mit der rechten Maustaste auf das Symbol der [!DNL Repeater] Sie aktualisieren möchten, und klicken Sie auf **[!UICONTROL Server Files]**.
1. Im [!DNL Server Files Manager]Führen Sie die folgenden Schritte aus, um die Aktualisierungsdateien auf den Server hochzuladen:

   1. Suchen Sie die [!DNL bin] Ordner.
   1. Klicken Sie mit der rechten Maustaste auf das Häkchen für die [!DNL bin] Ordner im Ordner &quot;Temp&quot;und wählen Sie **[!UICONTROL Save Directory to]** > *&lt;**[!UICONTROL server name]**>*.

>[!NOTE]
>
>Es wird eine Meldung angezeigt, die angibt, dass dieser Schritt Dateien mit demselben Namen überschreibt, die auf dem Server vorhanden sind. Klicken **[!UICONTROL Yes]** , um fortzufahren.

>[!NOTE]
>
>Wenn Sie zusätzliche Dateien hochladen müssen, um Ihre [!DNL Repeater] -Upgrade, stellt Adobe entsprechende Anweisungen bereit.

Nach dem Hochladen der Upgrade-Dateien in die [!DNL Repeater] Maschine, [!DNL Repeater] startet automatisch selbst neu und lädt die neue Version.

## Aktualisieren von Repeater durch Kopieren von Dateien {#section-202f2209f6604f19a15d96b517ea1bc1}

1. Öffnen Sie die von Adobe bereitgestellte Aktualisierungsdatei. Wahrscheinlich ist diese Datei eine [!DNL .zip] Datei für die Aktualisierung [!DNL Insight Server].
1. Navigieren Sie zum Verzeichnis, in dem Sie installiert haben [!DNL Repeater] (z. B. [!DNL D:\Adobe\Repeater]).
1. Kopieren Sie die [!DNL bin] -Ordner in [!DNL .zip] Datei speichern und in Ihre [!DNL Repeater] Installationsordner zum Überschreiben der vorhandenen [!DNL bin] Ordner.

>[!NOTE]
>
>Wenn Sie zusätzliche Dateien hochladen müssen, um Ihre [!DNL Insight Server] -Upgrade, stellt Adobe entsprechende Anweisungen bereit.

Nachdem Sie die Aktualisierungsdateien in die [!DNL Repeater] Maschine, [!DNL Repeater] startet automatisch selbst neu und lädt die neue Version.
