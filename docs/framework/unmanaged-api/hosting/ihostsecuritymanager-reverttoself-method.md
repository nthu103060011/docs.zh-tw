---
title: "IHostSecurityManager::RevertToSelf 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostSecurityManager.RevertToSelf
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostSecurityManager::RevertToSelf
helpviewer_keywords:
- RevertToSelf method [.NET Framework hosting]
- IHostSecurityManager::RevertToSelf method [.NET Framework hosting]
ms.assetid: 189f28f8-f9a1-4192-aedc-91084e4f8b99
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0fad325bc3df54f412a797e9944f5b1f38615786
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="ihostsecuritymanagerreverttoself-method"></a><span data-ttu-id="c8ec5-102">IHostSecurityManager::RevertToSelf 方法</span><span class="sxs-lookup"><span data-stu-id="c8ec5-102">IHostSecurityManager::RevertToSelf Method</span></span>
<span data-ttu-id="c8ec5-103">結束目前的使用者身分識別模擬並傳回原始的執行緒語彙基元。</span><span class="sxs-lookup"><span data-stu-id="c8ec5-103">Terminates impersonation of the current user identity and returns the original thread token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8ec5-104">語法</span><span class="sxs-lookup"><span data-stu-id="c8ec5-104">Syntax</span></span>  
  
```  
HRESULT RevertToSelf ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="c8ec5-105">傳回值</span><span class="sxs-lookup"><span data-stu-id="c8ec5-105">Return Value</span></span>  
  
|<span data-ttu-id="c8ec5-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c8ec5-106">HRESULT</span></span>|<span data-ttu-id="c8ec5-107">描述</span><span class="sxs-lookup"><span data-stu-id="c8ec5-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c8ec5-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="c8ec5-108">S_OK</span></span>|<span data-ttu-id="c8ec5-109">`RevertToSelf`已成功傳回。</span><span class="sxs-lookup"><span data-stu-id="c8ec5-109">`RevertToSelf` returned successfully.</span></span>|  
|<span data-ttu-id="c8ec5-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c8ec5-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c8ec5-111">Common language runtime (CLR) 尚未載入到處理程序，或 CLR 正在中它無法執行 managed 程式碼，或成功地處理呼叫的狀態。</span><span class="sxs-lookup"><span data-stu-id="c8ec5-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c8ec5-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c8ec5-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c8ec5-113">呼叫已逾時。</span><span class="sxs-lookup"><span data-stu-id="c8ec5-113">The call timed out.</span></span>|  
|<span data-ttu-id="c8ec5-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c8ec5-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c8ec5-115">呼叫端未擁有鎖定。</span><span class="sxs-lookup"><span data-stu-id="c8ec5-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c8ec5-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c8ec5-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c8ec5-117">事件已取消時封鎖的執行緒或 fiber 等候它。</span><span class="sxs-lookup"><span data-stu-id="c8ec5-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c8ec5-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c8ec5-118">E_FAIL</span></span>|<span data-ttu-id="c8ec5-119">發生未知的嚴重失敗。</span><span class="sxs-lookup"><span data-stu-id="c8ec5-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c8ec5-120">方法會傳回 E_FAIL CLR 已不再可用的處理序內。</span><span class="sxs-lookup"><span data-stu-id="c8ec5-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c8ec5-121">裝載方法的後續呼叫會傳回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="c8ec5-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c8ec5-122">備註</span><span class="sxs-lookup"><span data-stu-id="c8ec5-122">Remarks</span></span>  
 <span data-ttu-id="c8ec5-123">`RevertToSelf`呼叫之前呼叫之後，回到原始的執行緒語彙基元， [ImpersonateLoggedOnUser](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-impersonateloggedonuser-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="c8ec5-123">`RevertToSelf` is called to return to the original thread token, after an earlier call to the [ImpersonateLoggedOnUser](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-impersonateloggedonuser-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c8ec5-124">需求</span><span class="sxs-lookup"><span data-stu-id="c8ec5-124">Requirements</span></span>  
 <span data-ttu-id="c8ec5-125">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c8ec5-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c8ec5-126">**標頭：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c8ec5-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c8ec5-127">**程式庫：**包含做為 MSCorEE.dll 中的資源</span><span class="sxs-lookup"><span data-stu-id="c8ec5-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c8ec5-128">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c8ec5-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8ec5-129">另請參閱</span><span class="sxs-lookup"><span data-stu-id="c8ec5-129">See Also</span></span>  
 [<span data-ttu-id="c8ec5-130">IHostSecurityContext 介面</span><span class="sxs-lookup"><span data-stu-id="c8ec5-130">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)  
 [<span data-ttu-id="c8ec5-131">IHostSecurityManager 介面</span><span class="sxs-lookup"><span data-stu-id="c8ec5-131">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)  
 [<span data-ttu-id="c8ec5-132">ImpersonateLoggedOnUser 方法</span><span class="sxs-lookup"><span data-stu-id="c8ec5-132">ImpersonateLoggedOnUser Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-impersonateloggedonuser-method.md)