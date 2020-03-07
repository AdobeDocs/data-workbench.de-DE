---
description: Report Portal besteht aus einem Satz von Anwendungsserverseiten (ASPs) und unterstützenden Dateien.
solution: Analytics
title: Installieren der Report Portal-Anwendungsdateien
topic: Data workbench
uuid: 483a7401-1bb4-4a71-b8c7-e70ff1b129e7
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Installieren der Report Portal-Anwendungsdateien{#install-the-report-portal-application-files}

Report Portal besteht aus einem Satz von Anwendungsserverseiten (ASPs) und unterstützenden Dateien.

Um die [!DNL Report Portal]Datei zu installieren, müssen Sie diese Dateien aus der Distributionsdatei extrahieren, die Sie von Adobe erhalten haben, und sie auf dem Computer installieren, auf dem Microsoft IIS ausgeführt wird.

**So installieren Sie die[!DNL Report Portal]Anwendungsdateien**

1. Laden Sie das Installationspaket (ZIP-Datei) für die [!DNL Report Portal] Datei von der Adobe FTP-Site herunter, sofern noch nicht geschehen.
1. Extrahieren Sie auf dem Computer, auf dem IIS ausgeführt wird, die Dateien im Installationspaket an einen beliebigen Speicherort. Mit diesem Schritt werden die folgenden Unterordner und Dateien im Ordner &quot;VSVirtualPortalName&quot;installiert.

   | Ordner oder Datei | Beschreibung |
   |---|---|
   | [!DNL \data\users.mdb] | Datenbank mit der Liste der autorisierten [!DNL Report Portal] Benutzer. |
   | [!DNL \PortalASP\] | Ordner, der die ASP-Dateien enthält, aus denen [!DNL Report Portal]sich die Elemente zusammensetzen. |
   | [!DNL \PortalFiles\] | Ordner mit fünf Unterordnern (Core, CSS, HTC, Images und Output), die unterstützende Dateien enthalten, die von [!DNL Report Portal]Ihnen verwendet werden. |
   | [!DNL ReportPortalSetup.xml] | Konfigurationsdatei, die Sie zum Definieren der virtuellen Ordner verwenden, die mit [!DNL Report Portal] (nur mit IIS 6.0 verwendet) verknüpft sind. |

   Der Ordner sieht wie folgt aus:

   ![](assets/rptPort_scrn_installDir.png)

   >[!NOTE]
   >
   >Der Name des Ordners kann sich von dem im Beispiel angegebenen Namen unterscheiden.

1. Benennen Sie den Ordner &quot;VSVirtualPortalName&quot;(oder einen anderen Namen) in den Ordner um, den Sie als virtuellen Stammordner Ihres Ordners verwenden möchten [!DNL Report Portal] (nachstehend &quot; *PortalName*&quot;genannt). Weitere Informationen zu virtuellen Verzeichnissen finden Sie im nächsten Abschnitt.
