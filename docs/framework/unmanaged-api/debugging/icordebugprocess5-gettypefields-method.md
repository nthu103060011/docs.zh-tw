---
title: "ICorDebugProcess5::GetTypeFields 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess5.GetTypeFields
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess5::GetTypeFields
helpviewer_keywords:
- GetTypeFields method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::GetTypeFields method [.NET Framework debugging]
ms.assetid: 6a0ad3ee-dacb-47e9-abae-4536bcc4804b
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7a64e754a77c7d730d921f8a8c1547dd18b66d77
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugprocess5gettypefields-method"></a><span data-ttu-id="426a3-102">ICorDebugProcess5::GetTypeFields 方法</span><span class="sxs-lookup"><span data-stu-id="426a3-102">ICorDebugProcess5::GetTypeFields Method</span></span>
<span data-ttu-id="426a3-103">提供有關屬於型別之欄位的資訊。</span><span class="sxs-lookup"><span data-stu-id="426a3-103">Provides information about the fields that belong to a type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="426a3-104">語法</span><span class="sxs-lookup"><span data-stu-id="426a3-104">Syntax</span></span>  
  
```  
HRESULT GetTypeFields(  
    [in] COR_TYPEID id,  
    [in] ULONG32 celt,  
    [out] COR_FIELD fields[],   
    [out] ULONG32 *pceltNeeded  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="426a3-105">參數</span><span class="sxs-lookup"><span data-stu-id="426a3-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="426a3-106">[in]類型會擷取其欄位資訊的識別碼。</span><span class="sxs-lookup"><span data-stu-id="426a3-106">[in] The identifier of the type whose field information is retrieved.</span></span>  
  
 `celt`  
 <span data-ttu-id="426a3-107">[in]數目[COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md)其欄位資訊是要擷取的物件。</span><span class="sxs-lookup"><span data-stu-id="426a3-107">[in] The number of [COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) objects whose field information is to be retrieved.</span></span>  
  
 `fields`  
 <span data-ttu-id="426a3-108">[out]陣列[COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md)物件提供有關屬於型別之欄位的資訊。</span><span class="sxs-lookup"><span data-stu-id="426a3-108">[out] An array of [COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) objects that provide information about the fields that belong to the type.</span></span>  
  
 `pceltNeeded`  
 <span data-ttu-id="426a3-109">[out]數目的指標[COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md)物件包含在`fields`。</span><span class="sxs-lookup"><span data-stu-id="426a3-109">[out] A pointer to the number of [COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) objects included in `fields`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="426a3-110">備註</span><span class="sxs-lookup"><span data-stu-id="426a3-110">Remarks</span></span>  
 <span data-ttu-id="426a3-111">`celt`參數，指定此方法會使用來填入其欄位資訊的欄位數目`fields`，應該對應至值`COR_TYPE_LAYOUT::numFields`欄位。</span><span class="sxs-lookup"><span data-stu-id="426a3-111">The `celt` parameter, which specifies the number of fields whose field information the method uses to populate `fields`, should correspond to the value of the `COR_TYPE_LAYOUT::numFields` field.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="426a3-112">需求</span><span class="sxs-lookup"><span data-stu-id="426a3-112">Requirements</span></span>  
 <span data-ttu-id="426a3-113">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="426a3-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="426a3-114">**標頭：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="426a3-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="426a3-115">**程式庫：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="426a3-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="426a3-116">**.NET framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="426a3-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="426a3-117">另請參閱</span><span class="sxs-lookup"><span data-stu-id="426a3-117">See Also</span></span>  
 [<span data-ttu-id="426a3-118">ICorDebugProcess5 介面</span><span class="sxs-lookup"><span data-stu-id="426a3-118">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)  
 [<span data-ttu-id="426a3-119">偵錯介面</span><span class="sxs-lookup"><span data-stu-id="426a3-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)