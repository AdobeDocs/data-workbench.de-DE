---
description: Sie können jetzt CSV-, TSV-, Segmentexport- und Segmentexport mit Header mithilfe der FTP- und SFTP-Protokolle verwenden, um Segmentdateien vom Client (Workstation) auf den Server zu exportieren.
title: Exportieren eines Segments mit S/FTP-Bereitstellung
uuid: 4d654368-cbf7-4e7f-8ab9-82f4e0261ac6
translation-type: tm+mt
source-git-commit: 72761a57e4bb9f230581b2cd37bff04ba7be8e37

---


# Exportieren eines Segments mit S/FTP-Bereitstellung{#export-a-segment-using-s-ftp-delivery}

Sie können jetzt CSV-, TSV-, Segmentexport- und Segmentexport mit Header mithilfe der FTP- und SFTP-Protokolle verwenden, um Segmentdateien vom Client (Workstation) auf den Server zu exportieren.

**S/FTP-Exportkonfigurationsdateien einrichten**

Um die Exportkonfiguration festzulegen, wurden zwei neue Exportkonfigurationsdateien hinzugefügt, um eine FTP- oder SFTP-Verbindung einzurichten, sodass die Serverdetails aus der Datei *FTPServerInfo.cfg* ausgewählt werden können und die Anmeldeinformationen aus dem *Ordner FTPUserCredentials* ausgewählt werden (entsprechend dem in den Befehlsargumenten angegebenen Servernamen).

* Legen Sie die Datei **FTPServerInfo.cfg** fest.

   Geben Sie die FTP-Serverinformationen ein und legen Sie die zulässigen Verbindungsversuche auf der Workstation fest. Bearbeiten Sie die Datei von der Workstation oder vom Server unter [!DNL Server\Addresses\Export\] **[!DNL FTPServerInfo.cfg]** .

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

* Legen Sie die Datei **FTPUserCredentials.cfg** fest.

   Geben Sie mithilfe der Datei [!DNL Server\Admin\Export\] Benutzeranmeldeinformationen ein, um eine Verbindung zu Servern herzustellen **[!DNL FTPUserCredentials.cfg]** . Diese Datei enthält Benutzeranmeldeinformationen, die für die Verbindung mit Servern erforderlich sind. Sie können nur vom Server und nicht von der Workstation (Client) bearbeitet werden.

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
   >Stellen Sie sicher, dass die von Ihnen für die Authentifizierung generierten SSH-Schlüssel das gleiche Format haben wie die Schlüssel, die bei Verwendung des Befehls SSH-Schlüsselwort generiert werden.
   >
   >Beispiel zum Generieren von SSH-Schlüsseln mit Keygen:
   >
   >```
   >ssh-keygen -t rsa -b 4096 -C "<label>"
   >```

   Die Datei **FTPUserCredentials.cfg** enthält sechs Parameter, die für verschiedene FTP- oder SFTP-Übertragungen erforderlich sind.

   1. *Benutzername*
   1. *Benutzerkennwort*
   1. *Servername*
   1. *Öffentlicher Schlüsselpfad*
   1. *Private Schlüsselpfade*
   1. *Passphrase*
   <table id="table_4EB416DC770D4D1AA4FAD9676C0D680C"> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> Protokoll </th> 
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
      <td colname="col2"> <p>Legen Sie die Parameter 1, 2, 3, 4, 5 und 6 fest, wenn die Übertragung die Schlüsselauthentifizierung (-k in den Befehlsargumenten) verwendet. </p> </td> 
      </tr> 
    </tbody> 
    </table>

**Festlegen der FTP- und SFTP-Exportbefehle**

1. Öffnen Sie eine Exporttabelle.

   Klicken Sie auf der Workstation mit der rechten Maustaste auf eine *Detailtabelle* und wählen Sie einen der Exporttypen aus: CSV-, TSV-, Segmentexport- oder Segmentexport mit Kopfzeile. Oder öffnen Sie die [!DNL .export] Datei an einer Eingabeaufforderung und bearbeiten Sie sie (siehe [Konfigurieren von Segmenten für den Export](../../../home/c-get-started/c-exp-data-seg-exp/t-config-sgts-expt.md#task-8857f221fa66463990ec9b60db6db372)).

1. Legen Sie im Feld &quot; *Befehl* &quot;fest, dass es auf die ausführbare Datei &quot;export&quot;verweist:

   ```
   ExportIntegration.exe
   ```

1. Legen Sie die *Felder &quot;Befehlsargumente* &quot;wie unten für das erforderliche Protokoll und die erforderliche Authentifizierung fest:

   **FTP**

   ```
   <Command Arguments> set to  
   <ftp "%file%" ServerName ServerDestinationPath>
   ```

   ![](assets/FTP_Command_arguments.png)

   **SFTP** (bei Verwendung des Kennworts zur Authentifizierung)

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

Alle Befehlsargumente sind obligatorisch und müssen wie gezeigt eingegeben werden.

## S/FTP-Export mit privaten/öffentlichen Schlüsseln {#section-0534424d79a54a47b82594cfa7b3c17f}

Um den FTP- und den SFTP-Export mit privaten und öffentlichen Schlüsseln zu implementieren, platzieren Sie die Konfigurationsdateien in den folgenden Ordnern:

* Platzieren Sie **FTPServerInfo.cfg** im [!DNL Server/Addresses/Export/] Ordner.
* Platzieren Sie **FTPUserCredentials.cfg** im [!DNL Server/Admin/Export/] Ordner.

Sechs Parameter sind in der Datei **&quot;FTPServerInfo.cfg** &quot;enthalten:

1. *Benutzername*
1. *Benutzerkennwort*
1. *Servername*
1. *Öffentlicher Schlüsselpfad*
1. *Pfad des privaten Schlüssels —* Platzieren Sie den Pfad des privaten Schlüssels in der Konfigurationsdatei ohne die Erweiterung, z. B.:

[!DNL Private Key Path = string: E:\\Server\\campaign\\campaignprivatekey]

1. *Passphrase*

FTP verwendet die Parameter 1, 2 und 3.

SFTP verwendet die Parameter 1, 2 und 3, wenn die Übertragung die Kennwortauthentifizierung verwendet.

SFTP verwendet alle sechs Parameter, wenn die Übertragung mithilfe der Schlüsselauthentifizierung erfolgt. Wenn Sie beispielsweise Schlüssel zur Authentifizierung verwenden:

[!DNL 'Command Arguments' = sftp "%file%" ServerName ServerDestinationPath -k]

Die Konfigurationsdateien müssen sich am richtigen Speicherort befinden.

>[!NOTE]
>
>Die öffentlichen Schlüssel müssen auf eine **.pem** -Datei und nicht auf einen Ordnerspeicherort verweisen. Sie können Schlüssel mithilfe einer SSH-Schlüsselgenerierungsfunktion aus Anwendungen wie Cygwin erstellen. (Putty generiert Schlüssel im PPK-Format, das nicht unterstützt wird.)
