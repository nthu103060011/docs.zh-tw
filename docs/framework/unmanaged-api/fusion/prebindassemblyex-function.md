---
title: "PreBindAssemblyEx 函式"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: PreBindAssemblyEx
api_location: fusion.dll
api_type: DLLExport
f1_keywords: PreBindAssemblyEx
helpviewer_keywords: PreBindAssemblyEx function [.NET Framework fusion]
ms.assetid: bd285233-a4a2-4b52-bbca-0025a60e4864
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c9bd5cb6be2ccfd25d61a8a2f4347b384e1b2567
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2017
---
# <a name="prebindassemblyex-function"></a><span data-ttu-id="0eddf-102">PreBindAssemblyEx 函式</span><span class="sxs-lookup"><span data-stu-id="0eddf-102">PreBindAssemblyEx Function</span></span>
<span data-ttu-id="0eddf-103">取得組件的原則後顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="0eddf-103">Gets the post-policy display name for an assembly.</span></span>  
  
 <span data-ttu-id="0eddf-104">此功能支援.NET Framework 基礎結構，並不是直接從您的程式碼使用。</span><span class="sxs-lookup"><span data-stu-id="0eddf-104">This function supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0eddf-105">語法</span><span class="sxs-lookup"><span data-stu-id="0eddf-105">Syntax</span></span>  
  
```  
HRESULT PreBindAssemblyEx (  
    [in]  IApplicationContext *pAppCtx,  
    [in]  IAssemblyName       *pName,  
    [in]  IAssembly           *pAsmParent,  
    [in]  LPCWSTR             pwzRuntimeVersion,  
    [out] IAssemblyName       **ppNamePostPolicy,  
    [in]  LPVOID              pvReserved  
 );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0eddf-106">參數</span><span class="sxs-lookup"><span data-stu-id="0eddf-106">Parameters</span></span>  
 `pAppCtx`  
 <span data-ttu-id="0eddf-107">[in]識別應用程式內容。</span><span class="sxs-lookup"><span data-stu-id="0eddf-107">[in] Identifies the application context.</span></span>  
  
 `pName`  
 <span data-ttu-id="0eddf-108">[in]識別組件名稱。</span><span class="sxs-lookup"><span data-stu-id="0eddf-108">[in] Identifies the assembly name.</span></span>  
  
 `pAsmParent`  
 <span data-ttu-id="0eddf-109">[in]識別父組件。</span><span class="sxs-lookup"><span data-stu-id="0eddf-109">[in] Identifies the parent assembly.</span></span> <span data-ttu-id="0eddf-110">這個參數已忽略。</span><span class="sxs-lookup"><span data-stu-id="0eddf-110">This parameter is ignored.</span></span>  
  
 `pwzRuntimeVersion`  
 <span data-ttu-id="0eddf-111">[in]識別執行階段版本。</span><span class="sxs-lookup"><span data-stu-id="0eddf-111">[in] Identifies the runtime version.</span></span>  
  
 `ppNamePostPolicy`  
 <span data-ttu-id="0eddf-112">[out]包含原則後顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="0eddf-112">[out] Contains the post-policy display name.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="0eddf-113">[in]保留供未來擴充。</span><span class="sxs-lookup"><span data-stu-id="0eddf-113">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="0eddf-114">`pvReserved`必須是 null 參考。</span><span class="sxs-lookup"><span data-stu-id="0eddf-114">`pvReserved` must be a null reference.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0eddf-115">備註</span><span class="sxs-lookup"><span data-stu-id="0eddf-115">Remarks</span></span>  
 <span data-ttu-id="0eddf-116">`ppNamePostPolicy`輸出參數在此函數會傳回 HRESULT FUSION_E_REF_DEF_MISMATCH 時，才會設定。</span><span class="sxs-lookup"><span data-stu-id="0eddf-116">The `ppNamePostPolicy` output parameter is set only if the function returns HRESULT FUSION_E_REF_DEF_MISMATCH.</span></span> <span data-ttu-id="0eddf-117">否則，它是 null。</span><span class="sxs-lookup"><span data-stu-id="0eddf-117">Otherwise, it is null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0eddf-118">需求</span><span class="sxs-lookup"><span data-stu-id="0eddf-118">Requirements</span></span>  
 <span data-ttu-id="0eddf-119">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0eddf-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0eddf-120">**標頭：** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="0eddf-120">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="0eddf-121">**程式庫：**包含做為 MsCorEE.dll 中的資源</span><span class="sxs-lookup"><span data-stu-id="0eddf-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0eddf-122">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0eddf-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0eddf-123">另請參閱</span><span class="sxs-lookup"><span data-stu-id="0eddf-123">See Also</span></span>  
 [<span data-ttu-id="0eddf-124">融合全域靜態函式</span><span class="sxs-lookup"><span data-stu-id="0eddf-124">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)