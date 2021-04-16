---
description: Wenn Clients einen Insight-Server über mehrere Netzwerke erreichen können (z. B. über das firmeninterne Intranet und das Internet), muss die Adressdatei einen separaten Netzwerkspeicherort für jede IP-Adresse des Servers definieren.
title: Mehrere IP-Adressen für einen Insight Server
uuid: 6ed00b47-8ba3-4127-a5db-7e684e573d9c
exl-id: 71654a60-af82-45f2-826b-29ecc7127b0b
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 7%

---

# Mehrere IP-Adressen für einen Insight Server{#multiple-ip-addresses-for-an-insight-server}

Wenn Clients einen Insight-Server über mehrere Netzwerke erreichen können (z. B. über das firmeninterne Intranet und das Internet), muss die Adressdatei einen separaten Netzwerkspeicherort für jede IP-Adresse des Servers definieren.

Beispiel: Wenn der Server [!DNL VS01.myCompany.com] in einem internen Netzwerk eine IP-Adresse von 10.2.1.70 und im Internet eine IP-Adresse von 65.196.125.167 hat, enthält die Adressdatei einen Netzwerkspeicherort für jede der Adressen, wie im folgenden Beispiel gezeigt:

```
0 = NetworkLocation: 
  Addresses = vector: 1 items
    0 = AddressDefinition: 
      Address = string: 10.2.1.70
      Name = string: VS01.myCompany.com
  Name = string: MyCorporateIntranet
  Parent = string: 
1 = NetworkLocation: 
  Addresses = vector: 1 items
    0 = AddressDefinition: 
      Address = string: 65.196.125.167
      Name = string: VS01.myCompany.com
  Name = string: Internet
  Parent = string:
```

Wenn Benutzer eine Verbindung zu einem [!DNL Insight Server] herstellen, verwenden sie den NetworkLocation-Parameter (in der Client-Benutzeroberfläche), um den Netzwerkspeicherort anzugeben, über den der gemeinsame Name des Servers aufgelöst werden soll. Bei einer Adressdatei mit den beiden oben aufgeführten NetworkLocations würde ein Benutzer den NetworkLocation-Parameter auf &quot;MyCorporate Intranet&quot;setzen, um über das interne Netzwerk eine Verbindung zu [!DNL Insight Server] herzustellen, und auf &quot;Internet&quot;, um über das Internet eine Verbindung zum Server herzustellen.
