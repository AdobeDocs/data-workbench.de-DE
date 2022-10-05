---
description: Schritte zum Bereitstellen des Dashboards in IIS.
title: Implementieren des Dashboards
uuid: e9a5d62e-9d59-448a-9728-8087aec0fdec
exl-id: d59efcc3-7405-407d-840a-b5202f418d51
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 5%

---

# Implementieren des Dashboards{#deploying-the-dashboard}

{{eol}}

Schritte zum Bereitstellen des Dashboards in IIS.

1. Erstellen Sie einen Installationsordner zur Installation des Dashboards, z. B. [!DNL c:\inetpub\wwwroot\dashboard].
1. Erstellen Sie den Anwendungspool des Dashboards in IIS.
1. Öffnen Sie die IIS Manager-Konsole.
1. Öffnen von **[!UICONTROL Application Pools]**.
1. Wählen Sie **[!UICONTROL Add Application Pool…]**im **[!UICONTROL Actions]** Menü rechts.
1. Im **[!UICONTROL Add Application Pool]** verwenden Sie das Dashboard für den Namen und wählen Sie .NET Framework v.4.0.xxxxxx als .NET Framework-Version aus.
1. Belassen Sie andere Felder als Standard und klicken Sie auf **[!UICONTROL OK]** , um den Anwendungspool zu erstellen.
1. Stellen Sie die Dashboard-Anwendung bereit.
1. Öffnen Sie die IIS Manager-Konsole.
1. Erweitern Sie die **[!UICONTROL Default Web Site]** sollte der Ordner angezeigt werden, den Sie in c:\inetpub\wwwroot\dashboard by default erstellt haben.
1. Klicken Sie mit der rechten Maustaste auf den Ordner und wählen Sie **[!UICONTROL Convert to Application]**.
1. Wählen Sie ** aus.[!UICONTROL Application Pool]**erstellt in Schritt 2 (z. B. &quot;Dashboard&quot;).
1. under **[!UICONTROL Sites]** klicken Sie mit der rechten Maustaste auf die Website, die Sie bereitstellen möchten (z. B. &quot;Standardwebsite&quot;).
1. Auswählen **[!UICONTROL Deploy]** > **[!UICONTROL Import Application]**.
1. Suchen Sie die von Adobe bereitgestellte Dashboard-Bereitstellungsdatei und wählen Sie sie aus.
1. Klicken **[!UICONTROL Next]** zweimal, um zum Bildschirm &quot;Enter Application Information&quot;zu gelangen.
1. Auf diesem Bildschirm können Sie Ihre Dashboard-Implementierung anpassen.
1. Für **[!UICONTROL Application Path]** Geben Sie den zuvor ausgewählten Ordnernamen ein.
1. under **[!UICONTROL Disable Automatic Database Upgrade]**, eingeben `False`, da es sich um eine Neuinstallation handelt.
1. Passen Sie bei Bedarf Ihre Verbindungszeichenfolge an. Beispiel:

   ```
   Data Source=.;Initial Catalog=thinclientdb;Integrated Security=SSPI;Connect Timeout=30; 
   Application Name=Insight Dashboard;MultipleActiveResultSets=true;
   ```

1. Klicken **[!UICONTROL Next]** und IIS beginnen mit der Installation der Anwendung.
1. Nach Abschluss der Installation sollten keine Fehler im Installationsprotokoll angezeigt werden.
