---
description: Um Report Portal verwenden zu können, müssen Sie einen Satz von Anwendungsserverseiten (ASPs) auf IIS installieren und konfigurieren.
solution: Analytics
title: Installieren des Report Portals
topic: Data workbench
uuid: 6aeb6038-b0b0-48b9-a020-bc9dfd703c43
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Installieren des Report Portals{#installing-the-report-portal}

Um Report Portal verwenden zu können, müssen Sie einen Satz von Anwendungsserverseiten (ASPs) auf IIS installieren und konfigurieren.

**Vorabinformationen**

Die Verfahren in diesem Kapitel beschreiben, wie Sie installieren und konfigurieren [!DNL Report Portal]. Um diese Vorgänge abzuschließen, müssen Sie:

* Microsoft IIS installiert haben und dessen Version kennen.
* Erkennen Sie die Namen der Berichtssätze, nach denen die Berichte angezeigt werden [!DNL Report Portal].
* Erkennen Sie den Speicherort des Ordners, in dem die Ausgabe für diese Berichtssätze [!DNL Report Server] gespeichert wird. Vergewissern Sie sich, dass der IIS-Anwendungsserver Zugriff auf diesen Ordner hat.

>[!NOTE]
>
>* Damit Berichte angezeigt werden [!DNL Report Portal]können, müssen sie bestimmten Benennungskonventionen entsprechen. Darüber hinaus muss der Ordner, in dem Berichte gespeichert werden, eine vorgeschriebene Struktur aufweisen. Eine Beschreibung dieser Anforderungen finden Sie unter [Sicherstellen der Kompatibilität Ihrer Report Suites mit Report Portal...](../../../home/c-rpt-oview/c-install-rpt-port/c-rpt-port-user-inter.md#section-2b141e5d198a4bbea455699126c24706).
   >
   >
* Passwörter im Report Portal sind jetzt AES-256-Bit-kompatibel. Erhöhen Sie bei einem Upgrade auf Report Portal 2.0 das Feld &quot;Feldgröße für Kennwort&quot;in der Datenbank **users.mdb** von 50 auf 150. Eine Erhöhung der Feldgröße ist erforderlich, um Kennwörter mit aktualisierter Verschlüsselung aufzunehmen.
>* Wenn Sie auf Report Portal 2.0 aktualisieren, erhöhen Sie die Feldgröße für das Feld **Kennwort** in der Datenbank users.mdb von 50 auf 150. Eine Erhöhung der Feldgröße ist erforderlich, um Kennwörter mit aktualisierter Verschlüsselung aufzunehmen.
>* Das Report Portal bietet jetzt verbesserte Hashing-Algorithmen mit Salting-Unterstützung. Wenn Sie ein Upgrade auf **Report Portal 2.1** durchführen, fügen Sie ein neues Textfeld, *PasswordSalt* , mit einer Feldgröße von 20 Zeichen in der [!DNL users.mdb]Datenbank hinzu. Dieses Feld ist erforderlich, um das Passwortsalz zu speichern.
>



