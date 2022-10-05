---
description: Informationen über die erforderlichen Parameter für Sensor txlogd.conf.
title: Erforderliche Parameter
uuid: 187f4199-ec7f-4d5a-93eb-64a62d51ec7b
exl-id: 782e11e9-b11b-4003-9669-f31187208ec3
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '538'
ht-degree: 1%

---

# Erforderliche Parameter{#required-parameters}

{{eol}}

Informationen über die erforderlichen Parameter für Sensor txlogd.conf.

<table id="table_69CFE10A3707403F9793137B128E706A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> In diesem Parameter ... </th> 
   <th colname="col2" class="entry"> Legen Sie... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> SensorID </td> 
   <td colname="col2"> <p>Eine Zeichenfolge, die dies eindeutig identifiziert <span class="wintitle"> Sensor</span>. </p> <p> <span class="wintitle"> Sensor</span> hängt die Sensor-ID an jeden Ereignisdatensatz an, den sie an die <span class="keyword"> Data Workbench-Server</span>. Die SensorID ermöglicht die Unterscheidung der Ereignisdaten von diesem Webserver von den Ereignisdaten, die von anderen erfasst werden <span class="wintitle"> Sensoren</span>. </p> <p>Obwohl eine Sensor-ID aus einer beliebigen Zeichenfolge von Zeichen bestehen kann, ist der Name des Webservers, dessen Ereignisse die <span class="wintitle"> Sensor</span> wird erfasst. Die Verwendung des Servernamens als Sensor-ID erleichtert die Bestimmung der Ereignisquelle während der Analysephase. Außerdem wird sichergestellt, dass die Sensor-ID innerhalb der Implementierung eindeutig ist. </p> <p>Beispiel: <span class="filepath"> SensorID web001a</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ServerAddress </td> 
   <td colname="col2"> <p>Die Adresse der <span class="keyword"> Data Workbench-Server</span> für die <span class="wintitle"> Sensor</span> sendet Ereignisdaten. </p> <p>Hinweis:  <p>Wenn Sie in einer Clusterumgebung arbeiten, <span class="wintitle"> Sensor</span> sollte so konfiguriert werden, dass auf den Übergeordneten <span class="keyword"> Data Workbench-Server</span> um Synchronisierungsprobleme zu vermeiden. In Data Workbench können Sie Informationen zur Verarbeitung anzeigen <span class="keyword"> Data Workbench-Server</span> in Ihrem Cluster mithilfe des Menüelements "Verwandte Server"im <span class="wintitle"> Server-Manager</span>. Weitere Informationen zum <span class="wintitle"> Server-Manager</span>, siehe <i><span class="keyword"> Data Workbench</span><span class="wintitle"> Sensor</span> Handbuch</i>. </p> <p>Wenn Ihr Webserver Servernamen über das DNS auflösen kann, können Sie die Adresse des Servers nach Namen angeben. Ist dies nicht der Fall, müssen Sie die numerische IP-Adresse des Servers angeben. </p> <p>Beispiel: <span class="filepath"> ServerAddress 10.1.0.7</span> oder </p> <p> <span class="filepath"> ServerAddress vserver01.mycompany.com</span> </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL </td> 
   <td colname="col2"> <p>Ob <span class="wintitle"> Sensor</span> kommuniziert mit <span class="keyword"> Data Workbench-Server</span> mit HTTP oder HTTPS verwenden. Setzen Sie dies bei HTTPS auf "Ein"oder bei HTTP auf "Aus". </p> <p>Beispiel: <span class="filepath"> SSL on</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ServerPort </td> 
   <td colname="col2"> <p>Der Anschluss, an dem die <span class="keyword"> Data Workbench-Server</span> überwacht auf Ereignisdaten. </p> <p>Beispiel: <span class="filepath"> ServerPort 443</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> CertName </td> 
   <td colname="col2"> <p>Nur erforderlich, wenn der SSL-Parameter auf "on"gesetzt ist. </p> <p>Der allgemeine Name der <span class="keyword"> Data Workbench-Server</span> für die <span class="wintitle"> Sensor</span> sendet Ereignisdaten. </p> <p>Der angegebene Wert muss genau mit dem allgemeinen Namen übereinstimmen, der auf der <span class="keyword"> Data Workbench-Server</span> Lizenzzertifikat. </p> <p>Beispiel: <span class="filepath"> CertName vserver01.mycompany.com</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> CertPath </td> 
   <td colname="col2"> <p>Nur erforderlich, wenn der SSL-Parameter auf "on"gesetzt ist. </p> <p>Das Verzeichnis, in dem die Zertifizierungsstelle (<span class="filepath"> trust_ca_cert.pem</span>) befindet. </p> <p>Beispiele: </p> <p> <span class="filepath"> CertPath /usr/local/visualsensor</span> </p> <p> <span class="filepath"> CertPath C:\VisualSensor</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> QueueFile </td> 
   <td colname="col2"> <p>Nicht erforderlich für <span class="wintitle"> Sensor</span> Installationen auf Microsoft Windows 2000- oder 2003 Server-Computern mit IIS-Versionen 5.x oder 6.x (Internet Information Service). </p> <p>Der vollständig qualifizierte Name der Speicherwarteschlangendatei. </p> <p>Sie können dieser Datei zwar einen beliebigen Namen zuweisen, jedoch wird die Warteschlangendatei standardmäßig mit dem Namen <span class="filepath"> VisualSensor.dat</span>. </p> <p>Für <span class="wintitle"> Sensor</span> -Installationen auf Unix, können Sie diese Datei an einer beliebigen Stelle platzieren. Unter Windows, auf dem ein Java-Webserver ausgeführt wird, müssen Sie diese Datei im selben Ordner wie den Transmitter ablegen. Bei allen anderen Webservern sollte sich diese Datei im Ordner /var/queue befinden. </p> <p>Beispiel: <span class="filepath"> QueueFile /var/queue/VisualSensor.dat</span> </p> <p> <p>Hinweis: Stellen Sie sicher, dass das Gerät, dem Sie diese Datei zuweisen, über ausreichend freien Platz verfügt, um eine Warteschlange der benötigten Größe aufzunehmen. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> QueueSize </td> 
   <td colname="col2"> <p>Eine Ganzzahl, die die Größe der Festplattenwarteschlangendatei in MB darstellt. </p> <p>Für <span class="wintitle"> Sensor</span> Installationen unter Microsoft Windows werden die Warteschlangendatei selbst im selben Ordner wie der Transmitter erstellt und erhalten den Namen <span class="filepath"> Diskq2000.log</span>. </p> <p>Im folgenden Beispiel wird die Warteschlangengröße auf 200 MB festgelegt: </p> <p>QueueSize 200 </p> <p>Im folgenden Beispiel wird die Warteschlangengröße auf 2 GB festgelegt: </p> <p>QueueSize 2000 </p> </td> 
  </tr> 
 </tbody> 
</table>
