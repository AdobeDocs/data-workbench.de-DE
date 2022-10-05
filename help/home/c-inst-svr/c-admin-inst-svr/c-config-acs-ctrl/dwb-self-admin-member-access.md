---
description: Administratoren können Workstationbenutzern die teilweise Verwaltung der Zugangssteuerung für Benutzergruppen erteilen.
title: Benutzeradministration des Zugriffs von Gruppenmitgliedern
uuid: c31128f9-1094-4337-9bf6-96401278df33
exl-id: 6d2a0f19-a33c-49f6-a470-c95d2c1532c7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '732'
ht-degree: 6%

---

# Benutzeradministration des Zugriffs von Gruppenmitgliedern{#user-administration-of-group-member-access}

{{eol}}

Administratoren können Workstationbenutzern die teilweise Verwaltung der Zugangssteuerung für Benutzergruppen erteilen.

**Selbstverwaltung des Zugriffs auf Gruppenmitglieder** gibt Benutzern ohne Administratorrechte das Hinzufügen und Löschen von Mitgliedern in einer benutzerspezifischen Gruppe zu. Der Administrator erstellt eine **Benutzerliste** und richtet den Gruppenzugriff in der [Access Control.cfg](https://experienceleague.adobe.com/docs/data-workbench/using/server-admin-install/admin-dwb-server/access-control/c-config-acs-ctrl.html) -Datei für die neuen Gruppenmitglieder.

**Zugriff auf den Server Manager**

Einrichten der **[!DNL User List]** Datei und synchronisieren sie mit der **[!DNL Communications.cfg]** -Datei im **Server-Manager** Arbeitsbereich.

1. Klicken Sie auf der Arbeitsfläche auf die **Admin** tab > **Datensatz und Profil** Registerkarte.

1. Öffnen Sie die **Server-Manager** Arbeitsbereich.
1. Rechtsklick >*Name Ihres Servers*> im Diagramm und wählen Sie **Dateien**.

   Die Serverdateien werden in einer Tabelle mit Spalten geöffnet *Datei*, *`<server name>`* und *Temp*.

1. **Lokal machen** durch Rechtsklick in die Serverspalte einer Serverdatei (für diese Funktion) **[!DNL Access Control]** und **[!DNL Components/Communications.cfg)]**.

   Ein weißes Häkchen wird im **Temp** Spalte. Sie können sie im Ordner &quot;Temp&quot;bearbeiten. Klicken Sie dann mit der rechten Maustaste auf das Häkchen und **Speichern unter** den Server. (Beim Synchronisieren mit dem Server wird die Farbe rot).

## Erstellen einer Datei &quot;User List.cfg&quot; {#section-c25bcaf34f4546e6b8b65f5e7f69ac09}

Der Administrator muss eine **[!DNL User List.cfg]** in der Datei **[!DNL Access Control]** Ordner.

1. Klicken Sie mit der rechten Maustaste auf die Zeile &quot;Zugriffssteuerung&quot;im **Temp** und wählen Sie **Öffnen** > **Ordner**. ![](assets/6_4_workstation_groups_3.png)

   Der Ordner &quot;Zugriffssteuerung&quot;im **Temp** -Ordner wird geöffnet, in dem eine einzelne **[!DNL Access Control.cfg]** -Datei.

1. Fügen Sie diesem Ordner eine weitere Textdatei hinzu und benennen Sie sie. **[!DNL User List.cfg]** (neben dem **[!DNL Access Control.cfg]**).

1. Fügen Sie die folgenden Parameter zum **[!DNL User List.cfg]** -Datei.

Die Datei &quot;Benutzerliste&quot;sollte einen Vektor von **AccessGroup** Objekte und **AccessGroup** -Objekt sollte einen Namen und einen Vektor von Zeichenfolgen haben, die **Mitglieder**.

```
Access Control Groups = vector: 1 items 
  0 = AccessGroup:  
    Name = string: Group 1 
    Members = vector: 1 items 
      0 = string: CN:Joe User
```

Sie können diese dann bearbeiten und Benutzer in der Workstation-Ansicht des ** hinzufügen[!DNL User List.cfg]**Datei.

![](assets/6_4_workstation_groups_4.png)

Im Folgenden finden Sie die grundlegendsten Parameter, die der **[!DNL User List.cfg]** -Datei. Die Mitglieder können dann in der Workstation-Ansicht hinzugefügt werden.

