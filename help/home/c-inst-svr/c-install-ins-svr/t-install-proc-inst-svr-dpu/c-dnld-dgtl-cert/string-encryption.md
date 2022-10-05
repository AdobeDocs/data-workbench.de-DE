---
description: Verschlüsseln Sie bei der Kommunikation zwischen Client und Server Passwörter und andere Strings.
title: Zeichenfolgenverschlüsselung
uuid: b2ec6a10-136c-4694-a425-04dbb41d43d1
exl-id: 43696ff1-3153-4d85-b9a9-c2752dd2c29a
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 1%

---

# Zeichenfolgenverschlüsselung{#string-encryption}

{{eol}}

Verschlüsseln Sie bei der Kommunikation zwischen Client und Server Passwörter und andere Strings.

Bei der Kommunikation zwischen dem Data Workbench-Client (Workstation) und dem Server können Sie einen Value-Parameter (z. B. ein Kennwort) mit dem Typ *EncryptedString*. Dadurch wird der Parameter ausgeblendet und der String im *Windows Credential Store* auf dem Server mit dem entsprechenden Schlüssel zurückgegeben. Dadurch werden hauptsächlich in Exporten verwendete Anmeldeinformationen gespeichert, können jedoch zum Verschlüsseln beliebiger Parameter verwendet werden.

* Unter Server\* wurde ein neuer Ordner hinzugefügt.*EncryptStrings**.

   Hier legen Sie die Konfigurationsdatei fest, um Zeichenfolgen zu verschlüsseln.

* Eine neue Konfigurationsdatei wurde unter Server\Component\* hinzugefügt.*EncryptedStrings.cfg**.

   ```
   component = EncryptionComponent:
     Path = Path: EncryptStrings\\*.cfg
   ```

   Diese Datei fragt die *Server* Ordner \*EncryptStrings* für Verschlüsselungskonfigurationsdateien.

**Verschlüsseln einer Zeichenfolge**:

1. Erstellen Sie eine **EncryptedStrings.cfg** Konfigurationsdatei für eine Zeichenfolge mit den folgenden Feldern:

   ```
   Names = vector: 1 items
    0 = NameEncryptValuePair:
     EncryptValue = EncryptedString: // left empty as input then output will be filled by server
     Name = string: // Name for identifier 
     Value = string: // Value to be encrypted
   ```

   * *Wert* - Dieses Feld enthält die Nur-Text-Zeichenfolge, die verschlüsselt werden muss.

      Dies ist nur serverseitige Verschlüsselung. Die *Wert* -Einstellung ist nur auf dem Servercomputer verschlüsselt.

   * *Name* - Dieses Feld enthält einen Wert, der die verschlüsselte Zeichenfolge identifiziert.
   * *EncryptValue* - Dieses Feld wird in der Eingabekonfiguration leer gelassen. Der verschlüsselte Wert wird in diesem Feld zurückgegeben.

   Sie können mehrere **NameEncryptValuePair** Werte für verschiedene Felder zur Verschlüsselung.

   >[!NOTE]
   >
   >Alle leeren Wertfelder werden entfernt.

1. Speichern Sie die **EncryptedStrings.cfg** Datei auf den Server\**EncryptStrings** Ordner.

**Ausgabedatei**

Eine Ausgabedatei wird mit demselben Namen wie die Eingabedatei mit einem &lt;*filename*>.*verschlüsselt* -Erweiterung. Wenn die Eingabedatei beispielsweise *sample.cfg* dann erhält die Ausgabedatei den Namen *sample.cfg.encrypted*.
