---
description: Sie können den Profil-Manager verwenden, um Dateien herunterzuladen, die Sie ändern möchten.
title: Ändern lokaler Dateien im Benutzerprofil
uuid: 839417d1-34db-4b14-a103-8f5297af55b7
exl-id: 187d67a1-e436-4bfd-87ad-17b6c70dbee4
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '388'
ht-degree: 3%

---

# Ändern lokaler Dateien im Benutzerprofil{#modify-local-files-in-the-user-profile}

Sie können den Profil-Manager verwenden, um Dateien herunterzuladen, die Sie ändern möchten.

Möglicherweise möchten Sie eine Datei herunterladen, um Ihre vorhandene lokale Datei mit der Originalversion der Datei zu überschreiben oder Dateien zu öffnen, anzuzeigen und zu ändern, auf die über die Arbeitsbereichmenüs nicht zugegriffen werden kann.

**So laden Sie eine Datei herunter**

1. Öffnen Sie in [!DNL Profile Manager] die erforderlichen Ordner und Unterordner, um die Datei zu finden, die Sie herunterladen möchten.
1. Klicken Sie mit der rechten Maustaste auf das Häkchen neben dem Dateinamen und klicken Sie auf **[!UICONTROL Make Local]**.

   >[!NOTE]
   >
   >Konfigurations- ( [!DNL .cfg]), Dimensionsdateien ( [!DNL .dim]) und Metrikdateien ( [!DNL .metric]) können direkt in einem Profilordner bearbeitet und auf dem Server gespeichert werden, ohne sie lokal zu machen und separat auf dem Server zu speichern. Klicken Sie einfach mit der rechten Maustaste auf das Häkchen neben dem Dateinamen und klicken Sie in Workstation **auf **[!UICONTROL Open]**>** und dann auf .

Nachdem die Datei auf den lokalen Computer heruntergeladen wurde, wird in der Spalte [!DNL User] ein Häkchen angezeigt, das angibt, dass sich eine lokale Kopie der Datei im Ordner &quot;User\*profile name*&quot;auf Ihrem Computer befindet. Beachten Sie, dass das Häkchen dieselbe Farbe wie das Häkchen in der Spalte *Profilname* hat. Dies bedeutet, dass die lokale Datei dasselbe Änderungsdatum und dieselbe Änderungszeit hat wie die Datei im Ordner *Profilname* .

**So ändern Sie die Datei**

1. Klicken Sie in der Spalte [!DNL User] mit der rechten Maustaste auf das Häkchen neben dem Dateinamen.
1. Klicken Sie je nach gewünschter Dateibearbeitung auf eine der folgenden Menüoptionen:

   * **[!UICONTROL Open]** >  **[!UICONTROL in workstation]** wenn Sie eine  [!DNL .vw] Datei oder eine  [!DNL .cfg] Datei in einem Arbeitsbereich bearbeiten.

   * **Öffnen Sie**  > **in vW. Editor **wenn Sie eine VW-Datei bearbeiten, um neue Parameter hinzuzufügen.

   * **[!UICONTROL Open]** >  **[!UICONTROL In Notepad]** wenn Sie eine Textdatei öffnen oder neue Parameter zu einer  [!DNL .cfg] Datei hinzufügen müssen.

   * **[!UICONTROL Open]** >  **[!UICONTROL folder]** , wenn Sie den Ordner öffnen möchten, in dem sich die Datei auf Ihrem Computer befindet

1. Bearbeiten Sie die Datei nach Bedarf und speichern Sie sie.

Beachten Sie in [!DNL Profile Manager], dass das Häkchen in der Spalte [!DNL User] für die bearbeitete Datei die Farbe geändert hat. Dies bedeutet, dass sich die lokale Datei jetzt von der Version im Ordner *Profilname* unterscheidet. Bei Bedarf können Sie die überarbeitete Version der Datei im Profil veröffentlichen, um sie von anderen Benutzern zu verwenden, die mit diesem Profil arbeiten.
