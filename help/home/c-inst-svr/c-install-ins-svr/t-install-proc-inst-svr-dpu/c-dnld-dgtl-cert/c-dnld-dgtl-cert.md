---
description: Allgemeine Informationen zu digitalen Zertifikaten und Verfahren zum Herunterladen und Installieren.
title: Herunterladen und Installieren der digitalen Zertifikate
uuid: ac484e96-21dc-4643-ae74-01ac957e30ee
exl-id: 8aae9b63-7df0-4725-9833-711246bbe746
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: ht
source-wordcount: '916'
ht-degree: 100%

---

# Herunterladen und Installieren der digitalen Zertifikate {#downloading-and-installing-the-digital-certificates}

Allgemeine Informationen zu digitalen Zertifikaten und Verfahren zum Herunterladen und Installieren.

* [Grundlagen zu digitalen Zertifikaten](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-e48a776ef39042759d1dfb3444996d8b)
* [Knotenspezifische Zertifikate](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-b3dc7dcf2aa3439cbe66b0461b42d485)
* [Aktuelle Zertifikate](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-15aabaa8625c46edaa7436e1f3fc29c5)
* [Verwenden digitaler Zertifikate auf Computern ohne Internetzugang](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-809366329a7d4e198f95fe06c1f534fa)
* [Verfahren für die Installation von digitalen Zertifikaten](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-19f31676aad344a98e26e4fca1fad03b)

## Grundlagen zu digitalen Zertifikaten {#section-e48a776ef39042759d1dfb3444996d8b}

Adobe verwendet digitale X.509-Zertifikate, um die Client- und Serverkomponenten, aus denen eine Implementierung besteht, zu identifizieren und zu authentifizieren.

Bei der Installation einer Serverkomponente ([!DNL Insight Server] oder [!DNL Repeater]), müssen Sie das digitale Zertifikat installieren, das von Adobe für die Komponente ausgestellt wurde. Wenn Sie mit Ihrer Adobe-Anwendung zu einem anderen Computer migrieren müssen, ist es erforderlich, ein neues Zertifikat von Adobe anzufordern. Wenden Sie sich dazu an die Kundenunterstützung von Adobe.

Der allgemeine Name, der in diesem Zertifikat angezeigt wird, identifiziert den Server anhand eines angegebenen Domänennamens (z. B. [!DNL vs001a.mycompany.com]). Wenn ein Serverclient eine Verbindung zu diesem Server herstellt, zeigt der Server dieses Zertifikat als Nachweis an, dass es sich tatsächlich um den Server handelt, den der Client angefordert hat.

Ebenso müssen Sie bei der Installation eines Serverclients (z. B. [!DNL Insight] oder [!DNL Report]) das digitale Zertifikat installieren, das eine benannte Person (z. B. Jane Smith) zur Verwendung der installierten Clientanwendung autorisiert. Wenn Sie mit Ihrer Adobe-Anwendung zu einem anderen Computer oder einem anderen benannten Benutzer migrieren müssen, ist es erforderlich, ein neues Zertifikat von Adobe abzurufen. Wenden Sie sich dazu an die Kundenunterstützung von Adobe.

Die Clientanwendung präsentiert dieses digitale Zertifikat, um Zugriff auf eine Serverkomponente zu erhalten. Ein Administrator der Serverkomponente kann den Zugriff auf Serverressourcen auf Grundlage der im Zertifikat des Kunden angezeigten Werte für allgemeine Namen oder organisatorische Einheiten einschränken.

Die mit Adobe-Anwendungen installierten digitalen X.509-Zertifikate ermöglichen auch den Austausch von Informationen über Secure Sockets Layer (SSL). SSL sichert Übertragungen über HTTP mithilfe eines Verschlüsselungssystems mit öffentlichem und privatem Schlüssel. Die Implementierung von SSL durch Adobe unterstützt 1024-Bit-RSA-Schlüssel und verwendet einen 128-Bit-RC4-Verschlüsselungsalgorithmus.

Neben der Sicherheit werden die von Ihnen installierten digitalen Zertifikate auch als Lizenzschlüssel verwendet, mit denen Sie die installierte Adobe-Software ausführen können. Damit die Anwendung ordnungsgemäß funktioniert, muss das digitale Zertifikat knotenspezifisch und aktuell sein. Andernfalls startet die Anwendung nicht.

## Zeichenfolgenverschlüsselung {#section-8abe6b2d95704d38a04137d5c4602f0b}

