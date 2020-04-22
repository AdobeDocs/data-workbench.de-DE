---
description: Die Adressdatei erfüllt grundsätzlich denselben Zweck wie die ETC&bsol;HOSTS-Datei auf einem vernetzten Computer.
solution: Insight
title: Netzwerkspeicherorte
uuid: a2097eca-dd75-4d43-b8a8-fb4c768df38d
translation-type: tm+mt
source-git-commit: e8612fab1c13ca5262816dde7deaa6fd8bedbc62

---


# Netzwerkspeicherorte{#network-locations}

Die Adressdatei erfüllt grundsätzlich denselben Zweck wie die ETC&amp;bsol;HOSTS-Datei auf einem vernetzten Computer.

Im Gegensatz zur HOSTS-Datei, die eine einzelne Namenssammlung beschreibt, enthält die Adressdatei jedoch mehrere Namenssammlungen, die als Netzwerkspeicherorte bezeichnet werden.

Ein Netzwerkspeicherort ist eine benannte Sammlung von Adressdefinitionen. Jede Adressdefinition in der Sammlung verknüpft einen gemeinsamen Namen mit einer IP-Adresse.

In der Adressdatei wird ein Netzwerkspeicherort in einer Struktur definiert, die als NetworkLocation bezeichnet wird. Die NetworkLocation im folgenden Beispiel definiert einen Netzwerkspeicherort namens &quot;MyCorporate Intranet&quot;. Es enthält eine Adressdefinition, die den gemeinsamen Namen der IP-Adresse &quot;10.2.1.70&quot; [!DNL VS01.myCompany.com] zuordnet.

```
0 = NetworkLocation: 
  Addresses = vector: 1 items
    0 = AddressDefinition: 
      Address = string: 10.2.1.70
      Name = string: VS01.myCompany.com
  Name = string: MyCorporateIntranet
  Parent = string: 
```

Wie im Beispiel oben gezeigt, besteht die NetworkLocation-Struktur aus drei Hauptparametern:

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
   <td colname="col2"> Definiert null oder mehr AddressDefinitions. Jede AddressDefintion verknüpft einen gemeinsamen Namen mit einer IP-Adresse. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Name </td> 
   <td colname="col2"> Weist NetworkLocation einen Namen zu. Der einem NetworkLocation zugewiesene Name muss innerhalb der Adressdatei eindeutig sein. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Übergeordnet </td> 
   <td colname="col2"> <p>Gibt den Namen einer anderen NetworkLocation an, deren Mitglieder in dieser NetworkLocation enthalten sind. Mit diesem Parameter kann eine NetworkLocation eine andere erweitern. </p> <p>Sie können den Parameter "Parent"auf "DNS"setzen, um eine NetworkLocation auf das normale DNS-System des Clients zu erweitern. </p> <p>Beispiel: Übergeordnet = Zeichenfolge: DNS </p> <p>Wenn DNS das übergeordnete Element ist, versuchen Clients, einen gemeinsamen Namen mithilfe des DNS-Systems des Clientcomputers aufzulösen, wenn sie den Namen nicht über NetworkLocation auflösen können. </p> </td> 
  </tr> 
 </tbody> 
</table>
