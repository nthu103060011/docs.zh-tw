---
title: ICorDebugILFrame::SetIP 方法
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.SetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::SetIP
helpviewer_keywords:
- SetIP method, ICorDebugILFrame interface [.NET Framework debugging]
- ICorDebugILFrame::SetIP method [.NET Framework debugging]
ms.assetid: 23f38dc1-85e4-4263-9235-2d05bbb6a833
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ed7de70c8ea26f46f44abb3e063c6e4c4b115666
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugilframesetip-method"></a>ICorDebugILFrame::SetIP 方法
將指令指標設定為 Microsoft intermediate language (MSIL) 程式碼中指定的位移位置。  
  
## <a name="syntax"></a>語法  
  
```  
HRESULT SetIP (  
    [in] ULONG32 nOffset  
);  
```  
  
#### <a name="parameters"></a>參數  
 `nOffset`  
 MSIL 程式碼中的位移的位置。  
  
## <a name="remarks"></a>備註  
 呼叫`SetIP`立即使所有框架和目前執行緒的鏈結。 如果偵錯工具需要呼叫之後的畫面格資訊`SetIP`，它必須執行新的堆疊追蹤。  
  
 [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)會嘗試保留的堆疊框架是處於有效狀態。 不過，即使框架是處於有效狀態，仍可能有問題，例如未初始化的區域變數。 呼叫端會負責確保執行程式的一致性。  
  
 64 位元平台上，指令指標無法移出`catch`或`finally`區塊。 如果`SetIP`稱為 「 若要讓這類的 64 位元平台上移動，它會傳回 HRESULT，指出失敗。  
  
## <a name="requirements"></a>需求  
 **平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **標頭：** CorDebug.idl、 CorDebug.h  
  
 **程式庫：** CorGuids.lib  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
