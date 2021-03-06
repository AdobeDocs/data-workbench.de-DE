---
description: Administrative Warnungen senden E-Mail-Benachrichtigungen an die angegebenen E-Mail-Adressen, wenn vom Insight Server während des normalen Betriebs Fehler erkannt werden.
title: Konfigurieren administrativer Warnhinweise
uuid: 398e088b-ff83-46ae-a20c-ba0b50d85702
exl-id: 886e390f-fb2c-4922-8b01-9e5133a94e1b
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '300'
ht-degree: 2%

---

# Konfigurieren administrativer Warnhinweise{#configuring-administrative-alerts}

Administrative Warnungen senden E-Mail-Benachrichtigungen an die angegebenen E-Mail-Adressen, wenn vom Insight Server während des normalen Betriebs Fehler erkannt werden.

**Empfohlene Häufigkeit:** Vor der Produktion

>[!NOTE]
>
>Für die Verwendung administrativer Warnhinweise muss [!DNL Insight Server] Zugriff auf einen Weiterleitungs-SMTP-Server haben, um Warnhinweise per E-Mail zu senden.

Empfänger der E-Mail-Benachrichtigungen sollten die wichtigsten Verwaltungsmitarbeiter und die wichtigsten Interessengruppen sein.

Die Datei &quot;Administrative Warnhinweise&quot;[!DNL Administrative Alerts.cfg] wird verwendet, um die administrativen Warnhinweise für [!DNL Insight Server] zu konfigurieren.

>[!NOTE]
>
>Wenn Sie einen Cluster ausführen, müssen Sie Warnhinweise für das Übergeordnete [!DNL Insight Server] im Cluster erstellen oder ändern.

**So erstellen oder ändern Sie einen Admin-Warnhinweis**

1. Klicken Sie in [!DNL Insight] auf der Registerkarte [!DNL Admin] > [!DNL Dataset and Profile] auf die Miniaturansicht **[!UICONTROL Servers Manager]** , um den Arbeitsbereich &quot;Server Manager&quot;zu öffnen.
1. Klicken Sie mit der rechten Maustaste auf das Symbol des zu konfigurierenden [!DNL Insight Server] und klicken Sie auf **[!UICONTROL Server Files]**.
1. Klicken Sie in [!DNL Server Files Manager] auf **[!UICONTROL Components]** , um den Inhalt anzuzeigen. Die Datei [!DNL Administrative Alerts.cfg] befindet sich in diesem Verzeichnis.
1. Klicken Sie mit der rechten Maustaste auf das Häkchen in der Spalte *Servername *für [!DNL Administrative Alerts.cfg] und klicken Sie auf **[!UICONTROL Make Local]**. In der Spalte [!DNL Temp] für [!DNL Administrative Alerts.cfg] wird ein Häkchen angezeigt.
1. Klicken Sie mit der rechten Maustaste auf das neu erstellte Häkchen in der Spalte [!DNL Temp] und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. Klicken Sie im Fenster [!DNL Administrative Alerts.cfg] auf **[!UICONTROL component]** , um den Inhalt anzuzeigen.
1. Füllen Sie die Parameter nach Bedarf aus. Eine Liste der in dieser Datei verfügbaren Parameter finden Sie unter [Konfigurationseinstellungen für administrative Warnhinweise](../../../home/c-inst-svr/c-cfg-stgs-ref/c-admin-alts-cfg-stgs.md#concept-14c3c3ed797f47c5900ec04cae2fc491).

   ![Schritt-Info](assets/cfg_adminalerts_examplevalues.png)

1. Speichern Sie Ihre Änderungen auf dem Server, indem Sie Folgendes ausführen:

   1. Klicken Sie oben im Fenster mit der rechten Maustaste auf **[!UICONTROL (modified)]** und klicken Sie auf **[!UICONTROL Save]**.

   1. Klicken Sie in der Spalte [!DNL Server Files Manager] mit der rechten Maustaste auf das Häkchen für die Datei in der Spalte [!DNL Temp] und wählen Sie **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]***.

1. (Optional) Wenn Sie in einem Cluster arbeiten und möchten, dass für jede Datenverarbeitungseinheit dieselben Administratorwarnungen angewendet werden, müssen Sie die aktualisierte [!DNL Administrative Alerts.cfg]-Datei kopieren und in den Ordner [!DNL Components for Processing Servers] im Übergeordneten Installationsordner [!DNL Insight Server] einfügen.
