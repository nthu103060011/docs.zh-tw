---
title: "IMetaDataImport::GetPinvokeMap 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetPinvokeMap
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetPinvokeMap
helpviewer_keywords:
- IMetaDataImport::GetPinvokeMap method [.NET Framework metadata]
- GetPinvokeMap method [.NET Framework metadata]
ms.assetid: b8685c1e-b80c-4198-8eb3-748d6f48a99e
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: adb6a9a5f53dcfd8ada5b3aa9d75daac18d50283
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportgetpinvokemap-method"></a><span data-ttu-id="707ad-102">IMetaDataImport::GetPinvokeMap 方法</span><span class="sxs-lookup"><span data-stu-id="707ad-102">IMetaDataImport::GetPinvokeMap Method</span></span>
<span data-ttu-id="707ad-103">取得 ModuleRef 語彙基元以代表 PInvoke 呼叫的目標組件。</span><span class="sxs-lookup"><span data-stu-id="707ad-103">Gets a ModuleRef token to represent the target assembly of a PInvoke call.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="707ad-104">語法</span><span class="sxs-lookup"><span data-stu-id="707ad-104">Syntax</span></span>  
  
```  
HRESULT GetPinvokeMap (  
   [in]  mdToken       tk,  
   [out] DWORD         *pdwMappingFlags,  
   [out] LPWSTR        szImportName,  
   [in]  ULONG         cchImportName,  
   [out] ULONG         *pchImportName,  
   [out] mdModuleRef   *pmrImportDLL  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="707ad-105">參數</span><span class="sxs-lookup"><span data-stu-id="707ad-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="707ad-106">[in]若要取得的 PInvoke 對應中繼資料 FieldDef 或 MethodDef 語彙基元。</span><span class="sxs-lookup"><span data-stu-id="707ad-106">[in] A FieldDef or MethodDef token to get the PInvoke mapping metadata for.</span></span>  
  
 `pdwMappingFlags`  
 <span data-ttu-id="707ad-107">[out]使用對應的旗標指標。</span><span class="sxs-lookup"><span data-stu-id="707ad-107">[out] A pointer to flags used for mapping.</span></span> <span data-ttu-id="707ad-108">這個值是從位元遮罩[CorPinvokeMap](../../../../docs/framework/unmanaged-api/metadata/corpinvokemap-enumeration.md)列舉型別。</span><span class="sxs-lookup"><span data-stu-id="707ad-108">This value is a bitmask from the [CorPinvokeMap](../../../../docs/framework/unmanaged-api/metadata/corpinvokemap-enumeration.md) enumeration.</span></span>  
  
 `szImportName`  
 <span data-ttu-id="707ad-109">[out]未受管理的目標 DLL 的名稱。</span><span class="sxs-lookup"><span data-stu-id="707ad-109">[out] The name of the unmanaged target DLL.</span></span>  
  
 `cchImportName`  
 <span data-ttu-id="707ad-110">[in]中的寬字元大小`szImportName`。</span><span class="sxs-lookup"><span data-stu-id="707ad-110">[in] The size in wide characters of `szImportName`.</span></span>  
  
 `pchImportName`  
 <span data-ttu-id="707ad-111">[out]傳回的寬字元數目`szImportName`。</span><span class="sxs-lookup"><span data-stu-id="707ad-111">[out] The number of wide characters returned in `szImportName`.</span></span>  
  
 `pmrImportDLL`  
 <span data-ttu-id="707ad-112">[out]代表未受管理的目標物件程式庫 ModuleRef 語彙基元的指標。</span><span class="sxs-lookup"><span data-stu-id="707ad-112">[out] A pointer to a ModuleRef token that represents the unmanaged target object library.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="707ad-113">需求</span><span class="sxs-lookup"><span data-stu-id="707ad-113">Requirements</span></span>  
 <span data-ttu-id="707ad-114">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="707ad-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="707ad-115">**標頭：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="707ad-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="707ad-116">**程式庫：**包含做為 MsCorEE.dll 中的資源</span><span class="sxs-lookup"><span data-stu-id="707ad-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="707ad-117">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="707ad-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="707ad-118">另請參閱</span><span class="sxs-lookup"><span data-stu-id="707ad-118">See Also</span></span>  
 [<span data-ttu-id="707ad-119">IMetaDataImport 介面</span><span class="sxs-lookup"><span data-stu-id="707ad-119">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="707ad-120">IMetaDataImport2 介面</span><span class="sxs-lookup"><span data-stu-id="707ad-120">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)