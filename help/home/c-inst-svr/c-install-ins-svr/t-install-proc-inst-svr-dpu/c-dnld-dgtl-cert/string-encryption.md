---
description: Verschlüsseln Sie Kennwörter und andere Zeichenfolgen bei der Kommunikation zwischen Client und Server.
title: Zeichenfolgenverschlüsselung
uuid: b2ec6a10-136c-4694-a425-04dbb41d43d1
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Zeichenfolgenverschlüsselung{#string-encryption}

Verschlüsseln Sie Kennwörter und andere Zeichenfolgen bei der Kommunikation zwischen Client und Server.

Bei der Kommunikation zwischen dem Data Workbench-Client (Workstation) und dem Server können Sie einen Value-Parameter (z. B. ein Kennwort) mit dem Typ *EncryptedString* speichern. Dadurch wird der Parameter ausgeblendet und die Zeichenfolge wird im *Windows Credential Store* auf dem Server mit dem entsprechenden Schlüssel zurückgegeben. Hierbei werden in erster Linie in Exporten verwendete Anmeldeinformationen gespeichert, können aber zum Verschlüsseln von Parametern verwendet werden.

* Unter Server\**EncryptStrings** wurde ein neuer Ordner hinzugefügt.

   Hier legen Sie die Konfigurationsdatei auf Verschlüsseln von Zeichenfolgen fest.

* Eine neue Konfigurationsdatei wurde unter Server\Component\**EncryptedStrings.cfg** hinzugefügt.

   ```
   component = EncryptionComponent:
     Path = Path: EncryptStrings\\*.cfg
   ```

   Diese Datei fragt den Ordner *Server*\*EncryptStrings* nach Verschlüsselungskonfigurationsdateien ab.

**So verschlüsseln Sie eine Zeichenfolge**:

1. Erstellen Sie eine **EncryptedStrings.cfg** -Konfigurationsdatei für eine Zeichenfolge mit den folgenden Feldern:

   ```
   Names = vector: 1 items
    0 = NameEncryptValuePair:
     EncryptValue = EncryptedString: // left empty as input then output will be filled by server
     Name = string: // Name for identifier 
     Value = string: // Value to be encrypted
   ```

   * *Wert* : Dieses Feld enthält die Nur-Text-Zeichenfolge, die verschlüsselt werden muss.

      Dies ist nur serverseitige Verschlüsselung. Die *Einstellung &quot;Wert* &quot;wird nur auf dem Servercomputer verschlüsselt.

   * *Name* - Dieses Feld enthält einen Wert, der die verschlüsselte Zeichenfolge identifiziert.
   * *EncryptValue* - Dieses Feld wird in der Eingabekonfigurationsdatei leer gelassen. Der verschlüsselte Wert wird in diesem Feld zurückgegeben.
   Sie können mehrere **NameEncryptValuePair** -Werte für verschiedene Felder zur Verschlüsselung hinzufügen.

   >[!NOTE]
   >
   >Alle leeren Wertefelder werden entfernt.

1. Speichern Sie die Datei **EncryptedStrings.cfg** im Ordner Server\**EncryptStrings**.

**Ausgabedatei**

Eine Ausgabedatei wird mit demselben Namen wie die Eingabedatei mit einem &lt;*Dateiname*> generiert.*verschlüsselte* Erweiterung. Wenn die Eingabedatei beispielsweise den Namen *sample.cfg* hat, erhält die Ausgabedatei den Namen *sample.cfg.encrypted*.
