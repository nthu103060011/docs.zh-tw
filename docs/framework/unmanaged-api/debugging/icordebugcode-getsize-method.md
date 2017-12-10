---
title: "ICorDebugCode::GetSize 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugCode.GetSize
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugCode::GetSize
helpviewer_keywords:
- GetSize method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetSize method [.NET Framework debugging]
ms.assetid: 115bc6de-f5e2-4e8e-bb38-c7cf54045434
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 94c530015cc1770adf31c336dfb00eb06ffd70a7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugcodegetsize-method"></a><span data-ttu-id="94601-102">ICorDebugCode::GetSize 方法</span><span class="sxs-lookup"><span data-stu-id="94601-102">ICorDebugCode::GetSize Method</span></span>
<span data-ttu-id="94601-103">取得大小，以位元組為單位，表示這個 「 ICorDebugCode"的二進位的程式碼。</span><span class="sxs-lookup"><span data-stu-id="94601-103">Gets the size, in bytes, of the binary code represented by this "ICorDebugCode".</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94601-104">語法</span><span class="sxs-lookup"><span data-stu-id="94601-104">Syntax</span></span>  
  
```  
HRESULT GetSize (  
    [out] ULONG32    *pcBytes  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="94601-105">參數</span><span class="sxs-lookup"><span data-stu-id="94601-105">Parameters</span></span>  
 `pcBytes`  
 <span data-ttu-id="94601-106">[out]指標的大小，單位為位元組的二進位檔的程式碼這個`ICorDebugCode`物件表示。</span><span class="sxs-lookup"><span data-stu-id="94601-106">[out] A pointer to the size, in bytes, of the binary code that this `ICorDebugCode` object represents.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="94601-107">需求</span><span class="sxs-lookup"><span data-stu-id="94601-107">Requirements</span></span>  
 <span data-ttu-id="94601-108">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="94601-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94601-109">**標頭：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="94601-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="94601-110">**程式庫：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="94601-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="94601-111">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94601-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94601-112">另請參閱</span><span class="sxs-lookup"><span data-stu-id="94601-112">See Also</span></span>  
 