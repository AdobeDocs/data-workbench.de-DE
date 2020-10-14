---
description: Mit dem Windows-Zertifikatspeicher können Sie das Zertifikat und den privaten Schlüssel des Clients im Windows-Zertifikatspeicher für die SSL-Kommunikation mit Servern speichern.
title: Windows-Zertifikatspeicher
uuid: a8021295-375a-460b-8686-acf3bc43cd17
translation-type: ht
source-git-commit: a766b64ef809e2223fed869d8d63b75f270a3d39
workflow-type: ht
source-wordcount: '1000'
ht-degree: 100%

---


# Windows-Zertifikatspeicher {#windows-certificate-store}

Mit dem Windows-Zertifikatspeicher können Sie das Zertifikat und den privaten Schlüssel des Clients im Windows-Zertifikatspeicher für die SSL-Kommunikation mit Servern speichern.

Der Windows-Zertifikatspeicher für den Client ist eine neue Funktion, mit der Sie das SSL-Kommunikationszertifikat und den privaten Schlüssel im Windows-Zertifikatspeicher und nicht in der `Insight/Certificates/<CertName>.pem`-Datei speichern können. Die Verwendung des Windows-Zertifikatspeichers ist unter Umständen vorzuziehen, wenn Sie den Zertifikatspeicher für andere Anwendungen verwenden und die Zertifikatverwaltung an einer Stelle durchführen möchten, oder wenn Benutzer die zusätzliche Windows-Prüfprotokollierung nutzen, die der Windows-Zertifikatspeicher bereitstellt.

>[!NOTE]
>
>Die Lizenzierung mit dem Lizenzserver wird weiterhin mit der vorhandenen `<Common Name>.pem`-Datei verwaltet, und das Zertifikat, das vom Zertifikatspeicher bereitgestellt wurde, wird nur für die Kommunikation mit den von Ihnen angegebenen Servern verwendet.

## Voraussetzungen {#section-69b18600052145ff8e5299b7123e69c5}

1. Sie müssen Zugriff auf die [!DNL certmgr.msc]-Datei haben, damit Sie ein Zertifikat und einen Schlüssel in den **persönlichen** Speicher importieren können. (Dies sollte für die meisten Windows-Benutzer standardmäßig der Fall sein.)

