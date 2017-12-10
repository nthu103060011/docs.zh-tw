---
title: "ICorProfilerFunctionEnum::Next 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerFunctionEnum.Next Method
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerFunctionEnum::Next
helpviewer_keywords:
- ICorProfilerFunctionEnum::Next method [.NET Framework profiling]
- Next method, ICorProfilerFunctionEnum interface [.NET Framework profiling]
ms.assetid: 5ed4aa83-ce56-4b9f-9237-5da7587787fe
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 6cf37beced15305de60c3f57edb701adc7379a1f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerfunctionenumnext-method"></a><span data-ttu-id="fdf6b-102">ICorProfilerFunctionEnum::Next 方法</span><span class="sxs-lookup"><span data-stu-id="fdf6b-102">ICorProfilerFunctionEnum::Next Method</span></span>
<span data-ttu-id="fdf6b-103">於循序函式集合中，從序列中列舉值的目前位置開始，取得指定連續函式數目。</span><span class="sxs-lookup"><span data-stu-id="fdf6b-103">Gets the specified number of contiguous functions from a sequential collection of functions, starting at the enumerator's current position in the sequence.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fdf6b-104">語法</span><span class="sxs-lookup"><span data-stu-id="fdf6b-104">Syntax</span></span>  
  
```  
HRESULT Next([in]  ULONG      celt,  
             [out, size_is(celt), length_is(*pceltFetched)]  
                    COR_PRF_FUNCTION ids[],  
             [out] ULONG *   pceltFetched);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fdf6b-105">參數</span><span class="sxs-lookup"><span data-stu-id="fdf6b-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="fdf6b-106">[in] 要擷取的函式數目。</span><span class="sxs-lookup"><span data-stu-id="fdf6b-106">[in] The number of functions to retrieve.</span></span>  
  
 `ids`  
 <span data-ttu-id="fdf6b-107">[out] `COR_PRF_FUNCTION` 值的陣列，每個值各代表一個擷取的函式。</span><span class="sxs-lookup"><span data-stu-id="fdf6b-107">[out] An array of `COR_PRF_FUNCTION` values, each of which represents a retrieved function.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="fdf6b-108">[out] `ids` 陣列中實際傳回之函式數目的指標。</span><span class="sxs-lookup"><span data-stu-id="fdf6b-108">[out] A pointer to the number of functions actually returned in the `ids` array.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fdf6b-109">傳回值</span><span class="sxs-lookup"><span data-stu-id="fdf6b-109">Return Value</span></span>  
 <span data-ttu-id="fdf6b-110">這個方法會傳回下列特定的 HRESULT 以及 HRESULT 錯誤，以指出方法失敗。</span><span class="sxs-lookup"><span data-stu-id="fdf6b-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="fdf6b-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fdf6b-111">HRESULT</span></span>|<span data-ttu-id="fdf6b-112">描述</span><span class="sxs-lookup"><span data-stu-id="fdf6b-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fdf6b-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="fdf6b-113">S_OK</span></span>|<span data-ttu-id="fdf6b-114">已傳回 `celt` 項目。</span><span class="sxs-lookup"><span data-stu-id="fdf6b-114">`celt` elements were returned.</span></span>|  
|<span data-ttu-id="fdf6b-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="fdf6b-115">S_FALSE</span></span>|<span data-ttu-id="fdf6b-116">傳回少於 `celt` 的項目數，表示列舉已完成。</span><span class="sxs-lookup"><span data-stu-id="fdf6b-116">Fewer than `celt` elements were returned, which indicates that the enumeration is complete.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fdf6b-117">需求</span><span class="sxs-lookup"><span data-stu-id="fdf6b-117">Requirements</span></span>  
 <span data-ttu-id="fdf6b-118">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="fdf6b-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fdf6b-119">**標頭：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="fdf6b-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="fdf6b-120">**程式庫：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fdf6b-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fdf6b-121">**.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fdf6b-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdf6b-122">另請參閱</span><span class="sxs-lookup"><span data-stu-id="fdf6b-122">See Also</span></span>  
 [<span data-ttu-id="fdf6b-123">ICorProfilerFunctionEnum 介面</span><span class="sxs-lookup"><span data-stu-id="fdf6b-123">ICorProfilerFunctionEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)  
 [<span data-ttu-id="fdf6b-124">分析介面</span><span class="sxs-lookup"><span data-stu-id="fdf6b-124">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)