---
description: Der letzte Schritt besteht darin, das Dashboard zum ersten Mal auszuführen, damit es initialisiert werden kann.
solution: Analytics
title: Dashboard initialisieren
topic: Data workbench
uuid: 847ba63e-29d8-4950-aa74-22d825388e2b
translation-type: tm+mt
source-git-commit: 4b39a42285c39e26f097b91309c269c05a9475bd
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 1%

---


# Dashboard initialisieren{#initializing-the-dashboard}

Der letzte Schritt besteht darin, das Dashboard zum ersten Mal auszuführen, damit es initialisiert werden kann.

1. Öffnen Sie einen Webbrowser und geben Sie die URL der neu bereitgestellten Site ein (z. B. http://localhost/dashboard).
1. Beim erstmaligen Verbinden werden die Datenbanktabellen eingerichtet, sodass Sie eine leichte Verzögerung erleben können.
1. Die Anmeldeinformationen für die Erstanmeldung lauten:

   * **[!UICONTROL Username]**: admin
   * **[!UICONTROL Password]**: password

1. Gehen Sie bei Ihrer ersten Anmeldung zu **[!UICONTROL User]** > **[!UICONTROL Account Settings]** und wählen Sie **[!UICONTROL Change Password]** das Administratorkennwort aus.

Die Installation des Dashboards ist jetzt abgeschlossen. Wenn Sie dies noch nicht getan haben, verwenden Sie die Anweisungen, die im Abschnitt &quot;Vorbereiten von Data Workbench&quot;dieses Handbuchs beschrieben sind, um Ihre Kommunikation mit Data Workbench-Servern zu konfigurieren und Benutzer und Gruppen zu verwalten.

>[!NOTE]
>
>Dashboard- und Prüfprotokolle befinden sich im Ordner [!DNL logs] , der sich im Installationspfad befindet.

>[!NOTE]
>
>Wenn Sie die Anwendungspool-Identität in ein anderes Konto ändern müssen, stellen Sie sicher, dass Sie Zugriff auf die Datenbank gewähren und der Identität Lese-/Schreibzugriff auf den [!DNL logs] Ordner im Installationspfad gewähren.

>[!NOTE]
>
>Wenn Sie die Verbindungszeichenfolge für die Datenbank ändern müssen, bearbeiten Sie einfach den Wert mit der **[!UICONTROL IIS Management Console]**.
