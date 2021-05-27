---
description: Informationen über die erforderlichen Parameter für Sensor txlogd.conf.
title: Erforderliche Parameter
uuid: 187f4199-ec7f-4d5a-93eb-64a62d51ec7b
exl-id: 782e11e9-b11b-4003-9669-f31187208ec3
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '538'
ht-degree: 1%

---

# Erforderliche Parameter{#required-parameters}

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
   <td colname="col2"> <p>Eine Zeichenkette, die diesen <span class="wintitle"> Sensor</span> eindeutig identifiziert. </p> <p> <span class="wintitle"> </span> SensorID hängt die SensorID an jeden Ereignisdatensatz an, den sie an den  <span class="keyword"> Data Workbench-Server</span> sendet. Die SensorID ermöglicht die Unterscheidung der Ereignisdaten von diesem Webserver von den Ereignisdaten, die von anderen <span class="wintitle"> Sensoren</span> erfasst werden. </p> <p>Obwohl eine Sensor-ID aus einer beliebigen Zeichenkette bestehen kann, wird standardmäßig der Name des Webservers verwendet, dessen Ereignisse vom Sensor <span class="wintitle"></span> erfasst werden. Die Verwendung des Servernamens als Sensor-ID erleichtert die Bestimmung der Ereignisquelle während der Analysephase. Außerdem wird sichergestellt, dass die Sensor-ID innerhalb der Implementierung eindeutig ist. </p> <p>Beispiel: <span class="filepath"> SensorID web001a</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ServerAddress </td> 
   <td colname="col2"> <p>Die Adresse des <span class="keyword"> Data Workbench-Servers</span>, an den dieser <span class="wintitle"> Sensor</span> Ereignisdaten sendet. </p> <p>Hinweis:  <p>Bei der Arbeit in einer Clusterumgebung sollte <span class="wintitle"> Sensor</span> so konfiguriert sein, dass auf den Übergeordneten <span class="keyword"> Data Workbench-Server</span> zugegriffen wird, um Synchronisierungsprobleme zu vermeiden. In Data Workbench können Sie Informationen über die Verarbeitung von <span class="keyword"> Data Workbench-Servern</span> in Ihrem Cluster mithilfe des Menüelements "Related Servers"im <span class="wintitle"> Server Manager</span> anzeigen. Weitere Informationen zum <span class="wintitle"> Server Manager</span> finden Sie im <i><span class="keyword"> Data Workbench</span><span class="wintitle"> Sensor</span> Guide</i>. </p> <p>Wenn Ihr Webserver Servernamen über das DNS auflösen kann, können Sie die Adresse des Servers nach Namen angeben. Ist dies nicht der Fall, müssen Sie die numerische IP-Adresse des Servers angeben. </p> <p>Beispiel: <span class="filepath"> ServerAddress 10.1.0.7</span> oder </p> <p> <span class="filepath"> ServerAddress vserver01.mycompany.com</span> </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL </td> 
   <td colname="col2"> <p>Ob <span class="wintitle"> Sensor</span> mit <span class="keyword"> Data Workbench-Server</span> über HTTP oder HTTPS kommuniziert. Setzen Sie dies bei HTTPS auf "Ein"oder bei HTTP auf "Aus". </p> <p>Beispiel: <span class="filepath"> SSL on</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ServerPort </td> 
   <td colname="col2"> <p>Der Anschluss, an dem der <span class="keyword"> Data Workbench-Server</span> auf Ereignisdaten wartet. </p> <p>Beispiel: <span class="filepath"> ServerPort 443</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> CertName </td> 
   <td colname="col2"> <p>Nur erforderlich, wenn der SSL-Parameter auf "on"gesetzt ist. </p> <p>Der allgemeine Name des <span class="keyword"> Data Workbench-Servers</span>, an den dieser <span class="wintitle"> Sensor</span> Ereignisdaten sendet. </p> <p>Der angegebene Wert muss genau mit dem allgemeinen Namen übereinstimmen, der im Lizenzzertifikat <span class="keyword"> des Data Workbench-Servers</span> angezeigt wird. </p> <p>Beispiel: <span class="filepath"> CertName vserver01.mycompany.com</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> CertPath </td> 
   <td colname="col2"> <p>Nur erforderlich, wenn der SSL-Parameter auf "on"gesetzt ist. </p> <p>Das Verzeichnis, in dem sich die Datei der Zertifizierungsstelle (<span class="filepath"> trust_ca_cert.pem</span>) befindet </p> <p>Beispiele: </p> <p> <span class="filepath"> CertPath /usr/local/visualsensor</span> </p> <p> <span class="filepath"> CertPath C:\VisualSensor</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> QueueFile </td> 
   <td colname="col2"> <p>Nicht erforderlich für <span class="wintitle"> Sensor</span>-Installationen auf Microsoft Windows 2000- oder 2003 Server-Computern, auf denen Internet Information Service (IIS) Versionen 5.x oder 6.x ausgeführt werden. </p> <p>Der vollständig qualifizierte Name der Speicherwarteschlangendatei. </p> <p>Obwohl Sie dieser Datei einen beliebigen Namen zuweisen können, heißt die Warteschlangendatei standardmäßig <span class="filepath"> VisualSensor.dat</span>. </p> <p>Bei Installationen von <span class="wintitle"> Sensor</span> unter Unix können Sie diese Datei an einer beliebigen Stelle platzieren. Unter Windows, auf dem ein Java-Webserver ausgeführt wird, müssen Sie diese Datei im selben Ordner wie den Transmitter ablegen. Bei allen anderen Webservern sollte sich diese Datei im Ordner /var/queue befinden. </p> <p>Beispiel: <span class="filepath"> QueueFile /var/queue/VisualSensor.dat</span> </p> <p> <p>Hinweis:  Stellen Sie sicher, dass das Gerät, dem Sie diese Datei zuweisen, über ausreichend freien Platz verfügt, um eine Warteschlange der benötigten Größe aufzunehmen. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> QueueSize </td> 
   <td colname="col2"> <p>Eine Ganzzahl, die die Größe der Festplattenwarteschlangendatei in MB darstellt. </p> <p>Bei Installationen von <span class="wintitle"> Sensor</span> unter Microsoft Windows wird die Warteschlangendatei selbst im selben Verzeichnis wie der Sender erstellt und heißt <span class="filepath"> Diskq2000.log</span>. </p> <p>Im folgenden Beispiel wird die Warteschlangengröße auf 200 MB festgelegt: </p> <p>QueueSize 200 </p> <p>Im folgenden Beispiel wird die Warteschlangengröße auf 2 GB festgelegt: </p> <p>QueueSize 2000 </p> </td> 
  </tr> 
 </tbody> 
</table>
