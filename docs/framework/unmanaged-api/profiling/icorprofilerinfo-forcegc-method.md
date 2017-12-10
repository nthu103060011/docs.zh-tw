---
title: "ICorProfilerInfo::ForceGC 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.ForceGC
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo::ForceGC
helpviewer_keywords:
- ICorProfilerInfo::ForceGC method [.NET Framework profiling]
- ForceGC method [.NET Framework profiling]
ms.assetid: 0da1ef80-d242-4636-87d0-43e0470b342a
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 3a3389c6675e992c362e3e0a77dfbc97e142ef8a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerinfoforcegc-method"></a><span data-ttu-id="6517e-102">ICorProfilerInfo::ForceGC 方法</span><span class="sxs-lookup"><span data-stu-id="6517e-102">ICorProfilerInfo::ForceGC Method</span></span>
<span data-ttu-id="6517e-103">強制記憶體回收發生的 common language runtime (CLR) 中。</span><span class="sxs-lookup"><span data-stu-id="6517e-103">Forces garbage collection to occur within the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6517e-104">語法</span><span class="sxs-lookup"><span data-stu-id="6517e-104">Syntax</span></span>  
  
```  
HRESULT ForceGC();  
```  
  
## <a name="remarks"></a><span data-ttu-id="6517e-105">備註</span><span class="sxs-lookup"><span data-stu-id="6517e-105">Remarks</span></span>  
 <span data-ttu-id="6517e-106">`ForceGC`必須只能從從未執行 managed 程式碼，且其堆疊上沒有任何分析工具回呼的執行緒中呼叫方法。</span><span class="sxs-lookup"><span data-stu-id="6517e-106">The `ForceGC` method must be called only from a thread that has never run managed code and does not have any profiler callbacks on its stack.</span></span> <span data-ttu-id="6517e-107">最方便的實作會建立個別的執行緒中呼叫程式碼剖析工具`ForceGC`收到信號。</span><span class="sxs-lookup"><span data-stu-id="6517e-107">The most convenient implementation is to create a separate thread within the profiler that calls `ForceGC` when signaled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6517e-108">需求</span><span class="sxs-lookup"><span data-stu-id="6517e-108">Requirements</span></span>  
 <span data-ttu-id="6517e-109">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6517e-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6517e-110">**標頭：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6517e-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6517e-111">**程式庫：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6517e-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6517e-112">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6517e-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6517e-113">另請參閱</span><span class="sxs-lookup"><span data-stu-id="6517e-113">See Also</span></span>  
 [<span data-ttu-id="6517e-114">ICorProfilerInfo 介面</span><span class="sxs-lookup"><span data-stu-id="6517e-114">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)