---
title: '&lt;udpAnnouncementEndpoint&gt; 的 &lt;udpTransportSettings&gt;'
ms.date: 03/30/2017
ms.assetid: a7ddff1a-5eed-4bbc-8580-b95ef8890e1f
ms.openlocfilehash: 624dbada56a609452310218d26c5c6ff0ca49d64
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/03/2018
---
# <a name="ltudptransportsettingsgt-of-ltudpannouncementendpointgt"></a>&lt;udpAnnouncementEndpoint&gt; 的 &lt;udpTransportSettings&gt;
這個組態項目會公開 UDP 傳輸設定[ \<udpAnnoucementEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/udpannoucementendpoint.md)。  
  
\<system.ServiceModel>  
\<Kind >  
\<udpAnnouncementEndpoint >  
  
## <a name="syntax"></a>語法  
  
```xml  
<system.serviceModel>  
  <standardEndpoints>
    <udpAnnouncementEndpoint>
      <standardEndpoint>
        <updTransportSettings duplicateMessageHistoryLength="Integer" 
                              maxBufferPoolSize="Integer" 
                              maxMulticastRetransmitCount="Integer" 
                              maxPendingMessageCount="Integer" 
                              maxReceivedMessageSize="Integer" 
                              maxUnicastRetransmitCount="Integer" 
                              multicastInterfaceId="String" 
                              socketReceiveBufferSize="Integer" 
                              timeToLive="Integer" />
      </standardEndpoint>
    </udpAnnouncementEndpoint>
  </standardEndpoints>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a>屬性和項目  
 下列各節描述屬性、子項目和父項目。  
  
### <a name="attributes"></a>屬性  
  
|屬性|描述|  
|---------------|-----------------|  
|duplicateMessageHistoryLength|整數，指定傳輸用於識別重複訊息的最大訊息雜湊數目。  重複偵測會在 TransportManager 層級完成。 將這個屬性設定為 0 會停用重複訊偵測。<br /><br /> 這個屬性為系統管理員或開發人員提供關閉重複訊息偵測演算法的方式。 如果您要實作自己的重複偵測演算法，可以使用此設定。<br /><br /> 預設值為 4112。|  
|maxBufferPoolSize|整數，指定傳輸所使用之任何緩衝集區的大小上限。|  
|maxMulticastRetransmitCount|整數，指定應重新傳送訊息的次數上限 (除了第一次傳送之外)。<br /><br /> 預設值為 2。|  
|maxPendingMessageCount|整數，指定已接收但尚未從個別通道執行個體的 InputQueue 移除的訊息數目上限。  如果 InputQueue 已達到其暫止訊息計數的限制，則會捨棄訊息。<br /><br /> 預設值為 32。|  
|maxReceivedMessageSize|整數，指定繫結可處理之訊息的大小上限。<br /><br /> 預設值為 65507。|  
|maxUnicastRetransmitCount|整數，指定應重新傳送訊息的次數上限 (除了第一次傳送之外)。  如果訊息是傳送至單點傳播位址，並且收到含有對應 RelatesTo 標頭的回應訊息，重新傳輸可能會較早終止 (在重新傳輸您設定的次數之前)。<br /><br /> 預設值為 1。|  
|multicastInterfaceId|字串，這個字串可唯一識別在多重主目錄電腦上傳送及接收多點傳送流量時應使用的網路介面卡。 在執行階段，傳輸會使用這個屬性值查詢介面索引，接著使用介面索引設定 `IP_MULTICAST_IF` 和 `IPV6_MULTICAST_IF` 通訊端選項。  聯結多點傳送群組時會使用相同的介面索引 (如果適用的話)。<br /><br /> 預設值是 `null`。|  
|socketReceiveBufferSize|整數，指定基礎 WinSock 通訊端上接收緩衝區的大小。<br /><br /> 接收通道的使用者可以在繫結上使用此屬性控制系統接收資料時的行為。  例如，假設應用程式會於最大臨界值耗用傳入 WCF 訊息，則使用此屬性較高的值可讓訊息在等候應用程式能夠加以處理時，堆疊在 WinSock 緩衝區中。  同樣的情況下若使用較小的值，則會導致捨棄訊息。這個屬性會公開基礎 WinSock `SO_RCVBUF` 通訊端選項。此屬性的值至少須等於 `maxReceivedMessageSize` 的大小。   將它設定為小於 `maxReceivedMessageSize` 的值，會導致執行階段例外狀況。<br /><br /> 預設值為 65536。|  
|timeToLive|整數，指定多點傳送封包可以周遊的網路區段躍點數目。  這個屬性會公開與 `IP_MULTICAST_TTL` 和 `IP_TTL` 通訊端選項相關聯的功能。<br /><br /> 預設值為 1。|  
  
### <a name="child-elements"></a>子項目  
 無。  
  
### <a name="parent-elements"></a>父項目  
  
|項目|描述|  
|-------------|-----------------|  
|[\<udpAnnoucementEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/udpannoucementendpoint.md)|具有固定公告合約及 UDP 傳輸繫結的標準端點。|  
  
## <a name="see-also"></a>另請參閱  
 <xref:System.ServiceModel.Discovery.UdpTransportSettings>
