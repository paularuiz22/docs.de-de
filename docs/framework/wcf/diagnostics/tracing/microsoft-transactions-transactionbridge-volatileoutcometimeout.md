---
title: Microsoft.Transactions.TransactionBridge.VolatileOutcomeTimeout
ms.date: 03/30/2017
ms.assetid: 2dbe34c5-57c7-4b64-9257-63021911d03c
ms.openlocfilehash: 22992b4dfad4b4867adda0fcbbd8ecc5eb67d87e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59160146"
---
# <a name="microsofttransactionstransactionbridgevolatileoutcometimeout"></a>Microsoft.Transactions.TransactionBridge.VolatileOutcomeTimeout
Der WS-AT-Protokolldienst hat während des Wartens auf eine Antwort auf eine ausgehende Nachricht von einem flüchtigen Teilnehmer das Zeitlimit überschritten. Das Transaktionsergebnis ist möglicherweise zweifelhaft, wenn der Teilnehmer zurückkehrt.  
  
## <a name="description"></a>Beschreibung  
 Wird nachverfolgt, wenn ein flüchtiger Teilnehmer sich zu Commit oder Abbruch entschieden hat, aber nicht innerhalb eines vorgegebenen Zeitraums auf eine Commit- oder Rollback-Anforderung geantwortet hat.  
  
## <a name="troubleshooting"></a>Problembehandlung  
 Stellen Sie sicher, dass alle flüchtigen Teilnehmer fähig sind, innerhalb des gegebenen Zeitraums zu antworten. Der Standardzeitraum beträgt 180 Sekunden.  Wenn dies ungenügend ist, erhöhen Sie die `VolatileOutcomeDelay`-Timerrichtlinie für WS-AT.  
  
## <a name="see-also"></a>Siehe auch

- [Ablaufverfolgung](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [Verwaltung und Diagnose](../../../../../docs/framework/wcf/diagnostics/index.md)
