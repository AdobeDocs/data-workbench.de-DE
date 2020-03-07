---
description: Der Profil-Manager zeigt alle Ordner an, die mit Ihrem Arbeitsprofil verknüpft sind.
solution: Analytics
title: Profilmanager erstellen
topic: Data workbench
uuid: e16741e2-740b-4f57-861d-e2f57d30abbc
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Profilmanager erstellen{#create-a-profile-manager}

Der Profil-Manager zeigt alle Ordner an, die mit Ihrem Arbeitsprofil verknüpft sind.

Sie können auf einen Unterordner des Verzeichnisses zugreifen, [!DNL Profile Manager] ohne die gesamte Ordnerstruktur zu durchsuchen. Beispielsweise können Sie mit den im Menü des [!DNL Metrics] Arbeitsflächenfensters verfügbaren [!DNL Workspaces] [!DNL Manage] Menüoptionen die Ordner &quot;Profil-Manager-Metriken&quot;bzw. &quot;Arbeitsbereiche&quot;öffnen.

Weitere Informationen zum Profil [!DNL Profile Manager]finden Sie unter [Profilmanager](https://docs.adobe.com/content/help/en/data-workbench/using/client/ui-analysis-features/cstm-prof-files-mgrs/c-new-prof-mgrs.html).

Standardmäßig haben Sie Zugriff auf die folgenden Manager:

* **[!DNL Metrics Manager]:**Zeigt den Inhalt des Ordners Metriken des Profilmanagers an. Sie können die in jedem Profil definierten Metriken öffnen, bearbeiten, entfernen oder kopieren.
* **[!DNL Reports Manager]:**Zeigt den Inhalt des Ordners Berichte des Profilmanagers an. Sie können Berichtsarbeitsbereiche oder -dateien öffnen, bearbeiten, entfernen oder kopieren[!DNL report.cfg].

* **[!DNL Workspaces Manager]:**Zeigt den Inhalt des Ordners &quot;Arbeitsbereiche&quot;des Profilmanagers an. Hier finden Sie alle Dateien zum Konfigurieren der Registerkarten der[!DNL Worktop]Registerkarte. Siehe[Anpassen der Registerkarten](../../../../home/c-get-started/c-intf-anlys-ftrs/c-cstm-wktp-tabs/c-cstm-wktp-tabs.md)am Arbeitsplatz.

Mit Data Workbench können Sie zusätzliche Profilmanager erstellen, die einen Unterordner aus dem [!DNL Profile Manager]anzeigen. Jeder von Ihnen erstellte Manager muss über eine [!DNL .vw] Datei verfügen, die den [!DNL Profile Manager] Ordner, dessen Inhalt angezeigt wird, und die Eigenschaften dieses Fensters angibt. Sie können die [!DNL .vw] Datei für einen der angegebenen Manager als Vorlage verwenden.

**So erstellen Sie einen Profilmanager**

1. Klicken Sie im [!DNL Profile Manager]Ordner auf das **[!UICONTROL Menu]** Verzeichnis, um dessen Inhalt anzuzeigen.
1. Klicken Sie im Ordner &quot;Menu&quot;auf den **[!UICONTROL Admin]** Ordner und dann auf den **[!UICONTROL Profile]** Ordner. Die [!DNL .vw] Dateien für die vorhandenen Manager finden Sie hier.
1. Klicken Sie in der Spalte *Profilname* mit der rechten Maustaste auf das Häkchen für eine der [!DNL .vw] Dateien (z. B. [!DNL Workspaces.vw]) und klicken Sie dann auf **[!UICONTROL Make Local]**.

   Ein Häkchen für die Datei wird in der [!DNL User] Spalte angezeigt.

1. Klicken Sie mit der rechten Maustaste auf das Häkchen für die [!DNL .vw] Datei in der [!DNL User] Spalte und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**.
1. Geben Sie in das [!DNL Profile Path] Feld den [!DNL Profile Manager] Ordner ein, für den Sie einen neuen Manager erstellen möchten. Achten Sie darauf, den Schrägstrich (/) nach dem Ordnernamen einzufügen.

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

1. Klicken Sie in Notepad auf **[!UICONTROL File]** > **[!UICONTROL Save As]** , um die bearbeitete Datei im *Data Workbench-Installationsordner*\User\*Arbeitsprofilname*\Menu\Admin\Profile Management zu speichern.

   Achten Sie darauf, den Namen der [!DNL .vw] Datei so zu ändern, dass er dem Ordner entspricht, dem [!DNL Profile Manager] sie zugeordnet ist.

1. (Optional) Um die Änderungen allen Benutzern des Arbeitsprofils zur Verfügung zu stellen, klicken Sie mit der rechten Maustaste auf das Häkchen für die [!DNL .vw] Datei in der [!DNL User] Spalte und klicken Sie auf **[!UICONTROL Save to]** > &lt; **[!UICONTROL working profile name]**>.

