---
description: Report Portal besteht aus einer Reihe von Anwendungsserverseiten (ASPs) und unterstützenden Dateien.
title: Installieren der Report Portal-Programmdateien
uuid: 483a7401-1bb4-4a71-b8c7-e70ff1b129e7
exl-id: 0eb7805c-d8f6-4cfd-834e-babc1818ebc0
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 5%

---

# Installieren der Report Portal-Programmdateien{#install-the-report-portal-application-files}

Report Portal besteht aus einer Reihe von Anwendungsserverseiten (ASPs) und unterstützenden Dateien.

Um [!DNL Report Portal] zu installieren, müssen Sie diese Dateien aus der Verteilungsdatei extrahieren, die Sie von Adobe erhalten haben, und sie auf dem Computer installieren, auf dem Microsoft IIS ausgeführt wird.

**So installieren Sie die  [!DNL Report Portal] Anwendungsdateien**

1. Sofern noch nicht geschehen, laden Sie das Installationspaket (.zip-Datei) für [!DNL Report Portal] von der Adobe FTP-Site herunter.
1. Extrahieren Sie auf dem Computer, auf dem IIS ausgeführt wird, die Dateien im Installationspaket an einen beliebigen Speicherort. Mit diesem Schritt werden die folgenden Unterordner und Dateien im Ordner VSVirtualPortalName installiert.

   | Ordner oder Datei | Beschreibung |
   |---|---|
   | [!DNL \data\users.mdb] | Datenbank mit der Liste der autorisierten [!DNL Report Portal] Benutzer. |
   | [!DNL \PortalASP\] | Ordner mit den ASP-Dateien, aus denen [!DNL Report Portal] besteht. |
   | [!DNL \PortalFiles\] | Ordner mit fünf Unterordnern (Core, CSS, HTC, Bilder und Ausgabe), die unterstützende Dateien enthalten, die von [!DNL Report Portal] verwendet werden. |
   | [!DNL ReportPortalSetup.xml] | Konfigurationsdatei, die Sie verwenden, um die virtuellen Verzeichnisse zu definieren, die [!DNL Report Portal] zugeordnet sind (nur mit IIS 6.0 verwendet). |

   Das Verzeichnis sieht wie folgt aus:

   ![](assets/rptPort_scrn_installDir.png)

   >[!NOTE]
   >
   >Der Name des Verzeichnisses kann sich von dem im Beispiel gezeigten Namen unterscheiden.

1. Benennen Sie den Ordner VSVirtualPortalName (oder einen anderen Namen) in das virtuelle Stammverzeichnis Ihres [!DNL Report Portal] um (nachfolgend *PortalName* genannt). Weitere Informationen zu virtuellen Verzeichnissen finden Sie im nächsten Abschnitt.
