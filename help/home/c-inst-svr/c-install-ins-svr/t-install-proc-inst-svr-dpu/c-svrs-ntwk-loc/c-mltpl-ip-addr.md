---
description: Wenn Clients einen Insight-Server über mehrere Netzwerke erreichen können (z. B. über das firmeninterne Intranet und das Internet), muss die Adressdatei einen separaten Netzwerkspeicherort für jede IP-Adresse des Servers definieren.
solution: Insight
title: Mehrere IP-Adressen für einen Insight-Server
uuid: 6ed00b47-8ba3-4127-a5db-7e684e573d9c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Mehrere IP-Adressen für einen Insight-Server{#multiple-ip-addresses-for-an-insight-server}

Wenn Clients einen Insight-Server über mehrere Netzwerke erreichen können (z. B. über das firmeninterne Intranet und das Internet), muss die Adressdatei einen separaten Netzwerkspeicherort für jede IP-Adresse des Servers definieren.

Beispiel: Wenn der Server in einem internen Netzwerk eine IP-Adresse von 10.2.1.70 und im Internet eine IP-Adresse von 65.196.125.167 hat, enthält die Adressdatei einen Netzwerkspeicherort für jede der Adressen, wie im folgenden Beispiel gezeigt: [!DNL VS01.myCompany.com]

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

Wenn Benutzer eine Verbindung zu einer [!DNL Insight Server]herstellen, verwenden sie den NetworkLocation-Parameter (in der Client-Benutzeroberfläche), um den Netzwerkspeicherort anzugeben, über den der gemeinsame Name des Servers aufgelöst werden soll. Bei einer Adressdatei mit den beiden oben aufgeführten NetworkLocations würde ein Benutzer den NetworkLocation-Parameter auf &quot;MyCorporate Intranet&quot;setzen, um eine Verbindung [!DNL Insight Server] über das interne Netzwerk herzustellen, und auf &quot;Internet&quot;, um über das Internet eine Verbindung zum Server herzustellen.
