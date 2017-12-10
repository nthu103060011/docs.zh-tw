---
title: "_CorImageUnloading 函式"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: _CorImageUnloading
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: _CorImageUnloading
helpviewer_keywords: _CorImageUnloading function [.NET Framework hosting]
ms.assetid: b4367214-6dac-4280-aa11-fd487ff30bc4
topic_type: apiref
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 90df58e2765cdecf4a1ec22cf5540e5cfa9530a9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2017
---
# <a name="corimageunloading-function"></a><span data-ttu-id="e20dc-102">_CorImageUnloading 函式</span><span class="sxs-lookup"><span data-stu-id="e20dc-102">_CorImageUnloading Function</span></span>
<span data-ttu-id="e20dc-103">卸載 managed 的模組映像時，請通知載入器。</span><span class="sxs-lookup"><span data-stu-id="e20dc-103">Notifies the loader when the managed module images are unloaded.</span></span>  
  
 <span data-ttu-id="e20dc-104">未實作此函式。</span><span class="sxs-lookup"><span data-stu-id="e20dc-104">This function is not implemented.</span></span> <span data-ttu-id="e20dc-105">如果呼叫，它會傳回 E_NOTIMPL。</span><span class="sxs-lookup"><span data-stu-id="e20dc-105">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e20dc-106">語法</span><span class="sxs-lookup"><span data-stu-id="e20dc-106">Syntax</span></span>  
  
```  
STDAPI (VOID) _CorImageUnloading(   
   [in] PVOID* ImageBase  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e20dc-107">參數</span><span class="sxs-lookup"><span data-stu-id="e20dc-107">Parameters</span></span>  
 `ImageBase`  
 <span data-ttu-id="e20dc-108">[in]要卸載之影像的起始位置指標。</span><span class="sxs-lookup"><span data-stu-id="e20dc-108">[in] A pointer to the starting location of the image to unload.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e20dc-109">需求</span><span class="sxs-lookup"><span data-stu-id="e20dc-109">Requirements</span></span>  
 <span data-ttu-id="e20dc-110">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e20dc-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e20dc-111">**標頭：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e20dc-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e20dc-112">**程式庫：**包含做為 MsCorEE.dll 中的資源</span><span class="sxs-lookup"><span data-stu-id="e20dc-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e20dc-113">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e20dc-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e20dc-114">另請參閱</span><span class="sxs-lookup"><span data-stu-id="e20dc-114">See Also</span></span>  
 [<span data-ttu-id="e20dc-115">中繼資料全域靜態函式</span><span class="sxs-lookup"><span data-stu-id="e20dc-115">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)