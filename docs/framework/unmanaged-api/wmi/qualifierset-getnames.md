---
title: QualifierSet_GetNames 函式 （Unmanaged API 參考）
description: QualifierSet_GetNames 函式物件或屬性擷取限定詞的名稱。
ms.date: 11/06/2017
api_name:
- QualifierSet_GetNames
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_GetNames
helpviewer_keywords:
- QualifierSet_GetNames function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b7c96439cf50c18e336baa70cf463b9463203290
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
---
# <a name="qualifiersetgetnames-function"></a>QualifierSet_GetNames 函式
擷取所有的限定詞或都是從目前的物件或屬性的某些限定詞的名稱。 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>語法  
  
```  
HRESULT QualifierSet_GetNames (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr, 
   [in] LONG                 lFlags,
   [out] SAFEARRAY (BSTR)**  pstrNames
); 
```  

## <a name="parameters"></a>參數

`vFunc`   
[in]未使用這個參數。

`ptr`   
[in]指標[IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx)執行個體。

`lFlags`   
[in]其中一個的下列旗標或值，指定要包含在列舉中的名稱。

|常數  |值  |描述  |
|---------|---------|---------|
|  | 0 | 傳回所有限定詞的名稱。 |
| `WBEM_FLAG_LOCAL_ONLY` | 0x10 | 傳回目前的屬性或物件特定限定詞的名稱。 <br/> 屬性： 返回 （包括覆寫） 的屬性特定辨識符號，並不是這些限定詞傳播從類別定義。 <br/> 執行個體： 傳回只可使用特定執行個體的限定詞名稱。 <br/> 類別： 返回衍生的類別 beiong 特定只限定詞。
|`WBEM_FLAG_PROPAGATED_ONLY` | 0x20 | 傳回的傳播限定詞的名稱，從另一個物件。 <br/> 屬性： 傳回僅限定詞傳播給這個屬性從類別定義中，而不從本身的屬性。 <br/> 執行個體： 傳回傳播這些辨識符號，從類別定義。 <br/> 類別： 傳回繼承自父類別的只有這些限定詞的名稱。 |

`pstrNames` [out]新`SAFEARRAY`包含要求的名稱。 陣列可以有項目為 0。 如果發生錯誤時，新`SAFEARRAY`就不會傳回。

## <a name="return-value"></a>傳回值

這個函式傳回下列值會定義在*WbemCli.h*標頭檔，或者您可以定義它們以常數的形式在程式碼中：

|常數  |值  |描述  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | 參數不是有效的。 |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | 使用開始新的列舉型別沒有足夠的記憶體。 |
|`WBEM_S_NO_ERROR` | 0 | 函式呼叫成功。  |
  
## <a name="remarks"></a>備註

此函式會包裝呼叫[IWbemQualifierSet::GetNames](https://msdn.microsoft.com/library/aa391868(v=vs.85).aspx)方法。

一旦您已擷取的限定詞的名稱，您可以藉由呼叫依照名稱存取每個限定詞[QualifierSet_Get](qualifierset-get.md)函式。 

不是給定的物件，因此有零個限定詞，針對錯誤中的字串數目`pstrNames`傳回可以是 0，即使此函數會傳回`WBEM_S_NO_ERROR`。

## <a name="requirements"></a>需求  
 **平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **標頭：** WMINet_Utils.idl  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>另請參閱  
[WMI 和效能計數器 （Unmanaged API 參考）](index.md)
