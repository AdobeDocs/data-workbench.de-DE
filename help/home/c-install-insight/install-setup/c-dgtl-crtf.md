---
description: Nachdem Sie die Insight-Programmdateien installiert haben, müssen Sie das von Adobe bereitgestellte digitale Zertifikat herunterladen und installieren.
title: Herunterladen und Installieren des digitalen Zertifikats
uuid: 93ab2222-a977-4279-9e1e-71038b1d1cfa
exl-id: 0dff95ae-880b-45d5-96df-4eb6bea58891
source-git-commit: 79981e92dd1c2e552f958716626a632ead940973
workflow-type: tm+mt
source-wordcount: '2743'
ht-degree: 39%

---

# Herunterladen und Installieren des digitalen Zertifikats{#downloading-and-installing-the-digital-certificate}

Nachdem Sie die Insight-Programmdateien installiert haben, müssen Sie das von Adobe bereitgestellte digitale Zertifikat herunterladen und installieren.

## Herunterladen und Installieren des digitalen Zertifikats {#topic-fed3b44e472c4e4ca6dd5852af14cdb9}

Nachdem Sie die Insight-Programmdateien installiert haben, müssen Sie das von Adobe bereitgestellte digitale Zertifikat herunterladen und installieren.

## Grundlagen zu digitalen Zertifikaten {#concept-9eed01c8d95440cda6ce29d68e65098c}

Adobe verwendet digitale X.509-Zertifikate, um die Client- und Serverkomponenten, aus denen eine Implementierung besteht, zu identifizieren und zu authentifizieren.

<!--
c_undst_dgtl_crtf.xml
-->

Wenn Sie Insight installieren, müssen Sie das digitale Zertifikat installieren, das eine benannte Person (z. B. Jane Smith) zur Verwendung der installierten Clientanwendung autorisiert.

>[!NOTE]
>
>Wenn Sie Insight auf einen anderen Computer oder einen anderen benannten Benutzer migrieren müssen, müssen Sie ein neues Zertifikat von Adobe abrufen. Wenden Sie sich dazu an die Kundenunterstützung von Adobe.

Insight stellt dieses digitale Zertifikat vor, um Zugriff auf eine Serverkomponente zu erhalten. Ein Administrator einer Serverkomponente kann den Zugriff auf Serverressourcen auf der Grundlage der Werte für allgemeine Namen oder Organisationseinheiten einschränken, die im Zertifikat des Benutzers angezeigt werden.

Die mit Adobe-Anwendungen installierten digitalen X.509-Zertifikate ermöglichen auch den Austausch von Informationen über Secure Sockets Layer (SSL). SSL sichert Übertragungen über HTTP mithilfe eines Verschlüsselungssystems mit öffentlichem und privatem Schlüssel. Die Implementierung von SSL durch Adobe unterstützt 1024-Bit-RSA-Schlüssel und verwendet einen 128-Bit-RC4-Verschlüsselungsalgorithmus.

Neben der Sicherheit dient das von Ihnen installierte digitale Zertifikat auch als Lizenzschlüssel, mit dem Sie Insight ausführen können. Um ordnungsgemäß zu funktionieren, muss ein digitales Zertifikat knotenspezifisch und aktuell sein, andernfalls wird die Anwendung nicht gestartet.

## Knotenspezifische Zertifikate {#section-984aa8f2f5a1448cadc4afea978aedc9}

Ein knotenspezifisches Zertifikat ist ein digitales Zertifikat, das auf dem Computer registriert wurde, auf dem es installiert ist. Durch die Knotensperrung wird ein Zertifikat dauerhaft mit einer bestimmten Knotenkennung (einem Wert, der einen bestimmten Computer eindeutig identifiziert) verknüpft. Um das Zertifikat knotenspezifisch zu gestalten, muss Ihr Computer über Internetzugriff auf den Adobe License Server oder einen Proxyserver verfügen, der Zugriff auf den Lizenzserver hat.

