---
description: Administratoren können Workstationbenutzern die teilweise Verwaltung der Zugangssteuerung für Benutzergruppen erteilen.
title: Benutzeradministration des Zugriffs von Gruppenmitgliedern
uuid: c31128f9-1094-4337-9bf6-96401278df33
exl-id: 6d2a0f19-a33c-49f6-a470-c95d2c1532c7
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '732'
ht-degree: 6%

---

# Benutzeradministration des Zugriffs von Gruppenmitgliedern{#user-administration-of-group-member-access}

Administratoren können Workstationbenutzern die teilweise Verwaltung der Zugangssteuerung für Benutzergruppen erteilen.

**Die Selbstverwaltung des Gruppenmitglieds** verleiht Benutzern ohne Administratorrechte, Mitglieder einer benutzerspezifischen Gruppe hinzuzufügen und zu löschen. Der Administrator erstellt eine Datei **Benutzerliste** und richtet den Gruppenzugriff in der Datei [Zugriffssteuerung.cfg](https://experienceleague.adobe.com/docs/data-workbench/using/server-admin-install/admin-dwb-server/access-control/c-config-acs-ctrl.html) für die neuen Gruppenmitglieder ein.

**Zugriff auf den Server Manager**

Die Einrichtung der Datei **[!DNL User List]** und die Synchronisation mit der Datei **[!DNL Communications.cfg]** erfolgt im Arbeitsbereich **Server Manager** .

1. Klicken Sie auf der Arbeitsfläche auf die Registerkarte **Admin** > **Datensatz und Profil** .

1. Öffnen Sie den Arbeitsbereich **Server Manager** .
1. Klicken Sie mit der rechten Maustaste auf >*Ihr Servername* im Diagramm und wählen Sie **Dateien** aus.

   Die Serverdateien werden in einer Tabelle mit den Spalten *Datei*, *`<server name>`* und *Temp* geöffnet.

1. **Machen Sie** Localby, indem Sie mit der rechten Maustaste in die Serverspalte einer Serverdatei klicken (für diese Funktion  **[!DNL Access Control]** und  **[!DNL Components/Communications.cfg)]**).

   In der Spalte **Temp** wird ein weißes Häkchen angezeigt. Sie können sie im Ordner &quot;Temp&quot;bearbeiten. Klicken Sie dann mit der rechten Maustaste auf das Häkchen und **Speichern unter** den Server. (Beim Synchronisieren mit dem Server wird die Farbe rot).

## Erstellen einer Datei &quot;User List.cfg&quot; {#section-c25bcaf34f4546e6b8b65f5e7f69ac09}

Der Administrator muss eine **[!DNL User List.cfg]**-Datei im Ordner **[!DNL Access Control]** erstellen.

1. Klicken Sie mit der rechten Maustaste in die Zeile **Temp** und wählen Sie **Öffnen** > **Ordner**. ![](assets/6_4_workstation_groups_3.png).

   Der Ordner Zugriffskontrolle im Ordner **Temp** öffnet eine Liste mit einer einzelnen **[!DNL Access Control.cfg]**-Datei.

1. Fügen Sie diesem Ordner eine weitere Textdatei hinzu und nennen Sie sie **[!DNL User List.cfg]** (neben **[!DNL Access Control.cfg]**).

1. Fügen Sie der Datei **[!DNL User List.cfg]** die folgenden Parameter hinzu.

Die Datei &quot;Benutzerliste&quot;sollte einen Vektor von **AccessGroup** -Objekten enthalten. Jedes **AccessGroup** -Objekt sollte einen Namen und einen Vektor von Zeichenfolgen mit dem Namen **Mitglieder** enthalten.

```
Access Control Groups = vector: 1 items 
  0 = AccessGroup:  
    Name = string: Group 1 
    Members = vector: 1 items 
      0 = string: CN:Joe User
```

Sie können diese dann bearbeiten und Benutzer in der Workstation-Ansicht der Datei **[!DNL User List.cfg]**hinzufügen.

![](assets/6_4_workstation_groups_4.png)

Im Folgenden finden Sie die grundlegendsten Parameter, die Sie der Datei **[!DNL User List.cfg]** hinzufügen können. Die Mitglieder können dann in der Workstation-Ansicht hinzugefügt werden.

```
Access Control Groups = vector: 1 items 
  0 = AccessGroup:  
    Name = string:  
    Members = vector: 0 items
```

>[!IMPORTANT]
>
>Stellen Sie wie bei jeder **[!DNL .cfg]**-Datei, die Sie manuell bearbeiten, sicher, dass Sie Leerzeichen anstelle von Tabulatoren verwenden und dabei den Leerraum und die Syntax genau beachten. Ein Fehler in dieser Datei führt dazu, dass *Adobe Insight Server* die Benutzerlisten-Datei ignoriert.

