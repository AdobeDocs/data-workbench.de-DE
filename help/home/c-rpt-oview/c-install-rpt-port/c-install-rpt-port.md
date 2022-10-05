---
description: Um Report Portal zu verwenden, müssen Sie eine Reihe von Anwendungsserverseiten (ASPs) in IIS installieren und konfigurieren.
title: Installieren von Report Portal
uuid: 6aeb6038-b0b0-48b9-a020-bc9dfd703c43
exl-id: c6f140d4-a4fe-48e2-bbcd-b43efb2387dd
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 4%

---

# Installieren von Report Portal{#installing-the-report-portal}

{{eol}}

Um Report Portal zu verwenden, müssen Sie eine Reihe von Anwendungsserverseiten (ASPs) in IIS installieren und konfigurieren.

**Vorabinformationen**

In diesem Kapitel wird beschrieben, wie Sie [!DNL Report Portal]. Um diese Verfahren abzuschließen, müssen Sie:

* Lassen Sie Microsoft IIS installiert und kennen Sie die Version.
* die Namen der Berichtssätze kennen, deren Berichte angezeigt werden durch [!DNL Report Portal].
* Den Speicherort des Ordners kennen, in dem sich [!DNL Report Server] speichert die Ausgabe für diese Berichtssätze. Stellen Sie sicher, dass der IIS-Anwendungsserver Zugriff auf diesen Ordner hat.

>[!NOTE]
>
>* Zur Anzeige mit [!DNL Report Portal]müssen Berichte bestimmte Benennungskonventionen einhalten. Darüber hinaus muss das Verzeichnis, in dem Berichte gespeichert werden, einer vorgegebenen Struktur entsprechen. Eine Beschreibung dieser Anforderungen finden Sie unter [Sicherstellung der Kompatibilität Ihrer Berichtssätze mit Report Portal..](../../../home/c-rpt-oview/c-install-rpt-port/c-rpt-port-user-inter.md#section-2b141e5d198a4bbea455699126c24706).
>
>* Passwörter im Report Portal sind jetzt AES-256-Bit-kompatibel. Erhöhen Sie bei der Aktualisierung auf Report Portal 2.0 die Feldgröße für Kennwort im Feld **users.mdb** Datenbank. Eine Erhöhung der Feldgröße ist erforderlich, um Passwörter mit aktualisierter Verschlüsselung aufzunehmen.
>* Wenn Sie ein Upgrade auf Report Portal 2.0 durchführen, erhöhen Sie die Feldgröße für **Passwort** -Feld von 50 bis 150 in der Benutzer.mdb-Datenbank. Eine Erhöhung der Feldgröße ist erforderlich, um Passwörter mit aktualisierter Verschlüsselung aufzunehmen.
>* Das Report Portal bietet jetzt verbesserte Hashing-Algorithmen mit Salting-Unterstützung. Wenn Sie ein Upgrade auf **Report Portal 2.1**, fügen Sie ein neues Textfeld hinzu, *PasswordSalt* mit einer Feldgröße von 20 Zeichen in [!DNL users.mdb]Datenbank. Dieses Feld ist erforderlich, um das Kennwortsalz zu speichern.
>

