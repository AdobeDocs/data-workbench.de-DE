---
description: Die Datei "Access Control.cfg"verwaltet den Zugriff auf bestimmte Funktionen in Insight Server.
solution: Insight
title: Aktualisieren der Zugriffssteuerungsdatei
uuid: f73651e5-6a8b-45fc-8f36-6751304dc53c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Aktualisieren der Zugriffssteuerungsdatei{#updating-the-access-control-file}

Die Datei &quot;Access Control.cfg&quot;verwaltet den Zugriff auf bestimmte Funktionen in Insight Server.

Es definiert Entitäten mit der Bezeichnung AccessGroups. Eine AccessGroup identifiziert eine Gruppe von Benutzern, die berechtigt sind, bestimmte Funktionen des Servers zu verwenden.

Bevor Sie eine Verbindung [!DNL Insight Server] mit herstellen können, müssen Sie die AccessGroup von Administratoren aktualisieren, um eine der [!DNL Insight][!DNL Insight] Lizenzen einzuschließen, die Adobe für Ihr Unternehmen ausgestellt hat. Diese AccessGroup identifiziert Benutzer, über die Verwaltungsfunktionen ausgeführt werden dürfen [!DNL Insight].

Im folgenden Verfahren wird beschrieben, wie Sie der AccessGroup von Administratoren eine Lizenz hinzufügen. Um diese Aufgabe abzuschließen, müssen Sie festlegen, welche [!DNL Insight] Lizenz über Administratorrechte für Ihr Unternehmen verfügt. (Für die Ersteinrichtung und -konfiguration reicht es aus, einer einzigen Lizenz Administratorrechte zu gewähren. Sie können zu einem späteren Zeitpunkt Administratorrechte für zusätzliche Lizenzen erteilen.) Sie müssen auch den dieser Lizenz zugewiesenen &quot;gemeinsamen Namen&quot;kennen. Um diesen Wert abzurufen, können Sie die Lizenzzertifikate für Ihr Konto unter [https://aap.adobe.com](https://aap.adobe.com)überprüfen.

Der Zweck dieses Verfahrens besteht lediglich darin, eine lizenzierte Kopie zu identifizieren, [!DNL Insight] die Sie zum ersten Mal einrichten und konfigurieren können [!DNL Insight Server]. Nachdem Sie diese Lizenz identifiziert haben, können Sie alle nachfolgenden Serverkonfigurationen (einschließlich zusätzlicher AccessGroup-Konfigurationen) mit der lizenzierten Kopie von durchführen [!DNL Insight]. Weitere Informationen zum Steuern des Zugriffs auf den Server mithilfe von AccessGroups finden Sie unter [Konfigurieren der Zugriffssteuerung](../../../../home/c-inst-svr/c-admin-inst-svr/c-config-acs-ctrl/c-config-acs-ctrl.md#concept-ac385e870dbe4b57a72bf7266b60f93d).

**So aktualisieren Sie die Zugriffssteuerungsdatei**

1. Navigieren Sie zu dem [!DNL Access Control] Ordner, in dem Sie installiert haben [!DNL Insight Server].

   Beispiel: [!DNL C:\Adobe\Server\Access Control]

1. Öffnen Sie die [!DNL Access Control.cfg] Datei in einem Texteditor wie Notepad.
1. Suchen Sie den CN-Eintrag in der AccessGroup von Administratoren und ersetzen Sie den vorhandenen Wert dieses Eintrags durch den gemeinsamen Namen, der den Namen angibt, den Sie zum ersten Mal einrichten und verwalten [!DNL Insight] möchten [!DNL Insight Server]. Das folgende Dateifragment zeigt, wo Sie den allgemeinen Namen in die [!DNL Access Control.cfg] Datei einfügen.

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

   Wenn Sie die anmeldebasierte Authentifizierung verwenden, stehen Ihnen einige zusätzliche Einträge zur Konfiguration zur Verfügung. Diese Einträge sind:

   * O (Organisations-ID): Dieser Eintrag stellt die ID der Organisation dar. Beispiel: `1 = string: O:46F582D4582596B40A45491@ExampleOrg`. Diese ID befindet sich in der Admin-Konsole.
   * PLC - Dieser Eintrag erlaubt den Zugriff auf die Benutzer, die für eine bestimmte Produktkonfiguration bereitgestellt wurden. Es kann im Format verwendet werden `Organization_Id-PLC`. Beispiel: `1 = string: PLC:46F582D4582596B40A45491@ExampleOrg-DataworkbenchAdminUsers`. Die Benutzer, die mit der PLC für Data Workbench bereitgestellt wurden, `DataworkbenchAdminUsers` erhalten Zugriff auf ihre Server.
   * E-Mail - Dieser Eintrag erlaubt den Zugriff auf jeden einzelnen Benutzer. Der Wert sollte die E-Mail-Adresse des bereitgestellten Benutzers sein. Beispiel: `1 = string: Email:kim@exampleorg.com`.
   >[!NOTE]
   >
   >
   >    
   >    
   >    * Bei den Einträgen wird zwischen Groß- und Kleinschreibung unterschieden. Sie müssen sicherstellen, dass die für O, PLC und E-Mail angegebenen Werte mit denen in der Admin-Konsole identisch sind.
   >    * Geben Sie den allgemeinen Namen genau so ein, wie er im Zertifikat angezeigt wird.
   >    * Verwenden Sie nicht die Tabulatortaste, um Leerzeichen in der [!DNL Access Control.cfg] Datei (oder in einer anderen Konfigurationsdatei für eine Adobe-Komponente) zu generieren. Verwenden Sie nur Leerzeichen, um Leerzeichen zu erstellen. Ein Tabulatorzeichen verhindert, dass das System die Datei richtig liest.


1. Speichern und schließen Sie die Datei.

