### <a name="the-default-hash-algorithm-for-wpfs-markup-compiler-is-now-sha256"></a><span data-ttu-id="cb09f-101">現在，WPF 標記編譯器的預設雜湊演算法是 SHA256</span><span class="sxs-lookup"><span data-stu-id="cb09f-101">The default hash algorithm for WPF's Markup Compiler is now SHA256</span></span>

|   |   |
|---|---|
|<span data-ttu-id="cb09f-102">詳細資料</span><span class="sxs-lookup"><span data-stu-id="cb09f-102">Details</span></span>|<span data-ttu-id="cb09f-103">WPF 標記編譯器提供 XAML 標記檔案的編譯服務。</span><span class="sxs-lookup"><span data-stu-id="cb09f-103">The WPF MarkupCompiler provides compilation services for XAML markup files.</span></span>  <span data-ttu-id="cb09f-104">在 .NET Framework 4.7.1 和舊版本中，用於總和檢查碼的預設演算法是 SHA1。</span><span class="sxs-lookup"><span data-stu-id="cb09f-104">In the .NET Framework 4.7.1 and earlier versions, the default hash algorithm used for checksums was SHA1.</span></span> <span data-ttu-id="cb09f-105">但由於最近對 SHA1 產生的安全性顧慮，因此從 .NET Framework 4.7.2 開始，這個預設已變更為 SHA256。</span><span class="sxs-lookup"><span data-stu-id="cb09f-105">Due to recent security concerns with SHA1, this default has been changed to SHA256 starting with the .NET Framework 4.7.2.</span></span>  <span data-ttu-id="cb09f-106">這項變更會影響標記檔案在編譯期間產生的所有總和檢查碼。</span><span class="sxs-lookup"><span data-stu-id="cb09f-106">This change affects all checksum generation for markup files during compilation.</span></span>|
|<span data-ttu-id="cb09f-107">建議</span><span class="sxs-lookup"><span data-stu-id="cb09f-107">Suggestion</span></span>|<span data-ttu-id="cb09f-108">如果開發人員是以 .NET Framework 4.7.2 或更新版本為目標，並想還原到 SHA1 雜湊行為，則必須設定下列 AppContext 旗標。</span><span class="sxs-lookup"><span data-stu-id="cb09f-108">A developer who targets .NET Framework 4.7.2 or greater and wants to revert to SHA1 hashing behavior must set the following AppContext flag.</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Markup.DoNotUseSha256ForMarkupCompilerChecksumAlgorithm=true&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre><span data-ttu-id="cb09f-109">如果開發人員想要利用 SHA256 雜湊，同時以 .NET 4.7.2 以下的 Framework 版本為目標，則必須設定下列 AppContext 旗標。</span><span class="sxs-lookup"><span data-stu-id="cb09f-109">A developer who wants to utilize SHA256 hashing while targeting a framework version below .NET 4.7.2 must set the below AppContext flag.</span></span>  <span data-ttu-id="cb09f-110">請注意，安裝的 .NET Framework 版本必須為 4.7.2 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="cb09f-110">Note that the installed version of the .NET Framework must be 4.7.2 or greater.</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Markup.DoNotUseSha256ForMarkupCompilerChecksumAlgorithm=false&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|<span data-ttu-id="cb09f-111">範圍</span><span class="sxs-lookup"><span data-stu-id="cb09f-111">Scope</span></span>|<span data-ttu-id="cb09f-112">透明</span><span class="sxs-lookup"><span data-stu-id="cb09f-112">Transparent</span></span>|
|<span data-ttu-id="cb09f-113">版本</span><span class="sxs-lookup"><span data-stu-id="cb09f-113">Version</span></span>|<span data-ttu-id="cb09f-114">4.7.2</span><span class="sxs-lookup"><span data-stu-id="cb09f-114">4.7.2</span></span>|
|<span data-ttu-id="cb09f-115">類型</span><span class="sxs-lookup"><span data-stu-id="cb09f-115">Type</span></span>|<span data-ttu-id="cb09f-116">正在重定目標</span><span class="sxs-lookup"><span data-stu-id="cb09f-116">Retargeting</span></span>|
