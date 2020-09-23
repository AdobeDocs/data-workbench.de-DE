---
description: Die Clients von Insight Server (Report und Insight) verwenden allgemeine Namen, um auf Insight-Server zu verweisen.
solution: Analytics
title: Definieren des Netzwerkstandorts des Servers
uuid: 9cf2f268-6fde-4427-b832-a238d126d697
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 4%

---


# Definieren des Netzwerkstandorts des Servers{#defining-the-server-s-network-location}

Die Clients von Insight Server (Report und Insight) verwenden allgemeine Namen, um auf Insight-Server zu verweisen.

Wenn Sie z. B. eine Verbindung herstellen [!DNL Insight] oder [!DNL Report] eine Verbindung zu einem Server herstellen, [!DNL Insight Server]identifizieren Sie den Server anhand seines allgemeinen Namens (z. B. [!DNL Server.MyCompany.com]). Intern löst der Client den allgemeinen Namen in eine numerische IP-Adresse auf, bevor eine Anforderung an den Server gesendet wird.

Um häufige Namen an IP-Adressen aufzulösen, verwenden [!DNL Insight Server’s] Clients eine lokale Abfragedatei, die so genannte Adressdatei. In der Adressdatei werden die allgemeinen Namen der in Ihrem Unternehmen [!DNL Insight Servers] installierten IP-Adressen Liste und deren numerische IP-Adressen angegeben. Ein Client erhält automatisch eine Kopie der Adressdatei, wenn er ein Profil auf der [!DNL Insight Server]öffnet.

Wenn ein Client eine Anforderung an einen Server ausgibt, [!DNL Insight Server]versucht er, den allgemeinen Namen des Servers über die Adressdatei aufzulösen. Wenn die Adressdatei eine IP-Adresse für den angeforderten Server identifiziert, leitet der Client die Anforderung an die angegebene Adresse weiter. Wenn die Adresse nicht definiert ist (z. B. definiert die Adressdatei nicht den gemeinsamen Namen des Servers), schlägt die Anforderung fehl. Optional können Sie Clients so konfigurieren, dass Adressen über den normalen DNS-Mechanismus (Domain Naming Service) der Umgebung aufgelöst werden, wenn in der Adressdatei des Clients kein Name definiert ist. Anweisungen hierzu finden Sie im folgenden Abschnitt im Parameter &quot;Übergeordnet&quot;in der Tabelle &quot; [NetworkLocation-Parameter&quot;](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-ntwk-loc.md#concept-18587827cbd24805801caa86bc816e05) .
