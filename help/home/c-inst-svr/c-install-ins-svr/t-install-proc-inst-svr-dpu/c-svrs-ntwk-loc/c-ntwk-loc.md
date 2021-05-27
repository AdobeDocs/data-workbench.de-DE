---
description: Die Adressdatei erfüllt grundsätzlich denselben Zweck wie die Datei ETC&bsol;HOSTS auf einem vernetzten Computer.
title: Netzwerkstandorte
uuid: a2097eca-dd75-4d43-b8a8-fb4c768df38d
exl-id: 938217da-8935-4f2a-b5f8-9afc1dd489f3
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '254'
ht-degree: 2%

---

# Netzwerkstandorte{#network-locations}

Die Adressdatei erfüllt grundsätzlich denselben Zweck wie die Datei ETC&amp;bsol;HOSTS auf einem vernetzten Computer.

Im Gegensatz zur HOSTS-Datei, die eine Sammlung von Namen beschreibt, enthält die Adressdatei jedoch mehrere Sammlungen von Namen, die als Netzwerkspeicherorte bezeichnet werden.

Ein Netzwerkspeicherort ist eine benannte Sammlung von Adressendefinitionen. Jede Adressendefinition in der Kollektion ordnet einen gemeinsamen Namen einer IP-Adresse zu.

In der Adressdatei wird ein Netzwerkspeicherort in einer Struktur definiert, die als NetworkLocation bezeichnet wird. Im folgenden Beispiel definiert NetworkLocation einen Netzwerkspeicherort namens &quot;MyCorporate Intranet&quot;. Es enthält eine Adressdefinition, die den allgemeinen Namen [!DNL VS01.myCompany.com] der IP-Adresse &quot;10.2.1.70&quot;zuordnet.

```
0 = NetworkLocation: 
  Addresses = vector: 1 items
    0 = AddressDefinition: 
      Address = string: 10.2.1.70
      Name = string: VS01.myCompany.com
  Name = string: MyCorporateIntranet
  Parent = string: 
```

Wie im obigen Beispiel gezeigt, besteht die Struktur von NetworkLocation aus drei Hauptparametern:

<table id="table_9142A0EFA15E4C37975E7ACE234F6FDD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Adressen </td> 
   <td colname="col2"> Definiert null oder mehr AddressDefinitions. Jede AddressDefintion ordnet einen gemeinsamen Namen einer IP-Adresse zu. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Name </td> 
   <td colname="col2"> Weist dem NetworkLocation einen Namen zu. Der einem NetworkLocation zugewiesene Name muss innerhalb der Adressdatei eindeutig sein. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Übergeordnet </td> 
   <td colname="col2"> <p>Gibt den Namen eines anderen NetworkLocation an, dessen Mitglieder in diesem NetworkLocation enthalten sind. Dieser Parameter ermöglicht es einem NetworkLocation, einen anderen zu erweitern. </p> <p>Sie können den übergeordneten Parameter auf "DNS"setzen, um eine NetworkLocation auf das normale DNS-System des Clients zu erweitern. </p> <p>Beispiel: Übergeordnetes Element = Zeichenfolge: DNS </p> <p>Wenn DNS das übergeordnete Element ist, versuchen Clients, einen gemeinsamen Namen mithilfe des DNS-Systems des Clientcomputers aufzulösen, wenn sie den Namen nicht über NetworkLocation auflösen können. </p> </td> 
  </tr> 
 </tbody> 
</table>
