---
title: "適用於 Silverlight 的 CreateDebuggingInterfaceFromVersion 函式"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: CreateDebuggingInterfaceFromVersion
helpviewer_keywords:
- CreateDebuggingInterfaceFromVersion function
- debugging API [Silverlight]
- Silverlight, debugging
ms.assetid: 35c7a18f-133a-4584-bd25-bb338568b0c6
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1c37609d6fe95e95b19e6ab86bbb9ce4e9e1b87a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2017
---
# <a name="createdebugginginterfacefromversion-function-for-silverlight"></a><span data-ttu-id="5bc17-102">適用於 Silverlight 的 CreateDebuggingInterfaceFromVersion 函式</span><span class="sxs-lookup"><span data-stu-id="5bc17-102">CreateDebuggingInterfaceFromVersion Function for Silverlight</span></span>
<span data-ttu-id="5bc17-103">接受 common language runtime (CLR) 版本字串所傳回的[CreateVersionStringFromModule 函式](../../../../docs/framework/unmanaged-api/debugging/createversionstringfrommodule-function.md)，並傳回對應的偵錯工具介面 (一般而言， [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md))。</span><span class="sxs-lookup"><span data-stu-id="5bc17-103">Accepts a common language runtime (CLR) version string that is returned from the [CreateVersionStringFromModule function](../../../../docs/framework/unmanaged-api/debugging/createversionstringfrommodule-function.md), and returns a corresponding debugger interface (typically, [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5bc17-104">語法</span><span class="sxs-lookup"><span data-stu-id="5bc17-104">Syntax</span></span>  
  
```  
HRESULT CreateDebuggingInterfaceFromVersion (  
    [in]  LPCWSTR      szDebuggeeVersion,  
    [out] IUnknown**   ppCordb,  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5bc17-105">參數</span><span class="sxs-lookup"><span data-stu-id="5bc17-105">Parameters</span></span>  
 `szDebuggeeVersion`  
 <span data-ttu-id="5bc17-106">[in]傳回目標偵錯項目，在 CLR 的版本字串[CreateVersionStringFromModule 函式](../../../../docs/framework/unmanaged-api/debugging/createversionstringfrommodule-function.md)。</span><span class="sxs-lookup"><span data-stu-id="5bc17-106">[in] Version string of the CLR in the target debuggee, which is returned by the [CreateVersionStringFromModule function](../../../../docs/framework/unmanaged-api/debugging/createversionstringfrommodule-function.md).</span></span>  
  
 `ppCordb`  
 <span data-ttu-id="5bc17-107">[out] COM 物件 (`IUnknown`) 指標的指標。</span><span class="sxs-lookup"><span data-stu-id="5bc17-107">[out] Pointer to a pointer to a COM object (`IUnknown`).</span></span> <span data-ttu-id="5bc17-108">這個物件會轉換成[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)物件傳回之前。</span><span class="sxs-lookup"><span data-stu-id="5bc17-108">This object will be cast to an [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) object before it is returned.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5bc17-109">傳回值</span><span class="sxs-lookup"><span data-stu-id="5bc17-109">Return Value</span></span>  
 <span data-ttu-id="5bc17-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="5bc17-110">S_OK</span></span>  
 <span data-ttu-id="5bc17-111">`ppCordb`參考實作的有效物件[ICorDebug 介面](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)介面。</span><span class="sxs-lookup"><span data-stu-id="5bc17-111">`ppCordb` references a valid object that implements the [ICorDebug interface](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) interface.</span></span>  
  
 <span data-ttu-id="5bc17-112">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="5bc17-112">E_INVALIDARG</span></span>  
 <span data-ttu-id="5bc17-113">`szDebuggeeVersion` 或 `ppCordb` 為 null。</span><span class="sxs-lookup"><span data-stu-id="5bc17-113">Either `szDebuggeeVersion` or `ppCordb` is null.</span></span>  
  
 <span data-ttu-id="5bc17-114">CORDBG_E_DEBUG_COMPONENT_MISSING</span><span class="sxs-lookup"><span data-stu-id="5bc17-114">CORDBG_E_DEBUG_COMPONENT_MISSING</span></span>  
 <span data-ttu-id="5bc17-115">找不到 CLR 偵錯所需的元件。</span><span class="sxs-lookup"><span data-stu-id="5bc17-115">A component that is necessary for CLR debugging cannot be located.</span></span> <span data-ttu-id="5bc17-116">這表示在目標 CoreCLR.dll 所在的相同目錄中找不到 mscordbi.dll 或 mscordaccore.dll。</span><span class="sxs-lookup"><span data-stu-id="5bc17-116">This means that either mscordbi.dll or mscordaccore.dll was not found in the same directory as the target CoreCLR.dll.</span></span>  
  
 <span data-ttu-id="5bc17-117">CORDBG_E_INCOMPATIBLE_PROTOCOL</span><span class="sxs-lookup"><span data-stu-id="5bc17-117">CORDBG_E_INCOMPATIBLE_PROTOCOL</span></span>  
 <span data-ttu-id="5bc17-118">mscordbi.dll 或 mscordaccore.dll 的版本與目標 CoreCLR.dll 的版本不同。</span><span class="sxs-lookup"><span data-stu-id="5bc17-118">Either mscordbi.dll or mscordaccore.dll is not the same version as the target CoreCLR.dll.</span></span>  
  
 <span data-ttu-id="5bc17-119">E_FAIL (或其他 E_ 傳回碼)</span><span class="sxs-lookup"><span data-stu-id="5bc17-119">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="5bc17-120">無法傳回[ICorDebug 介面](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)。</span><span class="sxs-lookup"><span data-stu-id="5bc17-120">Unable to return an [ICorDebug interface](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5bc17-121">備註</span><span class="sxs-lookup"><span data-stu-id="5bc17-121">Remarks</span></span>  
 <span data-ttu-id="5bc17-122">傳回的介面提供了附加至目標處理序中的 CLR，以及對 CLR 正在執行之 Managed 程式碼進行偵錯的功能。</span><span class="sxs-lookup"><span data-stu-id="5bc17-122">The interface that is returned provides the facilities for attaching to a CLR in a target process and debugging the managed code that the CLR is running.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5bc17-123">需求</span><span class="sxs-lookup"><span data-stu-id="5bc17-123">Requirements</span></span>  
 <span data-ttu-id="5bc17-124">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5bc17-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5bc17-125">**標頭：** dbgshim.h</span><span class="sxs-lookup"><span data-stu-id="5bc17-125">**Header:** dbgshim.h</span></span>  
  
 <span data-ttu-id="5bc17-126">**程式庫：** dbgshim.dll</span><span class="sxs-lookup"><span data-stu-id="5bc17-126">**Library:** dbgshim.dll</span></span>  
  
 <span data-ttu-id="5bc17-127">**.NET framework 版本：** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="5bc17-127">**.NET Framework Versions:** 3.5 SP1</span></span>