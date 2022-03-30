---
description: Mit dem Parameter ExpCookieURL können Sie testen, ob Ihr gesteuertes Experiment ordnungsgemäß funktioniert.
solution: Analytics
title: Bearbeiten des ExpCookieURL-Parameters (optional)
uuid: 0c160c26-f9de-4e41-a05d-bf7bb32395bb
exl-id: fe3dadab-890d-4426-b6f5-8ffd1cd38c69
source-git-commit: 31f775478b0f0d968310ed10a43ad46791319ee9
workflow-type: tm+mt
source-wordcount: '146'
ht-degree: 6%

---

# Bearbeiten des ExpCookieURL-Parameters (optional){#modifying-the-expcookieurl-paramter-optional}

Mit dem Parameter ExpCookieURL können Sie testen, ob Ihr gesteuertes Experiment ordnungsgemäß funktioniert.

Dieser Parameter definiert die URL einer virtuellen Seite, die Sie auf Anforderung in ein bestimmtes Experiment und eine bestimmte Gruppe versetzt und Sie dann zum Stamm Ihrer Website weiterleitet. Von diesem Punkt bis zum Ende des Experiments sind Sie Teil des angegebenen Experiments und der angegebenen Gruppe.

Die Standardseite für diesen Parameter ist [!DNL setcookie.htm], Sie können jedoch jede gültige virtuelle URL verwenden.

>[!NOTE]
>
>Hierbei muss es sich um eine virtuelle URL handeln, die keine echte Seite oder keinen vorhandenen Inhalt sein darf. Auf dem Webserver sollte sich keine Datei im angegebenen Pfad mit dem angegebenen Namen befinden.

Im Folgenden finden Sie ein Beispiel für den Parameter ExpCookieURL :

[!DNL ExpCookieURL /setcookie.htm]
