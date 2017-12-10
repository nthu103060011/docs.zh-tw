---
title: "IGCHost::GetStats 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IGCHost.GetStats
api_location: mscoree.dll
api_type: COM
f1_keywords: GetStats
helpviewer_keywords:
- GetStats method, IGCHost interface [.NET Framework hosting]
- IGCHost::GetStats method [.NET Framework hosting]
ms.assetid: c4ae022c-46ac-4f19-9ddd-09b955f19412
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6c8db4f854b73d04e7260457c978a7a644677559
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2017
---
# <a name="igchostgetstats-method"></a><span data-ttu-id="e57be-102">IGCHost::GetStats 方法</span><span class="sxs-lookup"><span data-stu-id="e57be-102">IGCHost::GetStats Method</span></span>
<span data-ttu-id="e57be-103">取得目前的記憶體回收系統狀態的統計資料。</span><span class="sxs-lookup"><span data-stu-id="e57be-103">Gets the statistics for the current state of the garbage collection system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e57be-104">語法</span><span class="sxs-lookup"><span data-stu-id="e57be-104">Syntax</span></span>  
  
```  
HRESULT GetStats (  
    [in, out] COR_GC_STATS *pStats  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e57be-105">參數</span><span class="sxs-lookup"><span data-stu-id="e57be-105">Parameters</span></span>  
 `pStats`  
 <span data-ttu-id="e57be-106">[in、 out]指標[COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)結構，包含記憶體回收系統的目前狀態的統計資料。</span><span class="sxs-lookup"><span data-stu-id="e57be-106">[in, out] A pointer to a [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) structure that contains the statistics for the current state of the garbage collection system.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e57be-107">備註</span><span class="sxs-lookup"><span data-stu-id="e57be-107">Remarks</span></span>  
 <span data-ttu-id="e57be-108">統計資料可供智慧型配置系統，以協助記憶體回收系統運作。</span><span class="sxs-lookup"><span data-stu-id="e57be-108">The statistics can be used by a smart allocation system to help the garbage collection system operate.</span></span> <span data-ttu-id="e57be-109">例如，配置系統可能決定檢視的統計資料，以便增加更多記憶體，或強制回收之後。</span><span class="sxs-lookup"><span data-stu-id="e57be-109">For example, the allocation system may determine, after reviewing the statistics, that it needs to add more memory or force a collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e57be-110">需求</span><span class="sxs-lookup"><span data-stu-id="e57be-110">Requirements</span></span>  
 <span data-ttu-id="e57be-111">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e57be-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e57be-112">**標頭：** GCHost.idl、 GCHost.h</span><span class="sxs-lookup"><span data-stu-id="e57be-112">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="e57be-113">**程式庫：**包含做為 MSCorEE.dll 中的資源</span><span class="sxs-lookup"><span data-stu-id="e57be-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e57be-114">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e57be-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e57be-115">另請參閱</span><span class="sxs-lookup"><span data-stu-id="e57be-115">See Also</span></span>  
 [<span data-ttu-id="e57be-116">IGCHost 介面</span><span class="sxs-lookup"><span data-stu-id="e57be-116">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)