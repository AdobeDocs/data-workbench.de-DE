---
description: Administratoren können Workstationbenutzern die teilweise Verwaltung der Zugangssteuerung für Benutzergruppen erteilen.
title: Benutzerverwaltung des Zugriffs auf Gruppenmitglieder
uuid: c31128f9-1094-4337-9bf6-96401278df33
translation-type: tm+mt
source-git-commit: cb3ca4b3b993f5f04f6b6cee25850600ff3d8986

---


# User Administration of Group Member Access{#user-administration-of-group-member-access}

Administratoren können Workstationbenutzern die teilweise Verwaltung der Zugangssteuerung für Benutzergruppen erteilen.

**Die Selbstverwaltung des Zugriffs** auf Gruppenmitglieder gibt Nichtadministratoren die Möglichkeit, Mitglieder zu einer benutzerspezifischen Gruppe hinzuzufügen und zu löschen. Der Administrator erstellt eine **Benutzerlisten** -Datei und richtet den Gruppenzugriff für die neuen Gruppenmitglieder in der Datei [Access Control.cfg](https://docs.adobe.com/content/help/en/data-workbench/using/server-admin-install/admin-dwb-server/access-control/c-config-acs-ctrl.html) ein.

**Zugriff auf den Server Manager**

Die Einrichtung der **[!DNL User List]** Datei und die Synchronisierung mit der **[!DNL Communications.cfg]** Datei erfolgt im Arbeitsbereich &quot; **Server Manager** &quot;.

1. Klicken Sie auf der Arbeitsfläche auf die Registerkarte **Admin** > **Datensatz und Profil** .

1. Öffnen Sie den **Arbeitsbereich &quot;Server Manager** &quot;.
1. Klicken Sie mit der rechten Maustaste auf >*Ihren Servernamen*> im Diagramm und wählen Sie **Dateien**.

   Die Serverdateien werden in einer Tabelle mit den Spalten *Datei*, *`<server name>`* Temp und *Temp* geöffnet.

1. **&quot;Lokal** machen&quot;, indem Sie mit der rechten Maustaste in die Serverspalte einer Serverdatei klicken (für diese Funktion **[!DNL Access Control]** und **[!DNL Components/Communications.cfg)]**).

   In der Spalte **Temp** wird ein weißes Häkchen angezeigt. Sie können die Datei im Ordner &quot;Temp&quot;bearbeiten. Klicken Sie dann mit der rechten Maustaste auf das Kontrollkästchen und **Speichern unter** dem Server. (Wird beim Synchronisieren mit dem Server rot).

## Erstellen einer Datei &quot;User List.cfg&quot; {#section-c25bcaf34f4546e6b8b65f5e7f69ac09}

Der Administrator muss eine **[!DNL User List.cfg]** Datei im **[!DNL Access Control]** Ordner erstellen.

1. Klicken Sie mit der rechten Maustaste auf die Zeile** Zugriffssteuerung** in der Spalte **Temp** und wählen Sie **Öffnen** > **Ordner**. ![](assets/6_4_workstation_groups_3.png)

   Der Zugriffssteuerungsordner im **Temp** -Ordner öffnet eine Liste mit einer einzelnen **[!DNL Access Control.cfg]** Datei.

1. Fügen Sie diesem Ordner eine weitere Textdatei hinzu und geben Sie ihm einen Namen **[!DNL User List.cfg]** (neben dem **[!DNL Access Control.cfg]**).

1. Add the following parameters to the **[!DNL User List.cfg]** file.

Die Datei &quot;Benutzerliste&quot;sollte einen Vektor von **AccessGroup** -Objekten enthalten. Jedes **AccessGroup** -Objekt sollte einen Namen und einen Vektor von Zeichenfolgen mit der Bezeichnung &quot; **Member**&quot;haben.

```
Access Control Groups = vector: 1 items 
  0 = AccessGroup:  
    Name = string: Group 1 
    Members = vector: 1 items 
      0 = string: CN:Joe User
```

Sie können diese dann bearbeiten und Benutzern in der Workstation-Ansicht der **[!DNL User List.cfg]**Datei hinzufügen.

![](assets/6_4_workstation_groups_4.png)

Hier sind die grundlegendsten Parameter, die der **[!DNL User List.cfg]** Datei hinzugefügt werden müssen. Die Mitglieder können dann in der Workstation-Ansicht hinzugefügt werden.

```
Access Control Groups = vector: 1 items 
  0 = AccessGroup:  
    Name = string:  
    Members = vector: 0 items
```

