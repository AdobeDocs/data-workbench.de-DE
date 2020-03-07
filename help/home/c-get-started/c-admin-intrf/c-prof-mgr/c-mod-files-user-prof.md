---
description: Sie können den Profilmanager verwenden, um Dateien herunterzuladen, die Sie ändern möchten.
solution: Analytics
title: Lokale Dateien im Benutzerprofil ändern
topic: Data workbench
uuid: 839417d1-34db-4b14-a103-8f5297af55b7
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Lokale Dateien im Benutzerprofil ändern{#modify-local-files-in-the-user-profile}

Sie können den Profilmanager verwenden, um Dateien herunterzuladen, die Sie ändern möchten.

Möglicherweise möchten Sie eine Datei herunterladen, um die vorhandene lokale Datei mit der Originalversion der Datei zu überschreiben oder Dateien zu öffnen, anzuzeigen und zu ändern, auf die über die Menüs im Arbeitsbereich nicht zugegriffen werden kann.

**So laden Sie eine Datei herunter**

1. Öffnen Sie im [!DNL Profile Manager]Ordner die erforderlichen Ordner und Unterordner, um die Datei zu suchen, die Sie herunterladen möchten.
1. Klicken Sie mit der rechten Maustaste auf das Häkchen neben dem Namen der Datei und klicken Sie auf **[!UICONTROL Make Local]**.

   >[!NOTE]
   >
   >Konfigurations- ( [!DNL .cfg]), Dimensions- ( [!DNL .dim]) und Metrikdateien ( [!DNL .metric]) können direkt in einem Profilordner bearbeitet und auf dem Server gespeichert werden, ohne dass sie lokal gespeichert und separat auf dem Server gespeichert werden müssen. Klicken Sie einfach mit der rechten Maustaste auf das Häkchen neben dem Namen der Datei und klicken Sie auf **[!UICONTROL Open]** > **in Workstation**.

Nachdem die Datei auf den lokalen Computer heruntergeladen wurde, wird ein Häkchen in der [!DNL User] Spalte angezeigt, das angibt, dass sich eine lokale Kopie der Datei im Ordner &quot;User\*profile name*&quot;auf Ihrem Computer befindet. Beachten Sie, dass das Häkchen dieselbe Farbe hat wie das Häkchen in der Spalte *Profilname* . Dies bedeutet, dass die lokale Datei dasselbe Datum und dieselbe Uhrzeit hat wie die Datei im Ordner *Profilname* .

**So ändern Sie die Datei**

1. Klicken Sie mit der rechten Maustaste auf das Häkchen neben dem Dateinamen in der [!DNL User] Spalte.
1. Klicken Sie je nach der gewünschten Dateibearbeitung auf eine der folgenden Menüoptionen:

   * **[!UICONTROL Open]** > **[!UICONTROL in workstation]** , wenn Sie eine [!DNL .vw] Datei oder eine [!DNL .cfg] Datei in einem Arbeitsbereich bearbeiten.

   * **Öffnen** > **in vW. Editor **wenn Sie eine VW-Datei bearbeiten, um neue Parameter hinzuzufügen.

   * **[!UICONTROL Open]** > **[!UICONTROL In Notepad]** , wenn Sie eine Textdatei öffnen oder einer [!DNL .cfg] Datei neue Parameter hinzufügen müssen.

   * **[!UICONTROL Open]** > **[!UICONTROL folder]** , wenn Sie den Ordner öffnen möchten, in dem sich die Datei auf Ihrem Computer befindet

1. Bearbeiten Sie die Datei wie gewünscht und speichern Sie sie dann.

Beachten Sie [!DNL Profile Manager], dass sich die Farbe des Kontrollkästchens in der [!DNL User] Spalte der bearbeiteten Datei geändert hat. Dies weist darauf hin, dass sich die lokale Datei jetzt von der Version im Ordner mit dem *Profilnamen* unterscheidet. Bei Bedarf können Sie die überarbeitete Version der Datei im Profil veröffentlichen, damit sie von anderen Benutzern verwendet werden kann, die mit diesem Profil arbeiten.