Weitere Informationen zum Verschlüsseln von Kennwörtern finden Sie unter [Zeichenfolgenverschlüsselung](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/string-encryption.md#concept-35da0b53650a4d7e82b240ad27f6d45a).

## Knotenspezifische Zertifikate {#section-b3dc7dcf2aa3439cbe66b0461b42d485}

Ein knotenspezifisches Zertifikat ist ein digitales Zertifikat, das auf dem Computer registriert wurde, auf dem es installiert ist. Der Zusatz „knotenspezifisch“ bedeutet, dass das jeweilige Zertifikat dauerhaft mit einer bestimmten Knoten-ID (einem Wert, der einen bestimmten Computer eindeutig identifiziert) verknüpft ist. Für ein knotenspezifisches Zertifikat ist es erforderlich, dass Ihr Computer Internetzugriff auf den Adobe-Lizenzserver oder auf einen Proxyserver mit Zugriff auf den Lizenzserver hat.

Wenn Sie eine Installation auf einem Computer ohne Internetzugang durchführen, müssen Sie ein spezielles vorgesperrtes Zertifikat wie unter [Verwenden digitaler Zertifikate auf Computern ohne Internetzugang](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-809366329a7d4e198f95fe06c1f534fa) beschrieben abrufen und installieren.

Wenn Sie eine Installation auf einem Computer durchführen, der auf das Internet zugreifen kann, wird Ihr digitales Zertifikat automatisch beim ersten Starten Ihres Adobe-Produkts zu einem knotenspezifischen Zertifikat. Wenn es knotenspezifisch ist, kann das Zertifikat auf keinem anderen Computer verwendet werden. Wenn Sie mit Ihrem Adobe-Produkt zu einem anderen Computer migrieren müssen, ist es erforderlich, ein neues, nicht knotenspezifisches Zertifikat von Adobe abzurufen.

## Aktuelle Zertifikate {#section-15aabaa8625c46edaa7436e1f3fc29c5}

Digitale Zertifikate müssen nicht nur knotenspezifisch, sondern zudem auch aktuell sein. Um auf dem neuesten Stand zu bleiben, muss Ihr Zertifikat regelmäßig erneuert werden (in der Regel alle 30 Tage; dies kann aber je nach Vereinbarung mit der Adobe variieren). Wenn Ihr Computer über Internetzugang verfügt, ist der Erneuerungsvorgang vollkommen transparent. Ihr Adobe-Produkt stellt automatisch eine Verbindung zum Lizenzserver her und überprüft das Zertifikat bei Bedarf erneut. Wenn Ihr Computer keinen Internetzugang hat, müssen Sie die aktualisierten Zertifikate manuell installieren, wie im folgenden Abschnitt beschrieben.

## Verwenden digitaler Zertifikate auf Computern ohne Internetzugang {#section-809366329a7d4e198f95fe06c1f534fa}

Wenn Sie eine Installation auf einem Computer durchführen, der nicht auf das Internet zugreifen kann, müssen Sie ein vorgesperrtes Zertifikat für Ihre Installation von [!DNL Insight Server] anfordern. Ein vorgesperrtes Zertifikat ist ein digitales Zertifikat, das von Adobe manuell für die Knoten-ID des Computers festgelegt wird.

Um ein vorgesperrtes Zertifikat anzufordern, müssen Sie die Knoten-ID und Ihre Zertifikatnummer an die Adobe-Kundenunterstützung senden. Um die Knoten-ID für Ihren Computer abzurufen, wenden Sie sich an die Adobe-Kundenunterstützung, um das Adobe Node Identifier-Dienstprogramm anzufordern. Sie können die Knoten-ID auch über die Warnung abrufen, die die Adobe-Software ausgibt, wenn erfolglos versucht wird, eine Verbindung zum Lizenzserver herzustellen.

Wenn Sie das vorgesperrte Zertifikat erhalten, installieren Sie es wie in den letzten beiden Schritten der [Installationsverfahren für digitale Zertifikate](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-19f31676aad344a98e26e4fca1fad03b) beschrieben. Wenn eine erneute Validierung des Zertifikats erforderlich ist, müssen Sie ein neues, validiertes Zertifikat vom Lizenzserver herunterladen und auf Ihrem Computer neu installieren.

## Verfahren für die Installation von digitalen Zertifikaten {#section-19f31676aad344a98e26e4fca1fad03b}

**So laden Sie das digitale Zertifikat herunter und installieren es**

1. Öffnen Sie Ihren Webbrowser unter [https://aap.adobe.com](https://aap.adobe.com).

   >[!NOTE]
   >
   >Ihr Browser fordert Sie an dieser Stelle möglicherweise auf, ein digitales Zertifikat vorzulegen. Wenn dies der Fall ist, klicken Sie einfach auf **[!UICONTROL Cancel]**, um das Dialogfeld zu schließen.

1. Geben Sie auf dem Anmeldebildschirm die von Adobe erhaltenen Werte für **[!UICONTROL Account Name]** und **[!UICONTROL Password]** ein, und klicken Sie dann auf **[!UICONTROL login]**.

1. Suchen Sie nach dem Zertifikat, das für Sie ausgestellt wurde, [!DNL Insight Server] und klicken Sie dann auf das dem Zertifikat zugeordnete Symbol.

   >[!NOTE]
   >
   >Notieren Sie sich den diesem Zertifikat zugewiesenen allgemeinen Namen. Sie benötigen diesen Namen in einem späteren Schritt.

1. Wenn Sie aufgefordert werden, das Zertifikat zu speichern, klicken Sie auf **[!UICONTROL Save]**. (Beachten Sie, dass der Name der Datei mit dem allgemeinen Namen übereinstimmt, der dem Zertifikat zugeordnet ist.)
1. Laden Sie die Datei in den Ordner [!DNL Certificates] herunter, in dem Sie [!DNL Insight Server] installiert haben. Dieser Ordner enthält bereits eine Zertifikatdatei mit dem Namen [!DNL trust_ca_cert.pem]. Diese Zertifikatdatei muss immer vorhanden sein.

1. Benennen Sie die heruntergeladene Zertifikatdatei um und geben Sie ihr den folgenden Namen:

[!DNL server_cert.pem]
