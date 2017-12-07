---
title: ICorDebugManagedCallback::StepComplete-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback.StepComplete
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback::StepComplete
helpviewer_keywords:
- StepComplete method [.NET Framework debugging]
- ICorDebugManagedCallback::StepComplete method [.NET Framework debugging]
ms.assetid: 5e1f2c47-81df-4530-826d-96489cd68719
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: eabc9a2730a1afdf574cee97a6f1b40bae34c7ca
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugmanagedcallbackstepcomplete-method"></a><span data-ttu-id="b8fc3-102">ICorDebugManagedCallback::StepComplete-Methode</span><span class="sxs-lookup"><span data-stu-id="b8fc3-102">ICorDebugManagedCallback::StepComplete Method</span></span>
<span data-ttu-id="b8fc3-103">Benachrichtigt den Debugger, dass ein Schritt abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="b8fc3-103">Notifies the debugger that a step has completed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8fc3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b8fc3-104">Syntax</span></span>  
  
```  
HRESULT StepComplete (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] ICorDebugStepper    *pStepper,  
    [in] CorDebugStepReason   reason  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b8fc3-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b8fc3-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="b8fc3-106">[in] Ein Zeiger auf ein ICorDebugAppDomain-Objekt, das die Anwendungsdomäne mit dem Thread, in dem der Schritt abgeschlossen wurde, darstellt.</span><span class="sxs-lookup"><span data-stu-id="b8fc3-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the thread in which the step has completed.</span></span>  
  
 `pThread`  
 <span data-ttu-id="b8fc3-107">[in] Ein Zeiger auf ein ICorDebugThread-Objekt, das den Thread darstellt, in dem der Schritt abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="b8fc3-107">[in] A pointer to an ICorDebugThread object that represents the thread in which the step has completed.</span></span>  
  
 `pStepper`  
 <span data-ttu-id="b8fc3-108">[in] Ein Zeiger auf ein ICorDebugStepper-Objekt, das den Schritt in der codeausführung darstellt.</span><span class="sxs-lookup"><span data-stu-id="b8fc3-108">[in] A pointer to an ICorDebugStepper object that represents the step in code execution.</span></span>  
  
 `reason`  
 <span data-ttu-id="b8fc3-109">[in] Der Wert der CorDebugStepReason-Enumeration, die das Ergebnis eines einzelnen Schritts angibt.</span><span class="sxs-lookup"><span data-stu-id="b8fc3-109">[in] A value of the CorDebugStepReason enumeration that indicates the outcome of an individual step.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b8fc3-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b8fc3-110">Remarks</span></span>  
 <span data-ttu-id="b8fc3-111">Ausführen in Einzelschritten fortgesetzt, falls gewünscht, es sei denn, das Debuggen beendet wird, kann die zugeordnetem verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b8fc3-111">The stepper may be used to continue stepping if desired, unless the debugging is terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b8fc3-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b8fc3-112">Requirements</span></span>  
 <span data-ttu-id="b8fc3-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b8fc3-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b8fc3-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b8fc3-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b8fc3-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b8fc3-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b8fc3-116">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b8fc3-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8fc3-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b8fc3-117">See Also</span></span>  
 [<span data-ttu-id="b8fc3-118">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b8fc3-118">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)