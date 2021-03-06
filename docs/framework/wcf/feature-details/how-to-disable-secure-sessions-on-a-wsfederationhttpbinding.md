---
title: HOW TO：在 WSFederationHttpBinding 上停用安全工作階段
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, federation
- federation
ms.assetid: 675fa143-6a4e-4be3-8afc-673334ab55ec
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 97fc358ac66bb92ccc40c92207bf6561f61b84f6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-disable-secure-sessions-on-a-wsfederationhttpbinding"></a>HOW TO：在 WSFederationHttpBinding 上停用安全工作階段
某些服務可能會要求聯合認證，但卻不支援安全工作階段。 在此情況下，您必須停用安全工作階段功能。 不同於 <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`>，則<xref:System.ServiceModel.WSFederationHttpBinding>類別並未提供停用安全工作階段的方式與服務通訊時。 反之，您必須建立自訂繫結，以便使用啟動安裝程式繫結來取代安全工作階段。  
  
 此主題將示範如何修改 <xref:System.ServiceModel.WSFederationHttpBinding> 內所包含的繫結項目來建立自訂繫結。 除了不使用安全工作階段之外，其餘結果會與 <xref:System.ServiceModel.WSFederationHttpBinding> 相同。  
  
### <a name="to-create-a-custom-federated-binding-without-secure-session"></a>若要建立一個不包含安全工作階段的自訂聯合繫結  
  
1.  在程式碼中以命令方式建立 <xref:System.ServiceModel.WSFederationHttpBinding> 類別的執行個體，或是從組態檔中載入一個執行個體。  
  
2.  將 <xref:System.ServiceModel.WSFederationHttpBinding> 複製到 <xref:System.ServiceModel.Channels.CustomBinding>。  
  
3.  在 <xref:System.ServiceModel.Channels.SecurityBindingElement> 中尋找 <xref:System.ServiceModel.Channels.CustomBinding>。  
  
4.  在 <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters> 中尋找 <xref:System.ServiceModel.Channels.SecurityBindingElement>。  
  
5.  將原始的 <xref:System.ServiceModel.Channels.SecurityBindingElement> 取代為來自 <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters> 的啟動安裝安全性繫結項目。  
  
## <a name="example"></a>範例  
 下列範例會建立了一個不包含安全工作階段的自訂聯合繫結。  
  
 [!code-csharp[c_CustomFederationBinding#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customfederationbinding/cs/c_customfederationbinding.cs#0)]
 [!code-vb[c_CustomFederationBinding#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customfederationbinding/vb/c_customfederationbinding.vb#0)]  
  
## <a name="compiling-the-code"></a>編譯程式碼  
  
-   若要編譯此程式碼範例，請建立一個可參考 System.ServiceModel.dll 組件的專案。  
  
## <a name="see-also"></a>另請參閱  
 [繫結和安全性](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)