Wenn Sie eine Installation auf einem Computer durchführen, der nicht auf das Internet zugreifen kann, müssen Sie ein spezielles vorgesperrtes Zertifikat abrufen und installieren, wie unter [Verwenden digitaler Zertifikate auf Computern ohne Internetzugang](../../../home/c-install-insight/install-setup/c-dgtl-crtf.md#section-d3c060131d7f45cda27f68848b704fa1) beschrieben.

Wenn Sie eine Installation auf einem Computer durchführen, der auf das Internet zugreifen kann, wird Ihr digitales Zertifikat automatisch knotenspezifisch, wenn Sie Insight zum ersten Mal starten. Nachdem das Zertifikat knotenspezifisch war, kann es auf keinem anderen Computer verwendet werden. Wenn Sie Insight auf einen anderen Computer migrieren müssen, müssen Sie ein neues, entsperrtes Zertifikat von Adobe erhalten.

## Aktuelle Zertifikate {#section-0816b031df3e415ab3f0205b720c723e}

Ihr digitales Zertifikat muss nicht nur knotenspezifisch, sondern auch aktuell sein. Um auf dem neuesten Stand zu bleiben, muss Ihr Zertifikat regelmäßig erneuert werden (in der Regel alle 30 Tage; dies kann aber je nach Vereinbarung mit der Adobe variieren). Wenn Ihr Computer Internetzugang hat, ist der Erneuerungsvorgang vollkommen transparent. Insight stellt automatisch eine Verbindung zum Lizenzserver her und überprüft das Zertifikat bei Bedarf erneut. Wenn Ihr Computer keinen Internetzugang hat, müssen Sie ein aktualisiertes Zertifikat manuell installieren, wie im folgenden Abschnitt beschrieben.

## Verwenden digitaler Zertifikate auf Computern ohne Internetzugang {#section-d3c060131d7f45cda27f68848b704fa1}

Wenn Sie eine Installation auf einem Computer durchführen, der nicht auf das Internet zugreifen kann, müssen Sie ein vorgesperrtes Zertifikat für Ihre Installation von Insight anfordern. Ein vorgesperrtes Zertifikat ist ein digitales Zertifikat, das von Adobe manuell mit der Knotenkennung für den Computer gesperrt wird.

Um ein vorgesperrtes Zertifikat anzufordern, müssen Sie die Knoten-ID und Ihre Zertifikatnummer an die Adobe-Kundenunterstützung senden. Wenden Sie sich an die Kundenunterstützung von Adobe, um die Adobe [!DNL Node Identifier] anzufordern, um die Knoten-ID für Ihren Computer abzurufen. Sie können die Knoten-ID auch aus der Warnung abrufen, die Insight auslöst, wenn versucht wird, eine Verbindung zum Lizenzserver herzustellen, aber nicht kann. Wenn Sie das vorgesperrte Zertifikat erhalten, installieren Sie es wie in den letzten beiden Schritten von [Installieren digitaler Zertifikate](../../../home/c-install-insight/install-setup/c-dgtl-crtf.md#task-1dad1e1d86d04100a7bcf87f26303c38) beschrieben.

Wenn das Zertifikat erneut validiert werden muss, müssen Sie ein neues, validiertes Zertifikat vom Lizenzserver herunterladen und auf Ihrem Computer neu installieren (sofern Ihre Vereinbarung mit Adobe nichts anderes vorsieht).

## Installieren digitaler Zertifikate {#task-1dad1e1d86d04100a7bcf87f26303c38}

<!--
t_install_dgtl_crtf.xml
-->

**So laden Sie das digitale Zertifikat herunter und installieren es**

1. Öffnen Sie Ihren Webbrowser auf [!DNL https:\\license.visualsciences.com].

   >[!NOTE]
   >
   >Ihr Browser fordert Sie an dieser Stelle möglicherweise auf, ein digitales Zertifikat vorzulegen. Wenn dies der Fall ist, klicken Sie auf **[!UICONTROL Cancel]** , um das Dialogfeld zu schließen.

1. Geben Sie auf dem Anmeldebildschirm die von Adobe erhaltenen Werte für [!DNL Account Name] und [!DNL Password] ein, und klicken Sie dann auf **[!UICONTROL login]**.
1. Suchen Sie das Zertifikat, das für Ihre Instanz von Insight ausgestellt wurde ( *Ihr Name*.pem), und klicken Sie auf das Symbol ![](assets/btn_save_certificatedownload.PNG), das diesem Zertifikat zugeordnet ist.
1. Wenn Sie aufgefordert werden, das Zertifikat zu speichern, klicken Sie auf **[!UICONTROL Save]**.
1. Laden Sie die Datei in den Ordner [!DNL Certificates] in dem Verzeichnis herunter, in dem Insight installiert ist.

   Dieser Ordner enthält eine Zertifikatdatei mit dem Namen [!DNL trust_ca_cert.pem]. Beide Zertifikatdateien müssen immer vorhanden sein, damit Insight funktioniert.

## Windows-Zertifikatspeicher {#concept-4acb13b7de9340ea8cde8ad84b93358d}

Mit dem Windows-Zertifikatspeicher können Sie das Zertifikat und den privaten Schlüssel des Clients im Windows-Zertifikatspeicher für die SSL-Kommunikation mit Servern speichern.

<!--
crypto-api.xml
-->

Der Windows-Zertifikatspeicher für den Client ist eine neue Funktion, mit der Sie das SSL-Kommunikationszertifikat und den privaten Schlüssel im Windows-Zertifikatspeicher und nicht in der `Insight/Certificates/<CertName>.pem`-Datei speichern können. Die Verwendung des Windows-Zertifikatspeichers ist unter Umständen vorzuziehen, wenn Sie den Zertifikatspeicher für andere Anwendungen verwenden und die Zertifikatverwaltung an einer Stelle durchführen möchten, oder wenn Benutzer die zusätzliche Windows-Prüfprotokollierung nutzen, die der Windows-Zertifikatspeicher bereitstellt.

>[!NOTE]
>
>Die Lizenzierung mit dem Lizenzserver wird weiterhin mit der vorhandenen `<Common Name>.pem`-Datei verwaltet, und das Zertifikat, das vom Zertifikatspeicher bereitgestellt wurde, wird nur für die Kommunikation mit den von Ihnen angegebenen Servern verwendet.

## Voraussetzungen {#section-69b18600052145ff8e5299b7123e69c5}

1. Sie müssen Zugriff auf die [!DNL certmgr.msc]-Datei haben, damit Sie ein Zertifikat und einen Schlüssel in den **persönlichen** Speicher importieren können. (Dies sollte für die meisten Windows-Benutzer standardmäßig der Fall sein.)

1. Der Benutzer, der die Konfiguration durchführt, muss über eine Kopie des **OpenSSL** -Befehlszeilenwerkzeugs verfügen.
1. Server und Client müssen bereits für die Verwendung eines benutzerdefinierten SSL-Zertifikats konfiguriert sein und Anweisungen zum Speichern des Clientzertifikats im Windows-Zertifikatspeicher geben, anstatt es im Ordner **Zertifikate** zu speichern.

## Konfigurieren des Windows-Zertifikatspeichers {#section-3629802122e947d4b4f63e8b732cfe27}

Der Windows-Zertifikatspeicher für Clients wird wie folgt aktiviert:

**Schritt 1: Importieren Sie das SSL-Zertifikat und den privaten Schlüssel des Benutzers in den Windows-Zertifikatspeicher.**

Unter [Verwenden benutzerdefinierter Zertifikate in Data Workbench](../../../home/c-install-insight/install-setup/c-dgtl-crtf.md#concept-ee6a9b5015f84a0ba64a11428b0a72dd) werden Sie angewiesen, das SSL-Zertifikat und den SSL-Schlüssel im folgenden Ordner abzulegen:

```
<
<filepath>
  DWB Install folder
</filepath>>\Certificates\
```

Der Name des Zertifikats lautet `<Common Name>.pem`, z. B. Analytics Server 1.pem (nicht die Datei &quot;trust_ca_cert.pem&quot;).

Bevor das Zertifikat und der private Schlüssel importiert werden können, müssen sie aus dem . [!DNL pem]-Format in ein [!DNL .pfx]-Format konvertiert werden, z. B. [!DNL pkcs12.pfx]).

1. Öffnen Sie eine Eingabeaufforderung oder ein Terminal und navigieren Sie zum folgenden Verzeichnis:

   ```
   <CommonName>.pem c: cd \<filepath>DWB Install folder</filepath>>\Certificates
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

## Verwenden benutzerdefinierter Zertifikate in Data Workbench {#concept-ee6a9b5015f84a0ba64a11428b0a72dd}

Anweisungen zur Verwendung benutzerdefinierter Zertifikate.

<!--
using-custom-certificates-DWB.xml
-->

Ein Zertifikat, das entweder vom Data Workbench-Client oder -Server verwendet wird, muss von einer vertrauenswürdigen Zertifizierungsstelle (Certificate Authority) signiert werden. Data Workbench-Kunden erhalten Zertifikate, die von der Visual Sciences CA signiert werden. Diese Zertifikate werden von der Data Workbench-Software als vertrauenswürdig eingestuft, da das [!DNL trust_ca_cert.pem] (zusammen mit der Insight-Software bereitgestellt und im **Zertifikate**-Verzeichnis von Servern und Clients gespeichert) ein *Stammzertifikat* für die Visual Sciences-Zertifizierungsstelle enthält. Diese Zertifikate werden sowohl für die Lizenzierung der Software als auch für die Authentifizierung verwendet, wenn Clients und Server mithilfe von SSL miteinander kommunizieren. Nur von der Zertifizierungsstelle der Visual Sciences ausgestellte Zertifikate können für die Lizenzierung verwendet werden, andere Zertifikate können jedoch für die Kommunikation und Authentifizierung verwendet werden. Zertifikate, die von anderen Zertifizierungsstellen als Visual Sciences ausgestellt werden, werden im Folgenden als *benutzerdefinierte Zertifikate bezeichnet.*

**Wichtiger Hinweis:** Bei Servern und Clients verwendet die Data Workbench-Software die Zertifikatdateien, die im  **** Zertifikatverzeichnis des Clients oder Servers installiert sind, bzw. die Zertifikate, die explizit in der Konfiguration angegeben sind. Sie können jedoch auch den Windows-Zertifikatspeicher für Clients verwenden.

In den folgenden Anweisungen werden die Verfahren beschrieben, nach denen benutzerdefinierte Zertifikate für die Kommunikation zwischen Data Workbench-Clients und -Servern verwendet werden. Nicht jedes Detail ist eine schwierige Anforderung, und es können unterschiedliche Prozessvarianten eingesetzt werden. Die folgenden Verfahren wurden jedoch getestet, um zu funktionieren.

## Einrichten benutzerdefinierter Client-Zertifikate {#section-2083fd41973e451fa404e7a4ae4da591}

1. Fügen Sie das Zertifikat der ausstellenden Zertifizierungsstelle zum Ordner [!DNL trust_cert_ca.pem] hinzu, der im Ordner **Zertifikate** des Clients installiert ist, sowie zum Zertifikat jedes Servers in jedem Cluster, auf den mit diesem benutzerdefinierten Zertifikat zugegriffen werden soll.

1. Rufen Sie für jeden Server im Cluster ein benutzerdefiniertes Zertifikat mit den folgenden Bedingungen ab:

   1. Zertifikat ist als [!DNL .pem]-Zertifikat formatiert.
   1. Das Zertifikat enthält seinen Schlüssel und ist unverschlüsselt (d. h. es hat kein Kennwort/keine Passwort-Phrase).

      Ein Zertifikat enthält seinen Schlüssel mit einer der folgenden Zeilen:

      ```
      BEGIN PRIVATE KEY
      BEGIN RSA PRIVATE KEY
      ```

      Eine Möglichkeit, den Kennwortsatz aus einem [!DNL .pem]-Zertifikat zu entfernen:

      ```
      openssl rsa  -in password-protected-cert.pem -out no-password-cert.pem
      openssl x509 -in password-protected-cert.pem >> no-password.pem
      ```

   1. Das Zertifikat umfasst die Felder CN, O, OU usw. wie für diesen Client in der [!DNL Access Control.cfg]-Datei des Servers erforderlich.
   1. Das Zertifikat wurde mit einem *Zweck *** von *client* (oder sowohl *server* **als auch** *client*) ausgestellt.

      Um zu überprüfen, ob ein Zertifikat über einen Zielcode des Servers und/oder Clients verfügt, können die folgenden Befehle verwendet werden:

      ```
      openssl verify -CAfile trust_ca_cert.pem -purpose sslserver -x509_strict custom_communications_cert.pem
      openssl verify -CAfile trust_ca_cert.pem -purpose sslclient -x509_strict custom_communications_cert.pem
      ```

      Für Serverzertifikate sollten beide Befehle Folgendes liefern:

      ```
      custom_communications_cert.pem: OK
      ```

      Für ein Client-Zertifikat ist nur der zweite Befehl erforderlich, um [!DNL OK] auszugeben.

1. Platzieren Sie das Zertifikat im Verzeichnis **Zertifikate** des Clients.
1. Stellen Sie in [!DNL Insight.cfg] unter *serverInfo* für jeden Cluster, den Sie dieses Zertifikat verwenden möchten, sicher, dass das *benutzerdefinierte Client-Zertifikat* benannt ist, z. B.:

   ```
   Servers = vector: 1 items
     0 = serverInfo:
       SSL Client Certificate = string:
     <my_custom_client_cert.pem>
   ```

## Einrichten benutzerdefinierter Serverzertifikate {#setting-up-custom-server-certificates}

In diesem Abschnitt wird davon ausgegangen, dass Sie über einen Cluster verfügen, der aktiv ist und von Visual Sciences ausgestellte Zertifikate verwendet wird. Die Konfiguration folgt gängigen Verfahren (z. B. wird der Ordner *Komponenten für Verarbeitungsserver* auf dem Übergeordneten mit den Ordnern *Komponenten* aller DPUs synchronisiert).

1. Fügen Sie das Zertifikat der ausstellenden Zertifizierungsstelle zum [!DNL trust_cert_ca.pem] hinzu, das auf jedem Server im Cluster und jedem Client installiert ist, der mit diesem Cluster kommunizieren muss.
1. Rufen Sie für jeden Server im Cluster ein benutzerdefiniertes Zertifikat mit den folgenden Anforderungen ab:

   1. Benutzerdefiniertes Zertifikat ist als [!DNL .pem]-Zertifikat formatiert.
   1. Das Zertifikat enthält seinen Schlüssel und ist unverschlüsselt (d. h. es hat kein Kennwort/keine Passwort-Phrase).

      Ein Zertifikat enthält seinen Schlüssel, wenn er eine Zeile wie die folgende enthält:

      ```
      BEGIN PRIVATE KEY
      BEGIN RSA PRIVATE KEY
      ```

      Eine Möglichkeit, den Kennwortsatz aus einem [!DNL .pem]-Zertifikat zu entfernen:

      ```
      openssl rsa  -in password-protected-cert.pem -out no-password-cert.pem
      openssl x509 -in password-protected-cert.pem >> no-password.pem
      ```

   1. Das Zertifikat hat dieselbe KN wie das derzeit auf dem Server installierte [!DNL server_cert.pem].
   1. Das Zertifikat wurde mit dem Zweck *server* und *client* ausgestellt.

      Um zu überprüfen, ob ein Zertifikat über einen Zielcode des Servers und/oder Clients verfügt, können die folgenden Befehle verwendet werden:

      ```
      openssl verify -CAfile trust_ca_cert.pem -purpose sslserver -x509_strict custom_communications_cert.pem
      openssl verify -CAfile trust_ca_cert.pem -purpose sslclient -x509_strict custom_communications_cert.pem
      ```

      Für Serverzertifikate sollten beide Befehle Folgendes liefern:

      ```
      custom_communications_cert.pem: OK
      ```

      Für ein Client-Zertifikat ist nur der zweite Befehl erforderlich, um [!DNL OK] auszugeben.

1. Installieren Sie das benutzerdefinierte Zertifikat jedes Servers im Verzeichnis **Zertifikate** des Servers als [!DNL custom_communications_cert.pem].

1. Fügen Sie mithilfe eines Texteditors die folgende Zeile zur Datei **Communications.cfg** in den Verzeichnissen *Komponenten* und *Komponenten für Verarbeitungsserver* direkt unterhalb der ersten Zeile ( [!DNL component = CommServer]) hinzu:

   ```
   Certificate = string: Certificates\\custom_communications_cert.pem
   ```

1. Starten Sie alle Server neu.

**Über Zertifikatfehlerwarnung**

Wenn der Insight-Server oder -Client nach einem **license**-Zertifikat im Verzeichnis **Certificates** sucht, versucht er, alle Zertifikate (außer [!DNL trust_ca_cert.pem]) anhand einer hartcodierten Kopie des Insight CA-Zertifikats zu validieren, was bei einem im Verzeichnis vorhandenen benutzerdefinierten Zertifikat fehlschlägt. Der Server gibt diese Warnung aus:

```
Certificate failed to verify. Error 20 at 0 depth. Desc: unable to get local issuer certificate. Cert details:
```

Diese Warnung kann ignoriert werden.

## Zeichenfolgenverschlüsselung {#concept-35da0b53650a4d7e82b240ad27f6d45a}

Verschlüsseln Sie bei der Kommunikation zwischen Client und Server Passwörter und andere Strings.

<!--
string_encryption.xml
-->

Bei der Kommunikation zwischen dem Data Workbench-Client (Workstation) und dem Server können Sie einen Value-Parameter (z. B. ein Kennwort) mit dem Typ *EncryptedString* speichern. Dadurch wird der Parameter ausgeblendet und die Zeichenfolge im *Windows Credential Store* auf dem Server mit dem entsprechenden Schlüssel gespeichert. Dadurch werden hauptsächlich in Exporten verwendete Anmeldeinformationen gespeichert, können jedoch zum Verschlüsseln beliebiger Parameter verwendet werden.

* Unter Server\**EncryptStrings** wurde ein neuer Ordner hinzugefügt.

   Hier legen Sie die Konfigurationsdatei fest, um Zeichenfolgen zu verschlüsseln.

* Eine neue Konfigurationsdatei wurde unter Server\Component\**EncryptedStrings.cfg** hinzugefügt.

   ```
   component = EncryptionComponent:
     Path = Path: EncryptStrings\\*.cfg
   ```

   Diese Datei fragt den Ordner *Server*\*EncryptStrings* nach Verschlüsselungskonfigurationsdateien ab.

**Verschlüsseln einer Zeichenfolge**:

1. Erstellen Sie eine Konfigurationsdatei **EncryptedStrings.cfg** für eine Zeichenfolge mit den folgenden Feldern:

   ```
   Names = vector: 1 items
    0 = NameEncryptValuePair:
     EncryptValue = EncryptedString: // left empty as input then output will be filled by server
     Name = string: // Name for identifier
     Value = string: // Value to be encrypted
   ```

   * *Wert*  - Dieses Feld enthält die Nur-Text-Zeichenfolge, die verschlüsselt werden muss.

      Dies ist nur serverseitige Verschlüsselung. Die Einstellung *Wert* wird nur auf dem Servercomputer verschlüsselt.

   * *Name*  - Dieses Feld enthält einen Wert, der die verschlüsselte Zeichenfolge identifiziert.
   * *EncryptValue*  - Dieses Feld bleibt in der Eingabekonfiguration leer. Der verschlüsselte Wert wird in diesem Feld zurückgegeben.

   Sie können mehrere **NameEncryptValuePair**-Werte für verschiedene Felder zur Verschlüsselung hinzufügen.

   >[!NOTE]
   >
   >Alle leeren Wertfelder werden entfernt.

1. Speichern Sie die Datei **EncryptedStrings.cfg** im Ordner Server\**EncryptStrings** .

**Ausgabedatei**

Eine Ausgabedatei wird mit demselben Namen wie die Eingabedatei mit einem &lt;*Dateinamen*> generiert.** verschlüsselt. Wenn die Eingabedatei beispielsweise *sample.cfg* heißt, erhält die Ausgabedatei den Namen *sample.cfg.encrypted*.
