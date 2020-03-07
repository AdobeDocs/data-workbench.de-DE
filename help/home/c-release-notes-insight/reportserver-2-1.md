---
description: Sicherheits-Update für Data Workbench Report Portal.
title: DWB Report Portal 2.1
uuid: de8266f4-1f7b-4bfd-94e7-16bddb336db3
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# DWB Report Portal 2.1{#dwb-report-portal}

Sicherheits-Update für Data Workbench Report Portal.

**Wichtiges Sicherheitsupdate**

Das Report Portal bietet jetzt verbesserte Hashing-Algorithmen mit Salting-Unterstützung. Wenn Sie auf Report Portal 2.1 aktualisieren, fügen Sie ein neues Textfeld, PasswordSalt mit einer Feldgröße von 20 Zeichen in der Datenbank users.mdb hinzu. Dieses Feld ist erforderlich, um das Passwortsalz zu speichern.
