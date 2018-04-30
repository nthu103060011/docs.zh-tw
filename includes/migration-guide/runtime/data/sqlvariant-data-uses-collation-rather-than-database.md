### <a name="sqlvariant-data-uses-sqlvariant-collation-rather-than-database-collation"></a><span data-ttu-id="a10de-101">Sql_variant 資料使用的是 sql_variant 定序，而不是資料庫定序</span><span class="sxs-lookup"><span data-stu-id="a10de-101">Sql_variant data uses sql_variant collation rather than database collation</span></span>

|   |   |
|---|---|
|<span data-ttu-id="a10de-102">詳細資料</span><span class="sxs-lookup"><span data-stu-id="a10de-102">Details</span></span>|<span data-ttu-id="a10de-103"><code>sql_variant</code> 資料使用的是 <code>sql_variant</code> 定序，而不是資料庫定序。</span><span class="sxs-lookup"><span data-stu-id="a10de-103"><code>sql_variant</code> data uses <code>sql_variant</code> collation rather than database collation.</span></span>|
|<span data-ttu-id="a10de-104">建議</span><span class="sxs-lookup"><span data-stu-id="a10de-104">Suggestion</span></span>|<span data-ttu-id="a10de-105">這項變更可以解決資料庫定序與 <code>sql_variant</code> 定序不同時，可能發生的資料毀損。</span><span class="sxs-lookup"><span data-stu-id="a10de-105">This change addresses possible data corruption if the database collation differs from the <code>sql_variant</code> collation.</span></span> <span data-ttu-id="a10de-106">依賴損毀資料的應用程式可能會失敗。</span><span class="sxs-lookup"><span data-stu-id="a10de-106">Applications that rely on the corrupted data may experience failure.</span></span>|
|<span data-ttu-id="a10de-107">範圍</span><span class="sxs-lookup"><span data-stu-id="a10de-107">Scope</span></span>|<span data-ttu-id="a10de-108">透明</span><span class="sxs-lookup"><span data-stu-id="a10de-108">Transparent</span></span>|
|<span data-ttu-id="a10de-109">版本</span><span class="sxs-lookup"><span data-stu-id="a10de-109">Version</span></span>|<span data-ttu-id="a10de-110">4.5</span><span class="sxs-lookup"><span data-stu-id="a10de-110">4.5</span></span>|
|<span data-ttu-id="a10de-111">類型</span><span class="sxs-lookup"><span data-stu-id="a10de-111">Type</span></span>|<span data-ttu-id="a10de-112">執行階段</span><span class="sxs-lookup"><span data-stu-id="a10de-112">Runtime</span></span>|
