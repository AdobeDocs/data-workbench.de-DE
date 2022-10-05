---
description: Der Profil-Manager zeigt alle Ordner an, die mit Ihrem Arbeitsprofil verknüpft sind.
title: Erstellen von Profil-Managern
uuid: e16741e2-740b-4f57-861d-e2f57d30abbc
exl-id: 43b95473-ab3e-4a80-9b91-7c221e74b096
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '390'
ht-degree: 2%

---

# Erstellen von Profil-Managern{#create-a-profile-manager}

{{eol}}

Der Profil-Manager zeigt alle Ordner an, die mit Ihrem Arbeitsprofil verknüpft sind.

Sie können auf ein Unterverzeichnis der [!DNL Profile Manager] ohne die gesamte Ordnerstruktur durchlaufen zu müssen. Beispiel: die [!DNL Metrics] und [!DNL Workspaces] verfügbaren Menüoptionen auf [!DNL Manage] im Menü des Arbeitsbereich-Fensters können Sie die Ordner für die Kennzahlen des Profil-Managers bzw. für Arbeitsbereiche öffnen.

Weitere Informationen zum [!DNL Profile Manager], siehe [Der Profil-Manager](https://experienceleague.adobe.com/docs/data-workbench/using/client/ui-analysis-features/cstm-prof-files-mgrs/c-new-prof-mgrs.html).

Standardmäßig haben Sie Zugriff auf die folgenden Manager:

* **[!DNL Metrics Manager]:** Zeigt den Inhalt des Ordners Metriken des Profil-Managers an. Sie können die in jedem Profil definierten Metriken öffnen, bearbeiten, entfernen oder kopieren.
* **[!DNL Reports Manager]:** Zeigt den Inhalt des Ordners Berichte des Profil-Managers an. Sie können Berichtarbeitsbereiche öffnen, bearbeiten, entfernen oder kopieren oder [!DNL report.cfg] Dateien.

* **[!DNL Workspaces Manager]:** Zeigt den Inhalt des Ordners Arbeitsbereiche des Profil-Managers an. Alle Dateien zum Konfigurieren der [!DNL Worktop]Die Registerkarten finden Sie hier. Siehe [Anpassen von Registerkarten der Arbeitsfläche](../../../../home/c-get-started/c-intf-anlys-ftrs/c-cstm-wktp-tabs/c-cstm-wktp-tabs.md).

Mit Data Workbench können Sie zusätzliche Profilmanager erstellen, die ein Unterverzeichnis aus dem [!DNL Profile Manager]. Jeder von Ihnen erstellte Manager muss über eine [!DNL .vw] -Datei, die die [!DNL Profile Manager] Verzeichnis, dessen Inhalt es anzeigt, und Eigenschaften dieses Fensters. Sie können die [!DNL .vw] -Datei für einen der bereitgestellten Manager als Vorlage.

**So erstellen Sie einen Profil-Manager**

1. Im [!DNL Profile Manager], klicken Sie auf die **[!UICONTROL Menu]** Verzeichnis, um seinen Inhalt anzuzeigen.
1. Klicken Sie im Menü-Verzeichnis auf die **[!UICONTROL Admin]** und dann **[!UICONTROL Profile]** Verzeichnis. Die [!DNL .vw] Dateien für die vorhandenen Manager finden Sie hier.
1. Im *Profilname* klicken Sie mit der rechten Maustaste auf das Häkchen für die [!DNL .vw] -Dateien (z. B. [!DNL Workspaces.vw]), klicken Sie auf **[!UICONTROL Make Local]**.

   Ein Häkchen für die Datei wird im [!DNL User] Spalte.

1. Klicken Sie mit der rechten Maustaste auf das Häkchen für die [!DNL .vw] in der Datei [!DNL User] Spalte und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**.
1. Im [!DNL Profile Path] -Feld, geben Sie die [!DNL Profile Manager] -Verzeichnis, für das Sie einen neuen Manager erstellen möchten. Stellen Sie sicher, dass Sie den Schrägstrich (/) hinter dem Ordnernamen einfügen.

   ```
   window = simpleBorderWindow:
   client = scrollWindow: 
   client = fileManager:
     Profile Path = string: directory name/
     size = v3d: (820, 5649, 0)
     scroll_offset = v3d: (0, 0, 0)
     size = v3d: (830, 881, 0)
     pos = v3d: (525, 162, 0)
     size = v3d: (830, 900, 0)
   ```

1. Klicken Sie im Editor auf **[!UICONTROL File]** > **[!UICONTROL Save As]** , um die bearbeitete Datei in der *Installationsordner für Data Workbenchs*\User\*funktionierender Profilname*\Menu\Admin\Profile Management.

   Achten Sie darauf, den Namen der [!DNL .vw] -Datei, um den Ordner im [!DNL Profile Manager] dem sie entspricht.

1. (Optional) Um die Änderungen allen Benutzern des Arbeitsprofils zur Verfügung zu stellen, klicken Sie mit der rechten Maustaste auf das Häkchen für die [!DNL .vw] in der Datei [!DNL User] Spalte und klicken Sie auf **[!UICONTROL Save to]** > &lt; **[!UICONTROL working profile name]**>.
