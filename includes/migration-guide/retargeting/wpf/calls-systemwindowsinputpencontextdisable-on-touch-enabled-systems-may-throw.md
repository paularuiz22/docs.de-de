---
ms.openlocfilehash: 0778285ef1b5702bd79743038a1bd21ba04612d6
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2019
ms.locfileid: "58761069"
---
### <a name="calls-to-systemwindowsinputpencontextdisable-on-touch-enabled-systems-may-throw-an-argumentexception"></a>Aufrufe von System.Windows.Input.PenContext.Disable auf touchfähigen Systemen können eine ArgumentException auslösen

|   |   |
|---|---|
|Details|Unter bestimmten Umständen können Aufrufe der internen Methode <strong>System.Windows.Intput.PenContext.Disable</strong> auf touchfähigen Systemen eine nicht behandelte <code>T:System.ArgumentException</code> aufgrund von Eintrittsinvarianz auslösen.|
|Vorschlag|Dieses Problem wurde in .NET Framework 4.7 behoben. Führen Sie ein Upgrade auf .NET Framework 4.7 oder höher aus, um diese Ausnahme zu vermeiden.|
|Bereich|Microsoft Edge|
|Version|4.6.1|
|Typ|Neuzuweisung|

