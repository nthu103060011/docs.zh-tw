---
title: "CorDebugCodeInvokeKind 列舉"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugCodeInvokeKind
api_location: mscordbi.dll
api_type: COM
ms.assetid: e795e6a2-1008-4a81-af88-d777888e942e
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d46a47c7c655a960224bb836be0ea37cd07c8038
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="cordebugcodeinvokekind-enumeration"></a><span data-ttu-id="5bb29-102">CorDebugCodeInvokeKind 列舉</span><span class="sxs-lookup"><span data-stu-id="5bb29-102">CorDebugCodeInvokeKind Enumeration</span></span>
<span data-ttu-id="5bb29-103">描述匯出函式如何叫用 Managed 程式碼。</span><span class="sxs-lookup"><span data-stu-id="5bb29-103">Describes how an exported function invokes managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5bb29-104">語法</span><span class="sxs-lookup"><span data-stu-id="5bb29-104">Syntax</span></span>  
  
```  
typedef enum CorDebugCodeInvokeKind  
{  
    CODE_INVOKE_KIND_NONE,       
    CODE_INVOKE_KIND_RETURN,     
    CODE_INVOKE_KIND_TAILCALL,   
} CorDebugCodeInvokeKind;  
```  
  
## <a name="members"></a><span data-ttu-id="5bb29-105">成員</span><span class="sxs-lookup"><span data-stu-id="5bb29-105">Members</span></span>  
  
|<span data-ttu-id="5bb29-106">成員</span><span class="sxs-lookup"><span data-stu-id="5bb29-106">Member</span></span>|<span data-ttu-id="5bb29-107">描述</span><span class="sxs-lookup"><span data-stu-id="5bb29-107">Description</span></span>|  
|------------|-----------------|  
|`CODE_INVOKE_KIND_NONE`|<span data-ttu-id="5bb29-108">如果這個方法叫用任何 Managed 程式碼，明確事件或中斷點稍後必須找到這些程式碼。</span><span class="sxs-lookup"><span data-stu-id="5bb29-108">If any managed code is invoked by this method, it will have to be located by explicit events or breakpoints later.</span></span><br /><br /> <span data-ttu-id="5bb29-109">-或-</span><span class="sxs-lookup"><span data-stu-id="5bb29-109">--or--</span></span><br /><br /> <span data-ttu-id="5bb29-110">我們可能只是遺漏這個方法呼叫的一些 Managed 程式碼，因為沒有簡單的方法可以在其上停止。</span><span class="sxs-lookup"><span data-stu-id="5bb29-110">We may just miss some of the managed code this method calls because there is no easy way to stop on it.</span></span><br /><br /> <span data-ttu-id="5bb29-111">-或-</span><span class="sxs-lookup"><span data-stu-id="5bb29-111">--or--</span></span><br /><br /> <span data-ttu-id="5bb29-112">這個方法可能永遠不會叫用 Managed 程式碼。</span><span class="sxs-lookup"><span data-stu-id="5bb29-112">The method may never invoke managed code.</span></span>|  
|`CODE_INVOKE_KIND_RETURN`|<span data-ttu-id="5bb29-113">這個方法會透過傳回指令叫用 Managed 程式碼。</span><span class="sxs-lookup"><span data-stu-id="5bb29-113">This method will invoke managed code via a return instruction.</span></span> <span data-ttu-id="5bb29-114">跳離應該會抵達下一個 Managed 程式碼。</span><span class="sxs-lookup"><span data-stu-id="5bb29-114">Stepping out should arrive at the next managed code.</span></span>|  
|`CODE_INVOKE_KIND_TAILCALL`|<span data-ttu-id="5bb29-115">這個方法會透過 tail 呼叫叫用 Managed 程式碼。</span><span class="sxs-lookup"><span data-stu-id="5bb29-115">This method will invoke managed code via a tail-call.</span></span> <span data-ttu-id="5bb29-116">逐步執行和不進入任何呼叫指令應該會抵達 Managed 程式碼。</span><span class="sxs-lookup"><span data-stu-id="5bb29-116">Single-stepping and stepping over any call instructions should arrive at managed code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5bb29-117">備註</span><span class="sxs-lookup"><span data-stu-id="5bb29-117">Remarks</span></span>  
 <span data-ttu-id="5bb29-118">這個列舉型別由[icordebugprocess6:: Getexportstepinfo](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-getexportstepinfo-method.md)方法以提供資訊逐步執行 managed 程式碼。</span><span class="sxs-lookup"><span data-stu-id="5bb29-118">This enumeration is used by the [ICorDebugProcess6::GetExportStepInfo](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-getexportstepinfo-method.md) method to provide information about stepping through managed code.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5bb29-119">這個列舉僅適用於 .NET 原生偵錯案例。</span><span class="sxs-lookup"><span data-stu-id="5bb29-119">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5bb29-120">需求</span><span class="sxs-lookup"><span data-stu-id="5bb29-120">Requirements</span></span>  
 <span data-ttu-id="5bb29-121">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5bb29-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5bb29-122">**標頭：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5bb29-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5bb29-123">**程式庫：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5bb29-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5bb29-124">**.NET framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5bb29-124">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bb29-125">另請參閱</span><span class="sxs-lookup"><span data-stu-id="5bb29-125">See Also</span></span>  
 [<span data-ttu-id="5bb29-126">偵錯列舉</span><span class="sxs-lookup"><span data-stu-id="5bb29-126">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
 [<span data-ttu-id="5bb29-127">偵錯</span><span class="sxs-lookup"><span data-stu-id="5bb29-127">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)