---
title: "ISymUnmanagedReader::GetDocumentVersion 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedReader.GetDocumentVersion
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedReader::GetDocumentVersion
helpviewer_keywords:
- GetDocumentVersion method [.NET Framework debugging]
- ISymUnmanagedReader::GetDocumentVersion method [.NET Framework debugging]
ms.assetid: a51f1f64-e084-44c5-830c-2222da5a6bbf
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 377457fa852e1a4ae140f72d2dd83731490b81d9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedreadergetdocumentversion-method"></a>ISymUnmanagedReader::GetDocumentVersion 方法
取得指定的文件指定的版本。 文件版本從 1 開始，就會遞增每次更新文件時使用[UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md)方法。 如果`pbCurrent`參數是`true`，這是最新版本的文件。  
  
## <a name="syntax"></a>語法  
  
```  
HRESULT GetDocumentVersion (  
    [in]  ISymUnmanagedDocument *pDoc,  
    [out] int* version,  
    [out] BOOL* pbCurrent);  
```  
  
#### <a name="parameters"></a>參數  
 `pDoc`  
 [in]指定的文件。  
  
 `version`  
 [out]指定的文件的版本會接收變數的指標。  
  
 `pbCurrent`  
 [out]接收變數的指標`true`如果這是最新版本的文件或`false`如果不是最新版本。  
  
## <a name="return-value"></a>傳回值  
 如果方法成功則為 S_OK否則，E_FAIL 或其他錯誤程式碼。  
  
## <a name="requirements"></a>需求  
 **標頭：**於 CorSym.idl、 CorSym.h  
  
## <a name="see-also"></a>另請參閱  
 [ISymUnmanagedReader 介面](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)