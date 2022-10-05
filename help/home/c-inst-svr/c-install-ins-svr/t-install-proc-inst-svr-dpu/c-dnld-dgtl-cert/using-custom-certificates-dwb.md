---
description: Anweisungen zur Verwendung benutzerdefinierter Zertifikate.
title: Verwenden benutzerdefinierter Zertifikate in Data Workbench
uuid: c3a2db27-bdb2-44b3-95dd-65eedd05c957
exl-id: f813d599-723f-4b5d-a0b5-f4d71c1b1a22
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '732'
ht-degree: 1%

---

# Verwenden benutzerdefinierter Zertifikate in Data Workbench{#using-custom-certificates-in-data-workbench}

{{eol}}

Anweisungen zur Verwendung benutzerdefinierter Zertifikate.

Ein Zertifikat, das entweder vom Data Workbench-Client oder -Server verwendet wird, muss von einer vertrauenswürdigen Zertifizierungsstelle (Certificate Authority) signiert werden. Data Workbench-Kunden erhalten Zertifikate, die von der Visual Sciences CA signiert werden. Diese Zertifikate werden von der Data Workbench-Software als vertrauenswürdig eingestuft, da die [!DNL trust_ca_cert.pem] (zusammen mit der Insight-Software bereitgestellt und im **Zertifikate** Verzeichnis der Server und Clients) enthält eine *CA-Stammzertifikat* für die Visual Sciences CA. Diese Zertifikate werden sowohl für die Lizenzierung der Software als auch für die Authentifizierung verwendet, wenn Clients und Server mithilfe von SSL miteinander kommunizieren. Nur von der Zertifizierungsstelle der Visual Sciences ausgestellte Zertifikate können für die Lizenzierung verwendet werden, andere Zertifikate können jedoch für die Kommunikation und Authentifizierung verwendet werden. Die von anderen Zertifizierungsstellen als Visual Sciences ausgestellten Bescheinigungen werden im Folgenden als *benutzerdefinierte Zertifikate.*

