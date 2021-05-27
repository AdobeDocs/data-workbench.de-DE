---
description: Der Profil-Manager zeigt alle Ordner an, die mit Ihrem Arbeitsprofil verknüpft sind.
title: Erstellen von Profil-Managern
uuid: e16741e2-740b-4f57-861d-e2f57d30abbc
exl-id: 43b95473-ab3e-4a80-9b91-7c221e74b096
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '392'
ht-degree: 2%

---

# Erstellen von Profil-Managern{#create-a-profile-manager}

Der Profil-Manager zeigt alle Ordner an, die mit Ihrem Arbeitsprofil verknüpft sind.

Sie können auf ein Unterverzeichnis von [!DNL Profile Manager] zugreifen, ohne die gesamte Ordnerstruktur durchsuchen zu müssen. Beispielsweise können Sie mit den Menüoptionen [!DNL Metrics] und [!DNL Workspaces] im Menü [!DNL Manage] des Workspace-Fensters die Ordner &quot;Profil-Manager-Metriken&quot;bzw. &quot;Arbeitsbereiche&quot;öffnen.

Weitere Informationen zu [!DNL Profile Manager] finden Sie unter [Der Profil-Manager](https://docs.adobe.com/content/help/en/data-workbench/using/client/ui-analysis-features/cstm-prof-files-mgrs/c-new-prof-mgrs.html).

Standardmäßig haben Sie Zugriff auf die folgenden Manager:

* **[!DNL Metrics Manager]:** Zeigt den Inhalt des Ordners Metriken des Profil-Managers an. Sie können die in jedem Profil definierten Metriken öffnen, bearbeiten, entfernen oder kopieren.
* **[!DNL Reports Manager]:** Zeigt den Inhalt des Ordners Berichte des Profil-Managers an. Sie können Berichtarbeitsbereiche oder [!DNL report.cfg]-Dateien öffnen, bearbeiten, entfernen oder kopieren.

* **[!DNL Workspaces Manager]:** Zeigt den Inhalt des Ordners Arbeitsbereiche des Profil-Managers an. Alle Dateien zum Konfigurieren der Registerkarten von [!DNL Worktop] finden Sie hier. Siehe [Anpassen von Registerkarten der Arbeitsfläche](../../../../home/c-get-started/c-intf-anlys-ftrs/c-cstm-wktp-tabs/c-cstm-wktp-tabs.md).

Mit Data Workbench können Sie zusätzliche Profilmanager erstellen, die ein Unterverzeichnis aus dem Ordner [!DNL Profile Manager] anzeigen. Jeder von Ihnen erstellte Manager muss über eine [!DNL .vw]-Datei verfügen, die das Verzeichnis [!DNL Profile Manager] angibt, dessen Inhalt sie anzeigt, sowie die Eigenschaften dieses Fensters. Sie können die [!DNL .vw]-Datei für jeden der bereitgestellten Manager als Vorlage verwenden.

**So erstellen Sie einen Profil-Manager**

1. Klicken Sie im Ordner [!DNL Profile Manager] auf das Verzeichnis **[!UICONTROL Menu]** , um dessen Inhalt anzuzeigen.
1. Klicken Sie im Verzeichnis Menu auf das Verzeichnis **[!UICONTROL Admin]** und dann auf das Verzeichnis **[!UICONTROL Profile]** . Die [!DNL .vw] Dateien für die vorhandenen Manager finden Sie hier.
1. Klicken Sie in der Spalte *Profilname* mit der rechten Maustaste auf das Häkchen für die [!DNL .vw]-Datei (z. B. [!DNL Workspaces.vw]) und klicken Sie dann auf **[!UICONTROL Make Local]**.

   In der Spalte [!DNL User] wird ein Häkchen für die Datei angezeigt.

1. Klicken Sie mit der rechten Maustaste auf das Häkchen für die Datei [!DNL .vw] in der Spalte [!DNL User] und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**.
1. Geben Sie im Feld [!DNL Profile Path] den Ordner [!DNL Profile Manager] ein, für den Sie einen neuen Manager erstellen möchten. Stellen Sie sicher, dass Sie den Schrägstrich (/) hinter dem Ordnernamen einfügen.

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

1. Klicken Sie im Editor auf **[!UICONTROL File]** > **[!UICONTROL Save As]** , um die bearbeitete Datei im Installationsordner der Data Workbench *\User\*Arbeitsprofilname*\Menu\Admin\Profile Management zu speichern.*

   Stellen Sie sicher, dass Sie den Namen der Datei [!DNL .vw] ändern, um den Ordner in der Datei [!DNL Profile Manager] widerzuspiegeln, zu der er gehört.

1. (Optional) Um die Änderungen für alle Benutzer des Arbeitsprofils verfügbar zu machen, klicken Sie mit der rechten Maustaste auf das Häkchen für die Datei [!DNL .vw] in der Spalte [!DNL User] und klicken Sie auf **[!UICONTROL Save to]** > &lt; **[!UICONTROL working profile name]**.
