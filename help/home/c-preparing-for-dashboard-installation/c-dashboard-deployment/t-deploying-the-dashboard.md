---
description: Schritte zum Bereitstellen des Dashboards in IIS.
title: Implementieren des Dashboards
uuid: e9a5d62e-9d59-448a-9728-8087aec0fdec
exl-id: d59efcc3-7405-407d-840a-b5202f418d51
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 5%

---

# Implementieren des Dashboards{#deploying-the-dashboard}

Schritte zum Bereitstellen des Dashboards in IIS.

1. Erstellen Sie einen Installationsordner zum Installieren des Dashboards, z. B. [!DNL c:\inetpub\wwwroot\dashboard].
1. Erstellen Sie den Anwendungspool des Dashboards in IIS.
1. Öffnen Sie die IIS Manager-Konsole.
1. Öffnen von **[!UICONTROL Application Pools]**.
1. Wählen Sie **[!UICONTROL Add Application Pool…]**im Menü **[!UICONTROL Actions]** rechts aus.
1. Verwenden Sie im Formular **[!UICONTROL Add Application Pool]** das Dashboard für den Namen und wählen Sie .NET Framework v.4.0.xxxx als .NET Framework-Version aus.
1. Belassen Sie andere Felder standardmäßig und klicken Sie auf **[!UICONTROL OK]**, um den Anwendungspool zu erstellen.
1. Stellen Sie die Dashboard-Anwendung bereit.
1. Öffnen Sie die IIS Manager-Konsole.
1. Erweitern Sie den Ordner **[!UICONTROL Default Web Site]**, sollte der Ordner angezeigt werden, den Sie unter c:\inetpub\wwwroot\dashboard by default erstellt haben.
1. Klicken Sie mit der rechten Maustaste auf den Ordner und wählen Sie **[!UICONTROL Convert to Application]**.
1. Wählen Sie das in Schritt 2 erstellte **[!UICONTROL Application Pool]**aus (z. B. &quot;Dashboard&quot;).
1. Klicken Sie unter **[!UICONTROL Sites]** mit der rechten Maustaste auf die Website, für die Sie die Bereitstellung durchführen möchten (z. B. &quot;Standardwebsite&quot;).
1. Auswählen **[!UICONTROL Deploy]** > **[!UICONTROL Import Application]**.
1. Navigieren Sie zu der von der Adobe bereitgestellten Dashboard-Bereitstellungsdatei und wählen Sie sie aus.
1. Klicken Sie zweimal auf **[!UICONTROL Next]**, um mit dem Bildschirm &quot;Anwendungsinformationen eingeben&quot;fortzufahren.
1. In diesem Bildschirm können Sie die Bereitstellung Ihres Dashboards anpassen.
1. Geben Sie für **[!UICONTROL Application Path]** den zuvor ausgewählten Ordnernamen ein.
1. Geben Sie unter **[!UICONTROL Disable Automatic Database Upgrade]** `False` ein, da es sich um eine neue Installation handelt.
1. Passen Sie bei Bedarf Ihre Verbindungszeichenfolge an. Beispiel:

   ```
   Data Source=.;Initial Catalog=thinclientdb;Integrated Security=SSPI;Connect Timeout=30; 
   Application Name=Insight Dashboard;MultipleActiveResultSets=true;
   ```

1. Klicken Sie auf **[!UICONTROL Next]** und IIS beginnt mit der Installation der Anwendung.
1. Nach Abschluss der Installation sollten Sie keine Fehler im Installationsprotokoll sehen.