**Wichtiger Hinweis:** Bei Servern und Clients verwendet die Data Workbench-Software die im Client- oder Server-Fenster installierten Zertifikatdateien **Zertifikate** -Ordner oder -Zertifikate, die explizit in der Konfiguration angegeben sind. Sie können jedoch auch die [Windows-Zertifikatspeicher](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/crypto-api.md#concept-4acb13b7de9340ea8cde8ad84b93358d) für Clients.

In den folgenden Anweisungen werden die Verfahren beschrieben, nach denen benutzerdefinierte Zertifikate für die Kommunikation zwischen Data Workbench-Clients und -Servern verwendet werden. Nicht jedes Detail ist eine schwierige Anforderung, und es können unterschiedliche Prozessvarianten eingesetzt werden. Die folgenden Verfahren wurden jedoch getestet, um zu funktionieren.

## Einrichten benutzerdefinierter Client-Zertifikate {#section-2083fd41973e451fa404e7a4ae4da591}

1. Fügen Sie die Bescheinigung der ausstellenden Zertifizierungsstelle der [!DNL trust_cert_ca.pem], die in der **Zertifikate** Verzeichnis des Clients und des jedes Servers in jedem Cluster, auf den mit diesem benutzerdefinierten Zertifikat zugegriffen werden soll.

1. Rufen Sie für jeden Server im Cluster ein benutzerdefiniertes Zertifikat mit den folgenden Bedingungen ab:

   1. Zertifikat ist als [!DNL .pem] Zertifikat.
   1. Das Zertifikat enthält seinen Schlüssel und ist unverschlüsselt (d. h. es hat kein Kennwort/keine Passwort-Phrase).

      Ein Zertifikat enthält seinen Schlüssel mit einer der folgenden Zeilen:

      ```
      BEGIN PRIVATE KEY 
      BEGIN RSA PRIVATE KEY
      ```

      Eine Möglichkeit, den Kennwortsatz aus einem [!DNL .pem] certificate:

      ```
      openssl rsa  -in password-protected-cert.pem -out no-password-cert.pem 
      openssl x509 -in password-protected-cert.pem >> no-password.pem
      ```

   1. Das Zertifikat umfasst die Felder CN, O, OU usw. wie für diesen Client in der [!DNL Access Control.cfg] -Datei.
   1. Das Zeugnis wurde mit einem *Zweck&#42;&#42;&#42;* von *client* (oder beides) *server* **und** *client*).

      Um zu überprüfen, ob ein Zertifikat über einen Zielcode des Servers und/oder Clients verfügt, können die folgenden Befehle verwendet werden:

      ```
      openssl verify -CAfile trust_ca_cert.pem -purpose sslserver -x509_strict custom_communications_cert.pem 
      openssl verify -CAfile trust_ca_cert.pem -purpose sslclient -x509_strict custom_communications_cert.pem
      ```

      Für Serverzertifikate sollten beide Befehle Folgendes liefern:

      ```
      custom_communications_cert.pem: OK
      ```

      Für ein Client-Zertifikat ist nur der zweite Befehl erforderlich, um [!DNL OK].

1. Platzieren Sie das Zertifikat im **Zertifikate** Verzeichnis.
1. In [!DNL Insight.cfg] unter *serverInfo* Stellen Sie für jeden Cluster, den Sie dieses Zertifikat verwenden möchten, sicher, dass die *Benutzerdefinierte Client-Zertifikate* benannt ist, z. B.:

   ```
   Servers = vector: 1 items 
     0 = serverInfo: 
       SSL Client Certificate = string:
   <my_custom_client_cert.pem>
   ```

## Einrichten benutzerdefinierter Serverzertifikate {#setting-up-custom-server-certificates}

In diesem Abschnitt wird davon ausgegangen, dass Sie über einen Cluster verfügen, der aktiv ist und von dem Zertifikate verwendet werden, die von Visual Sciences ausgestellt wurden. Die Konfiguration folgt gängigen Verfahren (z. B. dem *Komponenten für Verarbeitungsserver* -Verzeichnis auf dem Übergeordneten wird mit dem *Komponenten* -Verzeichnissen aller DPUs).

1. Fügen Sie die Bescheinigung der ausstellenden Zertifizierungsstelle der [!DNL trust_cert_ca.pem] wird auf jedem Server im Cluster installiert und auf jedem Client, der mit diesem Cluster kommunizieren muss.
1. Rufen Sie für jeden Server im Cluster ein benutzerdefiniertes Zertifikat mit den folgenden Anforderungen ab:

   1. Benutzerdefiniertes Zertifikat wird als [!DNL .pem] Zertifikat.
   1. Das Zertifikat enthält seinen Schlüssel und ist unverschlüsselt (d. h. es hat kein Kennwort/keine Passwort-Phrase).

      Ein Zertifikat enthält seinen Schlüssel, wenn er eine Zeile wie die folgende enthält:

      ```
      BEGIN PRIVATE KEY 
      BEGIN RSA PRIVATE KEY
      ```

      Eine Möglichkeit, den Kennwortsatz aus einem [!DNL .pem] certificate:

      ```
      openssl rsa  -in password-protected-cert.pem -out no-password-cert.pem 
      openssl x509 -in password-protected-cert.pem >> no-password.pem
      ```

   1. Das Zertifikat hat dieselbe KN wie das [!DNL server_cert.pem] derzeit auf dem Server installiert ist.
   1. Die Bescheinigung wurde mit dem Ziel ausgestellt, *server* und *client*.

      Um zu überprüfen, ob ein Zertifikat über einen Zielcode des Servers und/oder Clients verfügt, können die folgenden Befehle verwendet werden:

      ```
      openssl verify -CAfile trust_ca_cert.pem -purpose sslserver -x509_strict custom_communications_cert.pem 
      openssl verify -CAfile trust_ca_cert.pem -purpose sslclient -x509_strict custom_communications_cert.pem
      ```

      Für Serverzertifikate sollten beide Befehle Folgendes liefern:

      ```
      custom_communications_cert.pem: OK
      ```

      Für ein Client-Zertifikat ist nur der zweite Befehl erforderlich, um [!DNL OK].

1. Installieren Sie das benutzerdefinierte Zertifikat jedes Servers im **Zertifikate** Verzeichnis des Servers als [!DNL custom_communications_cert.pem].

1. Fügen Sie mithilfe eines Texteditors die folgende Zeile hinzu **Communications.cfg** -Datei in beiden *Komponenten* und *Komponenten für Verarbeitungsserver* Verzeichnisse direkt unterhalb der ersten Zeile ([!DNL component = CommServer]):

   ```
   Certificate = string: Certificates\\custom_communications_cert.pem
   ```

1. Starten Sie alle Server neu.

**Über Zertifikatfehlerwarnung**

Wenn der Insight-Server oder -Client nach einer **Lizenz** Zertifikat im **Zertifikate** Verzeichnis, versucht es, alle Zertifikate zu validieren (mit Ausnahme von [!DNL trust_ca_cert.pem]), gegen eine hartcodierte Kopie des Insight CA-Zertifikats, die bei einem im Verzeichnis vorhandenen benutzerdefinierten Zertifikat fehlschlägt. Der Server gibt diese Warnung aus:

```
Certificate failed to verify. Error 20 at 0 depth. Desc: unable to get local issuer certificate. Cert details:
```

Diese Warnung kann ignoriert werden.
