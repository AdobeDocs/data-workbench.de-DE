---
description: Anweisungen zur Verwendung von benutzerdefinierten Zertifikaten.
title: Verwenden von benutzerdefinierten Zertifikaten in Data Workbench
uuid: c3a2db27-bdb2-44b3-95dd-65eedd05c957
translation-type: tm+mt
source-git-commit: 72761a57e4bb9f230581b2cd37bff04ba7be8e37

---


# Verwenden von benutzerdefinierten Zertifikaten in Data Workbench{#using-custom-certificates-in-data-workbench}

Anweisungen zur Verwendung von benutzerdefinierten Zertifikaten.

Ein Zertifikat, das entweder vom Data Workbench-Client oder vom Server verwendet wird, muss von einer vertrauenswürdigen Zertifizierungsstelle (Certificate Authority) signiert werden. Data Workbench-Kunden erhalten Zertifikate, die von der Visual Sciences-Zertifizierungsstelle signiert werden. Diese Zertifikate werden von der Data Workbench-Software als vertrauenswürdig eingestuft, da die [!DNL trust_ca_cert.pem] (zusammen mit der Insight-Software bereitgestellte und im **Zertifikatverzeichnis** von Servern und Clients gespeicherte) ein *Stammzertifikat* für die Visual Sciences-Zertifizierungsstelle enthält. Diese Zertifikate werden sowohl für die Lizenzierung der Software als auch für die Authentifizierung verwendet, wenn Clients und Server über SSL miteinander kommunizieren. Für die Lizenzierung können nur Zertifikate verwendet werden, die von der Visual Sciences CA ausgestellt wurden, andere Zertifikate dürfen jedoch für die Kommunikation und Authentifizierung verwendet werden. Zertifikate, die von anderen Zertifizierungsstellen als Visual Sciences ausgestellt wurden, werden nachstehend als *benutzerdefinierte Zertifikate bezeichnet.*

**Wichtiger Hinweis:** Bei Servern und Clients verwendet die Data Workbench-Software die Zertifikatdateien, die im **Zertifikatordner** des Clients oder des Servers installiert sind, oder die Zertifikate, die explizit in der Konfiguration angegeben sind. Sie können jedoch auch den [Windows-Zertifikatspeicher](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/crypto-api.md#concept-4acb13b7de9340ea8cde8ad84b93358d) für Clients verwenden.

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

1. Fügen Sie mithilfe eines Texteditors der Datei &quot; **Communications.cfg** &quot;in den Ordnern &quot; *Komponenten* &quot;und &quot; *Komponenten für Verarbeitungsserver* &quot;die folgende Zeile direkt unter der ersten Zeile ([!DNL component = CommServer]) hinzu:

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
