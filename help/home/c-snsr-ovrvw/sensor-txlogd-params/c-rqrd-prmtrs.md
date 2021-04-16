---
description: Informationen zu den erforderlichen Sensor-Parametern txlogd.conf.
title: Erforderliche Parameter
uuid: 187f4199-ec7f-4d5a-93eb-64a62d51ec7b
exl-id: 782e11e9-b11b-4003-9669-f31187208ec3
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '538'
ht-degree: 1%

---

# Erforderliche Parameter{#required-parameters}

Informationen zu den erforderlichen Sensor-Parametern txlogd.conf.

<table id="table_69CFE10A3707403F9793137B128E706A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> In diesem Parameter... </th> 
   <th colname="col2" class="entry"> Legen Sie... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> SensorID </td> 
   <td colname="col2"> <p>Eine Zeichenfolge, die diesen <span class="wintitle"> Sensor</span> eindeutig identifiziert. </p> <p> <span class="wintitle"> SensorID </span> hängt die SensorID an jeden Ereignis-Datensatz an, der an den  <span class="keyword"> Data Workbench-Server</span> gesendet wird. Die SensorID ermöglicht die Unterscheidung der Ereignis-Daten dieses Webservers von den Ereignis-Daten, die von anderen <span class="wintitle"> Sensoren</span> erfasst werden. </p> <p>Obwohl eine SensorID aus einer beliebigen Zeichenfolge bestehen kann, wird üblicherweise der Name des Webservers verwendet, dessen Ereignis vom Sensor<span class="wintitle"> erfasst werden. </span> Die Verwendung des Servernamens als SensorID erleichtert die Bestimmung der Quelle eines Ereignisses während der Analyse. Außerdem wird sichergestellt, dass die SensorID innerhalb der Implementierung eindeutig ist. </p> <p>Beispiel: <span class="filepath"> SensorID web001a</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ServerAddress </td> 
   <td colname="col2"> <p>Die Adresse des <span class="keyword">-Data Workbench-Servers</span>, an den dieser <span class="wintitle">-Sensor</span> Ereignis-Daten sendet. </p> <p>Hinweis:  <p>Bei der Arbeit in einer geclusterten Umgebung sollte <span class="wintitle"> Sensor</span> so konfiguriert werden, dass auf den Übergeordnet <span class="keyword"> Data Workbench-Server</span> zugegriffen wird, um Synchronisierungsprobleme zu vermeiden. In Data Workbench können Sie mithilfe des Menüpunkts "Verwandte Server"im <span class="wintitle"> Server Manager</span> Informationen zur Ansicht der Datenbasis-Server</span> im Cluster bereitstellen. <span class="keyword"> Weitere Informationen zum <span class="wintitle"> Server-Manager</span> finden Sie in der <i><span class="keyword"> Data Workbench</span><span class="wintitle"> Sensor</span> Guide</i>. </span></p> <p>Wenn Ihr Webserver Servernamen über DNS auflösen kann, können Sie die Serveradresse anhand des Namens angeben. Andernfalls müssen Sie die numerische IP-Adresse des Servers angeben. </p> <p>Beispiel: <span class="filepath"> ServerAddress 10.1.0.7</span> oder </p> <p> <span class="filepath"> ServerAddress vserver01.mycompany.com</span> </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL </td> 
   <td colname="col2"> <p>Ob <span class="wintitle"> Sensor</span> mit <span class="keyword"> Data Workbench-Server</span> über HTTP oder HTTPS kommuniziert. Bei HTTPS auf "Ein"oder bei HTTP auf "Aus" eingestellt. </p> <p>Beispiel: <span class="filepath"> SSL unter</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ServerPort </td> 
   <td colname="col2"> <p>Der Anschluss, an dem der Data Workbench-Server <span class="keyword"> auf Ereignis-Daten wartet.</span> </p> <p>Beispiel: <span class="filepath"> ServerPort 443</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> CertName </td> 
   <td colname="col2"> <p>Nur erforderlich, wenn der SSL-Parameter auf "on"gesetzt ist. </p> <p>Der allgemeine Name des Data Workbench-Servers <span class="keyword">, an den dieser <span class="wintitle">-Sensor</span> Ereignis-Daten sendet.</span> </p> <p>Der angegebene Wert muss exakt mit dem im Lizenzzertifikat <span class="keyword"> des Data Workbench-Servers</span> angegebenen allgemeinen Namen übereinstimmen. </p> <p>Beispiel: <span class="filepath"> CertName vserver01.mycompany.com</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> CertPath </td> 
   <td colname="col2"> <p>Nur erforderlich, wenn der SSL-Parameter auf "on"gesetzt ist. </p> <p>Der Ordner, in dem sich die Datei mit der Zertifizierungsstelle (<span class="filepath"> trust_ca_cert.pem</span>) befindet </p> <p>Beispiele: </p> <p> <span class="filepath"> CertPath /usr/local/visualsensor</span> </p> <p> <span class="filepath"> CertPath C:\VisualSensor</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> QueueFile </td> 
   <td colname="col2"> <p>Nicht erforderlich für <span class="wintitle"> Sensor</span>-Installationen auf Microsoft Windows 2000- oder 2003-Servercomputern, auf denen Internet Informationsdienst (IIS) Version 5.x oder 6.x ausgeführt wird. </p> <p>Der vollständig qualifizierte Name der Disk Queue-Datei. </p> <p>Obwohl Sie dieser Datei einen beliebigen Namen zuweisen können, heißt die Warteschlangendatei standardmäßig <span class="filepath"> VisualSensor.dat</span>. </p> <p>Bei Installationen unter Unix können Sie diese Datei an einer beliebigen Stelle platzieren. <span class="wintitle"></span> Unter Windows, auf dem ein Java-Webserver ausgeführt wird, müssen Sie diese Datei in demselben Ordner wie den Transmitter ablegen. Bei allen anderen Webservern sollte sich diese Datei im Ordner "/var/queue"befinden. </p> <p>Beispiel: <span class="filepath"> QueueFile /var/queue/VisualSensor.dat</span> </p> <p> <p>Hinweis:  Stellen Sie sicher, dass das Gerät, dem Sie diese Datei zuweisen, genügend freien Speicherplatz für eine Warteschlange in der benötigten Größe hat. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> QueueSize </td> 
   <td colname="col2"> <p>Eine Ganzzahl, die die Größe der Disk Queue-Datei in MB angibt. </p> <p>Bei Installationen von "<span class="wintitle"> Sensor</span>"unter Microsoft Windows wird die Warteschlangendatei selbst im selben Verzeichnis wie der Sender erstellt und trägt den Namen "<span class="filepath"> Diskq2000.log</span>". </p> <p>Im folgenden Beispiel wird die Warteschlangengröße auf 200 MB eingestellt: </p> <p>QueueSize 200 </p> <p>Im folgenden Beispiel wird die Warteschlangengröße auf 2 GB eingestellt: </p> <p>QueueSize 2000 </p> </td> 
  </tr> 
 </tbody> 
</table>
