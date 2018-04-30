### <a name="default-value-of-servicepointmanagersecurityprotocol-is-securityprotocoltypesystemdefault"></a><span data-ttu-id="aa98f-101">ServicePointManager.SecurityProtocol 的預設值是 SecurityProtocolType.System.Default</span><span class="sxs-lookup"><span data-stu-id="aa98f-101">Default value of ServicePointManager.SecurityProtocol is SecurityProtocolType.System.Default</span></span>

|   |   |
|---|---|
|<span data-ttu-id="aa98f-102">詳細資料</span><span class="sxs-lookup"><span data-stu-id="aa98f-102">Details</span></span>|<span data-ttu-id="aa98f-103">從以 .NET Framework 4.7 為目標的應用程式開始，<xref:System.Net.ServicePointManager.SecurityProtocol?displayProperty=nameWithType> 屬性是 <xref:System.Net.SecurityProtocolType.SystemDefault?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="aa98f-103">Starting with apps that target the .NET Framework 4.7, the default value of the <xref:System.Net.ServicePointManager.SecurityProtocol?displayProperty=nameWithType> property is <xref:System.Net.SecurityProtocolType.SystemDefault?displayProperty=nameWithType>.</span></span> <span data-ttu-id="aa98f-104">這項變更可以讓以 SslStream 為基礎的 .NET Framework 網路 API (例如 FTP、HTTPS 及 SMTP) 繼承作業系統的預設安全性通訊協定，而不要使用由 .NET Framework 定義的硬式編碼值。</span><span class="sxs-lookup"><span data-stu-id="aa98f-104">This change allows .NET Framework networking APIs based on SslStream (such as FTP, HTTPS, and SMTP) to inherit the default security protocols from the operating system instead of using hard-coded values defined by the .NET Framework.</span></span> <span data-ttu-id="aa98f-105">預設值會依作業系統和系統管理員執行的任何自訂設定而異。</span><span class="sxs-lookup"><span data-stu-id="aa98f-105">The default varies by operating system and any custom configuration performed by the system administrator.</span></span> <span data-ttu-id="aa98f-106">如需每個 Windows 作業系統版本中的預設安全通道通訊協定的資訊，請參閱 [TLS/SSL 中的通訊協定 (安全通道 SSP)](https://msdn.microsoft.com/library/windows/desktop/mt808159.aspx)。若為以舊版 .NET Framework 為目標的應用程式，<xref:System.Net.ServicePointManager.SecurityProtocol?displayProperty=nameWithType> 屬性的預設值會依目標 .NET Framework 版本而定。</span><span class="sxs-lookup"><span data-stu-id="aa98f-106">For information on the default SChannel protocol in each version of the Windows operating system, see [Protocols in TLS/SSL (Schannel SSP)](https://msdn.microsoft.com/library/windows/desktop/mt808159.aspx).For applications that target an earlier version of the .NET Framework, the default value of the <xref:System.Net.ServicePointManager.SecurityProtocol?displayProperty=nameWithType> property depends on the version of the .NET Framework targeted.</span></span> <span data-ttu-id="aa98f-107">如需詳細資訊，請參閱[從 .NET Framework 4.5.2 移轉到 4.6 的重定目標變更的網路區段](~/docs/framework/migration-guide/retargeting/4.5.2-4.6.md#networking)。</span><span class="sxs-lookup"><span data-stu-id="aa98f-107">See the [Networking section of Retargeting Changes for Migration from .NET Framework 4.5.2 to 4.6](~/docs/framework/migration-guide/retargeting/4.5.2-4.6.md#networking) for more information.</span></span>|
|<span data-ttu-id="aa98f-108">建議</span><span class="sxs-lookup"><span data-stu-id="aa98f-108">Suggestion</span></span>|<span data-ttu-id="aa98f-109">這項變更會影響以 .NET Framework 4.7 或更新版本為目標的應用程式。如果您想要使用定義的通訊協定，而不是依賴系統預設值，您可以明確設定 <xref:System.Net.ServicePointManager.SecurityProtocol?displayProperty=nameWithType> 屬性的值。如果不需要這項變更，您可以藉由新增組態設定至應用程式設定檔的 [\<runtime>](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) 區段，來選擇不使用它。</span><span class="sxs-lookup"><span data-stu-id="aa98f-109">This change affects applications that target the .NET Framework 4.7 or later versions.If you prefer to use a defined protocol rather than relying on the system default, you can explicitly set the value of the <xref:System.Net.ServicePointManager.SecurityProtocol?displayProperty=nameWithType> property.If this change is undesirable, you can opt out of it by adding a configuration setting to the [\<runtime>](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of your application configuration file.</span></span> <span data-ttu-id="aa98f-110">下列範例顯示 <code>&lt;runtime&gt;</code> 區段及 <code>Switch.System.Net.DontEnableSystemDefaultTlsVersions</code> 選擇退出參數：</span><span class="sxs-lookup"><span data-stu-id="aa98f-110">The following example shows both the <code>&lt;runtime&gt;</code> section and the <code>Switch.System.Net.DontEnableSystemDefaultTlsVersions</code> opt-out switch:</span></span><pre><code class="language-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Net.DontEnableSystemDefaultTlsVersions=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|<span data-ttu-id="aa98f-111">範圍</span><span class="sxs-lookup"><span data-stu-id="aa98f-111">Scope</span></span>|<span data-ttu-id="aa98f-112">次要</span><span class="sxs-lookup"><span data-stu-id="aa98f-112">Minor</span></span>|
|<span data-ttu-id="aa98f-113">版本</span><span class="sxs-lookup"><span data-stu-id="aa98f-113">Version</span></span>|<span data-ttu-id="aa98f-114">4.7</span><span class="sxs-lookup"><span data-stu-id="aa98f-114">4.7</span></span>|
|<span data-ttu-id="aa98f-115">類型</span><span class="sxs-lookup"><span data-stu-id="aa98f-115">Type</span></span>|<span data-ttu-id="aa98f-116">正在重定目標</span><span class="sxs-lookup"><span data-stu-id="aa98f-116">Retargeting</span></span>|
|<span data-ttu-id="aa98f-117">受影響的 API</span><span class="sxs-lookup"><span data-stu-id="aa98f-117">Affected APIs</span></span>|<ul><li><xref:System.Net.ServicePointManager.SecurityProtocol?displayProperty=nameWithType></li></ul>|
