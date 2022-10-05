---
description: Anweisungen zum Deinstallieren von Insight Server, Transform oder Repeater.
title: Deinstallieren der Software
uuid: 79cf0db6-0f99-40fa-a7b0-38dd8d7246bd
exl-id: 3ba5e5e3-c1a2-4ecb-9f88-a3fe923837e7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 4%

---

# Deinstallieren der Software{#uninstalling-your-software}

{{eol}}

Anweisungen zum Deinstallieren von Insight Server, Transform oder Repeater.

## Deinstallieren der Insight Server-Adobe {#section-7d7befe672854df79bb6c28ec02f6670}

1. Rückgängigmachen der Registrierung [!DNL Insight Server] Windows-Dienst.

   1. Öffnen Sie eine Eingabeaufforderung und navigieren Sie zum Unterordner &quot;bin&quot;im Ordner, in dem Sie installiert haben [!DNL Insight Server].

      Beispiel: [!DNL C:\Adobe\Server\bin]

   1. Führen Sie an der Eingabeaufforderung den folgenden Befehl aus, um die Registrierung als Dienst unter Microsoft Windows zu beenden und aufzuheben:

      ```
      InsightServer64.exe /unregserver
      ```

1. Löschen Sie die [!DNL Insight Server] Installationsverzeichnis.

## Deinstallieren von Transform {#section-5e6a604dadb5477ba4dc9f93c9be0897}

1. Führen Sie die folgenden Schritte aus, um die [!DNL profile.cfg] Datei für jedes Profil, mit dem Sie [!DNL Transform].

   1. Öffnen Sie den [!DNL Profile Manager].
   1. Klicken Sie mit der rechten Maustaste auf das Häkchen neben [!DNL profile.cfg] und klicken Sie auf **[!UICONTROL Make Local]**. Ein Häkchen für diese Datei wird im [!DNL User] Spalte.

   1. Klicken Sie mit der rechten Maustaste auf das neu erstellte Häkchen und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. Die [!DNL profile.cfg] angezeigt.

   1. Im [!DNL profile.cfg] -Fenster, löschen Sie die [!DNL Transform] Profileintrag aus dem Ordner-Vektor.

   1. Rechtsklick **[!UICONTROL (modified)]** Klicken Sie oben im Fenster auf **[!UICONTROL Save]**.

   1. Im [!DNL Profile Manager]klicken Sie mit der rechten Maustaste auf das Häkchen für [!DNL profile.cfg] im [!DNL User] und klicken Sie auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*.

1. Löschen Sie die [!DNL Transform] Ordner aus dem [!DNL Profiles] Ordner in [!DNL Insight Server] Installationsverzeichnis.

## Deinstallieren von Repeater {#section-2f94141d956749d88f549dbea26e5272}

1. Rückgängigmachen der Registrierung [!DNL Repeater] Windows-Dienst.

   1. Öffnen Sie eine Eingabeaufforderung und navigieren Sie zum Unterordner &quot;bin&quot;im Ordner, in dem Sie installiert haben [!DNL Repeater].

      Beispiel: [!DNL D:\Adobe\Repeater\bin]

   1. Führen Sie an der Eingabeaufforderung den folgenden Befehl aus, um die Registrierung als Dienst unter Microsoft Windows zu beenden und aufzuheben:

      ```
      InsightServer64.exe /unregserver
      ```

1. Löschen Sie die [!DNL Repeater] Installationsverzeichnis.
