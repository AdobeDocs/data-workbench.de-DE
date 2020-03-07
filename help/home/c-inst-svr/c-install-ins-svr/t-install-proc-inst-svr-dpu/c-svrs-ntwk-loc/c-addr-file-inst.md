---
description: Die auf Insight Server installierte Adressdatei enthält vier vordefinierte Netzwerkspeicherorte.
solution: Insight
title: Die auf dem Insight-Server installierte Adressdatei
uuid: a58d36d8-e1a3-43e7-91c5-c57351e1be49
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Die auf dem Insight-Server installierte Adressdatei{#the-address-file-installed-on-insight-server}

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

* NetworkLocation 0 ist ein leerer, unbenannter Netzwerkspeicherort, den Sie bearbeiten, um den gemeinsamen Namen Ihrer IP-Adresse [!DNL Insight Server] zuzuordnen. Wenn der Server über mehrere IP-Adressen verfügt, erstellen Sie zusätzliche NetworkLocations.
* NetworkLocation 1 ist der [!DNL Insight] Netzwerkspeicherort. Wenn Sie den NetworkLocation-Parameter nicht explizit festlegen, werden allgemeine Namen über diesen Netzwerkspeicherort aufgelöst [!DNL Insight] .

* NetworkLocation 2 ist der [!DNL Insight Server] Netzwerkspeicherort. Wenn sie in einem Cluster [!DNL Insight Servers] arbeiten, verwenden sie diesen Netzwerkspeicherort, um allgemeine Namen für die Kommunikation zwischen Servern aufzulösen.

* NetworkLocation 3 ist der Netzwerkspeicherort des [!DNL Report] Servers. Wenn Sie den NetworkLocation-Parameter nicht explizit festlegen, werden allgemeine Namen über diesen Netzwerkspeicherort aufgelöst [!DNL Report] .

## So konfigurieren Sie die Adressdatei {#section-10caab9854a244e39b09071946f7bd27}

Im folgenden Verfahren wird beschrieben, wie Sie die Adressdatei konfigurieren, um einen Netzwerkspeicherort (oder Netzwerkspeicherorte) für Ihre [!DNL Insight Server]Daten zu definieren.

1. Navigieren Sie zu dem [!DNL Addresses] Ordner, in dem Sie installiert haben [!DNL Insight Server] (z. B. [!DNL C:\Adobe\Server\Addresses)]).

1. Suchen Sie die [!DNL server.address] Datei und benennen Sie sie um, um den allgemeinen Namen des Servers wiederzugeben. Wenn der allgemeine Name beispielsweise [!DNL server.mycompany.com]lautet, würden Sie die Datei umbenennen [!DNL server.mycompany.com.address].

1. Öffnen Sie die umbenannte Datei in einem Texteditor wie Notepad.
1. Bearbeiten Sie NetworkLocation 0, um den allgemeinen Namen und die IP-Adresse des [!DNL Insight Server] wie unten gezeigt anzugeben. Wenn Ihr Server über mehrere IP-Adressen verfügt, verwenden Sie NetworkLocation 0, um die IP-Adresse des Servers im lokalen, nicht routingfähigen Netzwerk anzugeben (z. B. den Speicherort im internen Netzwerk).

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
   <th colname="col2" class="entry"> Legen Sie </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <i>IP-Adresse</i> </td> 
   <td colname="col2"> <p>Die numerische IP-Adresse des <span class="keyword"> Insight Server- </span> Computers. </p> <p>Beispiel: 192.168.124.176 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>Allgemeiner Name </i> </td> 
   <td colname="col2"> <p>Der allgemeine Name, der dem digitalen Zertifikat für <span class="keyword"> Insight Server zugewiesen ist </span>. </p> <p>Beispiel: <span class="filepath"> server.mycompany.com </span></p> <p>Hinweis: Achten Sie darauf, diesen Namen genau so einzugeben, wie er im Zertifikat angezeigt wird. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>Name des Netzwerkstandorts </i> </td> 
   <td colname="col2"> <p>Der Name, den Sie der Sammlung von allgemeinen Namen und IP-Adressen zuweisen möchten, die diese NetworkLocation darstellt. Der Name muss innerhalb der Adressdatei eindeutig sein. </p> <p>Beispiel: Firmenintranet </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Wenn Ihre IP-Adressen [!DNL Insight Server] zusätzlich sind, erstellen Sie für jede Adresse eine zusätzliche NetworkLocation. (Eine einfache Möglichkeit ist es, eine Kopie des oben erstellten NetworkLocation zu erstellen und die IP-Adresse in der Kopie zu aktualisieren.)

   Sie können die neue NetworkLocation-Datei am Ende der Adressdatei hinzufügen oder zwischen vorhandenen NetworkLocation-Definitionen einfügen. (Die Position eines NetworkLocation in der Adressdatei ist nicht von Bedeutung; Die [!DNL Insight]-, [!DNL Insight Server]und [!DNL Report] -Server-Netzwerkspeicherorte werden jedoch normalerweise am Dateiende platziert.)

   Nachdem Sie die erforderlichen NetworkLocations hinzugefügt haben, führen Sie die folgenden Schritte aus, um die Elemente in der Datei neu zu nummerieren:

   1. Aktualisieren Sie die Elementanzahl für die Ortsstruktur, damit sie mit der Gesamtanzahl der NetworkLocation-Definitionen in der Datei übereinstimmt. Wenn Ihre Datei beispielsweise vier NetworkLocation-Definitionen enthält, würde die Zeile &quot;Speicherorte&quot;wie folgt aussehen:

      ```
      Locations = vector: 4 items
      ```

   1. Aktualisieren Sie die NetworkLocation-Elementnummern, sodass NetworkLocations fortlaufend nummeriert werden (beginnend mit 0).
   Ein Beispiel für eine Adressdatei, die eine [!DNL Insight Server] mit zwei IP-Adressen definiert, finden Sie im Beispiel in diesem Abschnitt.

