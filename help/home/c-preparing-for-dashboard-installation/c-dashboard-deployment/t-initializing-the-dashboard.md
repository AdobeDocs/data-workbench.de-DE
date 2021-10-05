---
description: Der letzte Schritt besteht darin, das Dashboard zum ersten Mal auszuführen, damit es initialisiert werden kann.
title: Initialisieren des Dashboards
uuid: 847ba63e-29d8-4950-aa74-22d825388e2b
exl-id: 47098d73-d8c4-4d14-964f-108a731d3733
source-git-commit: 79981e92dd1c2e552f958716626a632ead940973
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 4%

---

# Initialisieren des Dashboards{#initializing-the-dashboard}

Der letzte Schritt besteht darin, das Dashboard zum ersten Mal auszuführen, damit es initialisiert werden kann.

1. Öffnen Sie einen Webbrowser und geben Sie die URL zur neu bereitgestellten Site ein (z. B. https://localhost/dashboard).
1. Beim erstmaligen Verbinden werden die Datenbanktabellen eingerichtet, sodass Sie eine geringfügige Verzögerung feststellen können.
1. Die ersten Anmeldedaten lauten:

   * **[!UICONTROL Username]**: admin
   * **[!UICONTROL Password]**: password

1. Gehen Sie bei Ihrer ersten Anmeldung zu **[!UICONTROL User]** > **[!UICONTROL Account Settings]** und wählen Sie **[!UICONTROL Change Password]** aus, um Ihr Administratorkennwort zu ändern.

Die Dashboard-Installation ist jetzt abgeschlossen. Verwenden Sie, falls noch nicht geschehen, die im Abschnitt &quot;Data Workbench vorbereiten&quot;dieses Handbuchs beschriebenen Anweisungen, um Ihre Kommunikation mit Data Workbench-Servern zu konfigurieren und Benutzer und Gruppen zu verwalten.

>[!NOTE]
>
>Dashboard-Fehler und Prüfprotokolle befinden sich im Ordner [!DNL logs] im Installationspfad.

>[!NOTE]
>
>Wenn Sie die App-Pool-Identität in ein anderes Konto ändern müssen, gewähren Sie Zugriff auf die Datenbank und gewähren Sie der Identität Lese-/Schreibzugriff auf den Ordner [!DNL logs] im Installationspfad.

>[!NOTE]
>
>Wenn Sie die Verbindungszeichenfolge für die Datenbank ändern müssen, bearbeiten Sie einfach den Wert mit **[!UICONTROL IIS Management Console]**.
