---
ms.openlocfilehash: a4f27c0b2bf95ed19e485881aba3c52073114117
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2019
ms.locfileid: "52742476"
---
### <a name="wpf-layout-rounding-of-margins-has-changed"></a>Die WPF-Layoutglättung von Rändern wurde geändert

|   |   |
|---|---|
|Details|Die Art und Weise, wie Ränder und die Grenzen und der Hintergrund darin geglättet werden, hat sich geändert. Auswirkungen durch diese Änderung:<ul><li>Die Breite oder Höhe der Elemente vergrößert oder verkleinert sich allenfalls um einen Pixel.</li><li>Die Platzierung eines Objekts kann sich allenfalls um einen Pixel verschieben.</li><li>Zentrierte Elemente können sich vertikal oder horizontal um allenfalls ein Pixel von der Mitte verschieben.</li></ul>Standardmäßig wird dieses neue Layout nur für Apps aktiviert, die auf .NET Framework 4.6 abzielen.|
|Vorschlag|Da durch diese Änderung das Clipping die rechte oder Unterseite von WPF-Steuerelementen bei hohen DPIs beseitigt wird, können Apps, die auf frühere Versionen von .NET Framework abzielen, aber auf .NET Framework 4.6 ausgeführt werden, dieses neue Verhalten übernehmen, sofern die folgende Zeile zum Abschnitt <code>&lt;runtime&gt;</code> der Datei „app.config“ hinzugefügt wird:<pre><code class="lang-xml">&lt;AppContextSwitchOverrides value=&quot;Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=false&quot; /&gt;&#39;&#13;&#10;</code></pre>Apps, die auf .NET Framework 4.6 ausgelegt sind, aber WPF-Steuerelemente zum Rendern mithilfe des vorherigen Layoutalgorithmus verwenden möchten, können dies vornehmen, sofern die folgende Zeile zum Abschnitt <code>&lt;runtime&gt;</code> der Datei „app.config“ hinzugefügt wird:<pre><code class="lang-xml">&lt;AppContextSwitchOverrides value=&quot;Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=true&quot; /&gt;&#39;.&#13;&#10;</code></pre>|
|Bereich|Gering|
|Version|4.6|
|Typ|Neuzuweisung|

