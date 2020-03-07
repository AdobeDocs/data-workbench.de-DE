---
description: Die Transform-Funktion wird auf einem Insight Server-FSU-Computer ausgeführt, um den Export von Protokollquellendaten für die Verwendung durch andere Anwendungen zu aktivieren.
solution: Insight
title: Transform konfigurieren
uuid: 0526704a-71b2-4094-9d3a-1ba84f4dc287
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Transform konfigurieren{#configuring-transform}

Die Transform-Funktion wird auf einem Insight Server-FSU-Computer ausgeführt, um den Export von Protokollquellendaten für die Verwendung durch andere Anwendungen zu aktivieren.

[!DNL Transform] Sie können [!DNL .vsl] Dateien, Protokolldateien, XML-Dateien und ODBC-Daten lesen und die Daten als [!DNL .vsl] Dateien, Textdateien oder durch Trennzeichen getrennte Textdateien exportieren, die von Data Warehouse beim Laden von Routinen, Prüfungsagenturen oder anderen Zielen verwendet werden können. Die Datenextrahierung und -umwandlung kann auf kontinuierlicher oder anderer planmäßiger Basis durchgeführt werden. Jede [!DNL Insight Server] FSU, die die Ausgabe von Daten zu geänderten Ereignissen bereitstellt, muss ausgeführt werden [!DNL Transform].

>[!NOTE]
>
>Normalerweise [!DNL Transform] wird auf einem [!DNL Insight Server] FSU installiert. Für Ihre Implementierung ist jedoch möglicherweise eine Installation auf einer [!DNL Insight Server] DPU erforderlich. Weitere Informationen erhalten Sie bei Adobe.

Informationen zu den Systemanforderungen für Installation, Konfiguration und Betrieb [!DNL Transform]finden Sie im Dokument *Mindestsystemanforderungen* .

Adobe verteilt die [!DNL Transform] Funktionen als Profil innerhalb der [!DNL .zip] Datei für das [!DNL Insight Server] Release-Paket. Das [!DNL Transform] Profil ist ein internes Profil, das zusätzliche Funktionen bietet [!DNL Insight Server]. Wie bei allen anderen von Adobe bereitgestellten internen Profilen sollte das Profil nicht geändert werden. Alle Anpassungen müssen in Ihrem Datensatz, in Ihren rollenspezifischen Profilen oder in anderen Profilen, die Sie erstellen, vorgenommen werden.

Das Profil besteht aus den folgenden Dateien:

* [!DNL Log Processing.cfg]
* [!DNL [!DNL Insight] Transform.cfg]
* [!DNL [!DNL Insight] Transform Mode.cfg]
* Eine Protokollverarbeitungsdataset enthält eine Datei

Alle diese Dateien befinden sich im [!DNL Dataset] Ordner für das Profil.

**So installieren Sie das[!DNL Transform]Profil unter[!DNL Insight Server]**

>[!NOTE]
>
>Bei den folgenden Installationsanweisungen wird davon ausgegangen, dass Sie eine Verbindung zwischen [!DNL Insight] und dem [!DNL Insight] Computer, auf dem Sie installieren, installiert und hergestellt haben [!DNL Insight Server] [!DNL Transform]. Wenn Sie dies noch nicht getan haben, lesen Sie das * [!DNL Insight] Benutzerhandbuch*.

1. Öffnen Sie die [!DNL .zip] Datei für das [!DNL Insight Server] Release-Paket und öffnen Sie den [!DNL Profiles] Ordner in dieser [!DNL .zip] Datei.
1. Kopieren Sie den [!DNL Transform] Ordner in den [!DNL Profiles] Ordner im [!DNL Insight Server] Installationsordner. Sie möchten wie im folgenden Beispiel einen [!DNL ...\Profiles\Transform] Ordner auf Ihrem Computer [!DNL Insight Server] haben.

   ![Schritt-Info](assets/win_installTransformProfile.png)

   >[!NOTE]
   >
   >Wenn Sie alle Installationsschritte ausgeführt haben [!DNL Insight Server] (siehe [Insight Server](../../../home/c-inst-svr/c-msr-server/c-msr-server.md)), befindet sich möglicherweise bereits ein [!DNL Transform] Ordner im Ordner &quot;Profile&quot;.

1. Führen Sie die folgenden Schritte aus, um die [!DNL profile.cfg] Datei für das Profil zu aktualisieren, mit dem Sie arbeiten möchten [!DNL Transform]. Der Datensatz wird nach Abschluss dieser Schritte erneut verarbeitet.

   1. Öffnen Sie den [!DNL Profile Manager].
   1. Klicken Sie mit der rechten Maustaste auf das Häkchen neben [!DNL profile.cfg] und klicken Sie auf **[!UICONTROL Make Local]**. Ein Häkchen für diese Datei wird in der [!DNL User] Spalte angezeigt.

   1. Klicken Sie mit der rechten Maustaste auf das neu erstellte Häkchen und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. Das [!DNL profile.cfg] Fenster wird angezeigt.

   1. Klicken Sie im [!DNL profile.cfg]Fenster mit der rechten Maustaste **[!UICONTROL Directories]** und klicken Sie auf **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

      Um den neuen Ordner am Ende der Liste der Ordner hinzuzufügen, klicken Sie mit der rechten Maustaste auf die Nummer oder den Namen des letzten Ordners in der Liste und klicken Sie auf **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

   1. Geben Sie den Namen des neuen Ordners ein: [!DNL Transform]
   1. Klicken Sie mit der rechten Maustaste **[!UICONTROL (modified)]** am oberen Rand des Fensters und klicken Sie auf **[!UICONTROL Save]**.

   1. Klicken Sie in der [!DNL Profile Manager]Spalte mit der rechten Maustaste auf das Häkchen für [!DNL profile.cfg] die [!DNL User] Spalte und klicken Sie dann auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*.

      >[!NOTE]
      >
      >Speichern Sie die geänderte Konfigurationsdatei nicht in einem der von Adobe bereitgestellten internen Profile (einschließlich des Profils), da Ihre Änderungen überschrieben werden, wenn Sie Updates für diese Profile installieren.

