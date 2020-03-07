---
description: Adobe verwendet digitale X.509-Zertifikate, um die Client- und Serverkomponenten, aus denen eine Implementierung besteht, zu identifizieren und zu authentifizieren.
solution: Analytics
title: Digitale Zertifikate
topic: Data workbench
uuid: a2d84e9a-16aa-4973-85da-303614a4ad7f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Digitale Zertifikate{#understanding-digital-certificates}

Adobe verwendet digitale X.509-Zertifikate, um die Client- und Serverkomponenten, aus denen eine Implementierung besteht, zu identifizieren und zu authentifizieren.

Bei der Installation [!DNL Report Server]müssen Sie das digitale Zertifikat installieren, das eine benannte Person (z. B. Jane Smith) zur Verwendung der installierten Clientanwendung autorisiert.

>[!NOTE]
>
>Wenn Sie [!DNL Report Server] zu einem anderen Computer oder einem anderen benannten Benutzer migrieren müssen, müssen Sie ein neues Zertifikat von Adobe abrufen. Wenden Sie sich dazu an den Adobe-Kundendienst.

[!DNL Report Server] präsentiert dieses digitale Zertifikat, um Zugriff auf eine Serverkomponente zu erhalten. Ein Administrator der Serverkomponente kann den Zugriff auf Serverressourcen auf der Grundlage der im Zertifikat des Kunden angezeigten Werte für allgemeine Namen oder organisatorische Einheiten einschränken.

Die mit Adobe-Anwendungen installierten digitalen X.509-Zertifikate ermöglichen es seinen Client- und Serverkomponenten auch, Informationen über Secure Sockets Layer (SSL) auszutauschen. SSL sichert Übertragungen über HTTP mithilfe eines Verschlüsselungssystems mit öffentlichem und privatem Schlüssel. Die Implementierung von SSL von Adobe unterstützt 1024-Bit-RSA-Schlüssel und verwendet einen 128-Bit-RC4-Verschlüsselungsalgorithmus.

Zusätzlich zur Sicherheit fungiert das von Ihnen installierte digitale Zertifikat auch als Lizenzschlüssel, mit dem Sie das installierte Zertifikat ausführen können [!DNL Report Server]. Um ordnungsgemäß funktionieren zu können, muss ein digitales Zertifikat Node-gesperrt und aktuell sein, andernfalls wird die Anwendung nicht gestartet.

## Freigegebene Zertifikate {#section-3338f1558e7844888dced8f395888744}

Ein knotengesperrtes Zertifikat ist ein digitales Zertifikat, das auf dem Computer registriert wurde, auf dem es installiert ist. Durch die Node-Sperrung wird ein Zertifikat dauerhaft mit einer bestimmten Node-ID (einem Wert, der eine bestimmte Maschine eindeutig identifiziert) verknüpft. Um Ihr Zertifikat zu sperren, muss Ihr Computer über Internetzugriff auf den Adobe License Server oder einen Proxyserver verfügen, der Zugriff auf den License Server hat.

Wenn Sie eine Installation auf einem Computer durchführen, der nicht auf das Internet zugreifen kann, müssen Sie ein spezielles vorgesperrtes Zertifikat abrufen und installieren, wie unter [Verwenden von digitalen Zertifikaten auf Computern ohne Internetzugriff](../../../../home/c-rpt-oview/c-inst-rpt/c-install-dig-cert/c-underst-dig-cert.md#section-18cce05e2204407bb2b6b75deab9197d) auf dieser Seite beschrieben.

Wenn Sie eine Installation auf einem Computer durchführen, der auf das Internet zugreifen kann, wird Ihr digitales Zertifikat automatisch beim ersten Starten gesperrt [!DNL Report Server]. Nach dem Sperren des Knotens kann das Zertifikat auf keinem anderen Computer verwendet werden. Wenn Sie [!DNL Report Server] zu einem anderen Computer migrieren müssen, müssen Sie ein neues, entsperrtes Zertifikat von Adobe erhalten.

## Aktuelle Zertifikate {#section-b4053ab714514dfb97ea7f61bbb8da1e}

Neben der Node-Sperre muss ein digitales Zertifikat aktuell sein. Um auf dem neuesten Stand zu bleiben, muss Ihr Zertifikat regelmäßig (in der Regel alle 30 Tage, je nach Ihrer Vereinbarung mit Adobe) erneuert werden. Wenn Ihr Computer über Internetzugang verfügt, ist der Erneuerungsvorgang vollkommen transparent. [!DNL Report Server] stellt automatisch eine Verbindung zum Lizenzserver her und überprüft das Zertifikat bei Bedarf erneut. Wenn Ihr Computer keinen Internetzugang hat, müssen Sie die aktualisierten Zertifikate manuell installieren, wie im folgenden Abschnitt beschrieben.

## Digitale Zertifikate auf Computern ohne Internetzugang verwenden {#section-18cce05e2204407bb2b6b75deab9197d}

Wenn Sie eine Installation auf einem Computer durchführen, der nicht auf das Internet zugreifen kann, müssen Sie ein vordefiniertes Zertifikat für Ihre Installation von [!DNL Report Server]anfordern. Ein vorab gesperrtes Zertifikat ist ein digitales Zertifikat, das von Adobe manuell an die Node-ID des Computers gesperrt wird.

Um ein vorab gesperrtes Zertifikat anzufordern, müssen Sie die Node-ID und Ihre Zertifikatnummer an die Adobe-Kundenunterstützung senden. Um die Node-ID für Ihren Computer abzurufen, wenden Sie sich an den Adobe-Kundendienst, um das Adobe- [!DNL Node Identifier] Dienstprogramm anzufordern. Sie können die Node-ID auch aus der Warnung abrufen, die beim Versuch, eine Verbindung zum Lizenzserver herzustellen, ausgelöst wird und nicht ausgeführt werden kann. [!DNL Report Server] Wenn Sie das vordefinierte Zertifikat erhalten, installieren Sie es wie in den letzten beiden Schritten der Installationsverfahren für [digitale Zertifikate beschrieben](../../../../home/c-rpt-oview/c-inst-rpt/c-install-dig-cert/t-dig-cert-install-proc.md#task-5c4bb352ff534b40adc46dd053874e5d).

Wenn das Zertifikat erneut überprüft werden muss, müssen Sie ein neues validiertes Zertifikat vom Lizenzserver herunterladen und auf Ihrem Computer neu installieren (sofern nicht Ihr Vertrag mit Adobe etwas Anderes vorsieht).