1. Der Benutzer, der die Konfiguration durchführt, muss über eine Kopie des **OpenSSL** -Befehlszeilenwerkzeugs verfügen.
1. Server und Client müssen bereits für die Verwendung eines benutzerdefinierten SSL-Zertifikats konfiguriert sein, wie unter [Verwenden benutzerdefinierter Zertifikate](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/using-custom-certificates-dwb.md#concept-ee6a9b5015f84a0ba64a11428b0a72dd) beschrieben. Dieser Abschnitt enthält Anweisungen zum Speichern des Client-Zertifikats im Windows-Zertifikatspeicher, anstatt es im Verzeichnis **Zertifikate** zu speichern.

## Konfigurieren des Windows-Zertifikatspeichers {#section-3629802122e947d4b4f63e8b732cfe27}

Der Windows-Zertifikatspeicher für Clients wird wie folgt aktiviert:

**Schritt 1: Importieren Sie das SSL-Zertifikat und den privaten Schlüssel des Benutzers in den Windows-Zertifikatspeicher.**

Unter [Verwenden benutzerdefinierter Zertifikate](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/using-custom-certificates-dwb.md#concept-ee6a9b5015f84a0ba64a11428b0a72dd) werden Sie angewiesen, das SSL-Zertifikat und den SSL-Schlüssel im folgenden Ordner abzulegen:

```
< 
<filepath>
  DWB Install folder 
</filepath>>\Certificates\
```

Der Name des Zertifikats lautet `<Common Name>.pem` (z. B. [!DNL Analytics Server 1.pem] (nicht die [!DNL trust_ca_cert.pem]-Datei).

Bevor das Zertifikat und der private Schlüssel importiert werden können, müssen sie aus dem . [!DNL pem]-Format in ein [!DNL .pfx]-Format konvertiert werden, z. B. [!DNL pkcs12.pfx]).

1. Öffnen Sie eine Eingabeaufforderung oder ein Terminal und navigieren Sie zum folgenden Verzeichnis:

   ```
   <CommonName>.pem c: cd \<DWB Install folder \Certificates
   ```

1. Führen Sie [!DNL openssl] mit den folgenden Argumenten aus (mit dem tatsächlichen [!DNL .pem]-Dateinamen):

   ```
   openssl pkcs12 -in "<Common Name>.pem" -export -out "<Common Name>.pfx"
   ```

   Wenn die entsprechende Aufforderung angezeigt wird, drücken Sie die **Eingabetaste**, um die Eingabe eines Exportkennworts zu überspringen.

1. Führen Sie [!DNL certmgr.msc] über die Aufforderung zur Ausführung, über das Startmenü oder über die Befehlszeile aus.
1. Öffnen Sie den **persönlichen** Zertifikatspeicher für den aktuellen Benutzer.

   ![](assets/6_5_crypto_api_0.png)

1. Klicken Sie mit der rechten Maustaste auf **Zertifikate** und dann auf **Alle Aufgaben** > **Importieren**.

   Vergewissern Sie sich, dass die Option **Aktueller Benutzer** ausgewählt ist, und klicken Sie auf **Weiter**.

   ![](assets/6_5_crypto_api_4.png)

1. Klicken Sie auf **Durchsuchen** und wählen Sie die zuvor erstellte `<CommonName>.pfx`-Datei aus. Sie müssen im Dropdown-Feld für die Dateierweiterung von einem X.509-Zertifikat entweder zum Dateityp **Personal Information Exchange** oder zu **Alle Dateien** wechseln, um die Datei anzeigen zu können.

   Wählen Sie die Datei aus und klicken Sie auf **Öffnen** und dann auf **Weiter**.

1. Geben Sie kein Kennwort ein und stellen Sie sicher, dass nur die Optionen **Diesen Schlüssel als exportierbar markieren** und **Alle erweiterten Eigenschaften einbeziehen** ausgewählt sind.

   ![](assets/6_5_crypto_api_3.png)

   Klicken Sie auf **Weiter**.

1. Vergewissern Sie sich, dass die Option **Alle Zertifikate im folgenden Speicher ablegen** ausgewählt ist und der angezeigte Zertifikatspeicher **persönlich** ist. (Wenn Sie ein fortgeschrittener Benutzer sind, können Sie zu diesem Zeitpunkt einen anderen Speicher auswählen. Sie werden die Konfiguration in diesem Fall jedoch später ändern müssen.)

1. Klicken Sie auf **Weiter** und dann auf **Beenden**. Es sollte ein Dialogfeld angezeigt werden, in dem Sie darüber informiert werden, dass der Import erfolgreich war, und das Zertifikat im Ordner „Zertifikate“ des Speichers angezeigt werden.

   >[!NOTE]
   >
   >Achten Sie besonders auf die Felder **Ausgestellt an** und **Ausgestellt von**. Sie werden diese im nächsten Schritt benötigen.

**Schritt 2: Bearbeiten Sie die Datei Insight.cfg.**

Die [!DNL Insight.cfg]-Datei muss bearbeitet werden, damit die Data Workbench die Windows-Zertifikatspeicher-Funktion verwenden kann. Jeder Servereintrag in dieser Datei muss einige zusätzliche Parameter enthalten. Wenn die Parameter weggelassen werden, verwendet die Workstation standardmäßig die vorhandene Zertifikatkonfiguration. Wenn die Parameter angegeben wurden, aber falsche Werte enthalten, gibt die Workstation einen Fehlerstatus aus. In diesem Fall finden Sie Informationen zum Fehler in der Protokolldatei.

1. Öffnen Sie die **Insight.cfg**-Datei (zu finden im **Insight**-Installationsordner).

1. Blättern Sie nach unten zu dem Servereintrag, den Sie konfigurieren möchten. Wenn Sie den Windows-Zertifikatspeicher für jeden Server verwenden möchten, müssen Sie diese Änderungen an jedem Eintrag im Vektor von [!DNL serverInfo]-Objekten vornehmen.
1. Fügen Sie diese Parameter zur [!DNL Insight.cfg]-Datei hinzu. Sie können dies über die Workstation oder manuell tun, indem Sie die folgenden Parameter zum [!DNL serverInfo]-Objekt hinzufügen. (Achten Sie darauf, Leerzeichen anstelle von Tabulatorzeichen zu verwenden, und vermeiden Sie in dieser Datei Tippfehler oder Syntaxfehler.)

   ```
   SSL Use CryptoAPI = bool: true  
   SSL CryptoAPI Cert Name = string: <Common Name>  
   SSL CryptoAPI Cert Issuer Name = string: Visual Sciences,LLC  
   SSL CryptoAPI Cert Store Name = string: My 
   ```

   Der boolesche Wert aktiviert oder deaktiviert die Funktion. Der Zertifikatname stimmt mit dem Wert für **Ausgestellt an** im Zertifikatmanager überein. Der Name des Zertifikatausstellers stimmt mit dem für **Ausgestellt von** angegebenen Namen überein, und der Wert für **Speichername** muss mit dem Namen des Zertifikatspeichers übereinstimmen.

   >[!NOTE]
   >
   >Der Name für „Persönlich“ im Zertifikatmanager (certmgr.msc) bezieht sich eigentlich auf den Zertifikatspeicher **Eigene Zertifikate.** Wenn Sie daher Ihr SSL-Kommunikationszertifikat und Ihren SSL-Schlüssel (.PFX) wie empfohlen in den **persönlichen** Zertifikatspeicher importieren, müssen Sie die Zeichenfolge für den **SSL-CryptoAPI-Zertifikatsspeichernamen** auf „Eigene Zertifikate“ setzen. Sie können diesen Parameter nicht auf „persönlich“ festlegen. Dies ist eine Besonderheit des Windows-Zertifikatspeichers.

   Eine vollständige Liste der vordefinierten Systemspeicher erhalten Sie hier: [https://msdn.microsoft.com/en-us/library/windows/desktop/aa388136(v=vs.85).aspx](https://msdn.microsoft.com/en-us/library/windows/desktop/aa388136%28v=vs.85%29.aspx). Ihr System verfügt möglicherweise über zusätzliche Zertifikatspeicher. Wenn Sie einen anderen Speicher als „persönlichen“ Speicher verwenden möchten (z. B. **Eigene Zertifikate**), müssen Sie den kanonischen Namen des Zertifikatspeichers abrufen und in der [!DNL Insight.cfg]-Datei angeben. (Der Systemspeichername „Eigene Zertifikate“ wird in der Windows-Dokumentation inkonsistent als „Eigene Zertifikate“ und „EIGENE ZERTIFIKATE“ bezeichnet. Beim Parameter wird nicht zwischen Groß- und Kleinschreibung unterschieden.)

1. Nachdem Sie diese Parameter hinzugefügt und überprüft haben, ob die Werte mit der Liste im Windows-Zertifikatmanager übereinstimmen, speichern Sie die [!DNL Insight.cfg]-Datei.

Sie können jetzt die Workstation starten (oder die Verbindung zum Server trennen/wiederherstellen). Data Workbench sollte Ihr Zertifikat und Ihren Schlüssel aus dem Zertifikatspeicher laden und wie gewohnt eine Verbindung herstellen.

## Protokollausgabe {#section-a7ef8c9e90ef4bbabaa3cd51a2aca3ab}

Wenn ein Zertifikat nicht gefunden wird oder ungültig ist, wird diese Fehlermeldung in der [!DNL HTTP.log]-Datei ausgegeben.

```
ERROR Fatal error: the cert could not be found!
```

>[!NOTE]
>
>Das L4-Protokollierungsframework kann aktiviert werden, indem Sie die [!DNL L4.cfg]-Datei einrichten (wenden Sie sich für die Einrichtung an Ihren Kundenbetreuer).
