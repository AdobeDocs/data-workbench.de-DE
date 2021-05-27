---
description: Um eine kontrollierte Experimentierung zu aktivieren, muss jemand mit Administratorzugriff auf Ihre Web- oder Anwendungsserver den Parameter ExpFile in der Konfigurationsdatei Sensor ändern (gewöhnlich mit txlogd.conf benannt), der auf jedem Web- oder Anwendungsserver in Ihrem Webcluster, auf dem ein Sensor installiert ist, installiert ist.
solution: Analytics,Analytics
title: Ermöglichen gesteuerter Experimente
uuid: 27d68fad-ae2d-4a2e-b449-fbaf88286cfa
exl-id: 53c18524-6050-4708-af63-9e8ef8da389e
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 2%

---

# Ermöglichen gesteuerter Experimente{#enabling-controlled-experimentation}

Um eine kontrollierte Experimentierung zu aktivieren, muss jemand mit Administratorzugriff auf Ihre Web- oder Anwendungsserver den Parameter ExpFile in der Konfigurationsdatei Sensor ändern (gewöhnlich mit txlogd.conf benannt), der auf jedem Web- oder Anwendungsserver in Ihrem Webcluster, auf dem ein Sensor installiert ist, installiert ist.

Darüber hinaus können zwei weitere Parameter in dieser Datei geändert werden, um ein Testtool zu implementieren (ExpCookieURL-Parameter) oder große Bereiche Ihrer Website zu überarbeiten (ExpPartialMatch-Parameter). Dieses Kapitel enthält weitere Informationen zu diesen Parametern.

**Bearbeiten der Datei &quot;txlogd.conf&quot;**

Wenn Sie Administratorzugriff haben, führen Sie die folgenden Schritte aus. Wenn Sie keinen Administratorzugriff haben, wenden Sie sich an Ihren Systemarchitekten, um die Änderungen anzufordern, und geben Sie ihnen die folgenden Schritte an.

1. Navigieren Sie zum Installationsordner [!DNL Sensor] auf einem Web- oder Anwendungsserver in Ihrem Webcluster, auf dem [!DNL Sensor] installiert ist.
1. Öffnen Sie die Konfigurationsdatei [!DNL Sensor] (die normalerweise mit [!DNL txlogd.conf] benannt ist) mithilfe eines Texteditors und bearbeiten Sie die Datei wie in [Bearbeiten des ExpFile-Parameters](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expfile-prm.md#concept-25232b386a654870becc789d4f1fcc28) angegeben.

   (Optional unter [Bearbeiten des ExpCookieURL-Parameters (optional)](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expckurl-prm.md#concept-215bf86bab4e4ec0b0cc803ec48a8fcf) und [Ändern des ExpPartialMatch-Parameters (optional)](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expplmth-prm.md#concept-9c817c4c49b74287b0f70d6a1a37655e).)

1. Speichern und schließen Sie die Datei.
1. Wiederholen Sie dieses Verfahren für jeden Web- oder Anwendungsserver im Webcluster, auf dem ein [!DNL Sensor] installiert ist.