>[!IMPORTANT]
>
>Achten Sie wie bei jeder **[!DNL .cfg]** Datei, die Sie manuell bearbeiten, darauf, Leerzeichen anstelle von Tabulatoren zu verwenden und den Leerraum und die Syntax genau zu beachten. Ein Fehler in dieser Datei führt dazu, dass *Adobe Insight Server* die Datei &quot;Benutzerliste&quot;ignoriert.

Das Feld **Name** in jeder **Zugriffsgruppe** wird in der [!DNL Access Control.cfg] Datei referenziert.

>[!NOTE]
>
>Nur gültige Mitglieder mit Ordnerdienst-Präfixen, wie z. B. **CN:** oder **OU:** akzeptiert werden, und diese dürfen kein Platzhalterzeichen (*) enthalten.

## Datei &quot;Communications.cfg&quot;einrichten {#section-9d6f05ba81c14f15be63e361533459e8}

Zuerst aktiviert ein Administrator diese Funktion, indem er die Datei **[!DNL Components]>[!DNL Communications.cfg]**öffnet und einen neuen Schlüssel mit dem Namen hinzufügt **[!DNL Access Control User List File]**. Der Zeichenfolgenwert dieses Schlüssels ist der Pfad, an dem sich diese neue Datei befindet.

1. Klicken Sie in den Serverdateien auf **Komponenten** und klicken Sie mit der rechten Maustaste auf das Kontrollkästchen in der Serverspalte. Klicken Sie auf **Als lokal** definieren.

   In der Spalte **Temp** wird ein weißes Häkchen angezeigt.

1. Klicken Sie mit der rechten Maustaste auf das Häkchen in der Spalte **Temp** und wählen Sie **Öffnen** > **in Workstation**.

1. Klicken Sie in der Datei &quot; **Communication.cfg** &quot;mit der rechten Maustaste auf die **Komponente** und wählen Sie &quot;Benutzerdefinierten Schlüssel **hinzufügen&quot;.** ![](assets/6_4_workstation_groups.png)

1. Geben Sie den **Namen** als Benutzerlistendatei *für die* Zugriffssteuerung und **vom Typ** als *Zeichenfolge* ein.

   >[!NOTE]
   Die neue Listendatei kann nicht als Pfad erstellt werden. Um dies zu beheben, müssen Sie die Datei speichern, sie in einem Editor öffnen (Notepad) und &quot;String&quot;in &quot;Path&quot;ändern:

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

1. Speichern Sie die **[!DNL Communications.cfg]** Datei und speichern Sie sie (falls erforderlich) auf dem Server. Dadurch werden Komponenten auf dem Server neu gestartet, um sicherzustellen, dass keine Fehler gemacht wurden, die das Parsen der **[!DNL Communications.cfg]** Datei verhindern könnten.
1. Wenn Ihr System Verarbeitungsserver enthält, ändern Sie die Konfigurationsdatei in der **[!DNL Components for Processing Servers.cfg]** Datei.
1. Klicken Sie mit der rechten Maustaste **[!DNL Communications.cfg]** und speichern Sie auf dem Server.

Der Data Workbench-Administrator kann nun bestätigen, dass die vorgesehenen Benutzer Zugriff auf die Benutzerlistendatei haben und den Benutzern die Verwaltung der Gruppe ermöglichen. Die Benutzer können die Datei &quot;Benutzerliste&quot;öffnen, sie bearbeiten und nach Bedarf CN- oder OU-Mitglieder hinzufügen und entfernen.

## Synchronisieren Sie die Datei &quot;Access Control.cfg&quot; {#section-ca6da453dfb4432bb40b86ef15ede872}

Der Administrator kann dann die Datei bearbeiten **[!DNL Access Control.cfg]** und Verweise auf die Gruppe(n) einfügen, die in der Datei &quot; *Benutzerliste* &quot;definiert ist.

Die Verweise auf die Gruppe(n) sollten wie jedes andere Element eingefügt werden, jedoch mit der folgenden Syntax:

```
$(Group Name)
```

Dabei stimmt &quot;Gruppenname&quot;mit dem überein, was in der Benutzerlistendatei definiert ist, einschließlich Leerzeichen. ![](assets/6_4_workstation_groups_2.png)

An dieser Stelle kann der Data Workbench-Administrator bestätigen, dass ausgewählte Gruppenbenutzer Zugriff auf die Benutzerlistendatei haben. Die ausgewählten Benutzer können die **[!DNL User List.cfg]** Datei dann öffnen, bearbeiten und nach Bedarf CN- oder OU-Mitglieder hinzufügen und entfernen.
