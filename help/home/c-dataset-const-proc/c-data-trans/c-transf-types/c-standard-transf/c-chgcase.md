---
description: Die ChangeCase-Transformation ändert die Groß-/Kleinschreibung der Zeichenfolge im Eingabeparameter, wie vom Parameter "Aktion"angegeben.
solution: Analytics
title: ChangeCase
topic: Data workbench
uuid: 676e79e6-324e-43d1-8982-b44596d0eeac
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# ChangeCase{#changecase}

Die ChangeCase-Transformation ändert die Groß-/Kleinschreibung der Zeichenfolge im Eingabeparameter, wie vom Parameter &quot;Aktion&quot;angegeben.

| Parameter | Beschreibung | Standardeinstellung |
|---|---|---|
| Name | Beschreibender Name der Transformation. Sie können hier einen beliebigen Namen eingeben. |  |
| Aktion | Oben oder unten. Gibt an, ob die Groß- oder Kleinschreibung geändert werden soll. | lower |
| Kommentare | Optional. Anmerkungen zur Transformation. |  |
| Bedingung | Die Bedingungen, unter denen diese Umwandlung angewendet wird. |  |
| Eingabe | Der Name des Felds im Protokolleintrag, der als Eingabe verwendet werden soll. |  |
| Ausgabe | Der Name des Ausgabefelds. |  |

In diesem Beispiel, in dem Datenfelder verwendet werden, die aus dem Website-Traffic gesammelt wurden, wird die Groß-/Kleinschreibung der Zeichenfolge im s-dns-Feld in Kleinbuchstaben geändert und der neue Wert wird im neuen Feld x-Kleinbuchstaben dns ausgegeben.

![](assets/cfg_TransformationType_ChangeCase.png)

