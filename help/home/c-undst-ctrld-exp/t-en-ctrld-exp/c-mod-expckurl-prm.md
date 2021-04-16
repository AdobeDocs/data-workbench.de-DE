---
description: Mit dem Parameter ExpCookieURL können Sie testen, ob Ihr kontrolliertes Experiment ordnungsgemäß funktioniert.
solution: Analytics,Analytics
title: Bearbeiten des ExpCookieURL-Parameters (optional)
uuid: 0c160c26-f9de-4e41-a05d-bf7bb32395bb
exl-id: fe3dadab-890d-4426-b6f5-8ffd1cd38c69
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '146'
ht-degree: 6%

---

# Bearbeiten des ExpCookieURL-Parameters (optional){#modifying-the-expcookieurl-paramter-optional}

Mit dem Parameter ExpCookieURL können Sie testen, ob Ihr kontrolliertes Experiment ordnungsgemäß funktioniert.

Dieser Parameter definiert die URL einer virtuellen Seite, die Sie auf Anforderung in ein bestimmtes Experiment und eine bestimmte Gruppe setzt und Sie dann an den Stammordner Ihrer Website weiterleitet. Von diesem Punkt bis zum Ende des Experiments sind Sie Teil des angegebenen Experiments und der angegebenen Gruppe.

Die Standardseite für diesen Parameter ist [!DNL setcookie.htm], Sie können jedoch eine beliebige gültige virtuelle URL verwenden.

>[!NOTE]
>
>Hierbei muss es sich um eine virtuelle URL handeln und darf es sich nicht um eine echte Seite oder einen Teil des vorhandenen Inhalts handeln. Es sollte auf dem Webserver am angegebenen Pfad mit dem angegebenen Namen keine Datei vorhanden sein.

Im Folgenden finden Sie ein Beispiel für den Parameter ExpCookieURL:

[!DNL ExpCookieURL /setcookie.htm]
