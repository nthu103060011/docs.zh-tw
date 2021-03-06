---
title: HOW TO：使用服務 Moniker 搭配中繼資料交換合約
ms.date: 03/30/2017
ms.assetid: c41a07e5-cb9d-45d6-9ea4-34511e227faf
ms.openlocfilehash: 6265860c2e1efb2f74a0243157a223a33889629a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-use-a-service-moniker-with-metadata-exchange-contracts"></a>HOW TO：使用服務 Moniker 搭配中繼資料交換合約
之後開發一些新的 WCF 服務，您可能會決定您想要能夠從指令碼或 Visual Basic 6.0 應用程式呼叫這些服務。 一種方法是將產生 WCF 用戶端組件、 向 COM 註冊組件、 組件安裝在 GAC 中，然後再從 Visual Basic 程式碼參照 COM 型別。 當您發佈應用程式時，您必須將發佈的 WCF 用戶端組件。 然後使用者必須向 COM 註冊 WCF 用戶端組件，並將它放在 GAC 中。 WCF COM Interop 也可讓您不需依賴 WCF 用戶端組件中進行相同的服務呼叫。 WCF moniker 可讓您從任何 COM 相容語言 （Visual Basic、 VBScript、 Visual Basic for Applications (VBA) 等等) 呼叫任何 WCF 服務，藉由指定的中繼資料交換 (Mex) 端點 URI 用來擷取類型的服務 moniker服務的相關資訊。 本主題描述如何呼叫使用者入門 WCF 範例使用指定 Mex 端點的 WCF moniker。  
  
> [!NOTE]
>  WCF 用戶端組件所定義的型別實際上永遠不會具現化。 此組件僅用於中繼資料。  
  
### <a name="using-the-service-moniker-with-a-mex-address"></a>使用含有 Mex 位址的服務 Moniker  
  
1.  建置 「 使用者入門 」 範例並使用 Internet Explorer 瀏覽至其 URL (http://localhost/ServiceModelSamples/Service.svc)以確保服務正在運作。  
  
2.  建立 Visual Basic 指令碼或含有下列程式碼的 Visual Basic 應用程式：  
  
    ```  
    monString = "service:mexaddress=http://localhost/ServiceModelSamples/Service.svc/MEX"  
    monString = monString + ", address=http://localhost/ServiceModelSamples/Service.svc"  
    monString = monString + ", contract=ICalculator, contractNamespace=http://Microsoft.ServiceModel.Samples"  
    monString = monString + ", binding=WSHttpBinding_ICalculator, bindingNamespace=http://Microsoft.ServiceModel.Samples"  
  
    Set calc = GetObject(monString)  
    MsgBox calc.Add(3, 4)  
    ```  
  
3.  執行 Visual Basic 應用程式或指令碼。  
  
    > [!NOTE]
    >  您正在呼叫的服務必須公開 Mex 端點，Moniker 才能從服務讀取中繼資料。 如需詳細資訊，請參閱[How to： 使用組態檔的服務發行中繼資料](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)。  
  
    > [!NOTE]
    >  如果 Moniker 的格式錯誤或服務無法使用，則呼叫 `GetObject` 時將會傳回「無效的語法」錯誤。  如果您收到這個錯誤，請確定您所使用的 Moniker 正確無誤，而且此服務為可用狀態。  
  
## <a name="see-also"></a>另請參閱  
 [如何：使用 Windows Communication Foundation 服務 Moniker 且不註冊](../../../../docs/framework/wcf/feature-details/use-the-wcf-service-moniker-without-registration.md)  
 [如何：使用服務 Moniker 搭配 WSDL 合約](../../../../docs/framework/wcf/feature-details/how-to-use-a-service-moniker-with-wsdl-contracts.md)
