---
description: Die Clients von Insight Server (Report and Insight) verwenden allgemeine Namen, um auf Insight Server zu verweisen.
title: Definieren des Netzwerkstandorts des Servers
uuid: 9cf2f268-6fde-4427-b832-a238d126d697
exl-id: def360b8-f146-45ca-ae61-fd213adef68b
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 4%

---

# Definieren des Netzwerkstandorts des Servers{#defining-the-server-s-network-location}

{{eol}}

Die Clients von Insight Server (Report and Insight) verwenden allgemeine Namen, um auf Insight Server zu verweisen.

Wenn Sie beispielsweise eine Verbindung herstellen [!DNL Insight] oder [!DNL Report] zu [!DNL Insight Server], identifizieren Sie den Server anhand seines allgemeinen Namens (z. B. [!DNL Server.MyCompany.com]). Intern löst der Client den allgemeinen Namen in eine numerische IP-Adresse auf, bevor eine Anfrage an den Server gesendet wird.

So lösen Sie allgemeine Namen für IP-Adressen auf: [!DNL Insight Server’s] -Clients verwenden eine lokale Lookup-Datei, die als Adressdatei bezeichnet wird. In der Adressdatei werden die allgemeinen Namen der [!DNL Insight Servers] in Ihrem Unternehmen installiert sind und deren numerische IP-Adressen identifizieren. Ein Client erhält automatisch eine Kopie der Adressdatei, wenn er ein Profil auf der [!DNL Insight Server].

Wenn ein Client eine Anforderung an eine [!DNL Insight Server], versucht es, den allgemeinen Namen des Servers über die Adressdatei aufzulösen. Wenn die Adressdatei eine IP-Adresse für den angeforderten Server angibt, leitet der Client die Anfrage an die angegebene Adresse weiter. Wenn die Adresse nicht definiert ist (z. B. definiert die Adressdatei nicht den allgemeinen Namen des Servers), schlägt die Anfrage fehl. Optional können Sie Clients so konfigurieren, dass Adressen über den normalen DNS-Mechanismus (Domain Naming Service) der Betriebsumgebung aufgelöst werden, wenn in der Adressdatei des Kunden kein Name definiert ist. Anweisungen finden Sie im Parameter Übergeordnetes Element im [Tabelle &quot;NetworkLocation Parameters&quot;](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-ntwk-loc.md#concept-18587827cbd24805801caa86bc816e05) im folgenden Abschnitt.
