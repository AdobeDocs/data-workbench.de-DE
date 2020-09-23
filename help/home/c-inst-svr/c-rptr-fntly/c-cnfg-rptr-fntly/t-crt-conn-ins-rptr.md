---
description: Wenn Netzwerk-Firewalls den Zugriff auf den Repeater-Server nicht von Insight-Computern verhindern, können Sie eine Verbindung zwischen dem Repeater-Server und Insight erstellen, damit Sie den Repeater-Server mit Insight verwalten können.
solution: Analytics
title: Erstellen einer Verbindung zwischen Insight und Repeater
uuid: dccce83a-8708-4763-a19a-64d905a9f624
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '341'
ht-degree: 4%

---


# Erstellen einer Verbindung zwischen Insight und Repeater{#creating-a-connection-between-insight-and-repeater}

Wenn Netzwerk-Firewalls den Zugriff auf den Repeater-Server nicht von Insight-Computern verhindern, können Sie eine Verbindung zwischen dem Repeater-Server und Insight erstellen, damit Sie den Repeater-Server mit Insight verwalten können.

**So erstellen Sie eine Verbindung zwischen[!DNL Insight]und dem Repeater-Server**

1. Klicken Sie [!DNL Insight]auf der [!DNL Admin] Registerkarte auf die **[!UICONTROL Configure Connections to Servers]** Miniaturansicht, um den Arbeitsbereich &quot;Verbindungen zu Servern konfigurieren&quot;zu öffnen.
1. Klicken Sie im [!DNL Insight.cfg] Fenster mit der rechten Maustaste **[!UICONTROL Servers]** und klicken Sie auf **[!UICONTROL Add new]** > **[!UICONTROL Server]**.
1. Führen Sie für den neuen Server die folgenden Parameter aus:

<table id="table_DD79587255134B5A888A0F57CF10E5B0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Für diesen Parameter... </th> 
   <th colname="col2" class="entry"> Legen Sie... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Name </td> 
   <td colname="col2">(Optional) Der Name, mit dem dieser <span class="keyword"> Insight</span> den Repeater-Server in seiner Benutzeroberfläche darstellen soll. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Adresse </td> 
   <td colname="col2"> <p>Der Hostname oder die numerische IP-Adresse des Repeater-Servers. </p> <p>Beispiel: <span class="filepath"> Repeater.mycompany.com</span> oder 192.168.1.90 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL-Client-Zertifikat </td> 
   <td colname="col2"> <p>Optional, es sei denn, Sie verfügen über mehr als ein Zertifikat. Der Name der Datei, die das digitale Zertifikat für diese Kopie von <span class="keyword"> Insight</span>enthält. (Dies ist die Datei, die Sie bei der Installation von <span class="keyword"> Insight</span>heruntergeladen haben.) </p> <p>Beispiel: <span class="filepath"> Samantha Smith.pem</span></p> <p>Wenn Sie diesen Parameter leer lassen, verwendet <span class="keyword"> Insight</span> das vorhandene Zertifikat. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>SSL-Server </p> <p>Allgemeiner Name </p> </td> 
   <td colname="col2">Der allgemeine Name, der dem Repeater-Server zugewiesen ist. Dieser Name muss mit dem allgemeinen Namen übereinstimmen, der dem Repeater-Server in seinem Lizenzzertifikat zugewiesen wurde. Wenn Sie Zugriff auf die Zertifikatdatei des Repeaters haben (<span class="filepath"> Certificates\server_cert.pem</span>), können Sie den gemeinsamen Namen finden, indem Sie die Datei mit einem Texteditor wie Notepad öffnen. Der gebräuchliche Name wird im KN-Feld der Bescheinigung angegeben. </td> 
  </tr> 
 </tbody> 
</table>

1. Speichern Sie die Datei, indem Sie mit der rechten Maustaste **[!UICONTROL (modified)]** am oberen Rand des Fensters klicken und auf **[!UICONTROL Save]**. [!DNL Insight] versucht, eine Verbindung mit dem Repeater-Server herzustellen, indem Sie die angegebenen Einstellungen verwenden. Wenn eine Verbindung hergestellt ist, wird auf der [!DNL Servers Manager] Oberfläche ein grünes Serversymbol angezeigt. Wenn keine Verbindung hergestellt werden kann, wird ein rotes Symbol angezeigt.

   Weitere Informationen zur [!DNL Servers Manager] Oberfläche finden Sie im * [!DNL Insight] Benutzerhandbuch*.

