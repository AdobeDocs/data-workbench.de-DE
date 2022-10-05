---
description: Die Umwandlungsfunktion wird auf einem Insight Server-FSU-Computer ausgeführt, um den Export von Protokollquelldaten für andere Anwendungen zu ermöglichen.
title: Konfigurieren von Transform
uuid: 0526704a-71b2-4094-9d3a-1ba84f4dc287
exl-id: 5dbd70e4-55fc-4446-b687-525e7957209b
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '481'
ht-degree: 1%

---

# Konfigurieren von Transform{#configuring-transform}

{{eol}}

Die Umwandlungsfunktion wird auf einem Insight Server-FSU-Computer ausgeführt, um den Export von Protokollquelldaten für andere Anwendungen zu ermöglichen.

[!DNL Transform] lesen [!DNL .vsl] Dateien, Protokolldateien, XML-Dateien und ODBC-Daten und exportieren Sie die Daten als [!DNL .vsl] -Dateien, Textdateien oder durch Trennzeichen getrennte Textdateien, die von Data Warehouse-Laderoutinen, Prüfstellen oder anderen Zielen verwendet werden können. Die Datenextraktion und -umwandlung kann fortlaufend oder auf andere geplante Weise durchgeführt werden. Jeder [!DNL Insight Server] FSU, die die Ausgabe von geänderten Ereignisdaten bereitstellt, muss ausgeführt werden [!DNL Transform].

>[!NOTE]
>
>In der Regel [!DNL Transform] auf einer [!DNL Insight Server] FSU. Ihre Implementierung erfordert jedoch möglicherweise eine Installation auf einem [!DNL Insight Server] DPU. Weitere Informationen erhalten Sie bei der Adobe.

Informationen zu den Systemanforderungen für Installation, Konfiguration und Betrieb [!DNL Transform], siehe *Mindestsystemanforderungen* Dokument.

Adobe verteilt die [!DNL Transform] als Profil innerhalb der [!DNL .zip] -Datei für [!DNL Insight Server] Release-Paket. Die [!DNL Transform] profile ist ein internes Profil, das zusätzliche Funktionen für [!DNL Insight Server]. Wie bei allen anderen von Adobe bereitgestellten internen Profilen sollte das Profil nicht geändert werden. Alle Anpassungen müssen in Ihrem Datensatz oder in rollenspezifischen Profilen oder anderen von Ihnen erstellten Profilen vorgenommen werden.

Das Profil besteht aus den folgenden Dateien:

* [!DNL Log Processing.cfg]
* [!DNL [!DNL Insight] Transform.cfg]
* [!DNL [!DNL Insight] Transform mode.cfg]
* Datensatzaufnahme zur Protokollverarbeitung

Alle diese Dateien befinden sich im [!DNL Dataset] Ordner für das Profil.

**So installieren Sie die [!DNL Transform] Profil auf[!DNL Insight Server]**

>[!NOTE]
>
>Die folgenden Installationsanweisungen setzen voraus, dass Sie installiert haben [!DNL Insight] und eine Verbindung zwischen [!DNL Insight] und [!DNL Insight Server] auf dem Sie installieren [!DNL Transform]. Wenn Sie dies noch nicht getan haben, lesen Sie den Abschnitt * [!DNL Insight] Benutzerhandbuch*.

1. Öffnen Sie die [!DNL .zip] -Datei für [!DNL Insight Server] Release-Paket und öffnen Sie die [!DNL Profiles] Ordner innerhalb dieses Ordners [!DNL .zip] -Datei.
1. Kopieren Sie die [!DNL Transform] Ordner in [!DNL Profiles] Ordner in [!DNL Insight Server] Installationsverzeichnis. Sie möchten am Ende eine [!DNL ...\Profiles\Transform] -Ordner in [!DNL Insight Server] wie im folgenden Beispiel gezeigt.

   ![Schritt-Info](assets/win_installTransformProfile.png)

   >[!NOTE]
   >
   >Wenn Sie alle Schritte zum Installieren von [!DNL Insight Server] (siehe [Insight Server](../../../home/c-inst-svr/c-msr-server/c-msr-server.md)), haben Sie möglicherweise bereits eine [!DNL Transform] im Ordner Profile .

1. Führen Sie die folgenden Schritte aus, um die [!DNL profile.cfg] Datei für das Profil, mit dem Sie verwenden möchten [!DNL Transform]. Der Datensatz wird nach Abschluss dieser Schritte erneut verarbeitet.

   1. Öffnen Sie den [!DNL Profile Manager].
   1. Klicken Sie mit der rechten Maustaste auf das Häkchen neben [!DNL profile.cfg] und klicken Sie auf **[!UICONTROL Make Local]**. Ein Häkchen für diese Datei wird im [!DNL User] Spalte.

   1. Klicken Sie mit der rechten Maustaste auf das neu erstellte Häkchen und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. Die [!DNL profile.cfg] angezeigt.

   1. Im [!DNL profile.cfg]Fenster, Rechtsklick **[!UICONTROL Directories]** und klicken Sie auf **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

      Um den neuen Ordner am Ende der Liste der Ordner hinzuzufügen, klicken Sie mit der rechten Maustaste auf die Nummer oder den Namen des letzten Ordners in der Liste und klicken Sie auf **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

   1. Geben Sie den Namen des neuen Ordners ein: [!DNL Transform]
   1. Rechtsklick **[!UICONTROL (modified)]** Klicken Sie oben im Fenster auf **[!UICONTROL Save]**.

   1. Im [!DNL Profile Manager]klicken Sie mit der rechten Maustaste auf das Häkchen für [!DNL profile.cfg] im [!DNL User] und klicken Sie auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*.

      >[!NOTE]
      >
      >Speichern Sie die geänderte Konfigurationsdatei nicht in einem der von Adobe bereitgestellten internen Profile (einschließlich des Profils), da Ihre Änderungen bei der Installation von Updates für diese Profile überschrieben werden.
