---
description: Die auf Insight Server installierte Adressdatei enthält vier vordefinierte Netzwerkspeicherorte.
title: Auf Insight Server installierte Adressdatei
uuid: a58d36d8-e1a3-43e7-91c5-c57351e1be49
exl-id: 12e9bfa2-99ac-4584-b761-38401d1bc3d1
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '804'
ht-degree: 2%

---

# Auf Insight Server installierte Adressdatei{#the-address-file-installed-on-insight-server}

{{eol}}

Die auf Insight Server installierte Adressdatei enthält vier vordefinierte Netzwerkspeicherorte.

Im nächsten Abschnitt wird beschrieben, wie Sie diese Datei konfigurieren.

```
Locations = vector: 4 items  
  0 = NetworkLocation:  
    Addresses = vector: 1 items 
      0 = AddressDefinition:  
        Address = string:  
        Name = string:  
    Name = string:  
    Parent = string:  
  1 = NetworkLocation:  
    Addresses = vector: 0 items 
    Name = string: Insight 
    Parent = string:  
  2 = NetworkLocation:  
    Addresses = vector: 0 items 
    Name = string: Insight Server 
    Parent = string: 
  3 = NetworkLocation:  
    Addresses = vector: 0 items 
    Name = string: Report Server 
    Parent = string:
```

* NetworkLocation 0 ist ein leerer, unbenannter Netzwerkspeicherort, den Sie bearbeiten, um den gemeinsamen Namen Ihrer [!DNL Insight Server] auf die IP-Adresse. Wenn der Server über mehrere IP-Adressen verfügt, erstellen Sie zusätzliche NetworkLocations.
* NetworkLocation 1 ist die [!DNL Insight] Netzwerkspeicherort. Wenn Sie den Parameter NetworkLocation nicht explizit festlegen, [!DNL Insight] löst allgemeine Namen über diesen Netzwerkspeicherort auf.

* NetworkLocation 2 ist die [!DNL Insight Server] Netzwerkspeicherort. Wann [!DNL Insight Servers] in einem Cluster arbeiten, verwenden sie diesen Netzwerkspeicherort, um allgemeine Namen für die Kommunikation zwischen Servern aufzulösen.

* NetworkLocation 3 ist die [!DNL Report] Server-Netzwerkspeicherort. Wenn Sie den Parameter NetworkLocation nicht explizit festlegen, [!DNL Report] löst allgemeine Namen über diesen Netzwerkspeicherort auf.

## So konfigurieren Sie die Adressdatei {#section-10caab9854a244e39b09071946f7bd27}

Im folgenden Verfahren wird beschrieben, wie Sie die Adressdatei konfigurieren, um einen Netzwerkspeicherort (oder Netzwerkspeicherorte) für Ihre [!DNL Insight Server].

1. Navigieren Sie zum [!DNL Addresses] Ordner im Verzeichnis, in dem Sie installiert haben [!DNL Insight Server] (z. B. [!DNL C:\Adobe\Server\Addresses)].

1. Suchen Sie die [!DNL server.address] und benennen Sie diese Datei um, um den allgemeinen Namen des Servers widerzuspiegeln. Wenn beispielsweise der allgemeine Name [!DNL server.mycompany.com], benennen Sie die Datei um. [!DNL server.mycompany.com.address].

1. Öffnen Sie die umbenannte Datei in einem Texteditor wie Notepad.
1. Bearbeiten Sie NetworkLocation 0, um den allgemeinen Namen und die IP-Adresse der [!DNL Insight Server] wie unten dargestellt. Wenn Ihr Server über mehrere IP-Adressen verfügt, geben Sie über NetworkLocation 0 die IP-Adresse des Servers im lokalen, nicht routbaren Netzwerk an (z. B. dessen Speicherort im internen Netzwerk).

   ```
   Locations = vector: 3 items 
   0 = NetworkLocation: 
     Addresses = vector: 1 items 
       0 = AddressDefinition: 
         Address = string: IPAddress 
         Name = string: CommonName 
     Name = string: NetworkLocationName 
     Parent = string: 
   ```

<table id="table_02C2A1630CCD40C4A51B314C3CB683F1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Für diesen Wert... </th> 
   <th colname="col2" class="entry"> Legen Sie  </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <i>IP-Adresse</i> </td> 
   <td colname="col2"> <p>Die numerische IP-Adresse der <span class="keyword"> Insight Server </span> Maschine. </p> <p>Beispiel: 192 168 124 176 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>Gebrauchsname </i> </td> 
   <td colname="col2"> <p>Der allgemeine Name, der dem digitalen Zertifikat für <span class="keyword"> Insight Server </span>. </p> <p>Beispiel: <span class="filepath"> server.mycompany.com </span></p> <p>Hinweis: Geben Sie diesen Namen genau so ein, wie er auf dem Zertifikat angezeigt wird. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>Netzwerkstandort-Name </i> </td> 
   <td colname="col2"> <p>Der Name, den Sie der Sammlung von allgemeinen Namen und IP-Adressen zuweisen möchten, die dieser NetworkLocation darstellt. Der Name muss innerhalb der Adressdatei eindeutig sein. </p> <p>Beispiel: Intranet für Unternehmen </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Wenn [!DNL Insight Server] über zusätzliche IP-Adressen verfügt, erstellen Sie für jede Adresse eine zusätzliche NetworkLocation. (Eine einfache Möglichkeit, dies zu tun, besteht darin, eine Kopie des oben erstellten NetworkLocation zu erstellen und die IP-Adresse in der Kopie zu aktualisieren.)

   Sie können den neuen NetworkLocation am Ende der Adressdatei hinzufügen oder ihn zwischen vorhandenen NetworkLocation-Definitionen einfügen. (Die Position eines NetworkLocation in der Adressdatei ist nicht signifikant. jedoch die [!DNL Insight], [!DNL Insight Server]und [!DNL Report] Server NetworkLocations werden normalerweise am Ende der Datei platziert.)

   Nachdem Sie die erforderlichen NetworkLocations hinzugefügt haben, führen Sie die folgenden Schritte aus, um die Elemente in der Datei neu zu nummerieren:

   1. Aktualisieren Sie die Elementanzahl für die Standortstruktur so, dass sie mit der Gesamtzahl der NetworkLocation-Definitionen in der Datei übereinstimmt. Wenn Ihre Datei beispielsweise vier NetworkLocation-Definitionen enthält, würde die Zeile Standorte wie folgt aussehen:

      ```
      Locations = vector: 4 items
      ```

   1. Aktualisieren Sie die NetworkLocation-Elementnummern so, dass NetworkLocations fortlaufend nummeriert wird (beginnend mit 0).
   Beispiel: eine Adressdatei, die eine [!DNL Insight Server] mit zwei IP-Adressen verwenden, siehe das Beispiel in diesem Abschnitt.

