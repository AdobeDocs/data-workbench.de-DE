---
description: Dateien, die im Installationspaket von Data Workbench enthalten sind.
title: Im Installationspaket enthaltene Dateien
uuid: 46cda536-ea71-4840-bd7f-3fe9e0242c33
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Im Installationspaket enthaltene Dateien{#files-included-in-the-installation-package}

Dateien, die im Installationspaket von Data Workbench enthalten sind.

Die folgenden Ordner sind im Insight-Paket enthalten.

## Programmdateien {#section-ddb14bf42cdd4dc7a6b4310a5b4388e4}

Die ausführbare (**[!DNL Insight.exe]**) Workstation-Datei und die zugehörigen Dateien werden standardmäßig in diesem Ordner installiert.

```
C:\Program Files\Adobe\Adobe Analytics\Data Workbench
```

<table id="table_56BAC85184A04E7680FBB4B36DE73285"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Verzeichnis </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> Insight.exe </span></b> </td> 
   <td colname="col2"> Die ausführbare Datei des Data Workbench-Clients. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> insight.ini </span></b> </td> 
   <td colname="col2"> Legen Sie die Sprache und den Pfad für den <span class="filepath"> Appdata- </span> Ordner fest. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> Insight.zbin </span></b> </td> 
   <td colname="col2"> <p>Data Workbench unterstützt jetzt einen Eingabemethoden-Editor (IME) als sekundären Texteingabeprozess, mit dem Sie internationale Zeichen über die Tastatur mit einem schwebenden Textfeld eingeben können. Data Workbench unterstützt standardmäßig Englisch, ermöglicht Ihnen aber auch, andere Dateien zu laden, um internationale Sprachen zu unterstützen, wie z.B. eine virtuelle chinesische Tastatur (Pinyin IME). </p> <p>Eine neue Wörterbuchdatei <span class="filepath"> (Insight.zbin </span>) wird von der Clientanwendung benötigt, um den IME zu unterstützen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> unins000.exe </span></b> </td> 
   <td colname="col2"> Es wird ausgeführt, um Workstation zu deinstallieren und Dateien zu löschen. </td> 
  </tr> 
 </tbody> 
</table>

## AppData-Dateien {#section-afddeedf8d29451f996fa46b2dfe932c}

Datendateien (**[!DNL Insight.cfg]**, Profile, Zertifikate, Ablaufverfolgungsprotokolle und Benutzerdateien) werden standardmäßig wie folgt gespeichert:

```
<filepath>
  C:\Users\<Winuser>\AppData\Adobe\Analytics\DataWorkbench\ 
</filepath>
```

<table id="table_DBA4DBB54C57409C8EC116C686A08560"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Verzeichnis </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> Insight.cfg </span></b> </td> 
   <td colname="col2"> Die Data Workbench-Konfigurationsdatei. Definiert Parameter, in denen Data Workbench ausgeführt wird. Siehe <a href="../../../home/c-install-insight/install-setup/c-conn-isvr.md#concept-9f47b2cd7c12492693a2cf810cfc1d9e"> Verbindung mit Insight Server konfigurieren </a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> Basis </span></b> </td> 
   <td colname="col2"> <p>Enthält die Programmdateien für Data Workbench. </p> <p> <p>Hinweis:  Sie sollten keine dieser Dateien entfernen oder ändern. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> Zertifikate </span></b> </td> 
   <td colname="col2"> Enthält die Zertifikatdatei <span class="filepath"> trust_ca_cert.pem </span>und das benannte digitale Benutzerzertifikat für Data Workbench. Siehe <a href="../../../home/c-install-insight/install-setup/c-dgtl-crtf.md#concept-4c6a900074d4464fb6ec7862f7e54f10"> Herunterladen und Installieren des digitalen Zertifikats </a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> Konfiguration </span> </b> </td> 
   <td colname="col2"> Enthält die Dateien, die für die Workstation-Konfiguration verwendet werden. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> Geografie </span></b> </td> 
   <td colname="col2"> Dateien zur grafischen Darstellung geografischer Visualisierungen. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> Trace </span></b> </td> 
   <td colname="col2"> Protokolldateien, die von der Workstation generiert wurden. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> Profile </span></b> </td> 
   <td colname="col2"> <i>AdobeSC</i>-, <i>Predictive Analytics</i> - und andere Profilkonfigurationsdateien. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> InsightSetup.exe </span></b> </td> 
   <td colname="col2"> Setup-Assistent zum Installieren zusätzlicher Clientcomputer im <b> Ordner <span class="filepath"> Software/Insight </span></b> . </td> 
  </tr> 
 </tbody> 
</table>

