---
description: Schritte zum Bereitstellen des Dashboards in IIS.
solution: Analytics
title: Bereitstellen des Dashboards
topic: Data workbench
uuid: e9a5d62e-9d59-448a-9728-8087aec0fdec
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Bereitstellen des Dashboards{#deploying-the-dashboard}

Schritte zum Bereitstellen des Dashboards in IIS.

1. Erstellen Sie einen Installationsordner, um das Dashboard zu installieren, z. B. [!DNL c:\inetpub\wwwroot\dashboard].
1. Erstellen Sie den Anwendungspool des Dashboards in IIS.
1. Öffnen Sie die IIS Manager-Konsole.
1. Go to **[!UICONTROL Application Pools]**.
1. Wählen Sie **[!UICONTROL Add Application Pool…]**im **[!UICONTROL Actions]** Menü rechts.
1. Verwenden Sie im **[!UICONTROL Add Application Pool]** Formular das Dashboard als Namen und wählen Sie .NET Framework v.4.0.xxxx als .NET Framework-Version.
1. Belassen Sie andere Felder standardmäßig und klicken Sie auf **[!UICONTROL OK]** , um den Anwendungspool zu erstellen.
1. Stellen Sie die Dashboard-Anwendung bereit.
1. Öffnen Sie die IIS Manager-Konsole.
1. Erweitern Sie den Ordner **[!UICONTROL Default Web Site]**, sollten Sie den Ordner sehen, den Sie unter c:\inetpub\wwwroot\dashboard by default erstellt haben.
1. Klicken Sie mit der rechten Maustaste auf den Ordner und wählen Sie **[!UICONTROL Convert to Application]**.
1. Wählen Sie das in Schritt 2 erstellte **[!UICONTROL Application Pool]**Dashboard aus (z. B. &quot;Dashboard&quot;).
1. Klicken Sie unter **[!UICONTROL Sites]** dem Link mit der rechten Maustaste auf die Website, für die Sie die Bereitstellung durchführen möchten (z. B. &quot;Standardwebsite&quot;).
1. Auswählen **[!UICONTROL Deploy]** > **[!UICONTROL Import Application]**.
1. Navigieren Sie zur von Adobe bereitgestellten Dashboard-Bereitstellungsdatei und wählen Sie sie aus.
1. Klicken Sie **[!UICONTROL Next]** zweimal, um zum Bildschirm &quot;Anwendungsinformationen eingeben&quot;zu wechseln.
1. In diesem Bildschirm können Sie Ihre Dashboard-Bereitstellung anpassen.
1. Geben Sie **[!UICONTROL Application Path]** beispielsweise den zuvor ausgewählten Ordnernamen ein.
1. Geben Sie **[!UICONTROL Disable Automatic Database Upgrade]** unter `False`, da es sich um eine Neuinstallation handelt.
1. Passen Sie bei Bedarf Ihre Verbindungszeichenfolge an. Beispiel:

   ```
   Data Source=.;Initial Catalog=thinclientdb;Integrated Security=SSPI;Connect Timeout=30; 
   Application Name=Insight Dashboard;MultipleActiveResultSets=true;
   ```

1. Klicken Sie auf **[!UICONTROL Next]** und IIS startet die Installation der Anwendung.
1. Nach Abschluss der Installation sollten Sie keine Fehler im Installationsprotokoll sehen.
