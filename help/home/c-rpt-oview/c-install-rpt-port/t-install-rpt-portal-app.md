---
description: Report Portal besteht aus einem Satz von Anwendungsserverseiten (ASPs) und unterstützenden Dateien.
title: Installieren der Report Portal-Programmdateien
uuid: 483a7401-1bb4-4a71-b8c7-e70ff1b129e7
exl-id: 0eb7805c-d8f6-4cfd-834e-babc1818ebc0
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 5%

---

# Installieren der Report Portal-Programmdateien{#install-the-report-portal-application-files}

Report Portal besteht aus einem Satz von Anwendungsserverseiten (ASPs) und unterstützenden Dateien.

Um die [!DNL Report Portal] zu installieren, müssen Sie diese Dateien aus der Distributionsdatei extrahieren, die Sie von der Adobe erhalten haben, und sie auf dem Computer installieren, auf dem Microsoft IIS ausgeführt wird.

**So installieren Sie die  [!DNL Report Portal] Anwendungsdateien**

1. Laden Sie das Installationspaket (.zip-Datei) für das [!DNL Report Portal] von der Adobe-FTP-Site herunter.
1. Extrahieren Sie auf dem Computer, auf dem IIS ausgeführt wird, die Dateien im Installationspaket an einen beliebigen Speicherort. Mit diesem Schritt werden die folgenden Unterordner und Dateien im Ordner &quot;VSVirtualPortalName&quot;installiert.

   | Ordner oder Datei | Beschreibung |
   |---|---|
   | [!DNL \data\users.mdb] | Datenbank mit der Liste autorisierter [!DNL Report Portal] Benutzer. |
   | [!DNL \PortalASP\] | Ordner mit den ASP-Dateien, aus denen [!DNL Report Portal] besteht. |
   | [!DNL \PortalFiles\] | Ordner mit fünf Unterordnern (Core, CSS, HTC, Images und Output), die unterstützende Dateien enthalten, die von [!DNL Report Portal] verwendet werden. |
   | [!DNL ReportPortalSetup.xml] | Konfigurationsdatei, mit der Sie die virtuellen Ordner definieren, die mit [!DNL Report Portal] verknüpft sind (nur mit IIS 6.0 verwendet). |

   Der Ordner sieht wie folgt aus:

   ![](assets/rptPort_scrn_installDir.png)

   >[!NOTE]
   >
   >Der Name des Ordners kann sich von dem im Beispiel angegebenen Namen unterscheiden.

1. Benennen Sie den Ordner &quot;VSVirtualPortalName&quot;(oder einen anderen Namen) in den gewünschten virtuellen Stammordner von [!DNL Report Portal] um (nachfolgend *PortalName* genannt). Weitere Informationen zu virtuellen Verzeichnissen finden Sie im nächsten Abschnitt.
