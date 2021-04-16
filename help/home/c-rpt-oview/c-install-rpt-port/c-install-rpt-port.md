---
description: Um Report Portal verwenden zu können, müssen Sie einen Satz von Anwendungsserverseiten (ASPs) auf IIS installieren und konfigurieren.
title: Installieren von Report Portal
uuid: 6aeb6038-b0b0-48b9-a020-bc9dfd703c43
exl-id: c6f140d4-a4fe-48e2-bbcd-b43efb2387dd
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 4%

---

# Installieren von Report Portal{#installing-the-report-portal}

Um Report Portal verwenden zu können, müssen Sie einen Satz von Anwendungsserverseiten (ASPs) auf IIS installieren und konfigurieren.

**Vorabinformationen**

Die Verfahren in diesem Kapitel beschreiben, wie [!DNL Report Portal] installiert und konfiguriert wird. Um diese Vorgänge abzuschließen, müssen Sie:

* Microsoft IIS installiert haben und dessen Version kennen.
* Kenne die Namen der Berichtssätze, deren Berichte von [!DNL Report Portal] angezeigt werden.
* Erkennen Sie den Speicherort des Ordners, in dem [!DNL Report Server] die Ausgabe für diese Berichtssätze speichert. Vergewissern Sie sich, dass der IIS-Anwendungsserver Zugriff auf diesen Ordner hat.

>[!NOTE]
>
>* Um mit [!DNL Report Portal] angezeigt zu werden, müssen Berichte bestimmten Benennungskonventionen entsprechen. Darüber hinaus muss der Ordner, in dem Berichte gespeichert werden, einer vorgegebenen Struktur entsprechen. Eine Beschreibung dieser Anforderungen finden Sie unter [Sicherstellen, dass Ihre Report Suites mit Report Portal kompatibel sind...](../../../home/c-rpt-oview/c-install-rpt-port/c-rpt-port-user-inter.md#section-2b141e5d198a4bbea455699126c24706).
   >
   >
* Passwörter im Report Portal sind jetzt AES-256-Bit-kompatibel. Erhöhen Sie bei einem Upgrade auf Report Portal 2.0 das Feld Feldgröße für Kennwort in der Datenbank **users.mdb** von 50 auf 150. Eine Erhöhung der Feldgröße ist erforderlich, um Kennwörter mit aktualisierter Verschlüsselung aufzunehmen.
>* Wenn Sie auf Report Portal 2.0 aktualisieren, erhöhen Sie die Feldgröße für das Feld **Kennwort** in der Datenbank users.mdb von 50 auf 150. Eine Erhöhung der Feldgröße ist erforderlich, um Kennwörter mit aktualisierter Verschlüsselung aufzunehmen.
>* Das Report Portal bietet jetzt verbesserte Hashing-Algorithmen mit Salting-Unterstützung. Wenn Sie ein Upgrade auf **Report Portal 2.1** durchführen, fügen Sie ein neues Textfeld mit der Feldgröße *PasswordSalt* in der [!DNL users.mdb]Datenbank ein. Dieses Feld ist erforderlich, um das Passwortsalz zu speichern.

>


