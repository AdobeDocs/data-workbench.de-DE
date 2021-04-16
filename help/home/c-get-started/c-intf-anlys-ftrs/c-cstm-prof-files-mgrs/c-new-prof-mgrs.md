---
description: Der Profil-Manager zeigt alle Ordner an, die mit Ihrem funktionierenden Profil verknüpft sind.
title: Erstellen von Profil-Managern
uuid: e16741e2-740b-4f57-861d-e2f57d30abbc
exl-id: 43b95473-ab3e-4a80-9b91-7c221e74b096
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '392'
ht-degree: 2%

---

# Erstellen von Profil-Managern{#create-a-profile-manager}

Der Profil-Manager zeigt alle Ordner an, die mit Ihrem funktionierenden Profil verknüpft sind.

Sie können auf einen Unterordner von [!DNL Profile Manager] zugreifen, ohne die gesamte Ordnerstruktur durchlaufen zu müssen. Beispielsweise können Sie mit den Menüoptionen [!DNL Metrics] und [!DNL Workspaces] im Menü [!DNL Manage] des Fensters &quot;Arbeitsbereich&quot;die Ordner &quot;Profil-Manager-Metriken&quot;bzw. &quot;Arbeitsbereiche&quot;öffnen.

Weitere Informationen zu [!DNL Profile Manager] finden Sie unter [Der Profil-Manager](https://docs.adobe.com/content/help/en/data-workbench/using/client/ui-analysis-features/cstm-prof-files-mgrs/c-new-prof-mgrs.html).

Standardmäßig haben Sie Zugriff auf die folgenden Manager:

* **[!DNL Metrics Manager]:** Zeigt den Inhalt des Ordners &quot;Metriken&quot;des Profil-Managers an. Sie können die in den einzelnen Profilen definierten Metriken öffnen, bearbeiten, entfernen oder kopieren.
* **[!DNL Reports Manager]:** Zeigt den Inhalt des Profil-Managers an. Sie können Berichtsarbeitsbereiche oder [!DNL report.cfg]-Dateien öffnen, bearbeiten, entfernen oder kopieren.

* **[!DNL Workspaces Manager]:** Zeigt den Inhalt des Ordners &quot;Arbeitsbereiche&quot;des Profil-Managers an. Alle Dateien zum Konfigurieren der Registerkarten von [!DNL Worktop] befinden sich hier. Siehe [Anpassen der Arbeitsflächen](../../../../home/c-get-started/c-intf-anlys-ftrs/c-cstm-wktp-tabs/c-cstm-wktp-tabs.md).

Mit der Data Workbench können Sie zusätzliche Profil-Manager erstellen, die ein Unterverzeichnis von [!DNL Profile Manager] anzeigen. Jeder von Ihnen erstellte Manager muss über eine [!DNL .vw]-Datei verfügen, die den Ordner [!DNL Profile Manager] angibt, dessen Inhalt angezeigt wird, sowie die Eigenschaften dieses Fensters. Sie können die [!DNL .vw]-Datei für alle bereitgestellten Manager als Vorlage verwenden.

**So erstellen Sie einen Profil-Manager**

1. Klicken Sie im Ordner [!DNL Profile Manager] auf das **[!UICONTROL Menu]**-Verzeichnis, um den Inhalt Ansicht.
1. Klicken Sie im Ordner Menu auf den Ordner **[!UICONTROL Admin]** und dann auf den Ordner **[!UICONTROL Profile]**. Die [!DNL .vw]-Dateien für die vorhandenen Manager finden Sie hier.
1. Klicken Sie in der Spalte *Profil* mit der rechten Maustaste auf das Häkchen für eine der [!DNL .vw]-Dateien (z. B. [!DNL Workspaces.vw]) und dann auf **[!UICONTROL Make Local]**.

   In der Spalte [!DNL User] wird ein Häkchen für die Datei angezeigt.

1. Klicken Sie mit der rechten Maustaste auf das Häkchen für die Datei [!DNL .vw] in der Spalte [!DNL User] und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**.
1. Geben Sie im Feld [!DNL Profile Path] den Ordner [!DNL Profile Manager] ein, für den Sie einen neuen Manager erstellen möchten. Achten Sie darauf, den Schrägstrich (/) nach dem Ordnernamen einzufügen.

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

1. Klicken Sie in Notepad auf **[!UICONTROL File]** > **[!UICONTROL Save As]**, um die bearbeitete Datei im Installationsordner *Data Workbench*\User\*Name des funktionierenden Profils*\Menu\Admin\Profile Management zu speichern.

   Achten Sie darauf, den Namen der [!DNL .vw]-Datei zu ändern, um den Ordner in der [!DNL Profile Manager] anzuzeigen, der dieser Datei entspricht.

1. (Optional) Um die Änderungen allen Benutzern des funktionierenden Profils zur Verfügung zu stellen, klicken Sie mit der rechten Maustaste auf das Häkchen für die [!DNL .vw]-Datei in der Spalte [!DNL User] und klicken Sie auf **[!UICONTROL Save to]** > &lt; **[!UICONTROL working profile name]**.
