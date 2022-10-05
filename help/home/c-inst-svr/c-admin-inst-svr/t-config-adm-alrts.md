---
description: Administrative Warnungen senden E-Mail-Benachrichtigungen an die angegebenen E-Mail-Adressen, wenn vom Insight Server während des normalen Betriebs Fehler erkannt werden.
title: Konfigurieren administrativer Warnhinweise
uuid: 398e088b-ff83-46ae-a20c-ba0b50d85702
exl-id: 886e390f-fb2c-4922-8b01-9e5133a94e1b
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '300'
ht-degree: 2%

---

# Konfigurieren administrativer Warnhinweise{#configuring-administrative-alerts}

{{eol}}

Administrative Warnungen senden E-Mail-Benachrichtigungen an die angegebenen E-Mail-Adressen, wenn vom Insight Server während des normalen Betriebs Fehler erkannt werden.

**Empfohlene Häufigkeit:** Vor der Produktion

>[!NOTE]
>
>Die Verwendung von administrativen Warnhinweisen erfordert, dass [!DNL Insight Server] hat Zugriff auf einen Weiterleitungs-SMTP-Server, um Warnhinweise per E-Mail zu senden.

Empfänger der E-Mail-Benachrichtigungen sollten die wichtigsten Verwaltungsmitarbeiter und die wichtigsten Interessengruppen sein.

Datei &quot;Administrative Warnungen&quot;, [!DNL Administrative Alerts.cfg], wird verwendet, um die administrativen Warnhinweise für [!DNL Insight Server].

>[!NOTE]
>
>Wenn Sie einen Cluster ausführen, müssen Sie Warnhinweise auf dem Übergeordneten [!DNL Insight Server] im Cluster.

**So erstellen oder ändern Sie einen Admin-Warnhinweis**

1. In [!DNL Insight]auf [!DNL Admin] > [!DNL Dataset and Profile] klicken Sie auf die **[!UICONTROL Servers Manager]** Miniaturansicht, um den Arbeitsbereich &quot;Server Manager&quot;zu öffnen.
1. Klicken Sie mit der rechten Maustaste auf das Symbol der [!DNL Insight Server] Sie möchten konfigurieren und klicken Sie auf **[!UICONTROL Server Files]**.
1. Im [!DNL Server Files Manager]klicken **[!UICONTROL Components]** , um den Inhalt anzuzeigen. Die [!DNL Administrative Alerts.cfg] -Datei befindet sich in diesem Verzeichnis.
1. Klicken Sie mit der rechten Maustaste auf das Häkchen in der Spalte *Servername *für [!DNL Administrative Alerts.cfg] und klicken Sie auf **[!UICONTROL Make Local]**. Ein Häkchen wird im [!DNL Temp] Spalte für [!DNL Administrative Alerts.cfg].
1. Klicken Sie mit der rechten Maustaste auf das neu erstellte Häkchen im [!DNL Temp] Spalte und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. Im [!DNL Administrative Alerts.cfg] Fenster, klicken Sie auf **[!UICONTROL component]** , um den Inhalt anzuzeigen.
1. Füllen Sie die Parameter nach Bedarf aus. Eine Liste der in dieser Datei verfügbaren Parameter finden Sie unter [Konfigurationseinstellungen für administrative Warnhinweise](../../../home/c-inst-svr/c-cfg-stgs-ref/c-admin-alts-cfg-stgs.md#concept-14c3c3ed797f47c5900ec04cae2fc491).

   ![Schritt-Info](assets/cfg_adminalerts_examplevalues.png)

1. Speichern Sie Ihre Änderungen auf dem Server, indem Sie Folgendes ausführen:

   1. Rechtsklick **[!UICONTROL (modified)]** Klicken Sie oben im Fenster auf **[!UICONTROL Save]**.

   1. Im [!DNL Server Files Manager]klicken Sie mit der rechten Maustaste auf das Häkchen für die Datei im [!DNL Temp] und wählen Sie **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

1. (Optional) Wenn Sie in einem Cluster arbeiten und möchten, dass dieselben Administratorwarnungen auf jede Datenverarbeitungseinheit angewendet werden, müssen Sie die aktualisierte Datei kopieren und einfügen [!DNL Administrative Alerts.cfg] in die [!DNL Components for Processing Servers] Ordner innerhalb des Übergeordneten [!DNL Insight Server] Installationsverzeichnis.
