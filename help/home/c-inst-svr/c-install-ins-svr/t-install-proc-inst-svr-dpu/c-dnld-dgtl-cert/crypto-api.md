---
description: Mit dem Windows-Zertifikatspeicher können Sie das Zertifikat und den privaten Schlüssel des Clients im Windows-Zertifikatspeicher für die SSL-Kommunikation mit Servern speichern.
title: Windows-Zertifikatspeicher
uuid: a8021295-375a-460b-8686-acf3bc43cd17
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Windows-Zertifikatspeicher{#windows-certificate-store}

Mit dem Windows-Zertifikatspeicher können Sie das Zertifikat und den privaten Schlüssel des Clients im Windows-Zertifikatspeicher für die SSL-Kommunikation mit Servern speichern.

Der Windows-Zertifikatspeicher für den Client ist eine neue Funktion, mit der Sie das SSL-Kommunikationszertifikat und den privaten Schlüssel im Windows-Zertifikatspeicher und nicht in der `Insight/Certificates/<CertName>.pem` Datei speichern können. Die Verwendung des Windows-Zertifikatspeichers ist unter Umständen vorzuziehen, wenn Sie den Zertifikatspeicher für andere Anwendungen verwenden und die Zertifikatverwaltung an einer Stelle durchführen möchten oder wenn Benutzer die zusätzliche Windows-Prüfprotokollierung nutzen, die der Windows-Zertifikatspeicher bereitstellt.

>[!NOTE]
>
>Die Lizenzierung mit dem Lizenzserver wird weiterhin mit der vorhandenen `<Common Name>.pem` Datei verwaltet und das Zertifikat, das vom Zertifikatspeicher erhalten wurde, wird nur für die Kommunikation mit den von Ihnen angegebenen Servern verwendet.

## Voraussetzungen {#section-69b18600052145ff8e5299b7123e69c5}

1. Sie müssen Zugriff auf die [!DNL certmgr.msc] Datei haben, um ein Zertifikat und einen Schlüssel in den **persönlichen** Speicher importieren zu können. (Dies sollte für die meisten Windows-Benutzer standardmäßig wahr sein.)

1. Der Benutzer, der die Konfiguration durchführt, muss über eine Kopie des **OpenSSL** -Befehlszeilenwerkzeugs verfügen.
1. Server und Client müssen bereits für die Verwendung eines benutzerdefinierten SSL-Zertifikats konfiguriert sein, wie unter [Verwenden von benutzerdefinierten Zertifikaten](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/using-custom-certificates-dwb.md#concept-ee6a9b5015f84a0ba64a11428b0a72dd)beschrieben. Anweisungen zum Speichern des Clientzertifikats im Windows-Zertifikatspeicher geben, anstatt es im **Zertifikatordner** zu speichern.

## Windows-Zertifikatspeicher konfigurieren {#section-3629802122e947d4b4f63e8b732cfe27}

Der Windows-Zertifikatspeicher für Clients ist wie folgt aktiviert:

**Schritt 1: Importieren Sie das SSL-Zertifikat und den privaten Schlüssel des Benutzers in den Windows-Zertifikatspeicher.**

Bei der [Verwendung von benutzerdefinierten Zertifikaten](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/using-custom-certificates-dwb.md#concept-ee6a9b5015f84a0ba64a11428b0a72dd) werden Sie angewiesen, das SSL-Zertifikat und den SSL-Schlüssel in den folgenden Ordner zu setzen:

```
< 
<filepath>
  DWB Install folder 
</filepath>>\Certificates\
```

Der Name des Zertifikats lautet `<Common Name>.pem` (z. B. [!DNL Analytics Server 1.pem](nicht die [!DNL trust_ca_cert.pem] Datei).

Bevor das Zertifikat und der private Schlüssel importiert werden können, müssen sie aus konvertiert werden. [!DNL pem] in ein [!DNL .pfx] Format, z. B. [!DNL pkcs12.pfx] ).

1. Öffnen Sie eine Eingabeaufforderung oder ein Terminal und navigieren Sie zum Ordner:

   ```
   <CommonName>.pem c: cd \<DWB Install folder \Certificates
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