1. Im [!DNL Insight] und [!DNL Report] Server-Netzwerkspeicherorte bearbeiten Sie den übergeordneten Parameter wie unten gezeigt, um den Namen des NetworkLocation anzugeben, der [!DNL Insight] und [!DNL Report] als Standard-Netzwerkspeicherorte verwenden. (Ein Beispiel dafür, wie der übergeordnete Parameter bei der Konfiguration aussieht, finden Sie im Beispiel in diesem Abschnitt.)

   ```
   1 = NetworkLocation:  
     Addresses = vector: 0 items 
     Name = string: Insight 
     Parent = string: ClientDefaultNetworkLocation 
   
   3 = NetworkLocation:  
     Addresses = vector: 0 items 
     Name = string: Report Server 
     Parent = string: ClientDefaultNetworkLocation
   ```

   Wenn [!DNL Insight Server] eine einzelne IP-Adresse hat und daher nur eine NetworkLocation hat, verweisen Sie den übergeordneten Parameter auf diese NetworkLocation. Wenn [!DNL Insight Server] über mehrere IP-Adressen verfügt, verweisen Sie den übergeordneten Parameter auf den NetworkLocation , der die Adresse definiert, an die Ihre [!DNL Insight] und [!DNL Report] Clients verbinden sich am häufigsten.

1. Im [!DNL Insight Server] Netzwerkspeicherort, bearbeiten Sie den übergeordneten Parameter wie unten gezeigt, um auf den Netzwerkspeicherort zu verweisen, mit dem der Server gebräuchliche Namen anderer [!DNL Insight Servers] wenn sie in einem Cluster ausgeführt wird. (Obwohl dieser Netzwerkspeicherort nur verwendet wird, wenn eine [!DNL Insight Server] in einem Cluster ausgeführt wird, empfiehlt es sich, auch in einer einzigen Serverkonfiguration den Parameter &quot;Parent&quot;auf einen Netzwerkspeicherort zu verweisen, der die interne IP-Adresse des Servers angibt.)

   ```
   2 = NetworkLocation:  
     Addresses = vector: 0 items 
     Name = string: Insight Server 
     Parent = string: ServerDefaultNetworkLocation
   ```

Das folgende Beispiel zeigt eine abgeschlossene Adressdatei. Diese Datei definiert fünf Netzwerkspeicherorte.

* NetworkLocation-Elemente 0 und 1 definieren Netzwerkstandorte namens &quot;MyCorporateIntranet&quot;und &quot;Internet&quot;. Diese Netzwerkstandorte definieren zwei verschiedene IP-Adressen für einen Server mit dem Namen [!DNL VS01.myCompany.com].
* NetworkLocation Element 2 ist die [!DNL Insight] Netzwerkspeicherort. Dies ist der standardmäßige Netzwerkspeicherort, der von [!DNL Insight]. In diesem Beispiel wird die [!DNL Insight] Der Netzwerkstandort erbt seine AddressDefinitions vom Netzwerkstandort &quot;Internet&quot;.

* NetworkLocation Element 3 ist das [!DNL Insight Server] Netzwerkspeicherort. Dies ist der standardmäßige Netzwerkspeicherort. [!DNL Insight Server] verwendet , wenn es mit anderen Servern in einem Cluster kommuniziert. In diesem Beispiel wird die [!DNL Insight Server] Der Netzwerkstandort übernimmt seine AddressDefinitions vom NetworkLocation &quot;MyCorporate Intranet&quot;.

* NetworkLocation Element 4 ist die [!DNL Report] Server-Netzwerkspeicherort. Dies ist der standardmäßige Netzwerkspeicherort, der von [!DNL Report]. In diesem Beispiel wird die [!DNL Report] Der Netzwerkstandort des Servers übernimmt die AddressDefinitions vom Netzwerkstandort &quot;Internet&quot;.

   ```
   Locations = vector: 5 items 
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
   
     2 = NetworkLocation:  
       Addresses = vector: 0 items 
       Name = string: Insight 
       Parent = string: Internet 
   
     3 = NetworkLocation:  
       Addresses = vector: 0 items 
       Name = string: Insight Server 
       Parent = string: MyCorporateIntranet 
   
     4 = NetworkLocation:  
       Addresses = vector: 0 items 
       Name = string: Report Server 
       Parent = string: Internet
   ```
