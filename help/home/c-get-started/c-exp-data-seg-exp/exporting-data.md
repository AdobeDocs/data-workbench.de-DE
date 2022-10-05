---
description: Sie können jetzt CSV-, TSV-, Segmentexport- und Segmentexport mit Header mithilfe der FTP- und SFTP-Protokolle verwenden, um Segmentdateien vom Client (Workstation) zum Server zu exportieren.
title: Segmentexport mittels SFTP/FTP-Bereitstellung
uuid: 4d654368-cbf7-4e7f-8ab9-82f4e0261ac6
exl-id: 0f1dc0a1-f376-47fb-887c-612a654ed0f0
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '543'
ht-degree: 4%

---

# Segmentexport mittels SFTP/FTP-Bereitstellung{#export-a-segment-using-s-ftp-delivery}

{{eol}}

Sie können jetzt CSV-, TSV-, Segmentexport- und Segmentexport mit Header mithilfe der FTP- und SFTP-Protokolle verwenden, um Segmentdateien vom Client (Workstation) zum Server zu exportieren.

**S/FTP-Export-Konfigurationsdateien einrichten**

Um die Exportkonfiguration festzulegen, wurden zwei neue Exportkonfigurationsdateien hinzugefügt, um eine FTP- oder SFTP-Verbindung einzurichten, sodass die Serverdetails aus der *FTPServerInfo.cfg* -Datei und die Anmeldeinformationen werden aus *FTPUserCredentials* Ordner (entspricht dem in den Befehlsargumenten angegebenen Servernamen).

* Legen Sie die **FTPServerInfo.cfg** -Datei.

   Geben Sie die FTP-Serverinformationen ein und legen Sie die zulässigen Verbindungsversuche für die Workstation fest. Bearbeiten Sie von der Workstation oder dem Server unter  [!DNL Server\Addresses\Export\] **[!DNL FTPServerInfo.cfg]**-Datei.

   ```
   FTP Servers = vector: 1 items 
     0 = ftpServerInfo:  
       Address = string:  
       Name = string:  
       Port = int: 21 
   Connect Retries = vector: 1 items 
     0 = connectServerRetries:  
       Retries = int: 0 
       Server Name = string:
   ```

* Legen Sie die **FTPUserCredentials.cfg** -Datei.

   Geben Sie Benutzeranmeldeinformationen ein, um mithilfe der  [!DNL Server\Admin\Export\] **[!DNL FTPUserCredentials.cfg]**-Datei. Diese Datei enthält Benutzeranmeldeinformationen, die zum Herstellen einer Verbindung zu Servern erforderlich sind. Sie kann nur vom Server und nicht von der Workstation (Client) aus bearbeitet werden.

   ```
   FTP User Credentials = vector: 1 items 
     0 = ftpUserCredInfo: 
       User Name = string:  
       User Password = EncryptedString:  
       Server Name = string:  
       Public Key Path = string:  
       Private Key Path = string:  
       Passphrase = EncryptedString:
   ```

   >[!NOTE]
   >
   >Stellen Sie sicher, dass die SSH-Schlüssel, die Sie für die Authentifizierung generieren, im gleichen Format wie die Schlüssel sind, die beim Verwenden des SSH-Schlüsselbefehls generiert werden.
   >
   >Beispiel für die Generierung von SSH-Schlüsseln mit Keygen:
   >
   >
   ```
   >ssh-keygen -t rsa -b 4096 -C "<label>"
   >```

   Es gibt sechs Parameter in der **FTPUserCredentials.cfg** Datei erforderlich für verschiedene FTP- oder SFTP-Übertragungen.

   1. *Benutzername*
   1. *Benutzerkennwort*
   1. *Servername*
   1. *Public Key Path*
   1. *Pfad für privaten Schlüssel*
   1. *Passphrase*

   <table id="table_4EB416DC770D4D1AA4FAD9676C0D680C"> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> Protocol </th> 
      <th colname="col2" class="entry"> Parameter </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>FTP </p> </td> 
      <td colname="col2"> <p>Legen Sie die Parameter 1, 2, 3 fest. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>SFTP mit Kennwortauthentifizierung </p> </td> 
      <td colname="col2"> <p>Legen Sie die Parameter 1, 2 und 3 fest, wenn die Übertragung die Kennwortauthentifizierung verwendet (-p in den Befehlsargumenten). </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>SFTP mit Schlüsselauthentifizierung </p> </td> 
      <td colname="col2"> <p>Legen Sie die Parameter 1, 2, 3, 4, 5, 6 fest, wenn die Übertragung die Schlüsselauthentifizierung verwendet (-k in den Befehlsargumenten). </p> </td> 
      </tr> 
    </tbody> 
    </table>

