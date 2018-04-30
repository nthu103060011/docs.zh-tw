### <a name="assemblies-compiled-with-regexcompiletoassembly-breaks-between-40-and-45"></a><span data-ttu-id="34020-101">使用 Regex.CompileToAssembly 編譯的組件在 4.0 與 4.5 之間中斷</span><span class="sxs-lookup"><span data-stu-id="34020-101">Assemblies compiled with Regex.CompileToAssembly breaks between 4.0 and 4.5</span></span>

|   |   |
|---|---|
|<span data-ttu-id="34020-102">詳細資料</span><span class="sxs-lookup"><span data-stu-id="34020-102">Details</span></span>|<span data-ttu-id="34020-103">如果使用 .NET Framework 4.5 建置編譯之規則運算式的組件，但以 .NET Framework 4 為目標，嘗試在安裝 .NET Framework 4 的系統上使用該組件中的其中一個規則運算式時，會擲回例外狀況。</span><span class="sxs-lookup"><span data-stu-id="34020-103">If an assembly of compiled regular expressions is built with the .NET Framework 4.5 but targets the .NET Framework 4, attempting to use one of the regular expressions in that assembly on a system with .NET Framework 4 installed throws an exception.</span></span>|
|<span data-ttu-id="34020-104">建議</span><span class="sxs-lookup"><span data-stu-id="34020-104">Suggestion</span></span>|<span data-ttu-id="34020-105">若要解決這個問題，您可以執行下列任何一項操作：</span><span class="sxs-lookup"><span data-stu-id="34020-105">To work around this problem, you can do either of the following:</span></span><ul><li><span data-ttu-id="34020-106">使用 .NET Framework 4 建置包含規則運算式的組件。</span><span class="sxs-lookup"><span data-stu-id="34020-106">Build the assembly that contains the regular expressions with the .NET Framework 4.</span></span></li><li><span data-ttu-id="34020-107">使用解譯的規則運算式。</span><span class="sxs-lookup"><span data-stu-id="34020-107">Use an interpreted regular expression.</span></span></li></ul>|
|<span data-ttu-id="34020-108">範圍</span><span class="sxs-lookup"><span data-stu-id="34020-108">Scope</span></span>|<span data-ttu-id="34020-109">次要</span><span class="sxs-lookup"><span data-stu-id="34020-109">Minor</span></span>|
|<span data-ttu-id="34020-110">版本</span><span class="sxs-lookup"><span data-stu-id="34020-110">Version</span></span>|<span data-ttu-id="34020-111">4.5</span><span class="sxs-lookup"><span data-stu-id="34020-111">4.5</span></span>|
|<span data-ttu-id="34020-112">類型</span><span class="sxs-lookup"><span data-stu-id="34020-112">Type</span></span>|<span data-ttu-id="34020-113">執行階段</span><span class="sxs-lookup"><span data-stu-id="34020-113">Runtime</span></span>|
|<span data-ttu-id="34020-114">受影響的 API</span><span class="sxs-lookup"><span data-stu-id="34020-114">Affected APIs</span></span>|<ul><li><xref:System.Text.RegularExpressions.Regex.CompileToAssembly(System.Text.RegularExpressions.RegexCompilationInfo[],System.Reflection.AssemblyName)?displayProperty=nameWithType></li><li><xref:System.Text.RegularExpressions.Regex.CompileToAssembly(System.Text.RegularExpressions.RegexCompilationInfo[],System.Reflection.AssemblyName,System.Reflection.Emit.CustomAttributeBuilder[])?displayProperty=nameWithType></li><li><xref:System.Text.RegularExpressions.Regex.CompileToAssembly(System.Text.RegularExpressions.RegexCompilationInfo[],System.Reflection.AssemblyName,System.Reflection.Emit.CustomAttributeBuilder[],System.String)?displayProperty=nameWithType></li></ul>|
