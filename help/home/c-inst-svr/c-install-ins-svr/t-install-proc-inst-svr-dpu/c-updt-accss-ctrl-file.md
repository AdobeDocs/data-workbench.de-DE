---
description: Die Datei "Zugriffskontrolle.cfg"verwaltet den Zugriff auf bestimmte Funktionen in Insight Server.
title: Aktualisieren der Datei für die Zugangssteuerung
uuid: f73651e5-6a8b-45fc-8f36-6751304dc53c
exl-id: 551758c1-f24b-49e6-ab6e-09979511e4f4
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '490'
ht-degree: 3%

---

# Aktualisieren der Datei für die Zugangssteuerung{#updating-the-access-control-file}

Die Datei &quot;Zugriffskontrolle.cfg&quot;verwaltet den Zugriff auf bestimmte Funktionen in Insight Server.

Es definiert Entitäten mit der Bezeichnung AccessGroups. Eine AccessGroup identifiziert eine Gruppe von Benutzern, die berechtigt sind, bestimmte Funktionen des Servers zu verwenden.

Bevor Sie eine Verbindung zu [!DNL Insight Server] mit [!DNL Insight] herstellen können, müssen Sie die AccessGroup von Administratoren aktualisieren, um eine der [!DNL Insight]-Lizenzen einzuschließen, die Ihre Adobe Ihrem Unternehmen erteilt hat. Diese AccessGroup identifiziert Benutzer, die Verwaltungsfunktionen über [!DNL Insight] ausführen dürfen.

Im folgenden Verfahren wird beschrieben, wie Sie der AccessGroup von Administratoren eine Lizenz hinzufügen. Um diese Aufgabe abzuschließen, müssen Sie festlegen, welche [!DNL Insight]-Lizenz über Administratorrechte für Ihr Unternehmen verfügt. (Für die Ersteinrichtung und -konfiguration reicht es aus, einer einzigen Lizenz Administratorrechte zu gewähren. Sie können später zusätzlichen Lizenzen Administratorrechte gewähren.) Sie müssen auch den dieser Lizenz zugewiesenen &quot;gemeinsamen Namen&quot;kennen. Um diesen Wert abzurufen, können Sie die Lizenzzertifikate für Ihr Konto unter [https://aap.adobe.com](https://aap.adobe.com) überprüfen.

Der Zweck dieses Verfahrens besteht lediglich darin, eine lizenzierte Kopie von [!DNL Insight] zu identifizieren, mit der Sie [!DNL Insight Server] zunächst einrichten und konfigurieren können. Nachdem Sie diese Lizenz identifiziert haben, können Sie alle nachfolgenden Serverkonfigurationen (einschließlich zusätzlicher AccessGroup-Konfigurationen) mit der lizenzierten Kopie von [!DNL Insight] durchführen. Weitere Informationen zum Steuern des Serverzugriffs mithilfe von AccessGroups finden Sie unter [Zugriffskontrolle konfigurieren](../../../../home/c-inst-svr/c-admin-inst-svr/c-config-acs-ctrl/c-config-acs-ctrl.md#concept-ac385e870dbe4b57a72bf7266b60f93d).

**So aktualisieren Sie die Zugriffskontrolle**

1. Navigieren Sie zum Ordner [!DNL Access Control] in dem Ordner, in dem Sie [!DNL Insight Server] installiert haben.

   Beispiel: [!DNL C:\Adobe\Server\Access Control]

1. Öffnen Sie die Datei [!DNL Access Control.cfg] in einem Texteditor wie Notepad.
1. Suchen Sie den CN-Eintrag in Administration AccessGroup und ersetzen Sie den vorhandenen Wert dieses Eintrags durch den allgemeinen Namen, der die [!DNL Insight] kennzeichnet, die Sie zum ersten Mal einrichten und verwalten werden. [!DNL Insight Server] Das folgende Dateifragment zeigt, wo Sie den allgemeinen Namen in die Datei [!DNL Access Control.cfg] einfügen.

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

   * O (Organisations-ID): Dieser Eintrag stellt die ID der Organisation dar. Beispiel: `1 = string: O:46F582D4582596B40A45491@ExampleOrg`. Diese ID befindet sich in der Admin Console.
   * PLC - Dieser Eintrag erlaubt den Zugriff auf die Benutzer, die für eine bestimmte Produktkonfiguration bereitgestellt wurden. Es kann im Format `Organization_Id-PLC` verwendet werden. Beispiel: `1 = string: PLC:46F582D4582596B40A45491@ExampleOrg-DataworkbenchAdminUsers`. Die zur Data Workbench mit dem PLC `DataworkbenchAdminUsers` bereitgestellten Benutzer erhalten Zugriff auf ihre Server.
   * E-Mail - Dieser Eintrag erlaubt den Zugriff auf jeden einzelnen Benutzer. Der Wert sollte die E-Mail-Adresse des bereitgestellten Benutzers sein. Beispiel: `1 = string: Email:kim@exampleorg.com`.

   >[!NOTE]
   >
   >
   >    
   >    
   >    * Bei den Einträgen wird zwischen Groß- und Kleinschreibung unterschieden. Sie müssen sicherstellen, dass die für O, PLC und E-Mail angegebenen Werte mit denen in der Admin Console identisch sind.
   >    * Geben Sie den allgemeinen Namen genau so ein, wie er im Zertifikat angezeigt wird.
   >    * Verwenden Sie nicht die Tabulatortaste, um Leerzeichen in der [!DNL Access Control.cfg]-Datei (oder in einer anderen Konfigurationsdatei für eine Adobe-Komponente) zu generieren. Verwenden Sie nur Leerzeichen, um Leerzeichen zu erstellen. Ein Tabulatorzeichen verhindert, dass das System die Datei richtig liest.


1. Speichern und schließen Sie die Datei.
