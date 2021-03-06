---
title: IMetaDataEmit::DefineParam 方法
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineParam
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineParam
helpviewer_keywords:
- IMetaDataEmit::DefineParam method [.NET Framework metadata]
- DefineParam method [.NET Framework metadata]
ms.assetid: d86a3d14-4796-4909-9591-dfafe3de5ce4
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5d49ac70aceb76f69711ea4bf514f69697ac156c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
---
# <a name="imetadataemitdefineparam-method"></a>IMetaDataEmit::DefineParam 方法
建立與指定的簽章與指定的語彙基元所參考的方法參數的定義，並取得該參數定義的語彙基元。  
  
## <a name="syntax"></a>語法  
  
```  
HRESULT DefineParam (  
    [in]  mdMethodDef md,   
    [in]  ULONG       ulParamSeq,   
    [in]  LPCWSTR     szName,   
    [in]  DWORD       dwParamFlags,   
    [in]  DWORD       dwCPlusTypeFlag,   
    [in]  void const  *pValue,  
    [in]  ULONG       cchValue,   
    [out] mdParamDef  *ppd   
);  
```  
  
#### <a name="parameters"></a>參數  
 `md`  
 [in]正在定義其參數的方法的語彙基元。  
  
 `ulParamSeq`  
 [in]參數的順序編號。  
  
 `szName`  
 [in]以 Unicode 參數的名稱。  
  
 `dwParamFlags`  
 [in]參數的旗標。 這是位元遮罩`CorParamAttr`值。  
  
 `dwCPlusTypeFlag`  
 [in]`ELEMENT_TYPE_` *\** 常數的值。  
  
 `pValue`  
 [in]參數的常值。  
  
 `cchValue`  
 [in]大小，以 Unicode 字元的`pValue`。  
  
 `ppd`  
 [out]`mdParamDef`指派的語彙基元。  
  
## <a name="remarks"></a>備註  
 中的值序列`ulParamSeq`參數 1 為開頭。 傳回值具有 0 的序號。  
  
## <a name="requirements"></a>需求  
 **平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **標頭：** Cor.h  
  
 **程式庫：**做為 MSCorEE.dll 中的資源  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另請參閱  
 [IMetaDataEmit 介面](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [IMetaDataEmit2 介面](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
