---
title: "IMetaDataEmit::SetFieldProps 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.SetFieldProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::SetFieldProps
helpviewer_keywords:
- IMetaDataEmit::SetFieldProps method [.NET Framework metadata]
- SetFieldProps method [.NET Framework metadata]
ms.assetid: 47132dda-fa92-4bd1-ae4b-24cd9a60665a
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5f031e79deab57184043eaa44d2d8a3d369187c7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitsetfieldprops-method"></a><span data-ttu-id="232f9-102">IMetaDataEmit::SetFieldProps 方法</span><span class="sxs-lookup"><span data-stu-id="232f9-102">IMetaDataEmit::SetFieldProps Method</span></span>
<span data-ttu-id="232f9-103">設定或更新指定的欄位語彙基元所參考之欄位的預設值。</span><span class="sxs-lookup"><span data-stu-id="232f9-103">Sets or updates the default value for the field referenced by the specified field token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="232f9-104">語法</span><span class="sxs-lookup"><span data-stu-id="232f9-104">Syntax</span></span>  
  
```  
HRESULT SetFieldProps (  
    [in]  mdFieldDef  fd,   
    [in]  DWORD       dwFieldFlags,   
    [in]  DWORD       dwCPlusTypeFlag,   
    [in]  void const  *pValue,   
    [in]  ULONG       cchValue   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="232f9-105">參數</span><span class="sxs-lookup"><span data-stu-id="232f9-105">Parameters</span></span>  
 `fd`  
 <span data-ttu-id="232f9-106">[in]目標欄位語彙基元。</span><span class="sxs-lookup"><span data-stu-id="232f9-106">[in] The token for the target field.</span></span>  
  
 `dwFieldFlags`  
 <span data-ttu-id="232f9-107">[in]欄位屬性。</span><span class="sxs-lookup"><span data-stu-id="232f9-107">[in] Field attributes.</span></span> <span data-ttu-id="232f9-108">這是位元遮罩`CorFieldAttr`值。</span><span class="sxs-lookup"><span data-stu-id="232f9-108">This is a bitmask of `CorFieldAttr` values.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="232f9-109">[in]`ELEMENT_TYPE_`  *\** 常數的值。</span><span class="sxs-lookup"><span data-stu-id="232f9-109">[in] The `ELEMENT_TYPE_`*\** for the constant value.</span></span> <span data-ttu-id="232f9-110">這是`CorElementType`值。</span><span class="sxs-lookup"><span data-stu-id="232f9-110">This is a `CorElementType` value.</span></span> <span data-ttu-id="232f9-111">如果未定義常數，此值設定為`ELEMENT_TYPE_END`。</span><span class="sxs-lookup"><span data-stu-id="232f9-111">If a constant is not being defined, set this value to `ELEMENT_TYPE_END`.</span></span>  
  
 `pValue`  
 <span data-ttu-id="232f9-112">[in]欄位的常值。</span><span class="sxs-lookup"><span data-stu-id="232f9-112">[in] The constant value for the field.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="232f9-113">[in]大小，以 Unicode 字元的`pValue`。</span><span class="sxs-lookup"><span data-stu-id="232f9-113">[in] The size, in Unicode characters, of `pValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="232f9-114">需求</span><span class="sxs-lookup"><span data-stu-id="232f9-114">Requirements</span></span>  
 <span data-ttu-id="232f9-115">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="232f9-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="232f9-116">**標頭：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="232f9-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="232f9-117">**程式庫：**做為 MSCorEE.dll 中的資源</span><span class="sxs-lookup"><span data-stu-id="232f9-117">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="232f9-118">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="232f9-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="232f9-119">另請參閱</span><span class="sxs-lookup"><span data-stu-id="232f9-119">See Also</span></span>  
 [<span data-ttu-id="232f9-120">IMetaDataEmit 介面</span><span class="sxs-lookup"><span data-stu-id="232f9-120">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="232f9-121">IMetaDataEmit2 介面</span><span class="sxs-lookup"><span data-stu-id="232f9-121">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)