---
description: Um eine kontrollierte Experimentierung zu aktivieren, muss jemand mit Administratorzugriff auf Ihre Web- oder Anwendungsserver den Parameter ExpFile in der Konfigurationsdatei des Sensors (gewöhnlich mit txlogd.conf benannt) auf jedem Web- oder Anwendungsserver im Webcluster, auf dem ein Sensor installiert ist, ändern.
solution: Insight,Analytics
title: Aktivieren der kontrollierten Experimentierung
topic: Data workbench
uuid: 27d68fad-ae2d-4a2e-b449-fbaf88286cfa
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Aktivieren der kontrollierten Experimentierung{#enabling-controlled-experimentation}

Um eine kontrollierte Experimentierung zu aktivieren, muss jemand mit Administratorzugriff auf Ihre Web- oder Anwendungsserver den Parameter ExpFile in der Konfigurationsdatei des Sensors (gewöhnlich mit txlogd.conf benannt) auf jedem Web- oder Anwendungsserver im Webcluster, auf dem ein Sensor installiert ist, ändern.

Darüber hinaus können zwei weitere Parameter in dieser Datei geändert werden, um ein Testwerkzeug zu implementieren (ExpCookieURL-Parameter) oder um große Bereiche Ihrer Website zu überarbeiten (ExpPartialMatch-Parameter). Dieses Kapitel enthält weitere Informationen zu diesen Parametern.

**So bearbeiten Sie die Datei &quot;txlogd.conf&quot;**

Wenn Sie über Administratorzugriff verfügen, führen Sie die folgenden Schritte aus. Wenn Sie keinen Administratorzugriff haben, wenden Sie sich an Ihren Systemarchitekten, um die Änderungen anzufordern, und führen Sie die folgenden Schritte aus.

1. Navigieren Sie zum [!DNL Sensor] Installationsordner auf einem Web- oder Anwendungsserver im Webcluster, auf dem ein [!DNL Sensor] Webcluster installiert ist.
1. Öffnen Sie die [!DNL Sensor] Konfigurationsdatei (die normalerweise mit einem Texteditor benannt wird [!DNL txlogd.conf]) und bearbeiten Sie die Datei, wie unter [Ändern des ExpFile-Parameters](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expfile-prm.md#concept-25232b386a654870becc789d4f1fcc28)angegeben.

   (Optional auch beim [Ändern des ExpCookieURL-Parameters (optional)](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expckurl-prm.md#concept-215bf86bab4e4ec0b0cc803ec48a8fcf) und [Ändern des ExpPartialMatch-Parameters (optional)](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expplmth-prm.md#concept-9c817c4c49b74287b0f70d6a1a37655e).)

1. Speichern und schließen Sie die Datei.
1. Wiederholen Sie diesen Vorgang für jeden Web- oder Anwendungsserver im Webcluster, auf dem eine [!DNL Sensor] installiert ist.
