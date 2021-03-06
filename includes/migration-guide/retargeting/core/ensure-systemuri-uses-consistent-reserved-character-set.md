---
ms.openlocfilehash: 4f92d773197c914a74dd7e9c18f5aab5309358ae
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2019
ms.locfileid: "58760830"
---
### <a name="ensure-systemuri-uses-a-consistent-reserved-character-set"></a>Sicherstellen, dass System.Uri einen konsistenten reservierten Zeichensatz verwendet

|   |   |
|---|---|
|Details|In <xref:System.Uri?displayProperty=fullName> sind bestimmte prozentcodierte Zeichen, die manchmal decodiert wurden, jetzt konsistent linkscodiert. Dies tritt für die Eigenschaften und Methoden auf, die auf die Pfad-, Abfrage-, Fragment- oder Benutzerinformationenkomponenten des URIs zugreifen. Das Verhalten ändert sich nur, wenn die beiden folgenden Bedingungen erfüllt sind:<ul><li>Der URI enthält die codierte Form eines der folgenden reservierten Zeichen: <code>:</code>, <code>'</code>, <code>(</code>, <code>)</code>, <code>!</code> oder <code>*</code>.</li><li>Der URI enthält ein Unicode- oder nicht codiertes reserviertes Zeichen. Wenn beide oben genannten Kriterien erfüllt sind, werden die codierten reservierten Zeichen linkscodiert. In früheren Versionen von .NET Framework wurden sie decodiert.</li></ul>|
|Vorschlag|Für Anwendungen mit Zielversionen von .NET Framework ab .NET Framework 4.7.2 ist dieses neue Decodierungsverhalten standardmäßig aktiviert. Wenn diese Änderung nicht erwünscht ist, können Sie sie deaktivieren, indem Sie den Schalter [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) dem Abschnitt <code>&lt;runtime&gt;</code> Ihrer Anwendungskonfigurationsdatei hinzufügen:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Uri.DontEnableStrictRFC3986ReservedCharacterSets=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>Für Anwendungen mit früheren Zielversionen von .NET Framework, die aber mit Versionen ab .NET Framework 4.7.2 ausgeführt werden, ist das neue Decodierungsverhalten standardmäßig deaktiviert. Sie können sie aktivieren, indem Sie den Schalter [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) dem Abschnitt <code>&lt;runtime&gt;</code> Ihrer Anwendungskonfigurationsdatei hinzufügen:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Uri.DontEnableStrictRFC3986ReservedCharacterSets=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|Bereich|Gering|
|Version|4.7.2|
|Typ|Neuzuweisung|
|Betroffene APIs|<ul><li><xref:System.Uri?displayProperty=nameWithType></li></ul>|

