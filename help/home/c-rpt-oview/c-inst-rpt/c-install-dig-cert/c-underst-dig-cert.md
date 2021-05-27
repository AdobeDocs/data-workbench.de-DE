---
description: Adobe verwendet digitale X.509-Zertifikate, um die Client- und Serverkomponenten, aus denen eine Implementierung besteht, zu identifizieren und zu authentifizieren.
title: Grundlagen zu digitalen Zertifikaten
uuid: a2d84e9a-16aa-4973-85da-303614a4ad7f
exl-id: 967e9d5b-7972-497e-8902-8db0eb304f27
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '617'
ht-degree: 54%

---

# Grundlagen zu digitalen Zertifikaten{#understanding-digital-certificates}

Adobe verwendet digitale X.509-Zertifikate, um die Client- und Serverkomponenten, aus denen eine Implementierung besteht, zu identifizieren und zu authentifizieren.

Wenn Sie [!DNL Report Server] installieren, müssen Sie das digitale Zertifikat installieren, das eine benannte Person (z. B. Jane Smith) zur Verwendung der installierten Clientanwendung autorisiert.

>[!NOTE]
>
>Wenn Sie [!DNL Report Server] zu einem anderen Computer oder einem anderen benannten Benutzer migrieren müssen, müssen Sie ein neues Zertifikat von Adobe abrufen. Wenden Sie sich dazu an die Kundenunterstützung von Adobe.

[!DNL Report Server] präsentiert dieses digitale Zertifikat, um Zugriff auf eine Serverkomponente zu erhalten. Ein Administrator der Serverkomponente kann den Zugriff auf Serverressourcen auf Grundlage der im Zertifikat des Kunden angezeigten Werte für allgemeine Namen oder organisatorische Einheiten einschränken.

Die mit Adobe-Anwendungen installierten digitalen X.509-Zertifikate ermöglichen auch den Austausch von Informationen über Secure Sockets Layer (SSL). SSL sichert Übertragungen über HTTP mithilfe eines Verschlüsselungssystems mit öffentlichem und privatem Schlüssel. Die Implementierung von SSL durch Adobe unterstützt 1024-Bit-RSA-Schlüssel und verwendet einen 128-Bit-RC4-Verschlüsselungsalgorithmus.

Neben der Sicherheit dient das von Ihnen installierte digitale Zertifikat auch als Lizenzschlüssel, mit dem Sie das installierte [!DNL Report Server] ausführen können. Um ordnungsgemäß zu funktionieren, muss ein digitales Zertifikat knotenspezifisch und aktuell sein, andernfalls wird die Anwendung nicht gestartet.

## Knotenspezifische Zertifikate {#section-3338f1558e7844888dced8f395888744}

Ein knotenspezifisches Zertifikat ist ein digitales Zertifikat, das auf dem Computer registriert wurde, auf dem es installiert ist. Der Zusatz „knotenspezifisch“ bedeutet, dass das jeweilige Zertifikat dauerhaft mit einer bestimmten Knoten-ID (einem Wert, der einen bestimmten Computer eindeutig identifiziert) verknüpft ist. Für ein knotenspezifisches Zertifikat ist es erforderlich, dass Ihr Computer Internetzugriff auf den Adobe-Lizenzserver oder auf einen Proxyserver mit Zugriff auf den Lizenzserver hat.

Wenn Sie eine Installation auf einem Computer durchführen, der nicht auf das Internet zugreifen kann, müssen Sie ein spezielles vorgesperrtes Zertifikat abrufen und installieren, wie unter [Verwenden digitaler Zertifikate auf Computern ohne Internetzugang](../../../../home/c-rpt-oview/c-inst-rpt/c-install-dig-cert/c-underst-dig-cert.md#section-18cce05e2204407bb2b6b75deab9197d) auf dieser Seite beschrieben.

Wenn Sie eine Installation auf einem Computer durchführen, der auf das Internet zugreifen kann, wird Ihr digitales Zertifikat automatisch beim ersten Start von [!DNL Report Server] knotenspezifisch. Wenn es knotenspezifisch ist, kann das Zertifikat auf keinem anderen Computer verwendet werden. Wenn Sie [!DNL Report Server] auf einen anderen Computer migrieren müssen, müssen Sie ein neues, entsperrtes Zertifikat von Adobe erhalten.

## Aktuelle Zertifikate {#section-b4053ab714514dfb97ea7f61bbb8da1e}

Digitale Zertifikate müssen nicht nur knotenspezifisch, sondern zudem auch aktuell sein. Um auf dem neuesten Stand zu bleiben, muss Ihr Zertifikat regelmäßig erneuert werden (in der Regel alle 30 Tage, kann aber je nach Vereinbarung mit Adobe variieren). Wenn Ihr Computer über Internetzugang verfügt, ist der Erneuerungsvorgang vollkommen transparent. [!DNL Report Server] stellt automatisch eine Verbindung zum Lizenzserver her und überprüft das Zertifikat bei Bedarf erneut. Wenn Ihr Computer keinen Internetzugang hat, müssen Sie die aktualisierten Zertifikate manuell installieren, wie im folgenden Abschnitt beschrieben.

## Verwenden digitaler Zertifikate auf Computern ohne Internetzugang {#section-18cce05e2204407bb2b6b75deab9197d}

Wenn Sie eine Installation auf einem Computer durchführen, der nicht auf das Internet zugreifen kann, müssen Sie ein vorgesperrtes Zertifikat für Ihre Installation von [!DNL Report Server] anfordern. Ein vorgesperrtes Zertifikat ist ein digitales Zertifikat, das von Adobe manuell für die Knoten-ID des Computers festgelegt wird.

Um ein vorgesperrtes Zertifikat anzufordern, müssen Sie die Knoten-ID und Ihre Zertifikatnummer an die Adobe-Kundenunterstützung senden. Wenden Sie sich an die Kundenunterstützung von Adobe, um die Adobe [!DNL Node Identifier] anzufordern, um die Knoten-ID für Ihren Computer abzurufen. Sie können die Knoten-ID auch aus der Warnung abrufen, die [!DNL Report Server] aufruft, wenn versucht wird, eine Verbindung zum Lizenzserver herzustellen, aber nicht möglich ist. Wenn Sie das vorgesperrte Zertifikat erhalten, installieren Sie es wie in den letzten beiden Schritten der [Installationsverfahren für digitale Zertifikate](../../../../home/c-rpt-oview/c-inst-rpt/c-install-dig-cert/t-dig-cert-install-proc.md#task-5c4bb352ff534b40adc46dd053874e5d) beschrieben.

Wenn das Zertifikat erneut validiert werden muss, müssen Sie ein neues validiertes Zertifikat vom Lizenzserver herunterladen und auf Ihrem Computer neu installieren (sofern Ihre Vereinbarung mit Adobe nichts anderes vorsieht).
