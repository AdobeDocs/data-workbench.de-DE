---
description: Der letzte Schritt besteht darin, das Dashboard zum ersten Mal auszuführen, damit es initialisiert werden kann.
title: Initialisieren des Dashboards
uuid: 847ba63e-29d8-4950-aa74-22d825388e2b
exl-id: 47098d73-d8c4-4d14-964f-108a731d3733
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 4%

---

# Initialisieren des Dashboards{#initializing-the-dashboard}

Der letzte Schritt besteht darin, das Dashboard zum ersten Mal auszuführen, damit es initialisiert werden kann.

1. Öffnen Sie einen Webbrowser und geben Sie die URL der neu bereitgestellten Site ein (z. B. http://localhost/dashboard).
1. Beim erstmaligen Verbinden werden die Datenbanktabellen eingerichtet, sodass Sie eine leichte Verzögerung erleben können.
1. Die Anmeldeinformationen für die Erstanmeldung lauten:

   * **[!UICONTROL Username]**: admin
   * **[!UICONTROL Password]**: password

1. Gehen Sie bei Ihrer ersten Anmeldung zu **[!UICONTROL User]** > **[!UICONTROL Account Settings]** und wählen Sie **[!UICONTROL Change Password]**, um Ihr Administratorkennwort zu ändern.

Die Installation des Dashboards ist jetzt abgeschlossen. Falls noch nicht geschehen, verwenden Sie die Anweisungen im Abschnitt &quot;Data Workbench vorbereiten&quot;dieses Handbuchs, um die Kommunikation mit den Data Workbench-Servern zu konfigurieren und Benutzer und Gruppen zu verwalten.

>[!NOTE]
>
>Dashboard- und Prüfprotokolle befinden sich im Ordner [!DNL logs] innerhalb des Installationspfads.

>[!NOTE]
>
>Wenn Sie die Anwendungspool-Identität in ein anderes Konto ändern müssen, stellen Sie sicher, dass Sie Zugriff auf die Datenbank gewähren und der Identität Lese-/Schreibzugriff auf den Ordner [!DNL logs] im Installationspfad geben.

>[!NOTE]
>
>Wenn Sie die Verbindungszeichenfolge für die Datenbank ändern müssen, bearbeiten Sie den Wert einfach mit dem **[!UICONTROL IIS Management Console]**.
