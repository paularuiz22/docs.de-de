---
ms.openlocfilehash: 649e4456ef6a11903ab1b390baf56583f31f5562
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2019
ms.locfileid: "58760842"
---
### <a name="wpf-textboxpasswordbox-text-selection-does-not-follow-system-colors"></a>TextBox-/PasswordBox-Textauswahl von WPF folgt nicht den Systemfarben

|   |   |
|---|---|
|Details|In .NET Framework 4.7.1 und früheren Versionen konnten <code>System.Windows.Controls.TextBox</code> und <code>System.Windows.Controls.PasswordBox</code> von WPF nur eine Textauswahl aus der Adorner-Ebene rendern. In einigen Systemdesigns verdeckte dies Text, wodurch die Lesbarkeit erschwert wurde.  In .NET Framework 4.7.2 und höher besteht für Entwickler eine Option, ein nicht auf Adorner basierendes Auswahlrenderingschema zu aktivieren, das dieses Problem behebt.|
|Vorschlag|Ein Entwickler, die diese Änderung nutzen möchte, muss das folgende AppContext-Flag entsprechend festlegen.  Um dieses Feature nutzen zu können, muss die installierte Version von .NET Framework 4.7.2 oder höher sein. Um die nicht auf Adorner basierende Auswahl zu aktivieren, verwenden Sie das folgenden AppContext-Flag.<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Controls.Text.UseAdornerForTextboxSelectionRendering=false&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|Bereich|Microsoft Edge|
|Version|4.7.2|
|Typ|Neuzuweisung|