**Festlegen der FTP- und SFTP-Exportbefehle**

1. Öffnen Sie eine Exporttabelle.

   Klicken Sie in der Workstation mit der rechten Maustaste auf einen *Detailtabelle* und wählen Sie einen der Exporttypen - CSV , TSV, Segmentexport oder Segmentexport mit Header. Oder öffnen Sie die [!DNL .export] Datei an einer Eingabeaufforderung und Bearbeitung (siehe [Konfigurieren von Segmenten für den Export](../../../home/c-get-started/c-exp-data-seg-exp/t-config-sgts-expt.md#task-8857f221fa66463990ec9b60db6db372)).

1. Im *Befehl* festlegen, dass sie auf die ausführbare Exportdatei verweist:

   ```
   ExportIntegration.exe
   ```

1. Legen Sie die *Befehlsargumente* wie unten für das erforderliche Protokoll und die Authentifizierung gezeigt:

   **FTP**

   ```
   <Command Arguments> set to  
   <ftp "%file%" ServerName ServerDestinationPath>
   ```

   ![](assets/FTP_Command_arguments.png)

   **SFTP** (bei Verwendung des Kennworts für die Authentifizierung)

   ```
   <Command Arguments> set to  
   <sftp "%file%" ServerName ServerDestinationPath -p>
   ```

   **SFTP** (bei Verwendung von Schlüsseln zur Authentifizierung)

   ```
   <Command Arguments> set to  
   <sftp "%file%" ServerName ServerDestinationPath -k>
   ```

   ![](assets/SFTP_command_arguments.png)

Alle Befehlsargumente sind obligatorisch und müssen wie unten gezeigt eingegeben werden.

## S/FTP-Export mithilfe privater/öffentlicher Schlüssel {#section-0534424d79a54a47b82594cfa7b3c17f}

Um den FTP- und SFTP-Export mithilfe privater und öffentlicher Schlüssel zu implementieren, platzieren Sie die Konfigurationsdateien in diese Ordner:

* Ort **FTPServerInfo.cfg** im [!DNL Server/Addresses/Export/] Ordner.
* Ort **FTPUserCredentials.cfg** im [!DNL Server/Admin/Export/] Ordner.

Sechs Parameter sind im **FTPServerInfo.cfg** Datei:

1. *Benutzername*
1. *Benutzerkennwort*
1. *Servername*
1. *Public Key Path*
1. *Pfad für privaten Schlüssel —* Platzieren Sie den Pfad des privaten Schlüssels in der Konfigurationsdatei ohne die Erweiterung, z. B.:

[!DNL Private Key Path = string: E:\\Server\\campaign\\campaignprivatekey]

1. *Passphrase*

FTP verwendet die Parameter 1, 2 und 3.

SFTP verwendet die Parameter 1, 2 und 3, wenn die Übertragung die Kennwortauthentifizierung verwendet.

SFTP verwendet alle sechs Parameter, wenn die Übertragung mithilfe der Schlüsselauthentifizierung erfolgt. Wenn Sie beispielsweise Schlüssel für die Authentifizierung verwenden:

[!DNL 'Command Arguments' = sftp "%file%" ServerName ServerDestinationPath -k]

Die Konfigurationsdateien müssen sich am richtigen Speicherort befinden.

>[!NOTE]
>
>Die öffentlichen Schlüssel müssen auf eine **.pem** und nicht an einen Ordnerspeicherort. Sie können Schlüssel mithilfe einer SSH-Schlüsselgenerierungsfunktion aus Anwendungen wie Cygwin erstellen. (Putty generiert Schlüssel im .ppk-Format, das nicht unterstützt wird.)
