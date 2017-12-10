---
title: "ICorDebugAppDomainEnum::Next 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugAppDomainEnum.Next
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugAppDomainEnum::Next method
helpviewer_keywords:
- ICorDebugAppDomainEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugAppDomainEnum interface [.NET Framework debugging]
ms.assetid: b8d1def7-0ebc-4314-a3a2-fd36a75973e7
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 10d53ebac99942ac9376041f217df53965bdbb2f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugappdomainenumnext-method"></a><span data-ttu-id="a5d73-102">ICorDebugAppDomainEnum::Next 方法</span><span class="sxs-lookup"><span data-stu-id="a5d73-102">ICorDebugAppDomainEnum::Next Method</span></span>
<span data-ttu-id="a5d73-103">從集合中，從目前游標位置開始，取得指定的應用程式定義域數目。</span><span class="sxs-lookup"><span data-stu-id="a5d73-103">Gets the specified number of application domains from the collection, starting at the current cursor position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5d73-104">語法</span><span class="sxs-lookup"><span data-stu-id="a5d73-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
                           ICorDebugAppDomain *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a5d73-105">參數</span><span class="sxs-lookup"><span data-stu-id="a5d73-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="a5d73-106">[in]要擷取的應用程式定義域數目。</span><span class="sxs-lookup"><span data-stu-id="a5d73-106">[in] The number of application domains to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="a5d73-107">[out]指標的陣列，其中每個指向 ICorDebugAppDomain 物件，表示應用程式定義域。</span><span class="sxs-lookup"><span data-stu-id="a5d73-107">[out] An array of pointers, each of which points to an ICorDebugAppDomain object that represents an application domain.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="a5d73-108">[out]實際傳回的應用程式定義域數目指標。</span><span class="sxs-lookup"><span data-stu-id="a5d73-108">[out] A pointer to the number of application domains actually returned.</span></span> <span data-ttu-id="a5d73-109">這個值可以是 null 如果`celt`是其中一個。</span><span class="sxs-lookup"><span data-stu-id="a5d73-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a5d73-110">需求</span><span class="sxs-lookup"><span data-stu-id="a5d73-110">Requirements</span></span>  
 <span data-ttu-id="a5d73-111">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a5d73-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a5d73-112">**標頭：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a5d73-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a5d73-113">**程式庫：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a5d73-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a5d73-114">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a5d73-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>