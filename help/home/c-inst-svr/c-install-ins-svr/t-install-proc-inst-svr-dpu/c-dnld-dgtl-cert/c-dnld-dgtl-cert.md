---
description: Allgemeine Informationen zu digitalen Zertifikaten und Verfahren zum Herunterladen und Installieren.
solution: Insight
title: Herunterladen und Installieren der digitalen Zertifikate
uuid: ac484e96-21dc-4643-ae74-01ac957e30ee
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Herunterladen und Installieren der digitalen Zertifikate{#downloading-and-installing-the-digital-certificates}

Allgemeine Informationen zu digitalen Zertifikaten und Verfahren zum Herunterladen und Installieren.

* [Digitale Zertifikate](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-e48a776ef39042759d1dfb3444996d8b)
* [Freigegebene Zertifikate](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-b3dc7dcf2aa3439cbe66b0461b42d485)
* [Aktuelle Zertifikate](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-15aabaa8625c46edaa7436e1f3fc29c5)
* [Digitale Zertifikate auf Computern ohne Internetzugang verwenden](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-809366329a7d4e198f95fe06c1f534fa)
* [Installationsverfahren für digitale Zertifikate](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-19f31676aad344a98e26e4fca1fad03b)

## Digitale Zertifikate {#section-e48a776ef39042759d1dfb3444996d8b}

Adobe verwendet digitale X.509-Zertifikate, um die Client- und Serverkomponenten, aus denen eine Implementierung besteht, zu identifizieren und zu authentifizieren.

Wenn Sie eine Serverkomponente ( [!DNL Insight Server] oder [!DNL Repeater]) installieren, müssen Sie das digitale Zertifikat installieren, das Adobe für die Komponente ausgestellt hat. Wenn Sie Ihre Adobe-Anwendung auf einen anderen Computer migrieren müssen, benötigen Sie ein neues Zertifikat von Adobe. Wenden Sie sich dazu an den Adobe-Kundendienst.

Der allgemeine Name, der in diesem Zertifikat angezeigt wird, identifiziert den Server anhand eines angegebenen Domänennamens (z. B. [!DNL vs001a.mycompany.com]). Wenn ein Server-Client eine Verbindung zu diesem Server herstellt, stellt der Server dieses Zertifikat als Beweis dafür vor, dass es sich tatsächlich um den Server handelt, den der Client angefordert hat.

Ebenso müssen Sie bei der Installation eines Serverclients (z. B. [!DNL Insight] oder [!DNL Report]) das digitale Zertifikat installieren, das eine benannte Person (z. B. Jane Smith) zur Verwendung der installierten Clientanwendung autorisiert. Wenn Sie Ihre Adobe-Anwendung auf einen anderen Computer oder einen anderen benannten Benutzer migrieren müssen, müssen Sie ein neues Zertifikat von Adobe abrufen. Wenden Sie sich dazu an den Adobe-Kundendienst.

Die Clientanwendung stellt dieses digitale Zertifikat zum Zugriff auf eine Serverkomponente vor. Ein Administrator der Serverkomponente kann den Zugriff auf Serverressourcen auf der Grundlage der im Zertifikat des Kunden angezeigten Werte für allgemeine Namen oder organisatorische Einheiten einschränken.

Die mit Adobe-Anwendungen installierten digitalen X.509-Zertifikate ermöglichen es seinen Client- und Serverkomponenten auch, Informationen über Secure Sockets Layer (SSL) auszutauschen. SSL sichert Übertragungen über HTTP mithilfe eines Verschlüsselungssystems mit öffentlichem und privatem Schlüssel. Die Implementierung von SSL von Adobe unterstützt 1024-Bit-RSA-Schlüssel und verwendet einen 128-Bit-RC4-Verschlüsselungsalgorithmus.

Neben der Sicherheit können die von Ihnen installierten digitalen Zertifikate auch als Lizenzschlüssel verwendet werden, mit denen Sie die installierte Adobe-Software ausführen können. Um ordnungsgemäß funktionieren zu können, muss ein digitales Zertifikat Node-gesperrt und aktuell sein, oder die Anwendung startet nicht.

## Zeichenfolgenverschlüsselung {#section-8abe6b2d95704d38a04137d5c4602f0b}

Weitere Informationen zum Verschlüsseln von Kennwörtern finden Sie unter [Zeichenfolgenverschlüsselung](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/string-encryption.md#concept-35da0b53650a4d7e82b240ad27f6d45a) .

## Freigegebene Zertifikate {#section-b3dc7dcf2aa3439cbe66b0461b42d485}

Ein knotengesperrtes Zertifikat ist ein digitales Zertifikat, das auf dem Computer registriert wurde, auf dem es installiert ist. Durch die Node-Sperrung wird ein Zertifikat dauerhaft mit einer bestimmten Node-ID (einem Wert, der eine bestimmte Maschine eindeutig identifiziert) verknüpft. Um Ihr Zertifikat zu sperren, muss Ihr Computer über Internetzugriff auf den Adobe License Server oder einen Proxyserver verfügen, der Zugriff auf den License Server hat.

Wenn Sie eine Installation auf einem Computer durchführen, der nicht auf das Internet zugreifen kann, müssen Sie ein spezielles vorgesperrtes Zertifikat abrufen und installieren, wie unter [Verwenden von digitalen Zertifikaten auf Computern ohne Internetzugang](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-809366329a7d4e198f95fe06c1f534fa)beschrieben.

Wenn Sie eine Installation auf einem Computer durchführen, der auf das Internet zugreifen kann, wird Ihr digitales Zertifikat automatisch beim ersten Starten Ihres Adobe-Produkts vom Knoten gesperrt. Nach dem Sperren des Knotens kann das Zertifikat auf keinem anderen Computer verwendet werden. Wenn Sie Ihr Adobe-Produkt auf einen anderen Computer migrieren müssen, benötigen Sie ein neues, entsperrtes Zertifikat von Adobe.

## Aktuelle Zertifikate {#section-15aabaa8625c46edaa7436e1f3fc29c5}

Neben der Node-Sperre muss ein digitales Zertifikat aktuell sein. Um auf dem neuesten Stand zu bleiben, muss Ihr Zertifikat regelmäßig erneuert werden (in der Regel alle 30 Tage, kann jedoch je nach Ihrer Vereinbarung mit Adobe variieren). Wenn Ihr Computer über Internetzugang verfügt, ist der Erneuerungsvorgang vollkommen transparent. Ihr Adobe-Produkt stellt automatisch eine Verbindung zum Lizenzserver her und überprüft das Zertifikat bei Bedarf erneut. Wenn Ihr Computer keinen Internetzugang hat, müssen Sie die aktualisierten Zertifikate manuell installieren, wie im folgenden Abschnitt beschrieben.

## Digitale Zertifikate auf Computern ohne Internetzugang verwenden {#section-809366329a7d4e198f95fe06c1f534fa}

Wenn Sie eine Installation auf einem Computer durchführen, der nicht auf das Internet zugreifen kann, müssen Sie ein vordefiniertes Zertifikat für Ihre Installation von [!DNL Insight Server]anfordern. Ein vorab gesperrtes Zertifikat ist ein digitales Zertifikat, das von Adobe manuell an die Node-ID des Computers gesperrt wird.

Um ein vorab gesperrtes Zertifikat anzufordern, müssen Sie die Node-ID und Ihre Zertifikatnummer an die Adobe-Kundenunterstützung senden. Um die Node-ID für Ihren Computer abzurufen, wenden Sie sich an den Adobe-Kundendienst, um das Adobe Node Identifier-Dienstprogramm anzufordern. Sie können die Node-ID auch aus der Warnung abrufen, die die Adobe-Software ausgibt, wenn sie versucht, eine Verbindung zum Lizenzserver herzustellen, und dies nicht.

Wenn Sie das vordefinierte Zertifikat erhalten, installieren Sie es wie in den letzten beiden Schritten der Installationsverfahren für [digitale Zertifikate beschrieben](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-19f31676aad344a98e26e4fca1fad03b). Wenn das Zertifikat erneut überprüft werden muss, müssen Sie ein neues, validiertes Zertifikat vom Lizenzserver herunterladen und auf Ihrem Computer neu installieren.

## Installationsverfahren für digitale Zertifikate {#section-19f31676aad344a98e26e4fca1fad03b}

**So laden Sie das digitale Zertifikat herunter und installieren es**

1. Öffnen Sie Ihren Webbrowser unter [https://aap.adobe.com](https://aap.adobe.com).

   >[!NOTE]
   >
   >Ihr Browser fordert Sie möglicherweise auf, zu diesem Zeitpunkt ein digitales Zertifikat vorzulegen. Wenn dies der Fall ist, klicken Sie einfach auf **[!UICONTROL Cancel]** , um das Dialogfeld zu schließen.

1. Geben Sie auf dem Anmeldebildschirm die Daten **[!UICONTROL Account Name]** und **[!UICONTROL Password]** die Daten ein, die Sie von Adobe erhalten haben, und klicken Sie dann auf **[!UICONTROL login]**.

1. Suchen Sie nach dem Zertifikat, das für Sie ausgestellt wurde, [!DNL Insight Server]und klicken Sie dann auf das Symbol, das dem Zertifikat zugeordnet ist.

   >[!NOTE]
   >
   >Notieren Sie sich den allgemeinen Namen, der diesem Zertifikat zugewiesen ist. Sie verwenden diesen Namen in einem späteren Schritt.

1. Wenn Sie zum Speichern des Zertifikats aufgefordert werden, klicken Sie auf **[!UICONTROL Save]**. (Beachten Sie, dass der Name der Datei mit dem allgemeinen Namen übereinstimmt, der dem Zertifikat zugeordnet ist.)
1. Laden Sie die Datei in den [!DNL Certificates] Ordner herunter, in dem Sie installiert haben [!DNL Insight Server]. Dieser Ordner enthält bereits eine Zertifikatdatei mit dem Namen [!DNL trust_ca_cert.pem]. Diese Zertifikatdatei muss immer vorhanden sein.

1. Benennen Sie die heruntergeladene Zertifikatdatei um in:

[!DNL server_cert.pem]

