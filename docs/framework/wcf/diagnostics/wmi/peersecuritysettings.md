---
title: PeerSecuritySettings
ms.date: 03/30/2017
ms.assetid: 24ae0d35-f3a3-419b-afd6-686e22aae27b
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 58b372f26fee7dc180d75731fd4855db569c87c7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
---
# <a name="peersecuritysettings"></a>PeerSecuritySettings
PeerSecuritySettings  
  
## <a name="syntax"></a>語法  
  
```  
class PeerSecuritySettings  
{  
  string Mode;  
  PeerTransportSecuritySettings Transport;  
};  
```  
  
## <a name="methods"></a>方法  
 PeerSecuritySettings 類別並未定義任何方法。  
  
## <a name="properties"></a>屬性  
 PeerSecuritySettings 類別有下列屬性：  
  
### <a name="mode"></a>模式  
 資料型別：字串  
  
 存取類型：唯讀  
  
 使用繫結設定之端點是否採用訊息層級與傳輸層級安全性。  
  
### <a name="transport"></a>Transport  
 資料型別：PeerTransportSecuritySettings  
  
 存取類型：唯讀  
  
 傳輸安全性設定。  
  
## <a name="requirements"></a>需求  
  
|MOF|於 Servicemodel.mof 中宣告。|  
|---------|-----------------------------------|  
|命名空間|於 root\ServiceModel 中定義|  
  
## <a name="see-also"></a>另請參閱  
 <xref:System.ServiceModel.PeerSecuritySettings>
