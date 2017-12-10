---
title: "ICorDebugCode::GetILToNativeMapping 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugCode.GetILToNativeMapping
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugCode::GetILToNativeMapping
helpviewer_keywords:
- GetILToNativeMapping method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetILToNativeMapping method [.NET Framework debugging]
ms.assetid: a8ecd8c8-9627-4356-9c6f-bd05e24637c0
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 54937e8d5d7a2e345ebcbccadbc592b12e3ee9b6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugcodegetiltonativemapping-method"></a><span data-ttu-id="80953-102">ICorDebugCode::GetILToNativeMapping 方法</span><span class="sxs-lookup"><span data-stu-id="80953-102">ICorDebugCode::GetILToNativeMapping Method</span></span>
<span data-ttu-id="80953-103">取得"COR_DEBUG_IL_TO_NATIVE_MAP 」 執行個體表示的對應從 Microsoft intermediate language (MSIL) 位移到原生位移的陣列。</span><span class="sxs-lookup"><span data-stu-id="80953-103">Gets an array of "COR_DEBUG_IL_TO_NATIVE_MAP" instances that represent mappings from Microsoft intermediate language (MSIL) offsets to native offsets.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80953-104">語法</span><span class="sxs-lookup"><span data-stu-id="80953-104">Syntax</span></span>  
  
```  
HRESULT GetILToNativeMapping (  
    [in]  ULONG32    cMap,  
    [out] ULONG32    *pcMap,  
    [out, size_is(cMap), length_is(*pcMap)]  
        COR_DEBUG_IL_TO_NATIVE_MAP map[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="80953-105">參數</span><span class="sxs-lookup"><span data-stu-id="80953-105">Parameters</span></span>  
 `cMap`  
 <span data-ttu-id="80953-106">[in] `map` 陣列的大小。</span><span class="sxs-lookup"><span data-stu-id="80953-106">[in] The size of the `map` array.</span></span>  
  
 `pcMap`  
 <span data-ttu-id="80953-107">[out]項目中傳回的實際數目的指標`map`陣列。</span><span class="sxs-lookup"><span data-stu-id="80953-107">[out] A pointer to the actual number of elements returned in the `map` array.</span></span>  
  
 `map`  
 <span data-ttu-id="80953-108">[out]陣列`COR_DEBUG_IL_TO_NATIVE_MAP`結構，每個都表示從 MSIL 位移到原生位移的對應。</span><span class="sxs-lookup"><span data-stu-id="80953-108">[out] An array of `COR_DEBUG_IL_TO_NATIVE_MAP` stuctures, each of which represents a mapping from an MSIL offset to a native offset.</span></span>  
  
 <span data-ttu-id="80953-109">沒有任何排序傳回的元素的陣列。</span><span class="sxs-lookup"><span data-stu-id="80953-109">There is no ordering to the array of elements returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="80953-110">備註</span><span class="sxs-lookup"><span data-stu-id="80953-110">Remarks</span></span>  
 <span data-ttu-id="80953-111">`GetILToNativeMapping`才本例"ICorDebugCode"代表已在 just-in-time (JIT) 編譯的 MSIL 程式碼的原生程式碼，方法會傳回有意義的結果。</span><span class="sxs-lookup"><span data-stu-id="80953-111">The `GetILToNativeMapping` method returns meaningful results only if this "ICorDebugCode" instance represents native code that was just-in-time (JIT) compiled from MSIL code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="80953-112">需求</span><span class="sxs-lookup"><span data-stu-id="80953-112">Requirements</span></span>  
 <span data-ttu-id="80953-113">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="80953-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="80953-114">**標頭：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="80953-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="80953-115">**程式庫：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="80953-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="80953-116">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="80953-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80953-117">另請參閱</span><span class="sxs-lookup"><span data-stu-id="80953-117">See Also</span></span>  
 [<span data-ttu-id="80953-118">ICorDebugCode Interface1</span><span class="sxs-lookup"><span data-stu-id="80953-118">ICorDebugCode Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-interface1.md)