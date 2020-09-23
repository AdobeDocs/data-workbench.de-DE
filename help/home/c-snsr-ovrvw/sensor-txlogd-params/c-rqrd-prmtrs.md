---
description: Informationen zu den erforderlichen Sensor-Parametern txlogd.conf.
solution: Analytics
title: Erforderliche Parameter
uuid: 187f4199-ec7f-4d5a-93eb-64a62d51ec7b
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
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
   <td colname="col2"> <p>Eine Zeichenfolge, die diesen <span class="wintitle"> Sensor</span>eindeutig identifiziert. </p> <p> <span class="wintitle"> Sensor</span> hängt die SensorID an jeden Ereignis-Datensatz an, den er an den <span class="keyword"> Data Workbench-Server</span>sendet. Mit der SensorID können die Ereignis-Daten dieses Webservers von den Ereignis-Daten anderer <span class="wintitle"> Sensoren</span>unterschieden werden. </p> <p>Obwohl eine SensorID aus einer beliebigen Zeichenfolge bestehen kann, wird der Name des Webservers, dessen Ereignis der <span class="wintitle"> Sensor</span> erfasst, standardmäßig verwendet. Die Verwendung des Servernamens als SensorID erleichtert die Bestimmung der Quelle eines Ereignisses während der Analyse. Außerdem wird sichergestellt, dass die SensorID innerhalb der Implementierung eindeutig ist. </p> <p>Beispiel: <span class="filepath"> SensorID web001a</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ServerAddress </td> 
   <td colname="col2"> <p>Die Adresse des <span class="keyword"> Data Workbench-Servers</span> , an den dieser <span class="wintitle"> Sensor</span> Ereignis-Daten sendet. </p> <p>Hinweis:  <p>Bei der Arbeit mit einer geclusterten Umgebung sollte <span class="wintitle"> Sensor</span> so konfiguriert werden, dass auf den Übergeordnet <span class="keyword"> Data Workbench-Server</span> zugegriffen werden kann, um Synchronisierungsprobleme zu vermeiden. In Data Workbench können Sie Informationen zu den Verarbeitungsservern <span class="keyword"> in Ihrem Cluster über das Menüelement "Verwandte Server"im</span> Server-Manager <span class="wintitle"></span>Ansicht geben. Weitere Informationen zum <span class="wintitle"> Server-Manager</span>finden Sie im Handbuch <i><span class="keyword"> Data Workbench</span><span class="wintitle"> Sensor</span></i>. </p> <p>Wenn Ihr Webserver Servernamen über DNS auflösen kann, können Sie die Serveradresse anhand des Namens angeben. Andernfalls müssen Sie die numerische IP-Adresse des Servers angeben. </p> <p>Beispiel: <span class="filepath"> ServerAddress 10.1.0.7</span> oder </p> <p> <span class="filepath"> ServerAddress vserver01.mycompany.com</span> </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL </td> 
   <td colname="col2"> <p>Ob <span class="wintitle"> Sensor</span> mit dem <span class="keyword"> Data Workbench-Server</span> über HTTP oder HTTPS kommuniziert. Bei HTTPS auf "Ein"oder bei HTTP auf "Aus" eingestellt. </p> <p>Beispiel: <span class="filepath"> SSL on</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ServerPort </td> 
   <td colname="col2"> <p>Der Anschluss, an dem der <span class="keyword"> Data Workbench-Server</span> auf Ereignis-Daten überwacht. </p> <p>Beispiel: <span class="filepath"> ServerPort 443</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> CertName </td> 
   <td colname="col2"> <p>Nur erforderlich, wenn der SSL-Parameter auf "on"gesetzt ist. </p> <p>Der allgemeine Name des <span class="keyword"> Data Workbench-Servers</span> , an den dieser <span class="wintitle"> Sensor</span> Ereignis-Daten sendet. </p> <p>Der von Ihnen angegebene Wert muss exakt mit dem allgemeinen Namen übereinstimmen, der im <span class="keyword"> Data Workbench-Server</span> -Lizenzzertifikat angezeigt wird. </p> <p>Beispiel: <span class="filepath"> CertName vserver01.mycompany.com</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> CertPath </td> 
   <td colname="col2"> <p>Nur erforderlich, wenn der SSL-Parameter auf "on"gesetzt ist. </p> <p>Der Ordner, in dem sich die Datei mit der Zertifizierungsstelle (<span class="filepath"> trust_ca_cert.pem</span>) befindet </p> <p>Beispiele: </p> <p> <span class="filepath"> CertPath /usr/local/visualsensor</span> </p> <p> <span class="filepath"> CertPath C:\VisualSensor</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> QueueFile </td> 
   <td colname="col2"> <p>Nicht erforderlich für <span class="wintitle"> Sensor</span> -Installationen auf Microsoft Windows 2000- oder 2003-Servercomputern, auf denen Internet Informationsdienst (IIS) Version 5.x oder 6.x ausgeführt wird. </p> <p>Der vollständig qualifizierte Name der Disk Queue-Datei. </p> <p>Obwohl Sie dieser Datei einen beliebigen Namen zuweisen können, trägt die Warteschlangendatei den Namen <span class="filepath"> VisualSensor.dat</span>. </p> <p>Bei <span class="wintitle"> Sensor</span> -Installationen unter Unix können Sie diese Datei an einer beliebigen Stelle platzieren. Unter Windows, auf dem ein Java-Webserver ausgeführt wird, müssen Sie diese Datei in demselben Ordner wie den Transmitter ablegen. Bei allen anderen Webservern sollte sich diese Datei im Ordner "/var/queue"befinden. </p> <p>Beispiel: <span class="filepath"> QueueFile /var/queue/VisualSensor.dat</span> </p> <p> <p>Hinweis:  Stellen Sie sicher, dass das Gerät, dem Sie diese Datei zuweisen, genügend freien Speicherplatz für eine Warteschlange in der benötigten Größe hat. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> QueueSize </td> 
   <td colname="col2"> <p>Eine Ganzzahl, die die Größe der Disk Queue-Datei in MB angibt. </p> <p>Bei <span class="wintitle"> Sensor</span> -Installationen unter Microsoft Windows wird die Warteschlangendatei im selben Verzeichnis wie der Transmitter erstellt und heißt <span class="filepath"> Diskq2000.log</span>. </p> <p>Im folgenden Beispiel wird die Warteschlangengröße auf 200 MB eingestellt: </p> <p>QueueSize 200 </p> <p>Im folgenden Beispiel wird die Warteschlangengröße auf 2 GB eingestellt: </p> <p>QueueSize 2000 </p> </td> 
  </tr> 
 </tbody> 
</table>