```
Access Control Groups = vector: 1 items 
  0 = AccessGroup:  
    Name = string:  
    Members = vector: 0 items
```

>[!IMPORTANT]
>
>Wie bei allen **[!DNL .cfg]** -Datei, die Sie manuell bearbeiten, stellen Sie sicher, dass Sie Leerzeichen anstelle von Registerkarten verwenden, und achten Sie dabei besonders auf Leerzeichen und Syntax. Ein Fehler in dieser Datei verursacht *Adobe Insight Server* , um die Datei &quot;Benutzerliste&quot;zu ignorieren.

Die **Name** in jedem **Zugriffsgruppe** wird innerhalb der [!DNL Access Control.cfg] -Datei.

>[!NOTE]
>
>Nur gültige Mitglieder mit Ordnerdienst-Präfixen, z. B. **CN:** oder **OU:** akzeptiert werden, die keine Platzhalterzeichen (&#42;).

## Datei &quot;Communications.cfg&quot;einrichten {#section-9d6f05ba81c14f15be63e361533459e8}

Ein Administrator aktiviert diese Funktion zuerst, indem er **[!DNL Components]>[!DNL Communications.cfg]** und fügen Sie einen neuen Schlüssel mit dem Namen hinzu. **[!DNL Access Control User List File]**. Der Zeichenfolgenwert dieses Schlüssels ist der Pfad, in dem sich diese neue Datei befindet.

1. Klicken Sie in den Serverdateien auf **Komponenten** und klicken Sie mit der rechten Maustaste auf das Häkchen in der Serverspalte. Klicken **Lokal machen**.

   Ein weißes Häkchen wird im **Temp** Spalte.

1. Klicken Sie mit der rechten Maustaste auf das Häkchen im **Temp** und wählen Sie **Öffnen** > **in Workstation**.

1. Im **Communication.cfg** Datei, Rechtsklick **component** und wählen Sie **Fügen Sie benutzerdefinierten Schlüssel hinzu.** ![](assets/6_4_workstation_groups.png)

1. Geben Sie die **Name** as *Zugriffssteuerungslisten-Datei* und **des Typs** as *Zeichenfolge*.

   >[!NOTE]
   >
   >Sie können die neue Listendatei nicht als Pfad erstellen. Um dies zu beheben, müssen Sie die Datei speichern, sie in einem Editor (Editor) öffnen und &quot;String&quot;in &quot;Path&quot;ändern:

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

1. Speichern Sie die **[!DNL Communications.cfg]** und speichern Sie sie (falls erforderlich) auf dem Server. Dadurch werden Komponenten auf dem Server neu gestartet, um sicherzustellen, dass Sie keine Fehler gemacht haben, die die **[!DNL Communications.cfg]** -Datei analysiert werden.
1. Wenn Ihr System Verarbeitungsserver enthält, ändern Sie die Konfigurationsdatei im **[!DNL Components for Processing Servers.cfg]** -Datei.
1. Rechtsklick **[!DNL Communications.cfg]** und auf dem Server speichern.

Der Gruppenadministrator kann jetzt bestätigen, dass die vorgesehenen Data Workbenchs Zugriff auf die Benutzerlistendatei haben und den Benutzern die Gruppenverwaltung ermöglichen. Benutzer können die Datei &quot;Benutzerliste&quot;öffnen, sie bearbeiten und CN- oder OU-Mitglieder nach Bedarf hinzufügen und entfernen.

## Synchronisieren Sie die Datei Access Control.cfg . {#section-ca6da453dfb4432bb40b86ef15ede872}

Der Administrator kann dann die **[!DNL Access Control.cfg]** und fügen Sie Verweise auf die Gruppe(n) ein, die durch die *Benutzerliste* -Datei.

Die Verweise auf die Gruppe(n) sollten wie jedes andere Mitglied eingefügt werden, jedoch mit der folgenden Syntax:

```
$(Group Name)
```

Dabei entspricht &quot;Gruppenname&quot;dem, was in der Benutzerlistendatei definiert ist, einschließlich Leerzeichen. ![](assets/6_4_workstation_groups_2.png)

An dieser Stelle kann der Data Workbench-Administrator bestätigen, dass ausgewählte Gruppenbenutzer Zugriff auf die Benutzerlistendatei haben. Die ausgewählten Benutzer können dann die **[!DNL User List.cfg]** -Datei speichern, bearbeiten und fügen Sie bei Bedarf CN- oder OU-Mitglieder hinzu und entfernen Sie sie.
