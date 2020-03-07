---
description: Nachdem Sie die Insight-Programmdateien installiert haben, müssen Sie das von Adobe bereitgestellte digitale Zertifikat herunterladen und installieren.
title: Herunterladen und Installieren des digitalen Zertifikats
uuid: 93ab2222-a977-4279-9e1e-71038b1d1cfa
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Herunterladen und Installieren des digitalen Zertifikats{#downloading-and-installing-the-digital-certificate}

Nachdem Sie die Insight-Programmdateien installiert haben, müssen Sie das von Adobe bereitgestellte digitale Zertifikat herunterladen und installieren.

## Herunterladen und Installieren des digitalen Zertifikats {#topic-fed3b44e472c4e4ca6dd5852af14cdb9}

Nachdem Sie die Insight-Programmdateien installiert haben, müssen Sie das von Adobe bereitgestellte digitale Zertifikat herunterladen und installieren.

## Digitale Zertifikate {#concept-9eed01c8d95440cda6ce29d68e65098c}

Adobe verwendet digitale X.509-Zertifikate, um die Client- und Serverkomponenten, aus denen eine Implementierung besteht, zu identifizieren und zu authentifizieren.

<!--
c_undst_dgtl_crtf.xml
-->

Bei der Installation von Insight müssen Sie das digitale Zertifikat installieren, das eine benannte Person (z. B. Jane Smith) zur Verwendung der installierten Clientanwendung autorisiert.

>[!NOTE]
>
>Wenn Sie Insight auf einen anderen Computer oder einen anderen benannten Benutzer migrieren müssen, müssen Sie ein neues Zertifikat von Adobe abrufen. Wenden Sie sich dazu an den Adobe-Kundendienst.

Insight präsentiert dieses digitale Zertifikat, um Zugriff auf eine Serverkomponente zu erhalten. Ein Administrator einer Serverkomponente kann den Zugriff auf Serverressourcen auf der Grundlage der im Benutzerzertifikat angezeigten allgemeinen Werte für Namen oder organisatorische Einheiten einschränken.

Die mit Adobe-Anwendungen installierten digitalen X.509-Zertifikate ermöglichen es seinen Client- und Serverkomponenten auch, Informationen über Secure Sockets Layer (SSL) auszutauschen. SSL sichert Übertragungen über HTTP mithilfe eines Verschlüsselungssystems mit öffentlichem und privatem Schlüssel. Die Implementierung von SSL von Adobe unterstützt 1024-Bit-RSA-Schlüssel und verwendet einen 128-Bit-RC4-Verschlüsselungsalgorithmus.

Neben der Sicherheit fungiert das von Ihnen installierte digitale Zertifikat auch als Lizenzschlüssel, mit dem Sie Insight ausführen können. Um ordnungsgemäß funktionieren zu können, muss ein digitales Zertifikat Node-gesperrt und aktuell sein, andernfalls wird die Anwendung nicht gestartet.

## Freigegebene Zertifikate {#section-984aa8f2f5a1448cadc4afea978aedc9}

Ein knotengesperrtes Zertifikat ist ein digitales Zertifikat, das auf dem Computer registriert wurde, auf dem es installiert ist. Durch die Node-Sperrung wird ein Zertifikat dauerhaft mit einer bestimmten Node-ID (einem Wert, der einen bestimmten Computer eindeutig identifiziert) verknüpft. Um Ihr Zertifikat zu sperren, muss Ihr Computer über Internetzugriff auf den Adobe License Server oder einen Proxyserver verfügen, der Zugriff auf den License Server hat.

Wenn Sie eine Installation auf einem Computer durchführen, der nicht auf das Internet zugreifen kann, müssen Sie ein besonderes vorgesperrtes Zertifikat erwerben und installieren, wie unter [Verwenden digitaler Zertifikate auf Computern ohne Internetzugang](../../../home/c-install-insight/install-setup/c-dgtl-crtf.md#section-d3c060131d7f45cda27f68848b704fa1)beschrieben.

Wenn Sie die Installation auf einem Computer durchführen, der auf das Internet zugreifen kann, wird Ihr digitales Zertifikat automatisch beim ersten Starten von Insight gesperrt. Nach dem Sperren des Knotens kann das Zertifikat auf keinem anderen Computer verwendet werden. Wenn Sie Insight auf einen anderen Computer migrieren müssen, benötigen Sie ein neues, entsperrtes Zertifikat von Adobe.

## Aktuelle Zertifikate {#section-0816b031df3e415ab3f0205b720c723e}

Neben der Node-Sperre muss Ihr digitales Zertifikat aktuell sein. Um auf dem neuesten Stand zu bleiben, muss Ihr Zertifikat regelmäßig erneuert werden (in der Regel alle 30 Tage, kann jedoch je nach Ihrer Vereinbarung mit Adobe variieren). Wenn Ihr Computer über Internetzugang verfügt, ist der Erneuerungsvorgang vollkommen transparent. Insight stellt automatisch eine Verbindung zum Lizenzserver her und überprüft das Zertifikat bei Bedarf erneut. Wenn Ihr Computer keinen Internetzugang hat, müssen Sie ein aktualisiertes Zertifikat manuell installieren, wie im folgenden Abschnitt beschrieben.

## Digitale Zertifikate auf Computern ohne Internetzugang verwenden {#section-d3c060131d7f45cda27f68848b704fa1}

Wenn Sie eine Installation auf einem Computer durchführen, der nicht auf das Internet zugreifen kann, müssen Sie ein vordefiniertes Zertifikat für Ihre Installation von Insight anfordern. Ein vorab gesperrtes Zertifikat ist ein digitales Zertifikat, das von Adobe manuell mit der Node-ID des Computers gesperrt wird.

Um ein vorab gesperrtes Zertifikat anzufordern, müssen Sie die Node-ID und Ihre Zertifikatnummer an die Adobe-Kundenunterstützung senden. Um die Node-ID für Ihren Computer abzurufen, wenden Sie sich an den Adobe-Kundendienst, um das Adobe- [!DNL Node Identifier] Dienstprogramm anzufordern. Sie können die Node-ID auch aus der Warnung abrufen, die Insight ausgibt, wenn es versucht, eine Verbindung zum Lizenzserver herzustellen, und dies nicht. Wenn Sie das vorab gesperrte Zertifikat erhalten, installieren Sie es wie in den letzten beiden Schritten zum [Installieren digitaler Zertifikate](../../../home/c-install-insight/install-setup/c-dgtl-crtf.md#task-1dad1e1d86d04100a7bcf87f26303c38)beschrieben.

Wenn das Zertifikat erneut überprüft werden muss, müssen Sie ein neues, validiertes Zertifikat vom Lizenzserver herunterladen und auf Ihrem Computer neu installieren (es sei denn, Ihr Vertrag mit Adobe sieht etwas Anderes vor).

## Installieren digitaler Zertifikate {#task-1dad1e1d86d04100a7bcf87f26303c38}

<!--
t_install_dgtl_crtf.xml
-->

**So laden Sie das digitale Zertifikat herunter und installieren es**

1. Öffnen Sie Ihren Webbrowser zu [!DNL http:\\license.visualsciences.com].

   >[!NOTE]
   >
   >Ihr Browser fordert Sie möglicherweise auf, zu diesem Zeitpunkt ein digitales Zertifikat vorzulegen. Wenn dies der Fall ist, klicken Sie auf **[!UICONTROL Cancel]** , um das Dialogfeld zu schließen.

1. Geben Sie auf dem Anmeldebildschirm die Daten [!DNL Account Name] und [!DNL Password] die Daten ein, die Sie von Adobe erhalten haben, und klicken Sie dann auf **[!UICONTROL login]**.
1. Suchen Sie nach dem Zertifikat, das für Ihre Instanz von Insight ausgestellt wurde ( *Ihr Name*.pem), und klicken Sie auf das mit diesem Zertifikat verknüpfte ![](assets/btn_save_certificatedownload.PNG) Symbol.
1. Wenn Sie zum Speichern des Zertifikats aufgefordert werden, klicken Sie auf **[!UICONTROL Save]**.
1. Laden Sie die Datei in den [!DNL Certificates] Ordner herunter, in dem Sie Insight installiert haben.

   Dieser Ordner enthält eine Zertifikatdatei mit dem Namen [!DNL trust_ca_cert.pem]. Beide Zertifikatdateien müssen immer vorhanden sein, damit Insight funktioniert.

## Windows-Zertifikatspeicher {#concept-4acb13b7de9340ea8cde8ad84b93358d}

Mit dem Windows-Zertifikatspeicher können Sie das Zertifikat und den privaten Schlüssel des Clients im Windows-Zertifikatspeicher für die SSL-Kommunikation mit Servern speichern.

<!--
crypto-api.xml
-->

Der Windows-Zertifikatspeicher für den Client ist eine neue Funktion, mit der Sie das SSL-Kommunikationszertifikat und den privaten Schlüssel im Windows-Zertifikatspeicher und nicht in der `Insight/Certificates/<CertName>.pem` Datei speichern können. Die Verwendung des Windows-Zertifikatspeichers ist unter Umständen vorzuziehen, wenn Sie den Zertifikatspeicher für andere Anwendungen verwenden und die Zertifikatverwaltung an einer Stelle durchführen möchten oder wenn Benutzer die zusätzliche Windows-Prüfprotokollierung nutzen, die der Windows-Zertifikatspeicher bereitstellt.

>[!NOTE]
>
>Die Lizenzierung mit dem Lizenzserver wird weiterhin mit der vorhandenen `<Common Name>.pem` Datei verwaltet und das Zertifikat, das vom Zertifikatspeicher erhalten wurde, wird nur für die Kommunikation mit den von Ihnen angegebenen Servern verwendet.

## Voraussetzungen {#section-69b18600052145ff8e5299b7123e69c5}

1. Sie müssen Zugriff auf die [!DNL certmgr.msc] Datei haben, um ein Zertifikat und einen Schlüssel in den **persönlichen** Speicher importieren zu können. (Dies sollte für die meisten Windows-Benutzer standardmäßig wahr sein.)

1. Der Benutzer, der die Konfiguration durchführt, muss über eine Kopie des **OpenSSL** -Befehlszeilenwerkzeugs verfügen.
1. Server und Client müssen bereits für die Verwendung eines benutzerdefinierten SSL-Zertifikats konfiguriert sein. Anweisungen zum Speichern des Clientzertifikats im Windows-Zertifikatspeicher geben, anstatt es im **Zertifikatordner** zu speichern.

## Windows-Zertifikatspeicher konfigurieren {#section-3629802122e947d4b4f63e8b732cfe27}

Der Windows-Zertifikatspeicher für Clients ist wie folgt aktiviert:

**Schritt 1: Importieren Sie das SSL-Zertifikat und den privaten Schlüssel des Benutzers in den Windows-Zertifikatspeicher.**

Bei der [Verwendung von benutzerdefinierten Zertifikaten in Data Workbench](../../../home/c-install-insight/install-setup/c-dgtl-crtf.md#concept-ee6a9b5015f84a0ba64a11428b0a72dd) werden Sie angewiesen, das SSL-Zertifikat und den SSL-Schlüssel in den folgenden Ordner zu verschieben:

```
< 
<filepath>
  DWB Install folder 
</filepath>>\Certificates\
```

Der Name des Zertifikats lautet `<Common Name>.pem` z. B. Analytics Server 1.pem (nicht die Datei &quot;trust_ca_cert.pem&quot;).

Bevor das Zertifikat und der private Schlüssel importiert werden können, müssen sie aus konvertiert werden. [!DNL pem] in ein [!DNL .pfx] Format, z. B. [!DNL pkcs12.pfx] ).

1. Öffnen Sie eine Eingabeaufforderung oder ein Terminal und navigieren Sie zum Ordner:

   ```
   <CommonName>.pem c: cd \<filepath>DWB Install folder</filepath>>\Certificates
   ```

1. Führen Sie [!DNL openssl] die folgenden Argumente aus (mit dem tatsächlichen [!DNL .pem] Dateinamen):

   ```
   openssl pkcs12 -in "<Common Name>.pem" -export -out "<Common Name>.pfx"
   ```

   Wenn Sie dazu aufgefordert werden, drücken Sie die **Eingabetaste** , um die Eingabe eines Exportkennworts zu überspringen.

1. Führen Sie [!DNL certmgr.msc] die Ausführung über die Eingabeaufforderung, das Startmenü oder die Befehlszeile aus.
1. Öffnen Sie den **persönlichen** Zertifikatspeicher für den aktuellen Benutzer.

   ![](assets/6_5_crypto_api_0.png)

1. Klicken Sie mit der rechten Maustaste auf **Zertifikate** und dann auf **Alle Aufgaben** > **Importieren**.

   Vergewissern Sie sich, dass die Option **Aktueller Benutzer** ausgewählt ist, und klicken Sie auf **Weiter**.

   ![](assets/6_5_crypto_api_4.png)

1. Klicken Sie auf **Durchsuchen** und wählen Sie die zuvor erstellte `<CommonName>.pfx` Datei aus. Sie müssen das Dropdown-Feld für die Dateierweiterung von einem X.509-Zertifikat zu einem **persönlichen Informationsaustausch** oder zu **allen Dateien** ändern, um es anzuzeigen.

   Wählen Sie die Datei aus und klicken Sie auf **Öffnen** und dann auf **Weiter**.

1. Geben Sie kein Kennwort ein und stellen Sie sicher, dass nur die Optionen **Markieren Sie diesen Schlüssel als exportierbar** und **Einschließen aller erweiterten Eigenschaften** ausgewählt sind.

   ![](assets/6_5_crypto_api_3.png)

   Klicken Sie auf **Weiter**.

1. Vergewissern Sie sich, dass **Platzieren Sie alle Zertifikate im folgenden Store** ausgewählt ist und der Zertifikatspeicher **Persönlich** ist. (Wenn Sie ein fortgeschrittener Benutzer sind, können Sie zu diesem Zeitpunkt einen anderen Store auswählen, die Konfiguration jedoch später ändern.)

1. Klicken Sie auf **Weiter** und dann auf **Fertig stellen**. Es sollte ein Dialogfeld angezeigt werden, in dem Sie darüber informiert werden, dass der Import erfolgreich war, und das Zertifikat im Ordner &quot;Zertifikate&quot;des Stores angezeigt werden.

   >[!NOTE]
   >
   >Achten Sie besonders auf die **Felder &quot;Ausgestellt an** &quot;und &quot; **Ausgestellt von** &quot;. Sie werden diese im nächsten Schritt benötigen.

**Schritt 2: Bearbeiten Sie die Datei Insight.cfg.**

Die [!DNL Insight.cfg] Datei muss bearbeitet werden, damit Data Workbench die Windows-Zertifikatspeicherung nutzen kann. Jeder Servereintrag in dieser Datei muss einige zusätzliche Parameter enthalten. Wenn die Parameter weggelassen werden, verwendet die Workstation standardmäßig die vorhandene Zertifikatkonfiguration. Wenn die Parameter angegeben sind, aber falsche Werte haben, gibt die Workstation einen Fehlerstatus ein und Sie müssen in der Protokolldatei auf Fehlerinformationen verweisen.

1. Öffnen Sie die Datei **Insight.cfg** (die sich im Installationsordner von **Insight** befindet).

1. Blättern Sie nach unten zu dem Servereintrag, den Sie konfigurieren möchten. Wenn Sie den Windows-Zertifikatspeicher für jeden Server verwenden möchten, müssen Sie diese Änderungen an jedem Eintrag im Vektor von [!DNL serverInfo] Objekten vornehmen.
1. Fügen Sie diese Parameter ihrer [!DNL Insight.cfg] Datei hinzu. Sie können dies auf der Workstation oder manuell tun, indem Sie die folgenden Parameter zum [!DNL serverInfo] Objekt hinzufügen. (Achten Sie darauf, Leerzeichen anstelle von Tabulatorzeichen zu verwenden, und führen Sie in dieser Datei keine anderen Tippfehler oder Syntaxfehler durch. )

   ```
   SSL Use CryptoAPI = bool: true  
   SSL CryptoAPI Cert Name = string: <Common Name>  
   SSL CryptoAPI Cert Issuer Name = string: Visual Sciences,LLC  
   SSL CryptoAPI Cert Store Name = string: My 
   ```

   Der boolesche Wert aktiviert oder deaktiviert die Funktion. Der Zertifikatname stimmt mit **Issuer To** im Zertifikatmanager überein. Der Name des Zertifikatausstellers stimmt mit dem Namen des **Ausstellers überein**, und der **Store-Name** muss mit dem Namen des Zertifikatspeichers übereinstimmen.

   >[!NOTE]
   >
   >Der Name &quot;Persönlich&quot;im Zertifikatmanager (certmgr.msc) bezieht sich eigentlich auf den Zertifikatspeicher **My.** Wenn Sie daher Ihr SSL-Kommunikationszertifikat und Ihren SSL-Schlüssel (.PFX) wie empfohlen in den **persönlichen** Zertifikatspeicher importieren, müssen Sie die Zeichenfolge für den **SSL-CryptoAPI-Zertifikatsspeichernamen** auf &quot;My&quot;setzen. Die Festlegung dieses Parameters auf &quot;Persönlich&quot;funktioniert nicht. Dies ist eine Besonderheit des Windows-Zertifikatspeichers.

   Eine vollständige Liste der vordefinierten Systemspeicher finden Sie hier: [https://msdn.microsoft.com/en-us/library/windows/desktop/aa388136(v=vs.85).aspx](https://msdn.microsoft.com/en-us/library/windows/desktop/aa388136%28v=vs.85%29.aspx). Ihr System verfügt möglicherweise über zusätzliche Zertifikatspeicher. Wenn Sie einen anderen Store als &quot;Persönlich&quot; (z. B. **My**) verwenden möchten, müssen Sie den kanonischen Namen des Zertifikatspeichers abrufen und in der [!DNL Insight.cfg] Datei angeben. (Der Systemspeichername &quot;My&quot;wird in der Windows-Dokumentation inkonsistent als &quot;My&quot;und &quot;MY&quot;bezeichnet. Beim Parameter wird nicht zwischen Groß- und Kleinschreibung unterschieden.)

1. Nachdem Sie diese Parameter hinzugefügt und überprüft haben, ob die Werte mit der Liste im Windows-Zertifikatmanager übereinstimmen, speichern Sie die [!DNL Insight.cfg] Datei.

Sie können jetzt die Workstation starten (oder die Verbindung zum Server trennen/wieder herstellen). Data Workbench sollte Ihr Zertifikat und Ihren Schlüssel aus dem Zertifikatspeicher laden und eine normale Verbindung herstellen.

## Protokollausgabe {#section-a7ef8c9e90ef4bbabaa3cd51a2aca3ab}

Wenn ein Zertifikat nicht gefunden oder ungültig ist, wird diese Fehlermeldung in die [!DNL HTTP.log] Datei ausgegeben.

```
ERROR Fatal error: the cert could not be found!
```

>[!NOTE]
>
>Das L4-Protokollierungsframework kann aktiviert werden, indem Sie die [!DNL L4.cfg] Datei einrichten (siehe dazu Konfiguration durch Ihren Kundenbetreuer).

## Verwenden von benutzerdefinierten Zertifikaten in Data Workbench {#concept-ee6a9b5015f84a0ba64a11428b0a72dd}

Anweisungen zur Verwendung von benutzerdefinierten Zertifikaten.

<!--
using-custom-certificates-DWB.xml
-->

Ein Zertifikat, das entweder vom Data Workbench-Client oder vom Server verwendet wird, muss von einer vertrauenswürdigen Zertifizierungsstelle (Certificate Authority) signiert werden. Data Workbench-Kunden erhalten Zertifikate, die von der Visual Sciences-Zertifizierungsstelle signiert werden. Diese Zertifikate werden von der Data Workbench-Software als vertrauenswürdig eingestuft, da die [!DNL trust_ca_cert.pem] (zusammen mit der Insight-Software bereitgestellte und im **Zertifikatverzeichnis** von Servern und Clients gespeicherte) ein *Stammzertifikat* für die Visual Sciences-Zertifizierungsstelle enthält. Diese Zertifikate werden sowohl für die Lizenzierung der Software als auch für die Authentifizierung verwendet, wenn Clients und Server über SSL miteinander kommunizieren. Für die Lizenzierung können nur Zertifikate verwendet werden, die von der Visual Sciences CA ausgestellt wurden, andere Zertifikate dürfen jedoch für die Kommunikation und Authentifizierung verwendet werden. Zertifikate, die von anderen Zertifizierungsstellen als Visual Sciences ausgestellt wurden, werden nachstehend als *benutzerdefinierte Zertifikate bezeichnet.*

**Wichtiger Hinweis:** Bei Servern und Clients verwendet die Data Workbench-Software die Zertifikatdateien, die im **Zertifikatordner** des Clients oder des Servers installiert sind, oder die Zertifikate, die explizit in der Konfiguration angegeben sind. Sie können jedoch auch den Windows-Zertifikatspeicher für Clients verwenden.

Die folgenden Anweisungen beschreiben die Verfahren, die bei der Verwendung von benutzerdefinierten Zertifikaten für die Kommunikation zwischen Data Workbench-Clients und -Servern befolgt werden müssen. Nicht jedes Detail ist eine schwierige Anforderung, und es können unterschiedliche Prozessvarianten eingesetzt werden. Die folgenden Verfahren wurden jedoch getestet, um zu funktionieren.

## Einrichten von benutzerdefinierten Clientzertifikaten {#section-2083fd41973e451fa404e7a4ae4da591}

1. Fügen Sie das Zertifikat der ausstellenden Zertifizierungsstelle dem [!DNL trust_cert_ca.pem]hinzu, das im **Zertifikatordner** des Clients installiert ist, und dem jedes Servers in jedem Cluster, auf den mit diesem benutzerdefinierten Zertifikat zugegriffen werden soll.

1. Besorgen Sie sich ein benutzerdefiniertes Zertifikat für jeden Server im Cluster mit den folgenden Bedingungen:

   1. Zertifikat ist als [!DNL .pem] Zertifikat formatiert.
   1. Das Zertifikat enthält seinen Schlüssel und ist unverschlüsselt (d. h. es hat kein Kennwort und keinen Passwort).

      Ein Zertifikat enthält seinen Schlüssel mit einer der folgenden Zeilen:

      ```
      BEGIN PRIVATE KEY 
      BEGIN RSA PRIVATE KEY
      ```

      Eine Möglichkeit, den Passwortsatz aus einem [!DNL .pem] Zertifikat zu entfernen:

      ```
      openssl rsa  -in password-protected-cert.pem -out no-password-cert.pem 
      openssl x509 -in password-protected-cert.pem >> no-password.pem
      ```

   1. Das Zertifikat hat die KN, O, OU usw. , wie für diesen Client in der [!DNL Access Control.cfg] Serverdatei erforderlich.
   1. Das Zertifikat wurde mit einem *Zweck **** des *Clients* (oder sowohl *Server* **als auch** *Client*) ausgestellt.

      Um zu überprüfen, ob ein Zertifikat über einen Zweckcode des Servers und/oder Clients verfügt, können die folgenden Befehle verwendet werden:

      ```
      openssl verify -CAfile trust_ca_cert.pem -purpose sslserver -x509_strict custom_communications_cert.pem 
      openssl verify -CAfile trust_ca_cert.pem -purpose sslclient -x509_strict custom_communications_cert.pem
      ```

      Für Serverzertifikate sollten beide Befehle Folgendes ausgeben:

      ```
      custom_communications_cert.pem: OK
      ```

      Bei einem Client-Zertifikat ist nur der zweite Befehl erforderlich, um [!DNL OK]Ergebnisse zu liefern.

1. Platzieren Sie das Zertifikat im **Zertifikatverzeichnis** des Kunden.
1. Stellen Sie [!DNL Insight.cfg] unter &quot; *serverInfo* &quot;für jeden Cluster, der dieses Zertifikat verwenden soll, sicher, dass der Name des *benutzerdefinierten Client-Zertifikats* angegeben ist, z. B.:

   ```
   Servers = vector: 1 items 
     0 = serverInfo: 
       SSL Client Certificate = string:  
     <my_custom_client_cert.pem>
   ```

## Einrichten von benutzerdefinierten Serverzertifikaten {#setting-up-custom-server-certificates}

In diesem Abschnitt wird davon ausgegangen, dass Sie über einen Cluster verfügen, der mit von Visual Sciences ausgestellten Zertifikaten ausgeführt wird. Die Konfiguration folgt gängigen Verfahren (z. B. wird der Ordner &quot; *Komponenten für Verarbeitungsserver* &quot;auf dem Master mit den Ordnern &quot; *Komponenten* &quot;aller DPUs synchronisiert).

1. Fügen Sie das Zertifikat der ausstellenden Zertifizierungsstelle der Datei hinzu, die auf jedem Server im Cluster und jedem Client installiert ist, der mit diesem Cluster kommunizieren muss. [!DNL trust_cert_ca.pem]
1. Erstellen Sie für jeden Server im Cluster ein benutzerdefiniertes Zertifikat mit folgenden Anforderungen:

   1. Benutzerdefiniertes Zertifikat wird als [!DNL .pem] Zertifikat formatiert.
   1. Das Zertifikat enthält seinen Schlüssel und ist unverschlüsselt (d. h. es hat kein Kennwort und keinen Passwort).

      Ein Zertifikat enthält seinen Schlüssel, wenn es eine Zeile wie die folgende enthält:

      ```
      BEGIN PRIVATE KEY 
      BEGIN RSA PRIVATE KEY
      ```

      Eine Möglichkeit, den Passwortsatz aus einem [!DNL .pem] Zertifikat zu entfernen:

      ```
      openssl rsa  -in password-protected-cert.pem -out no-password-cert.pem 
      openssl x509 -in password-protected-cert.pem >> no-password.pem
      ```

   1. Das Zertifikat hat dieselbe KN wie das derzeit auf dem Server installierte [!DNL server_cert.pem] .
   1. Das Zertifikat wurde mit dem Zweck *Server* und *Client* ausgestellt.

      Um zu überprüfen, ob ein Zertifikat über einen Zweckcode des Servers und/oder Clients verfügt, können die folgenden Befehle verwendet werden:

      ```
      openssl verify -CAfile trust_ca_cert.pem -purpose sslserver -x509_strict custom_communications_cert.pem 
      openssl verify -CAfile trust_ca_cert.pem -purpose sslclient -x509_strict custom_communications_cert.pem
      ```

      Für Serverzertifikate sollten beide Befehle Folgendes ausgeben:

      ```
      custom_communications_cert.pem: OK
      ```

      Bei einem Client-Zertifikat ist nur der zweite Befehl erforderlich, um [!DNL OK]Ergebnisse zu liefern.

1. Installieren Sie das benutzerdefinierte Zertifikat jedes Servers im **Zertifikatordner** des Servers als [!DNL custom_communications_cert.pem].

1. Fügen Sie mithilfe eines Texteditors der Datei &quot; **Communications.cfg** &quot;in den Ordnern &quot; *Komponenten* &quot;und &quot; *Komponenten für Verarbeitungsserver* &quot;die folgende Zeile direkt unter der ersten Zeile ( [!DNL component = CommServer]) hinzu:

   ```
   Certificate = string: Certificates\\custom_communications_cert.pem
   ```

1. Starten Sie alle Server neu.

**Warnung wegen Zertifikatfehlers**

Wenn der Insight-Server oder -Client ein **Lizenzzertifikat** im Verzeichnis &quot; **Zertifikate** &quot;sucht, versucht er, alle Zertifikate (außer [!DNL trust_ca_cert.pem]) mit einer hartkodierten Kopie des Insight CA-Zertifikats zu validieren, was bei einem benutzerdefinierten Zertifikat im Ordner fehlschlägt. Der Server gibt folgende Warnung aus:

```
Certificate failed to verify. Error 20 at 0 depth. Desc: unable to get local issuer certificate. Cert details:
```

Diese Warnung kann unbedenklich ignoriert werden.

## Zeichenfolgenverschlüsselung {#concept-35da0b53650a4d7e82b240ad27f6d45a}

Verschlüsseln Sie Kennwörter und andere Zeichenfolgen bei der Kommunikation zwischen Client und Server.

<!--
string_encryption.xml
-->

Bei der Kommunikation zwischen dem Data Workbench-Client (Workstation) und dem Server können Sie einen Value-Parameter (z. B. ein Kennwort) mit dem Typ *EncryptedString* speichern. Dadurch wird der Parameter ausgeblendet und die Zeichenfolge wird im *Windows Credential Store* auf dem Server mit dem entsprechenden Schlüssel zurückgegeben. Hierbei werden in erster Linie in Exporten verwendete Anmeldeinformationen gespeichert, können aber zum Verschlüsseln von Parametern verwendet werden.

* Unter Server\**EncryptStrings** wurde ein neuer Ordner hinzugefügt.

   Hier legen Sie die Konfigurationsdatei auf Verschlüsseln von Zeichenfolgen fest.

* Eine neue Konfigurationsdatei wurde unter Server\Component\**EncryptedStrings.cfg** hinzugefügt.

   ```
   component = EncryptionComponent: 
     Path = Path: EncryptStrings\\*.cfg
   ```

   Diese Datei fragt den Ordner *Server*\*EncryptStrings* nach Verschlüsselungskonfigurationsdateien ab.

**So verschlüsseln Sie eine Zeichenfolge**:

1. Erstellen Sie eine **EncryptedStrings.cfg** -Konfigurationsdatei für eine Zeichenfolge mit den folgenden Feldern:

   ```
   Names = vector: 1 items 
    0 = NameEncryptValuePair: 
     EncryptValue = EncryptedString: // left empty as input then output will be filled by server 
     Name = string: // Name for identifier  
     Value = string: // Value to be encrypted
   ```

   * *Wert* : Dieses Feld enthält die Nur-Text-Zeichenfolge, die verschlüsselt werden muss.

      Dies ist nur serverseitige Verschlüsselung. Die *Einstellung &quot;Wert* &quot;wird nur auf dem Servercomputer verschlüsselt.

   * *Name* - Dieses Feld enthält einen Wert, der die verschlüsselte Zeichenfolge identifiziert.
   * *EncryptValue* - Dieses Feld wird in der Eingabekonfigurationsdatei leer gelassen. Der verschlüsselte Wert wird in diesem Feld zurückgegeben.
   Sie können mehrere **NameEncryptValuePair** -Werte für verschiedene Felder zur Verschlüsselung hinzufügen.

   >[!NOTE]
   >
   >Alle leeren Wertefelder werden entfernt.

1. Speichern Sie die Datei **EncryptedStrings.cfg** im Ordner Server\**EncryptStrings**.

**Ausgabedatei**

Eine Ausgabedatei wird mit demselben Namen wie die Eingabedatei mit einem &lt;*Dateiname*> generiert.*verschlüsselte* Erweiterung. Wenn die Eingabedatei beispielsweise den Namen *sample.cfg* hat, erhält die Ausgabedatei den Namen *sample.cfg.encrypted*.