Das Feld **Name** in jedem **Zugriffsgruppe** wird in der Datei [!DNL Access Control.cfg] referenziert.

>[!NOTE]
>
>Es werden nur gültige Mitglieder mit Verzeichnisdienstpräfixen wie **CN:** oder **OU:** akzeptiert, die keine Platzhalterzeichen (*) enthalten.

## Datei &quot;Communications.cfg&quot;einrichten {#section-9d6f05ba81c14f15be63e361533459e8}

Ein Administrator aktiviert diese Funktion zuerst, indem er die Datei **[!DNL Components]>[!DNL Communications.cfg]** öffnet und einen neuen Schlüssel mit dem Namen **[!DNL Access Control User List File]** hinzufügt. Der Zeichenfolgenwert dieses Schlüssels ist der Pfad, in dem sich diese neue Datei befindet.

1. Klicken Sie in den Serverdateien auf **Komponenten** und klicken Sie mit der rechten Maustaste auf das Häkchen in der Serverspalte. Klicken Sie auf **Make Local**.

   In der Spalte **Temp** wird ein weißes Häkchen angezeigt.

1. Klicken Sie mit der rechten Maustaste auf das Häkchen in der Spalte **Temp** und wählen Sie **Öffnen** > **in Workstation** aus.

1. Klicken Sie in der Datei **Communication.cfg** mit der rechten Maustaste auf **component** und wählen Sie **Benutzerdefinierten Schlüssel hinzufügen.** ![](assets/6_4_workstation_groups.png)

1. Geben Sie **Name** als *Zugriffssteuerungslisten-Datei* ein und setzen Sie **vom Typ** auf *String*.

   >[!NOTE]
   Sie können die neue Listendatei nicht als Pfad erstellen. Um dies zu beheben, müssen Sie die Datei speichern, sie in einem Editor (Editor) öffnen und &quot;String&quot;in &quot;Path&quot;ändern:

   Bevor:

   ```
   component = CommServer:  
     Access Control File = Path: Access Control\\Access Control.cfg 
     Access Control User List File =  
    <string>: Access Control\\User List.cfg
   ```

   Nachher:

   ```
   component = CommServer:  
     Access Control File = Path: Access Control\\Access Control.cfg 
     Access Control User List File =  
    <Path>: Access Control\\User List.cfg
   ```

1. Speichern Sie die Datei **[!DNL Communications.cfg]** und speichern Sie sie (falls erforderlich) auf dem Server. Dadurch werden Komponenten auf dem Server neu gestartet, um sicherzustellen, dass Sie keine Fehler gemacht haben, die die Analyse der **[!DNL Communications.cfg]**-Datei verhindern könnten.
1. Wenn Ihr System Verarbeitungsserver enthält, ändern Sie die Konfigurationsdatei in der Datei **[!DNL Components for Processing Servers.cfg]** .
1. Klicken Sie mit der rechten Maustaste auf **[!DNL Communications.cfg]** und speichern Sie auf dem Server.

Der Gruppenadministrator kann jetzt bestätigen, dass die vorgesehenen Data Workbenchs Zugriff auf die Benutzerlistendatei haben und den Benutzern die Gruppenverwaltung ermöglichen. Benutzer können die Datei &quot;Benutzerliste&quot;öffnen, sie bearbeiten und CN- oder OU-Mitglieder nach Bedarf hinzufügen und entfernen.

## Synchronisieren Sie die Datei Access Control.cfg . {#section-ca6da453dfb4432bb40b86ef15ede872}

Der Administrator kann dann **[!DNL Access Control.cfg]** bearbeiten und Verweise auf die Gruppe(n) einfügen, die durch die Datei *Benutzerliste* definiert wurde.

Die Verweise auf die Gruppe(n) sollten wie jedes andere Mitglied eingefügt werden, jedoch mit der folgenden Syntax:

```
$(Group Name)
```

Dabei entspricht &quot;Gruppenname&quot;dem, was in der Benutzerlistendatei definiert ist, einschließlich Leerzeichen. ![](assets/6_4_workstation_groups_2.png)

An dieser Stelle kann der Data Workbench-Administrator bestätigen, dass ausgewählte Gruppenbenutzer Zugriff auf die Benutzerlistendatei haben. Die ausgewählten Benutzer können dann die Datei **[!DNL User List.cfg]** öffnen, sie bearbeiten und CN- oder OU-Mitglieder nach Bedarf hinzufügen und entfernen.
