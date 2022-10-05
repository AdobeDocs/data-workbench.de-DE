---
description: Sie können den Profil-Manager verwenden, um Dateien herunterzuladen, die Sie ändern möchten.
title: Ändern lokaler Dateien im Benutzerprofil
uuid: 839417d1-34db-4b14-a103-8f5297af55b7
exl-id: 187d67a1-e436-4bfd-87ad-17b6c70dbee4
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '388'
ht-degree: 3%

---

# Ändern lokaler Dateien im Benutzerprofil{#modify-local-files-in-the-user-profile}

{{eol}}

Sie können den Profil-Manager verwenden, um Dateien herunterzuladen, die Sie ändern möchten.

Möglicherweise möchten Sie eine Datei herunterladen, um Ihre vorhandene lokale Datei mit der Originalversion der Datei zu überschreiben oder Dateien zu öffnen, anzuzeigen und zu ändern, auf die über die Arbeitsbereichmenüs nicht zugegriffen werden kann.

**So laden Sie eine Datei herunter**

1. Im [!DNL Profile Manager], öffnen Sie die erforderlichen Ordner und Unterordner, um die Datei zu finden, die Sie herunterladen möchten.
1. Klicken Sie mit der rechten Maustaste auf das Häkchen neben dem Dateinamen und klicken Sie auf **[!UICONTROL Make Local]**.

   >[!NOTE]
   >
   >Konfiguration ( [!DNL .cfg]), Dimension ( [!DNL .dim]) und Metrik ( [!DNL .metric]) Dateien können direkt in einem Profilordner bearbeitet und auf dem Server gespeichert werden, ohne sie lokal zu machen und separat auf dem Server zu speichern. Klicken Sie einfach mit der rechten Maustaste auf das Häkchen neben dem Dateinamen und klicken Sie auf **[!UICONTROL Open]** > **in Workstation**.

Nachdem die Datei auf den lokalen Computer heruntergeladen wurde, wird ein Häkchen im [!DNL User] -Spalte, die angibt, dass sich eine lokale Kopie der Datei im Ordner &quot;User\*profile name*&quot;auf Ihrem Computer befindet. Beachten Sie, dass das Häkchen dieselbe Farbe hat wie das Häkchen im *Profilname* Spalte. Dies bedeutet, dass die lokale Datei dasselbe Änderungsdatum und dieselbe Änderungszeit hat wie die Datei im *Profilname* Ordner.

**So ändern Sie die Datei**

1. Klicken Sie mit der rechten Maustaste auf das Häkchen neben dem Dateinamen im [!DNL User] Spalte.
1. Klicken Sie je nach gewünschter Dateibearbeitung auf eine der folgenden Menüoptionen:

   * **[!UICONTROL Open]** > **[!UICONTROL in workstation]** wenn Sie eine [!DNL .vw] oder [!DNL .cfg] in einem Arbeitsbereich.

   * **Öffnen** > **in vw. Editor **wenn Sie eine VW-Datei bearbeiten, um neue Parameter hinzuzufügen.

   * **[!UICONTROL Open]** > **[!UICONTROL In Notepad]** wenn Sie eine Textdatei öffnen oder neue Parameter zu einer [!DNL .cfg] -Datei.

   * **[!UICONTROL Open]** > **[!UICONTROL folder]** wenn Sie den Ordner öffnen möchten, in dem sich die Datei auf Ihrem Computer befindet

1. Bearbeiten Sie die Datei nach Bedarf und speichern Sie sie.

Im [!DNL Profile Manager], beachten Sie, dass das Häkchen im [!DNL User] -Spalte für die bearbeitete Datei hat die Farbe geändert. Dies weist darauf hin, dass sich die lokale Datei jetzt von der Version im *Profilname* Ordner. Bei Bedarf können Sie die überarbeitete Version der Datei im Profil veröffentlichen, um sie von anderen Benutzern zu verwenden, die mit diesem Profil arbeiten.
