---
title: "CorTokenType 列舉"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorTokenType
api_location: mscoree.dll
api_type: COM
f1_keywords: CorTokenType
helpviewer_keywords: CorTokenType enumeration [.NET Framework metadata]
ms.assetid: 93c9a369-225f-4eff-9b78-3fbee4902cf1
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 1910321942ebac26d8c377f9d156cdf97bd34b62
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2017
---
# <a name="cortokentype-enumeration"></a><span data-ttu-id="b46e3-102">CorTokenType 列舉</span><span class="sxs-lookup"><span data-stu-id="b46e3-102">CorTokenType Enumeration</span></span>
<span data-ttu-id="b46e3-103">表示中繼資料語彙基元的類型。</span><span class="sxs-lookup"><span data-stu-id="b46e3-103">Indicates the type of a metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b46e3-104">語法</span><span class="sxs-lookup"><span data-stu-id="b46e3-104">Syntax</span></span>  
  
```  
typedef enum CorTokenType {  
  
    mdtModule                       = 0x00000000,  
    mdtTypeRef                      = 0x01000000,  
    mdtTypeDef                      = 0x02000000,  
    mdtFieldDef                     = 0x04000000,  
    mdtMethodDef                    = 0x06000000,  
    mdtParamDef                     = 0x08000000,  
    mdtInterfaceImpl                = 0x09000000,  
    mdtMemberRef                    = 0x0a000000,  
    mdtCustomAttribute              = 0x0c000000,  
    mdtPermission                   = 0x0e000000,  
    mdtSignature                    = 0x11000000,  
    mdtEvent                        = 0x14000000,  
    mdtProperty                     = 0x17000000,  
    mdtModuleRef                    = 0x1a000000,  
    mdtTypeSpec                     = 0x1b000000,  
    mdtAssembly                     = 0x20000000,  
    mdtAssemblyRef                  = 0x23000000,  
    mdtFile                         = 0x26000000,  
    mdtExportedType                 = 0x27000000,  
    mdtManifestResource             = 0x28000000,  
    mdtGenericParam                 = 0x2a000000,  
    mdtMethodSpec                   = 0x2b000000,  
    mdtGenericParamConstraint       = 0x2c000000,  
    mdtString                       = 0x70000000,  
    mdtName                         = 0x71000000,  
    mdtBaseType                     = 0x72000000  
  
} CorTokenType;  
```  
  
## <a name="members"></a><span data-ttu-id="b46e3-105">成員</span><span class="sxs-lookup"><span data-stu-id="b46e3-105">Members</span></span>  
  
