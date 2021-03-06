---
ms.openlocfilehash: 38c50244b1cee41bd95c232ac5d1691c59c55488
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2019
ms.locfileid: "58760848"
---
### <a name="wpf-focusvisual-for-radiobutton-and-checkbox-now-displays-correctly-when-the-controls-have-no-content"></a>WPF FocusVisual für RadioButton und CheckBox wird jetzt ordnungsgemäß angezeigt, wenn die Steuerelemente keinen Inhalt enthalten

|   |   |
|---|---|
|Details|In .NET Framework 4.7.1 und früheren Versionen weisen <xref:System.Windows.Controls.CheckBox?displayProperty=nameWIthType> und <xref:System.Windows.Controls.RadioButton?displayProperty=nameWIthType> von WPF inkonsistente und im klassischen Design und im Design mit hohem Kontrast falsche visuelle Fokuselemente auf.  Diese Probleme treten in Fällen auf, in denen für die Steuerelemente keine Inhalte festgelegt sind.  Dadurch kann der Übergang zwischen Designs verwirrend wirken und das visuelle Fokuselement schwer zu erkennen sein. In .NET Framework, 4.7.2 sind diese visuellen Elemente jetzt designübergreifend konsistenter und im klassischen Design sowie im Design mit hohem Kontrast leichter zu erkennen.|
|Vorschlag|Ein Entwickler, die Code für .NET Framework 4.7.2 erstellt und das Verhalten von .NET 4.7.1 wiederherstellen möchte, muss das folgende AppContext-Flag festlegen.<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.UseLegacyAccessibilityFeatures.2=true;&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>Ein Entwickler, der diese Änderung für eine niedrigere Frameworkversion als .NET 4.7.2 nutzen möchte, muss die folgenden AppContext-Flags festlegen. Beachten Sie, dass alle Flags ordnungsgemäß festgelegt werden müssen, und die installierte Version von .NET Framework muss 4.7.2 oder höher sein. WPF-Anwendungen müssen alle früheren Barrierefreiheitsverbesserungen aktivieren, um die neuesten Verbesserungen abrufen zu können. Stellen Sie zu diesem Zweck sicher, dass die AppContext-Schalter „Switch.UseLegacyAccessibilityFeatures“ und „Switch.UseLegacyAccessibilityFeatures.2“ auf FALSE festgelegt sind.<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false;&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|Bereich|Microsoft Edge|
|Version|4.7.2|
|Typ|Neuzuweisung|

