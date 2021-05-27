---
description: Anweisungen zum Deinstallieren von Insight Server, Transform oder Repeater.
title: Deinstallieren der Software
uuid: 79cf0db6-0f99-40fa-a7b0-38dd8d7246bd
exl-id: 3ba5e5e3-c1a2-4ecb-9f88-a3fe923837e7
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 4%

---

# Deinstallieren der Software{#uninstalling-your-software}

Anweisungen zum Deinstallieren von Insight Server, Transform oder Repeater.

## Deinstallieren der Insight Server-Adobe {#section-7d7befe672854df79bb6c28ec02f6670}

1. Heben Sie die Registrierung für den Windows-Dienst auf.[!DNL Insight Server]

   1. Öffnen Sie eine Eingabeaufforderung und navigieren Sie zum Unterverzeichnis &quot;bin&quot;im Ordner, in dem Sie [!DNL Insight Server] installiert haben.

      Beispiel: [!DNL C:\Adobe\Server\bin]

   1. Führen Sie an der Eingabeaufforderung den folgenden Befehl aus, um die Registrierung als Dienst unter Microsoft Windows zu beenden und aufzuheben:

      ```
      InsightServer64.exe /unregserver
      ```

1. Löschen Sie das Installationsverzeichnis [!DNL Insight Server].

## Deinstallieren von Transform {#section-5e6a604dadb5477ba4dc9f93c9be0897}

1. Führen Sie die folgenden Schritte aus, um die [!DNL profile.cfg]-Datei für jedes Profil zu aktualisieren, mit dem Sie [!DNL Transform] verwendet haben.

   1. Öffnen Sie den [!DNL Profile Manager].
   1. Klicken Sie mit der rechten Maustaste auf das Häkchen neben [!DNL profile.cfg] und klicken Sie auf **[!UICONTROL Make Local]**. Ein Häkchen für diese Datei wird in der Spalte [!DNL User] angezeigt.

   1. Klicken Sie mit der rechten Maustaste auf das neu erstellte Häkchen und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. Das Fenster [!DNL profile.cfg] wird angezeigt.

   1. Löschen Sie im Fenster [!DNL profile.cfg] den Profileintrag [!DNL Transform] aus dem Ordner-Vektor.

   1. Klicken Sie oben im Fenster mit der rechten Maustaste auf **[!UICONTROL (modified)]** und klicken Sie auf **[!UICONTROL Save]**.

   1. Klicken Sie in der Spalte [!DNL Profile Manager] mit der rechten Maustaste auf das Häkchen für [!DNL profile.cfg] in der Spalte [!DNL User] und klicken Sie dann auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]***.

1. Löschen Sie den Ordner [!DNL Transform] aus dem Ordner [!DNL Profiles] in Ihrem [!DNL Insight Server] -Installationsverzeichnis.

## Deinstallieren von Repeater {#section-2f94141d956749d88f549dbea26e5272}

1. Heben Sie die Registrierung für den Windows-Dienst auf.[!DNL Repeater]

   1. Öffnen Sie eine Eingabeaufforderung und navigieren Sie zum Unterverzeichnis &quot;bin&quot;im Ordner, in dem Sie [!DNL Repeater] installiert haben.

      Beispiel: [!DNL D:\Adobe\Repeater\bin]

   1. Führen Sie an der Eingabeaufforderung den folgenden Befehl aus, um die Registrierung als Dienst unter Microsoft Windows zu beenden und aufzuheben:

      ```
      InsightServer64.exe /unregserver
      ```

1. Löschen Sie das Installationsverzeichnis [!DNL Repeater].