1. Bearbeiten Sie in den Netzwerkspeicherorten [!DNL Insight] und [!DNL Report] Server den Parameter Übergeordnet wie unten dargestellt, um den Namen der NetworkLocation anzugeben, die als Standardnetzwerkspeicherorte verwendet [!DNL Insight] und verwendet werden [!DNL Report] . (Ein Beispiel für das Aussehen des übergeordneten Parameters bei der Konfiguration finden Sie im Beispiel in diesem Abschnitt.)

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

   Wenn Sie [!DNL Insight Server] über eine einzige IP-Adresse verfügen und daher nur über eine NetworkLocation verfügen, verweisen Sie den übergeordneten Parameter auf diese NetworkLocation. Wenn Ihre IP-Adresse mehrere IP-Adressen [!DNL Insight Server] hat, verweisen Sie den Parameter Übergeordnet auf die NetworkLocation, die die Adresse definiert, zu der Ihre [!DNL Insight] und [!DNL Report] Clients am häufigsten eine Verbindung herstellen.

1. Bearbeiten Sie im [!DNL Insight Server] Netzwerkspeicherort den Parameter Übergeordnet wie unten dargestellt, um auf den NetworkLocation zu verweisen, mit dem der Server allgemeine Namen anderer auflösen kann, [!DNL Insight Servers] wenn er in einem Cluster arbeitet. (Obwohl dieser Netzwerkspeicherort nur verwendet wird, wenn ein [!DNL Insight Server] Cluster in einem Cluster ausgeführt wird, empfiehlt es sich, auch bei einer Einzelserverkonfiguration den Parameter &quot;Übergeordnet&quot;auf einen Netzwerkspeicherort zu verweisen, der die interne IP-Adresse des Servers identifiziert.)

   ```
   2 = NetworkLocation:  
     Addresses = vector: 0 items 
     Name = string: Insight Server 
     Parent = string: ServerDefaultNetworkLocation
   ```

Das folgende Beispiel zeigt eine abgeschlossene Adressdatei. Diese Datei definiert fünf Netzwerkspeicherorte.

* NetworkLocation-Elemente 0 und 1 definieren Netzwerkspeicherorte namens &quot;MyCorporateIntranet&quot;und &quot;Internet&quot;. Diese Netzwerkspeicherorte definieren zwei verschiedene IP-Adressen für einen Server mit dem Namen [!DNL VS01.myCompany.com].
* NetworkLocation Element 2 ist der [!DNL Insight] Netzwerkspeicherort. Dies ist der Standard-Netzwerkspeicherort, der von [!DNL Insight]verwendet wird. In diesem Beispiel übernimmt der [!DNL Insight] Netzwerkspeicherort seine AddressDefinitions aus dem NetworkLocation &quot;Internet&quot;.

* NetworkLocation Element 3 ist der [!DNL Insight Server] Netzwerkspeicherort. Dies ist der Standardnetzwerkspeicherort, der [!DNL Insight Server] verwendet wird, wenn er mit anderen Servern in einem Cluster kommuniziert. In diesem Beispiel übernimmt der [!DNL Insight Server] Netzwerkstandort seine AddressDefinitions vom NetworkLocation &quot;MyCorporate Intranet&quot;.

* NetworkLocation-Element 4 ist der [!DNL Report] Server-Netzwerkspeicherort. Dies ist der Standard-Netzwerkspeicherort, der von [!DNL Report]verwendet wird. In diesem Beispiel übernimmt der Netzwerkspeicherort [!DNL Report] Server seine AddressDefinitions vom NetworkLocation &quot;Internet&quot;.

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

