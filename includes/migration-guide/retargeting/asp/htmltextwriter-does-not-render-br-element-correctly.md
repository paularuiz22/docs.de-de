---
ms.openlocfilehash: 0ab6be6f2c6d8ebbe67051e4e3f967a325e654c8
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2019
ms.locfileid: "58761089"
---
### <a name="htmltextwriter-does-not-render-br-element-correctly"></a>HtmlTextWriter rendert das Element `<br/>` nicht ordnungsgemäß

|   |   |
|---|---|
|Details|Ab .NET Framework 4.6 fügt der Aufruf von <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)> und <xref:System.Web.UI.HtmlTextWriter.RenderEndTag> mit einem <code>&lt;BR /&gt;</code>-Element ordnungsgemäß nur ein (anstatt zwei) <code>&lt;BR /&gt;</code> ein.|
|Vorschlag|Wenn eine App vom zusätzlichen <code>&lt;BR /&gt;</code>-Tag abhängig ist, sollte <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)> ein zweites Mal aufgerufen werden. Beachten Sie, das sich diese Verhaltensänderung nur auf Apps mit der Zielplattform .NET Framework 4.6 oder höher auswirkt. Eine weitere Möglichkeit ist daher die Ausrichtung auf eine vorherige Version von .NET Framework, mit der das alte Verhalten genutzt werden kann.|
|Bereich|Microsoft Edge|
|Version|4.6|
|Typ|Neuzuweisung|
|Betroffene APIs|<ul><li><xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)?displayProperty=nameWithType></li><li><xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.Web.UI.HtmlTextWriterTag)?displayProperty=nameWithType></li></ul>|

