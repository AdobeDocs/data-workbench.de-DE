---
description: Anweisungen zum Deinstallieren von Insight Server, Transform oder Repeater.
solution: Insight
title: Deinstallieren der Software
uuid: 79cf0db6-0f99-40fa-a7b0-38dd8d7246bd
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Deinstallieren der Software{#uninstalling-your-software}

Anweisungen zum Deinstallieren von Insight Server, Transform oder Repeater.

## Deinstallieren von Insight Server Adobe {#section-7d7befe672854df79bb6c28ec02f6670}

1. Heben Sie die Registrierung des [!DNL Insight Server] Windows-Dienstes auf.

   1. Öffnen Sie eine Eingabeaufforderung und navigieren Sie zum Unterverzeichnis &quot;bin&quot;in dem Ordner, in dem Sie installiert haben [!DNL Insight Server].

      Beispiel: [!DNL C:\Adobe\Server\bin]

   1. Führen Sie an der Eingabeaufforderung den folgenden Befehl aus, um ihn unter Microsoft Windows als Dienst zu beenden und die Registrierung aufzuheben:

      ```
      InsightServer64.exe /unregserver
      ```

1. Löschen Sie den [!DNL Insight Server] Installationsordner.

## Transform deinstallieren {#section-5e6a604dadb5477ba4dc9f93c9be0897}

1. Führen Sie die folgenden Schritte aus, um die [!DNL profile.cfg] Datei für jedes Profil zu aktualisieren, mit dem Sie arbeiten [!DNL Transform].

   1. Öffnen Sie den [!DNL Profile Manager].
   1. Klicken Sie mit der rechten Maustaste auf das Häkchen neben [!DNL profile.cfg] und klicken Sie auf **[!UICONTROL Make Local]**. Ein Häkchen für diese Datei wird in der [!DNL User] Spalte angezeigt.

   1. Klicken Sie mit der rechten Maustaste auf das neu erstellte Häkchen und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. Das [!DNL profile.cfg] Fenster wird angezeigt.

   1. Löschen Sie im [!DNL profile.cfg] Fenster den [!DNL Transform] Profileintrag aus dem Ordner-Vektor.

   1. Klicken Sie mit der rechten Maustaste **[!UICONTROL (modified)]** am oberen Rand des Fensters und klicken Sie auf **[!UICONTROL Save]**.

   1. Klicken Sie in der [!DNL Profile Manager]Spalte mit der rechten Maustaste auf das Häkchen für [!DNL profile.cfg] die [!DNL User] Spalte und klicken Sie dann auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*.

1. Löschen Sie den [!DNL Transform] Ordner aus dem [!DNL Profiles] Ordner in Ihrem [!DNL Insight Server] Installationsordner.

## Deinstallieren von Repeater {#section-2f94141d956749d88f549dbea26e5272}

1. Heben Sie die Registrierung des [!DNL Repeater] Windows-Dienstes auf.

   1. Öffnen Sie eine Eingabeaufforderung und navigieren Sie zum Unterverzeichnis &quot;bin&quot;in dem Ordner, in dem Sie installiert haben [!DNL Repeater].

      Beispiel: [!DNL D:\Adobe\Repeater\bin]

   1. Führen Sie an der Eingabeaufforderung den folgenden Befehl aus, um ihn unter Microsoft Windows als Dienst zu beenden und die Registrierung aufzuheben:

      ```
      InsightServer64.exe /unregserver
      ```

1. Löschen Sie den [!DNL Repeater] Installationsordner.

