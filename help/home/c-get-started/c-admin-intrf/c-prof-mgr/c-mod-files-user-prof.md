---
description: Mit dem Profil-Manager können Sie Dateien herunterladen, die Sie ändern möchten.
title: Ändern lokaler Dateien im Benutzerprofil
uuid: 839417d1-34db-4b14-a103-8f5297af55b7
exl-id: 187d67a1-e436-4bfd-87ad-17b6c70dbee4
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '388'
ht-degree: 3%

---

# Ändern lokaler Dateien im Benutzerprofil{#modify-local-files-in-the-user-profile}

Mit dem Profil-Manager können Sie Dateien herunterladen, die Sie ändern möchten.

Möglicherweise möchten Sie eine Datei herunterladen, um die vorhandene lokale Datei mit der Originalversion der Datei zu überschreiben oder Dateien zu öffnen, Ansicht zu erstellen und zu ändern, auf die über die Menüs im Arbeitsbereich nicht zugegriffen werden kann.

**So laden Sie eine Datei herunter**

1. Öffnen Sie unter [!DNL Profile Manager] die erforderlichen Ordner und Unterordner, um die Datei zu suchen, die Sie herunterladen möchten.
1. Klicken Sie mit der rechten Maustaste auf das Häkchen neben dem Namen der Datei und klicken Sie auf **[!UICONTROL Make Local]**.

   >[!NOTE]
   >
   >Konfigurations- ( [!DNL .cfg]), Dimensionsdateien ( [!DNL .dim]) und Metrikdateien ( [!DNL .metric]) können direkt in einem Serverordner bearbeitet und auf dem Profil gespeichert werden, ohne dass sie lokal gespeichert und separat auf dem Server gespeichert werden müssen. Klicken Sie einfach mit der rechten Maustaste auf das Häkchen neben dem Namen der Datei und klicken Sie auf **[!UICONTROL Open]** > **in Workstation**.

Nachdem die Datei auf den lokalen Profil heruntergeladen wurde, wird in der Spalte [!DNL User] ein Häkchen angezeigt, das angibt, dass sich eine lokale Dateikopie auf Ihrem Computer im Ordner &quot;User\*Name*&quot;befindet. Beachten Sie, dass das Häkchen dieselbe Farbe hat wie das Häkchen in der Spalte *Profil*. Dies bedeutet, dass die lokale Datei dasselbe Datum und dieselbe Uhrzeit hat wie die Datei im Ordner *Profil*.

**So ändern Sie die Datei**

1. Klicken Sie mit der rechten Maustaste auf das Häkchen neben dem Dateinamen in der Spalte [!DNL User].
1. Klicken Sie je nach der gewünschten Dateibearbeitung auf eine der folgenden Menüoptionen:

   * **[!UICONTROL Open]** >  **[!UICONTROL in workstation]** wenn Sie eine  [!DNL .vw] Datei oder eine  [!DNL .cfg] Datei in einem Arbeitsbereich bearbeiten.

   * **Öffnen** > **in vw. Editor **wenn Sie eine VW-Datei bearbeiten, um neue Parameter hinzuzufügen.

   * **[!UICONTROL Open]** >  **[!UICONTROL In Notepad]** wenn Sie eine Textdatei öffnen oder einer  [!DNL .cfg] Datei neue Parameter hinzufügen müssen.

   * **[!UICONTROL Open]** >  **[!UICONTROL folder]** wenn Sie den Ordner öffnen möchten, in dem sich die Datei auf Ihrem Computer befindet

1. Bearbeiten Sie die Datei wie gewünscht und speichern Sie sie dann.

Beachten Sie in der Spalte [!DNL Profile Manager], dass das Häkchen in der Spalte [!DNL User] für die bearbeitete Datei die Farbe geändert hat. Dies bedeutet, dass sich die lokale Datei jetzt von der Version im Ordner *Profil* unterscheidet. Bei Bedarf können Sie die überarbeitete Dateiversion im Profil veröffentlichen, damit sie von anderen Benutzern verwendet werden kann, die mit diesem Profil arbeiten.
