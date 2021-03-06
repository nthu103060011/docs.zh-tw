---
title: HOW TO：使用 WCF 用戶端來存取 WSE 3.0 服務
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1f9bcd9b-8f8f-47fa-8f1e-0d47236eb800
ms.openlocfilehash: 54d795858b85bd72a01f619b3603c9927df655d5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-access-a-wse-30-service-with-a-wcf-client"></a>HOW TO：使用 WCF 用戶端來存取 WSE 3.0 服務
WCF 用戶端設定為使用 August 2004 Ws-addressing 規格版本時，Windows Communication Foundation (WCF) 用戶端會將 Microsoft.NET 服務的連線層級相容 Web Services Enhancements (WSE) 3.0 與。 不過，WSE 3.0 服務不支援中繼資料交換 (MEX) 通訊協定，因此當您使用[ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)若要建立 WCF 用戶端類別，安全性設定不會套用至所產生WCF 用戶端。 因此，您必須指定安全性設定，將 WSE 3.0 服務需要產生 WCF 用戶端之後。  
  
 您可以使用自訂繫結，若要將 WSE 3.0 服務的需求和 WSE 3.0 服務的 WCF 用戶端之間的互通需求納入考量來套用這些安全性設定。 這些互通性需求包含上述的 WS-Addressing August 2004 規格使用和 WSE 3.0 預設訊息保護 <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncrypt>。 WCF 的預設訊息保護為<xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncryptAndEncryptSignature>。 本主題詳細說明如何建立與 WSE 3.0 服務相互操作的 WCF 繫結。 WCF 還提供包含這個繫結的範例。 如需有關此範例的詳細資訊，請參閱[與 ASMX Web 服務互通](../../../../docs/framework/wcf/samples/interoperating-with-asmx-web-services.md)。  
  
### <a name="to-access-a-wse-30-web-service-with-a-wcf-client"></a>若要使用 WCF 用戶端來存取 WSE 3.0 Web 服務  
  
1.  執行[ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)建立 WSE 3.0 Web 服務的 WCF 用戶端。  
  
     WSE 3.0 Web 服務中，建立 WCF 用戶端。 因為 WSE 3.0 不支援 MEX 通訊協定，所以您無法使用此工具擷取 Web 服務的安全性需求。 應用程式開發人員必須為用戶端加入安全性設定。  
  
     如需建立 WCF 用戶端的詳細資訊，請參閱[How to： 建立用戶端](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md)。  
  
2.  建立類別，表示可與 WSE 3.0 Web 服務通訊的繫結。  
  
     下列類別是一部分[與 WSE 互通](http://msdn.microsoft.com/library/f6816861-96a0-45f9-8736-8e4e82cd3a41)範例：  
  
    1.  建立從 <xref:System.ServiceModel.Channels.Binding> 類別衍生的類別。  
  
         下列程式碼範例會建立一個名為 `WseHttpBinding` 的類別，此類別衍生自 <xref:System.ServiceModel.Channels.Binding> 類別。  
  
         [!code-csharp[c_WCFClientToWSEService#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#1)]
         [!code-vb[c_WCFClientToWSEService#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#1)]  
  
    2.  將屬性加入至類別，這些屬性會指定 WSE 服務所使用的 WSE 通行判斷提示 (Turnkey Assertion)、是否需要衍生金鑰、是否使用安全工作階段、是否需要簽章確認，以及訊息保護設定。 在 WSE 3.0 通行判斷提示會指定用戶端或 Web 服務的安全性需求，類似於 WCF 中的繫結的驗證模式。  
  
         下列程式碼範例會定義 `SecurityAssertion`、`RequireDerivedKeys`、`EstablishSecurityContext` 和 `MessageProtectionOrder` 屬性，這些屬性會分別指定 WSE 通行判斷提示、是否需要衍生金鑰、是否使用安全工作階段、是否需要簽章確認，以及訊息保護設定。  
  
         [!code-csharp[c_WCFClientToWSEService#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#3)]
         [!code-vb[c_WCFClientToWSEService#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#3)]  
  
    3.  覆寫 <xref:System.ServiceModel.Channels.Binding.CreateBindingElements%2A> 方法來設定繫結屬性。  
  
         下列程式碼範例會藉由取得 `SecurityAssertion` 和 `MessageProtectionOrder` 屬性的值，指定傳輸、訊息編碼和訊息保護設定。  
  
         [!code-csharp[c_WCFClientToWSEService#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#2)]
         [!code-vb[c_WCFClientToWSEService#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#2)]  
  
3.  在用戶端應用程式程式碼中，加入程式碼以設定繫結屬性。  
  
     下列程式碼範例指定 WCF 用戶端必須使用訊息保護和驗證所定義的 WSE 3.0`AnonymousForCertificate`通行安全性判斷提示。 此外，也需要安全工作階段和衍生金鑰。  
  
     [!code-csharp[c_WCFClientToWSEService#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/client.cs#4)]
     [!code-vb[c_WCFClientToWSEService#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/client.vb#4)]  
  
## <a name="example"></a>範例  
 下列程式碼範例會定義自訂的繫結，此繫結會公開 WSE 3.0 通行安全性判斷提示屬性的對應屬性。 名為此自訂繫結`WseHttpBinding`，然後用來指定可與 WSSecurityAnonymous WSE 3.0 快速入門範例通訊的 WCF 用戶端的繫結屬性。  
  
  
  
## <a name="see-also"></a>另請參閱  
 <xref:System.ServiceModel.Channels.Binding>  
 [與 WSE 互通](http://msdn.microsoft.com/library/f6816861-96a0-45f9-8736-8e4e82cd3a41)
