---
title: '&lt;清除&gt;connectionManagement （網路設定） 的項目'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/connectionManagement/clear
- http://schemas.microsoft.com/.NetConfiguration/v2.0#clear
helpviewer_keywords:
- <clear> element, connectionManagement
- connectionManagement, clear element
- clear element, connectionManagement
- <connectionManagement>, clear element
ms.assetid: fb259282-84c4-4dc4-a226-78d904a6edc3
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 5bcd17cfe1f3bd7531453b62552a4907df5b96bc
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/03/2018
---
# <a name="ltcleargt-element-for-connectionmanagement-network-settings"></a>&lt;清除&gt;connectionManagement （網路設定） 的項目
清除連線管理清單中。  
  
 \<configuration>  
\<system.net>  
\<connectionManagement >  
\<清除 >  
  
## <a name="syntax"></a>語法  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a>屬性和項目  
 下列各節描述屬性、子項目和父項目。  
  
### <a name="attributes"></a>屬性  
 無。  
  
### <a name="child-elements"></a>子項目  
 無。  
  
### <a name="parent-elements"></a>父項目  
  
|**目**|**描述**|  
|-----------------|---------------------|  
|[connectionManagement](../../../../../docs/framework/configure-apps/file-schema/network/connectionmanagement-element-network-settings.md)|指定連接至網路主機的連線數目上限。|  
  
## <a name="remarks"></a>備註  
 `clear`項目清除從連線管理清單中的所有項目。  
  
## <a name="configuration-files"></a>組態檔  
 此項目可以用於應用程式組態檔或電腦組態檔 (Machine.config)。  
  
## <a name="example"></a>範例  
 下列範例會清除連線管理清單，並將新 www.contoso.com 伺服器和所有其他網路主機的連接管理項目。  
  
```xml  
<configuration>  
  <system.net>  
    <connectionManagement>  
      <clear/>  
      <add address = "http://www.contoso.com" maxconnection = "4" />  
      <add address = "*" maxconnection = "2" />  
    </connectionManagement>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>另請參閱  
 <xref:System.Net.ServicePoint>  
 <xref:System.Net.ServicePointManager>  
 [網路設定結構描述](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
