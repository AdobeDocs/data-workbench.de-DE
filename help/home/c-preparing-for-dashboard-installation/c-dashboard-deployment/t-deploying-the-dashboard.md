---
description: Schritte zum Bereitstellen des Dashboards in IIS.
title: Implementieren des Dashboards
uuid: e9a5d62e-9d59-448a-9728-8087aec0fdec
exl-id: d59efcc3-7405-407d-840a-b5202f418d51
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 5%

---

# Implementieren des Dashboards{#deploying-the-dashboard}

Schritte zum Bereitstellen des Dashboards in IIS.

1. Erstellen Sie einen Installationsordner, um das Dashboard zu installieren, z. B. [!DNL c:\inetpub\wwwroot\dashboard].
1. Erstellen Sie den Anwendungspool des Dashboards in IIS.
1. Öffnen Sie die IIS Manager-Konsole.
1. Öffnen von **[!UICONTROL Application Pools]**.
1. Wählen Sie **[!UICONTROL Add Application Pool…]**im Menü **[!UICONTROL Actions]** rechts aus.
1. Verwenden Sie im Formular **[!UICONTROL Add Application Pool]** das Dashboard für den Namen und wählen Sie .NET Framework v.4.0.xxxxxx als .NET Framework-Version aus.
1. Belassen Sie andere Felder als Standard und klicken Sie auf **[!UICONTROL OK]** , um den Anwendungspool zu erstellen.
1. Stellen Sie die Dashboard-Anwendung bereit.
1. Öffnen Sie die IIS Manager-Konsole.
1. Erweitern Sie **[!UICONTROL Default Web Site]**, Sie sollten den Ordner sehen, den Sie in c:\inetpub\wwwroot\dashboard by default erstellt haben.
1. Klicken Sie mit der rechten Maustaste auf den Ordner und wählen Sie **[!UICONTROL Convert to Application]** aus.
1. Wählen Sie die **[!UICONTROL Application Pool]**, die in Schritt 2 erstellt wurden (z. B. &quot;Dashboard&quot;).
1. Klicken Sie unter **[!UICONTROL Sites]** mit der rechten Maustaste auf die Website, die Sie bereitstellen möchten (z. B. &quot;Standardwebsite&quot;).
1. Auswählen **[!UICONTROL Deploy]** > **[!UICONTROL Import Application]**.
1. Suchen Sie die von Adobe bereitgestellte Dashboard-Bereitstellungsdatei und wählen Sie sie aus.
1. Klicken Sie zweimal auf **[!UICONTROL Next]** , um mit dem Bildschirm &quot;Enter Application Information&quot;(Anwendungs-Informationen eingeben) fortzufahren.
1. Auf diesem Bildschirm können Sie Ihre Dashboard-Implementierung anpassen.
1. Geben Sie für **[!UICONTROL Application Path]** den zuvor ausgewählten Ordnernamen ein.
1. Geben Sie unter **[!UICONTROL Disable Automatic Database Upgrade]** `False` ein, da es sich um eine neue Installation handelt.
1. Passen Sie bei Bedarf Ihre Verbindungszeichenfolge an. Beispiel:

   ```
   Data Source=.;Initial Catalog=thinclientdb;Integrated Security=SSPI;Connect Timeout=30; 
   Application Name=Insight Dashboard;MultipleActiveResultSets=true;
   ```

1. Klicken Sie auf **[!UICONTROL Next]** und IIS beginnt mit der Installation der Anwendung.
1. Nach Abschluss der Installation sollten keine Fehler im Installationsprotokoll angezeigt werden.
