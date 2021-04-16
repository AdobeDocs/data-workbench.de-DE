---
description: Die Transform-Funktion wird auf einem Insight Server-FSU-Computer ausgeführt, um den Export von Protokollquellendaten für die Verwendung durch andere Anwendungen zu aktivieren.
title: Konfigurieren von Transform
uuid: 0526704a-71b2-4094-9d3a-1ba84f4dc287
exl-id: 5dbd70e4-55fc-4446-b687-525e7957209b
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '481'
ht-degree: 1%

---

# Konfigurieren von Transform{#configuring-transform}

Die Transform-Funktion wird auf einem Insight Server-FSU-Computer ausgeführt, um den Export von Protokollquellendaten für die Verwendung durch andere Anwendungen zu aktivieren.

[!DNL Transform] Sie können  [!DNL .vsl] Dateien, Protokolldateien, XML-Dateien und ODBC-Daten lesen und die Daten als  [!DNL .vsl] Dateien, Textdateien oder durch Trennzeichen getrennte Textdateien exportieren, die von Data Warehouse-Laderoutinen, Prüfungsagenturen oder anderen Zielgruppen verwendet werden können. Die Extraktion und Transformation der Daten kann kontinuierlich oder auf andere geplante Weise durchgeführt werden. Jede [!DNL Insight Server]-FSU, die die Ausgabe von geänderten Ereignis-Daten bereitstellt, muss [!DNL Transform] ausführen.

>[!NOTE]
>
>Normalerweise wird [!DNL Transform] auf einer [!DNL Insight Server]-FSU installiert. Für Ihre Implementierung ist jedoch möglicherweise eine Installation auf einer [!DNL Insight Server]-DPU erforderlich. Weitere Informationen erhalten Sie bei der Adobe.

Informationen zu den Systemanforderungen für die Installation, Konfiguration und den Betrieb von [!DNL Transform] finden Sie im Dokument *Systemanforderungen*.

Adobe verteilt die [!DNL Transform]-Funktion als Profil innerhalb der [!DNL .zip]-Datei für das [!DNL Insight Server]-Versionspaket. Das [!DNL Transform]-Profil ist ein internes Profil, das zusätzliche Funktionen für [!DNL Insight Server] bereitstellt. Wie bei allen anderen internen Profilen, die von der Adobe bereitgestellt werden, sollte das Profil nicht geändert werden. Alle Anpassungen müssen in Ihrem Datensatz oder in rollenspezifischen Profilen oder anderen von Ihnen erstellten Profilen vorgenommen werden.

Das Profil besteht aus den folgenden Dateien:

* [!DNL Log Processing.cfg]
* [!DNL [!DNL Insight] Transform.cfg]
* [!DNL [!DNL Insight] Transform Mode.cfg]
* Eine Protokollverarbeitungsdataset enthält eine Datei

Alle diese Dateien befinden sich im Ordner [!DNL Dataset] für das Profil.

**So installieren Sie das  [!DNL Transform] Profil[!DNL Insight Server]**

>[!NOTE]
>
>Bei den folgenden Installationsanweisungen wird davon ausgegangen, dass Sie [!DNL Insight] installiert und eine Verbindung zwischen [!DNL Insight] und [!DNL Insight Server] hergestellt haben, auf der Sie [!DNL Transform] installieren. Wenn Sie dies noch nicht getan haben, lesen Sie das * [!DNL Insight] Benutzerhandbuch*.

1. Öffnen Sie die Datei [!DNL .zip] für das [!DNL Insight Server] Release-Paket und öffnen Sie den Ordner [!DNL Profiles] in dieser [!DNL .zip]-Datei.
1. Kopieren Sie den Ordner [!DNL Transform] in den Ordner [!DNL Profiles] im Installationsordner von [!DNL Insight Server]. Sie möchten wie im folgenden Beispiel mit einem [!DNL ...\Profiles\Transform]-Ordner auf Ihrem [!DNL Insight Server] enden.

   ![Schritt-Info](assets/win_installTransformProfile.png)

   >[!NOTE]
   >
   >Wenn Sie alle Schritte zum Installieren von [!DNL Insight Server] ausgeführt haben (siehe [Insight Server](../../../home/c-inst-svr/c-msr-server/c-msr-server.md)), befindet sich möglicherweise bereits ein Ordner [!DNL Transform] im Ordner &quot;Profils&quot;.

1. Führen Sie die folgenden Schritte aus, um die [!DNL profile.cfg]-Datei für das Profil zu aktualisieren, mit dem Sie [!DNL Transform] verwenden möchten. Der Datensatz wird nach Abschluss dieser Schritte erneut verarbeitet.

   1. Öffnen Sie den [!DNL Profile Manager].
   1. Klicken Sie mit der rechten Maustaste auf das Häkchen neben [!DNL profile.cfg] und klicken Sie auf **[!UICONTROL Make Local]**. In der Spalte [!DNL User] wird ein Häkchen für diese Datei angezeigt.

   1. Klicken Sie mit der rechten Maustaste auf das neu erstellte Häkchen und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. Das Fenster [!DNL profile.cfg] wird angezeigt.

   1. Klicken Sie im Fenster [!DNL profile.cfg]mit der rechten Maustaste auf **[!UICONTROL Directories]** und dann auf **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

      Um den neuen Ordner am Ende der Liste der Ordner hinzuzufügen, klicken Sie mit der rechten Maustaste auf die Nummer oder den Namen des letzten Ordners in der Liste und klicken Sie auf **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

   1. Geben Sie den Namen des neuen Ordners ein: [!DNL Transform]
   1. Klicken Sie mit der rechten Maustaste auf **[!UICONTROL (modified)]** oben im Fenster und klicken Sie auf **[!UICONTROL Save]**.

   1. Klicken Sie in der Spalte [!DNL Profile Manager] mit der rechten Maustaste auf das Häkchen für [!DNL profile.cfg] in der Spalte [!DNL User] und dann auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]***.

      >[!NOTE]
      >
      >Speichern Sie die geänderte Konfigurationsdatei nicht in einem der von der Adobe bereitgestellten internen Profil (einschließlich des Profils), da Ihre Änderungen bei der Installation von Updates auf diesen Profilen überschrieben werden.
