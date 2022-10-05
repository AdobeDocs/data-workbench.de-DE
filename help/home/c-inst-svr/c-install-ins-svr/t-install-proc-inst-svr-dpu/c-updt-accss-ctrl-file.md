---
description: Die Datei Access Control.cfg verwaltet den Zugriff auf bestimmte Funktionen in Insight Server.
title: Aktualisieren der Datei für die Zugangssteuerung
uuid: f73651e5-6a8b-45fc-8f36-6751304dc53c
exl-id: 551758c1-f24b-49e6-ab6e-09979511e4f4
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '490'
ht-degree: 3%

---

# Aktualisieren der Datei für die Zugangssteuerung{#updating-the-access-control-file}

{{eol}}

Die Datei Access Control.cfg verwaltet den Zugriff auf bestimmte Funktionen in Insight Server.

Sie definiert Entitäten, die AccessGroups genannt werden. Eine AccessGroup gibt eine Gruppe von Benutzern an, die zur Verwendung bestimmter Funktionen des Servers berechtigt sind.

Bevor Sie eine Verbindung zu [!DNL Insight Server] mit [!DNL Insight]müssen Sie die AccessGroup der Administratoren so aktualisieren, dass eine der [!DNL Insight] -Lizenzen, die die Adobe Ihrer Organisation erteilt hat. Diese AccessGroup identifiziert Benutzer, die Administratorfunktionen über ausführen dürfen. [!DNL Insight].

Im folgenden Verfahren wird beschrieben, wie Sie der AccessGroup der Administratoren eine Lizenz hinzufügen. Um diese Aufgabe abzuschließen, müssen Sie festlegen, welche [!DNL Insight] -Lizenz hat Administratorrechte für Ihr Unternehmen. (Für die Ersteinrichtung und -konfiguration reicht es aus, einer einzigen Lizenz Administratorrechte zu gewähren. Sie können zusätzlichen Lizenzen später Administratorrechte gewähren.) Sie müssen auch den dieser Lizenz zugewiesenen &quot;gemeinsamen Namen&quot;kennen. Um diesen Wert zu erhalten, können Sie die Lizenzzertifikate für Ihr Konto unter [https://aap.adobe.com](https://aap.adobe.com).

Dieser Vorgang dient lediglich der Identifizierung einer lizenzierten Kopie von [!DNL Insight] Sie können verwenden, um zunächst [!DNL Insight Server]. Sobald Sie diese Lizenz identifiziert haben, können Sie alle nachfolgenden Serverkonfigurationen (einschließlich zusätzlicher AccessGroup-Konfigurationen) mit der lizenzierten Kopie von [!DNL Insight]. Weitere Informationen zum Steuern des Serverzugriffs mithilfe von AccessGroups finden Sie unter [Konfigurieren der Zugriffssteuerung](../../../../home/c-inst-svr/c-admin-inst-svr/c-config-acs-ctrl/c-config-acs-ctrl.md#concept-ac385e870dbe4b57a72bf7266b60f93d).

**Aktualisieren der Zugriffssteuerungsdatei**

1. Navigieren Sie zum [!DNL Access Control] Ordner im Verzeichnis, in dem Sie installiert haben [!DNL Insight Server].

   Beispiel: [!DNL C:\Adobe\Server\Access Control]

1. Öffnen Sie die [!DNL Access Control.cfg] in einem Texteditor wie Notepad.
1. Suchen Sie den KN-Eintrag in der Zugriffsgruppe der Administratoren und ersetzen Sie den vorhandenen Wert dieses Eintrags durch den gemeinsamen Namen, der die [!DNL Insight] die Sie zum ersten Mal verwenden werden, um [!DNL Insight Server]. Das folgende Dateifragment zeigt, wo Sie den allgemeinen Namen in die [!DNL Access Control.cfg] -Datei.

   ```
   Access Control Groups = vector: 5 items 
     0 = AccessGroup: 
       Members = vector: 2 items 
         0 = string: IP:127.0.0.1 
         1 = string: CN: CommonName 
       Name = string: Administrators 
       Read-Only Access = vector: 0 items 
       Read-Write Access = vector: 1 items 
         0 = string: / 
     1 = AccessGroup: 
     . . . 
   ```

   Wenn Sie anmeldebasierte Authentifizierung verwenden, stehen Ihnen einige zusätzliche Einträge zur Konfiguration zur Verfügung. Diese Einträge sind:

   * O (Organisations-ID): Dieser Eintrag stellt die Kennung der Organisation dar. Zum Beispiel `1 = string: O:46F582D4582596B40A45491@ExampleOrg`. Diese ID finden Sie in der -Admin Console.
   * PLC - Dieser Eintrag ermöglicht den Zugriff auf die Benutzer, die für eine bestimmte Produktkonfiguration bereitgestellt wurden. Es kann im Format verwendet werden `Organization_Id-PLC`. Zum Beispiel `1 = string: PLC:46F582D4582596B40A45491@ExampleOrg-DataworkbenchAdminUsers`. Die Benutzer, die für die Data Workbench mit der PLC bereitgestellt wurden `DataworkbenchAdminUsers` erhält Zugriff auf ihre Server.
   * E-Mail - Dieser Eintrag ermöglicht den Zugriff auf jeden einzelnen Benutzer. Sein Wert sollte die E-Mail-Adresse des bereitgestellten Benutzers sein. Zum Beispiel `1 = string: Email:kim@exampleorg.com`.

   >[!NOTE]
   >
   >
   >    
   >    
   >    * Bei den Einträgen wird zwischen Groß- und Kleinschreibung unterschieden. Sie müssen sicherstellen, dass die für O, PLC und E-Mail angegebenen Werte mit denen in der Admin Console übereinstimmen.
   >    * Geben Sie den allgemeinen Namen genau so ein, wie er auf dem Zertifikat angezeigt wird.
   >    * Verwenden Sie nicht die Tabulatortaste, um Leerzeichen im [!DNL Access Control.cfg] -Datei (oder in einer anderen Konfigurationsdatei für eine Adobe-Komponente). Verwenden Sie nur Leerzeichen, um Leerzeichen zu erstellen. Ein Tabulatorzeichen verhindert, dass das System die Datei korrekt liest.


1. Speichern und schließen Sie die Datei.
