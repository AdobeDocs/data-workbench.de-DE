---
description: Report Portal besteht aus einer Reihe von Anwendungsserverseiten (ASPs) und unterstützenden Dateien.
title: Installieren der Report Portal-Programmdateien
uuid: 483a7401-1bb4-4a71-b8c7-e70ff1b129e7
exl-id: 0eb7805c-d8f6-4cfd-834e-babc1818ebc0
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 5%

---

# Installieren der Report Portal-Programmdateien{#install-the-report-portal-application-files}

{{eol}}

Report Portal besteht aus einer Reihe von Anwendungsserverseiten (ASPs) und unterstützenden Dateien.

So installieren Sie die [!DNL Report Portal]müssen Sie diese Dateien aus der Verteilungsdatei extrahieren, die Sie von Adobe erhalten haben, und sie auf dem Computer installieren, auf dem Microsoft IIS ausgeführt wird.

**So installieren Sie die [!DNL Report Portal] Anwendungsdateien**

1. Sofern noch nicht geschehen, laden Sie das Installationspaket (.zip-Datei) für die [!DNL Report Portal] von der FTP-Site der Adobe aus.
1. Extrahieren Sie auf dem Computer, auf dem IIS ausgeführt wird, die Dateien im Installationspaket an einen beliebigen Speicherort. Mit diesem Schritt werden die folgenden Unterordner und Dateien im Ordner VSVirtualPortalName installiert.

   | Ordner oder Datei | Beschreibung |
   |---|---|
   | [!DNL \data\users.mdb] | Datenbank mit der Liste der autorisierten Benutzer [!DNL Report Portal] Benutzer. |
   | [!DNL \PortalASP\] | Ordner mit den ASP-Dateien [!DNL Report Portal]. |
   | [!DNL \PortalFiles\] | Ordner mit fünf Unterordnern (Core, CSS, HTC, Bilder und Ausgabe), die unterstützende Dateien enthalten, die von [!DNL Report Portal]. |
   | [!DNL ReportPortalSetup.xml] | Konfigurationsdatei, mit der Sie die virtuellen Verzeichnisse definieren, die mit [!DNL Report Portal] (nur mit IIS 6.0 verwendet). |

   Das Verzeichnis sieht wie folgt aus:

   ![](assets/rptPort_scrn_installDir.png)

   >[!NOTE]
   >
   >Der Name des Verzeichnisses kann sich von dem im Beispiel gezeigten Namen unterscheiden.

1. Benennen Sie den Ordner VSVirtualPortalName (oder einen anderen Namen) in den Ordner um, den Sie als virtuellen Stammordner Ihrer [!DNL Report Portal] (nachstehend: *PortalName*). Weitere Informationen zu virtuellen Verzeichnissen finden Sie im nächsten Abschnitt.
