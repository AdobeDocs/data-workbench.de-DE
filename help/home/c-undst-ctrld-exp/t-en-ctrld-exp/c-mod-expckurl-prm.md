---
description: Mit dem Parameter ExpCookieURL können Sie testen, ob Ihr kontrolliertes Experiment ordnungsgemäß funktioniert.
solution: Insight,Analytics
title: Ändern des ExpCookieURL-Parameters (optional)
topic: Data workbench
uuid: 0c160c26-f9de-4e41-a05d-bf7bb32395bb
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Ändern des ExpCookieURL-Parameters (optional){#modifying-the-expcookieurl-paramter-optional}

Mit dem Parameter ExpCookieURL können Sie testen, ob Ihr kontrolliertes Experiment ordnungsgemäß funktioniert.

Dieser Parameter definiert die URL einer virtuellen Seite, die Sie auf Anforderung in ein bestimmtes Experiment und eine bestimmte Gruppe setzt und Sie dann an den Stammordner Ihrer Website weiterleitet. Von diesem Punkt bis zum Ende des Experiments sind Sie Teil des angegebenen Experiments und der angegebenen Gruppe.

Die Standardseite für diesen Parameter ist [!DNL setcookie.htm]festgelegt, Sie können jedoch eine beliebige gültige virtuelle URL verwenden.

>[!NOTE]
>
>Hierbei muss es sich um eine virtuelle URL handeln und darf es sich nicht um eine echte Seite oder einen Teil des vorhandenen Inhalts handeln. Es sollte auf dem Webserver am angegebenen Pfad mit dem angegebenen Namen keine Datei vorhanden sein.

Im Folgenden finden Sie ein Beispiel für den Parameter ExpCookieURL:

[!DNL ExpCookieURL /setcookie.htm]