|<span data-ttu-id="b46e3-106">成員</span><span class="sxs-lookup"><span data-stu-id="b46e3-106">Member</span></span>|<span data-ttu-id="b46e3-107">說明</span><span class="sxs-lookup"><span data-stu-id="b46e3-107">Description</span></span>|  
|------------|-----------------|  
|`mdtModule`|<span data-ttu-id="b46e3-108">`mdModule`語彙基元。</span><span class="sxs-lookup"><span data-stu-id="b46e3-108">An `mdModule` token.</span></span>|  
|`mdtTypeRef`|<span data-ttu-id="b46e3-109">`mdTypeRef`語彙基元。</span><span class="sxs-lookup"><span data-stu-id="b46e3-109">An `mdTypeRef` token.</span></span>|  
|`mdtTypeDef`|<span data-ttu-id="b46e3-110">`mdTypeDef`語彙基元。</span><span class="sxs-lookup"><span data-stu-id="b46e3-110">An `mdTypeDef` token.</span></span>|  
|`mdtFieldDef`|<span data-ttu-id="b46e3-111">`mdFieldDef`語彙基元。</span><span class="sxs-lookup"><span data-stu-id="b46e3-111">An `mdFieldDef` token.</span></span>|  
|`mdtMethodDef`|<span data-ttu-id="b46e3-112">`mdMethodDef`語彙基元。</span><span class="sxs-lookup"><span data-stu-id="b46e3-112">An `mdMethodDef` token.</span></span>|  
|`mdtParamDef`|<span data-ttu-id="b46e3-113">`mdParamDef`語彙基元。</span><span class="sxs-lookup"><span data-stu-id="b46e3-113">An `mdParamDef` token.</span></span>|  
|`mdtInterfaceImpl`|<span data-ttu-id="b46e3-114">`mdInterfaceImpl`語彙基元。</span><span class="sxs-lookup"><span data-stu-id="b46e3-114">An `mdInterfaceImpl` token.</span></span>|  
|`mdtMemberRef`|<span data-ttu-id="b46e3-115">`mdMemberRef`語彙基元。</span><span class="sxs-lookup"><span data-stu-id="b46e3-115">An `mdMemberRef` token.</span></span>|  
|`mdtCustomAttribute`|<span data-ttu-id="b46e3-116">`mdCustomAttribute`語彙基元。</span><span class="sxs-lookup"><span data-stu-id="b46e3-116">An `mdCustomAttribute` token.</span></span>|  
|`mdtPermission`|<span data-ttu-id="b46e3-117">`mdPermission`語彙基元。</span><span class="sxs-lookup"><span data-stu-id="b46e3-117">An `mdPermission` token.</span></span>|  
|`mdtSignature`|<span data-ttu-id="b46e3-118">`mdSignature`語彙基元。</span><span class="sxs-lookup"><span data-stu-id="b46e3-118">An `mdSignature` token.</span></span>|  
|`mdtEvent`|<span data-ttu-id="b46e3-119">`mdEvent`語彙基元。</span><span class="sxs-lookup"><span data-stu-id="b46e3-119">An `mdEvent` token.</span></span>|  
|`mdtProperty`|<span data-ttu-id="b46e3-120">`mdProperty`語彙基元。</span><span class="sxs-lookup"><span data-stu-id="b46e3-120">An `mdProperty` token.</span></span>|  
|`mdtModuleRef`|<span data-ttu-id="b46e3-121">`mdModuleRef`語彙基元。</span><span class="sxs-lookup"><span data-stu-id="b46e3-121">An `mdModuleRef` token.</span></span>|  
|`mdtTypeSpec`|<span data-ttu-id="b46e3-122">`mdTypeSpec`語彙基元。</span><span class="sxs-lookup"><span data-stu-id="b46e3-122">An `mdTypeSpec` token.</span></span>|  
|`mdtAssembly`|<span data-ttu-id="b46e3-123">`mdAssembly`語彙基元。</span><span class="sxs-lookup"><span data-stu-id="b46e3-123">An `mdAssembly` token.</span></span>|  
|`mdtAssemblyRef`|<span data-ttu-id="b46e3-124">`mdAssemblyRef`語彙基元。</span><span class="sxs-lookup"><span data-stu-id="b46e3-124">An `mdAssemblyRef` token.</span></span>|  
|`mdtFile`|<span data-ttu-id="b46e3-125">`mdFile`語彙基元。</span><span class="sxs-lookup"><span data-stu-id="b46e3-125">An `mdFile` token.</span></span>|  
|`mdtExportedType`|<span data-ttu-id="b46e3-126">`mdExportedType`語彙基元。</span><span class="sxs-lookup"><span data-stu-id="b46e3-126">An `mdExportedType` token.</span></span>|  
|`mdtManifestResource`|<span data-ttu-id="b46e3-127">`mdManifestResource`語彙基元。</span><span class="sxs-lookup"><span data-stu-id="b46e3-127">An `mdManifestResource` token.</span></span>|  
|`mdtGenericParam`|<span data-ttu-id="b46e3-128">`mdGenericParam`語彙基元。</span><span class="sxs-lookup"><span data-stu-id="b46e3-128">An `mdGenericParam` token.</span></span>|  
|`mdtMethodSpec`|<span data-ttu-id="b46e3-129">`mdMethodSpec`語彙基元。</span><span class="sxs-lookup"><span data-stu-id="b46e3-129">An `mdMethodSpec` token.</span></span>|  
|`mdtGenericParamConstraint`|<span data-ttu-id="b46e3-130">`mdGenericParamConstraint`語彙基元。</span><span class="sxs-lookup"><span data-stu-id="b46e3-130">An `mdGenericParamConstraint` token.</span></span>|  
|`mdtString`|<span data-ttu-id="b46e3-131">`mdString`語彙基元。</span><span class="sxs-lookup"><span data-stu-id="b46e3-131">An `mdString` token.</span></span>|  
|`mdtName`|<span data-ttu-id="b46e3-132">`mdName`語彙基元。</span><span class="sxs-lookup"><span data-stu-id="b46e3-132">An `mdName` token.</span></span>|  
|`mdtBaseType`|<span data-ttu-id="b46e3-133">未使用。</span><span class="sxs-lookup"><span data-stu-id="b46e3-133">Not used.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b46e3-134">備註</span><span class="sxs-lookup"><span data-stu-id="b46e3-134">Remarks</span></span>  
 <span data-ttu-id="b46e3-135">每個值會等於對應的中繼資料語彙基元中的第一個位元組的值。</span><span class="sxs-lookup"><span data-stu-id="b46e3-135">Each value is equal to the value of the top byte in the corresponding metadata token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b46e3-136">需求</span><span class="sxs-lookup"><span data-stu-id="b46e3-136">Requirements</span></span>  
 <span data-ttu-id="b46e3-137">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b46e3-137">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b46e3-138">**標頭：** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="b46e3-138">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="b46e3-139">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b46e3-139">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b46e3-140">另請參閱</span><span class="sxs-lookup"><span data-stu-id="b46e3-140">See Also</span></span>  
 [<span data-ttu-id="b46e3-141">中繼資料列舉</span><span class="sxs-lookup"><span data-stu-id="b46e3-141">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)