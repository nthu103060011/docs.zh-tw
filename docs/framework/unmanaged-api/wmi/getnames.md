---
title: "GetNames 函式 （Unmanaged API 參考）"
description: "GetNames 函式會擷取物件的屬性名稱。"
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: GetNames
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: GetNames
helpviewer_keywords: GetNames function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2ba2530dd43e6924187c80214d5efa13ebc548de
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/15/2017
---
# <a name="getnames-function"></a><span data-ttu-id="e177d-103">GetNames 函式</span><span class="sxs-lookup"><span data-stu-id="e177d-103">GetNames function</span></span>
<span data-ttu-id="e177d-104">擷取部分或所有物件的屬性名稱。</span><span class="sxs-lookup"><span data-stu-id="e177d-104">Retrieves either a subset or all of the names of the properties of an object.</span></span> 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="e177d-105">語法</span><span class="sxs-lookup"><span data-stu-id="e177d-105">Syntax</span></span>  
  
```  
HRESULT GetNames (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LPCWSTR             wszQualifierName,
   [in] LONG                lFlags,
   [in] VARIANT*            pQualifierValue,
   [out] SAFEARRAY (BSTR)** pstrNames
); 
```  

## <a name="parameters"></a><span data-ttu-id="e177d-106">參數</span><span class="sxs-lookup"><span data-stu-id="e177d-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="e177d-107">[in]未使用這個參數。</span><span class="sxs-lookup"><span data-stu-id="e177d-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="e177d-108">[in]指標[IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx)執行個體。</span><span class="sxs-lookup"><span data-stu-id="e177d-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`wszQualifierName`  
<span data-ttu-id="e177d-109">[in]有效的指標`LPCWSTR`運作限定詞名稱指定為篩選的一部分。</span><span class="sxs-lookup"><span data-stu-id="e177d-109">[in] A pointer to a valid `LPCWSTR` that specifies a qualifier name that operates as part of a filter.</span></span> <span data-ttu-id="e177d-110">如需詳細資訊，請參閱[備註](#remarks)> 一節。</span><span class="sxs-lookup"><span data-stu-id="e177d-110">For more information, see the [Remarks](#remarks) section.</span></span> <span data-ttu-id="e177d-111">這個參數可以是 `null`。</span><span class="sxs-lookup"><span data-stu-id="e177d-111">This parameter can be `null`.</span></span> 

`lFlags`  
<span data-ttu-id="e177d-112">[in]位元欄位的組合。</span><span class="sxs-lookup"><span data-stu-id="e177d-112">[in] A combination of bit fields.</span></span> <span data-ttu-id="e177d-113">如需詳細資訊，請參閱[備註](#remarks)> 一節。</span><span class="sxs-lookup"><span data-stu-id="e177d-113">For more information, see the [Remarks](#remarks) section.</span></span>

`pQualifierValue`   
<span data-ttu-id="e177d-114">[in]有效的指標`VARIANT`與篩選值初始化結構。</span><span class="sxs-lookup"><span data-stu-id="e177d-114">[in] A pointer to a valid `VARIANT` structure initialized to a filter value.</span></span> <span data-ttu-id="e177d-115">這個參數可以是 `null`。</span><span class="sxs-lookup"><span data-stu-id="e177d-115">This parameter can be `null`.</span></span> 

`pstrNames`  
<span data-ttu-id="e177d-116">[out]A`SAFEARRAY`結構，其中包含屬性名稱。</span><span class="sxs-lookup"><span data-stu-id="e177d-116">[out] A `SAFEARRAY` structure that contains property names.</span></span> <span data-ttu-id="e177d-117">在項目，這個參數必須一律為指標`null`。</span><span class="sxs-lookup"><span data-stu-id="e177d-117">On entry, this parameter must always be a pointer to `null`.</span></span> <span data-ttu-id="e177d-118">請參閱[備註](#remarks)節的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="e177d-118">See the [Remarks](#remarks) section for more information.</span></span> 

## <a name="return-value"></a><span data-ttu-id="e177d-119">傳回值</span><span class="sxs-lookup"><span data-stu-id="e177d-119">Return value</span></span>

<span data-ttu-id="e177d-120">這個函式傳回下列值會定義在*WbemCli.h*標頭檔，或者您可以定義它們以常數的形式在程式碼中：</span><span class="sxs-lookup"><span data-stu-id="e177d-120">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="e177d-121">常數</span><span class="sxs-lookup"><span data-stu-id="e177d-121">Constant</span></span>  |<span data-ttu-id="e177d-122">值</span><span class="sxs-lookup"><span data-stu-id="e177d-122">Value</span></span>  |<span data-ttu-id="e177d-123">說明</span><span class="sxs-lookup"><span data-stu-id="e177d-123">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="e177d-124">0x80041001</span><span class="sxs-lookup"><span data-stu-id="e177d-124">0x80041001</span></span> | <span data-ttu-id="e177d-125">發生一般失敗。</span><span class="sxs-lookup"><span data-stu-id="e177d-125">There has been a general failure.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="e177d-126">0x80041008</span><span class="sxs-lookup"><span data-stu-id="e177d-126">0x80041008</span></span> | <span data-ttu-id="e177d-127">一或多個參數都不是有效的或指定的旗標和參數不正確的組合。</span><span class="sxs-lookup"><span data-stu-id="e177d-127">One or more parameters are not valid, or an incorrect combination of flags and parameters was specified.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="e177d-128">0x80041006</span><span class="sxs-lookup"><span data-stu-id="e177d-128">0x80041006</span></span> | <span data-ttu-id="e177d-129">沒有足夠的記憶體可完成作業。</span><span class="sxs-lookup"><span data-stu-id="e177d-129">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="e177d-130">0</span><span class="sxs-lookup"><span data-stu-id="e177d-130">0</span></span> | <span data-ttu-id="e177d-131">函式呼叫成功。</span><span class="sxs-lookup"><span data-stu-id="e177d-131">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="e177d-132">備註</span><span class="sxs-lookup"><span data-stu-id="e177d-132">Remarks</span></span>

<span data-ttu-id="e177d-133">此函式會包裝呼叫[IWbemClassObject::GetNames](https://msdn.microsoft.com/library/aa391447(v=vs.85).aspx)方法。</span><span class="sxs-lookup"><span data-stu-id="e177d-133">This function wraps a call to the [IWbemClassObject::GetNames](https://msdn.microsoft.com/library/aa391447(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="e177d-134">傳回具名是由控制旗標和參數的組合。</span><span class="sxs-lookup"><span data-stu-id="e177d-134">The named returned are controlled by a combination of flags and parameters.</span></span> <span data-ttu-id="e177d-135">比方說，此函數可以傳回所有屬性的名稱或索引鍵屬性的名稱。</span><span class="sxs-lookup"><span data-stu-id="e177d-135">For example, the function can return the names of all properties or only the names of the key properties.</span></span>  <span data-ttu-id="e177d-136">主要的篩選條件中指定`lFlags`參數和其他參數根據它而有所不同。</span><span class="sxs-lookup"><span data-stu-id="e177d-136">The primary filter is specified in the `lFlags` parameter, and the other parameters vary depending on it.</span></span>

<span data-ttu-id="e177d-137">中的旗標值`lFlags`是位元欄位</span><span class="sxs-lookup"><span data-stu-id="e177d-137">The flag values in `lFlags` are bit fields</span></span>


<span data-ttu-id="e177d-138">可以做為傳遞的旗標`lEnumFlags`引數是中所定義的位元欄位*WbemCli.h*標頭檔，或者您可以定義它們以常數的形式在程式碼中。</span><span class="sxs-lookup"><span data-stu-id="e177d-138">The flags that can be passed as the `lEnumFlags` argument are bit fields that are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span>  <span data-ttu-id="e177d-139">您可以結合任何旗標，任何其他群組的每個群組從一個旗標。</span><span class="sxs-lookup"><span data-stu-id="e177d-139">You can combine one flag from each group with any flag from any other group.</span></span> <span data-ttu-id="e177d-140">不過，從相同群組的旗標互斥。</span><span class="sxs-lookup"><span data-stu-id="e177d-140">However, flags from the same group are mutually exclusive.</span></span> 

| <span data-ttu-id="e177d-141">群組 1 旗標</span><span class="sxs-lookup"><span data-stu-id="e177d-141">Group 1 flags</span></span> |<span data-ttu-id="e177d-142">值</span><span class="sxs-lookup"><span data-stu-id="e177d-142">Value</span></span>  |<span data-ttu-id="e177d-143">描述</span><span class="sxs-lookup"><span data-stu-id="e177d-143">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_ALWAYS` | <span data-ttu-id="e177d-144">0</span><span class="sxs-lookup"><span data-stu-id="e177d-144">0</span></span> | <span data-ttu-id="e177d-145">傳回所有屬性名稱。</span><span class="sxs-lookup"><span data-stu-id="e177d-145">Return all property names.</span></span> <span data-ttu-id="e177d-146">`strQualifierName`和`pQualifierVal`未使用。</span><span class="sxs-lookup"><span data-stu-id="e177d-146">`strQualifierName` and `pQualifierVal` are unused.</span></span> |
| `WBEM_FLAG_ONLY_IF_TRUE` | <span data-ttu-id="e177d-147">1</span><span class="sxs-lookup"><span data-stu-id="e177d-147">1</span></span> | <span data-ttu-id="e177d-148">傳回具有所指定之名稱的限定詞的唯一屬性`strQualifierName`參數。</span><span class="sxs-lookup"><span data-stu-id="e177d-148">Return only properties that have a qualifier of the name specified by the `strQualifierName` parameter.</span></span> <span data-ttu-id="e177d-149">如果使用這個旗標，您必須指定`strQualifierName`。</span><span class="sxs-lookup"><span data-stu-id="e177d-149">If this flag is used, you must specify `strQualifierName`.</span></span> |
|`WBEM_FLAG_ONLY_IF_FALSE` | <span data-ttu-id="e177d-150">2</span><span class="sxs-lookup"><span data-stu-id="e177d-150">2</span></span> |  <span data-ttu-id="e177d-151">傳回唯一的屬性所指定之名稱的限定詞沒有`strQualifierName`參數。</span><span class="sxs-lookup"><span data-stu-id="e177d-151">Return only properties that do not have a qualifier of the name specified by the `strQualifierName` parameter.</span></span> <span data-ttu-id="e177d-152">如果使用這個旗標，您必須指定`strQualifierName`。</span><span class="sxs-lookup"><span data-stu-id="e177d-152">If this flag is used, you must specify `strQualifierName`.</span></span> |
|`WBEM_FLAG_ONLY_IF_IDENTICAL` | <span data-ttu-id="e177d-153">3</span><span class="sxs-lookup"><span data-stu-id="e177d-153">3</span></span> | <span data-ttu-id="e177d-154">傳回具有所指定之名稱的辨識符號的屬性`wszQualifierName`參數，而且也有等於指定的值`pQualifierVal`結構。</span><span class="sxs-lookup"><span data-stu-id="e177d-154">Return only properties that have a qualifier of the name specified by the `wszQualifierName` parameter and also have a value identical to that specified by the `pQualifierVal` structure.</span></span> <span data-ttu-id="e177d-155">如果使用這個旗標時，您必須同時指定`wszQualifierName`和`pQualifierValue`。</span><span class="sxs-lookup"><span data-stu-id="e177d-155">If this flag is used, you must specify both a `wszQualifierName` and a `pQualifierValue`.</span></span> |

| <span data-ttu-id="e177d-156">群組 2 旗標</span><span class="sxs-lookup"><span data-stu-id="e177d-156">Group 2 flags</span></span> |<span data-ttu-id="e177d-157">值</span><span class="sxs-lookup"><span data-stu-id="e177d-157">Value</span></span>  |<span data-ttu-id="e177d-158">說明</span><span class="sxs-lookup"><span data-stu-id="e177d-158">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_KEYS_ONLY` | <span data-ttu-id="e177d-159">0x4</span><span class="sxs-lookup"><span data-stu-id="e177d-159">0x4</span></span> | <span data-ttu-id="e177d-160">傳回定義索引鍵的屬性名稱。</span><span class="sxs-lookup"><span data-stu-id="e177d-160">Return only the names of properties that define the keys.</span></span> |
|`WBEM_FLAG_REFS_ONLY` | <span data-ttu-id="e177d-161">0x8</span><span class="sxs-lookup"><span data-stu-id="e177d-161">0x8</span></span> | <span data-ttu-id="e177d-162">傳回唯一屬性的名稱是物件參考。</span><span class="sxs-lookup"><span data-stu-id="e177d-162">Return only property names that are object references.</span></span> |

| <span data-ttu-id="e177d-163">群組 3 旗標</span><span class="sxs-lookup"><span data-stu-id="e177d-163">Group 3 flags</span></span> |<span data-ttu-id="e177d-164">值</span><span class="sxs-lookup"><span data-stu-id="e177d-164">Value</span></span>  |<span data-ttu-id="e177d-165">說明</span><span class="sxs-lookup"><span data-stu-id="e177d-165">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="e177d-166">0x10</span><span class="sxs-lookup"><span data-stu-id="e177d-166">0x10</span></span> | <span data-ttu-id="e177d-167">傳回屬於最常衍生的類別屬性名稱。</span><span class="sxs-lookup"><span data-stu-id="e177d-167">Return only property names that belong to the most derived class.</span></span> <span data-ttu-id="e177d-168">排除的父類別中的屬性。</span><span class="sxs-lookup"><span data-stu-id="e177d-168">Exclude properties from the parent classes.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="e177d-169">0x20</span><span class="sxs-lookup"><span data-stu-id="e177d-169">0x20</span></span> | <span data-ttu-id="e177d-170">傳回屬於父類別屬性名稱。</span><span class="sxs-lookup"><span data-stu-id="e177d-170">Return only property names that belong to the parent classes.</span></span> |
|`WBEM_FLAG_SYSTEM_ONLY` | <span data-ttu-id="e177d-171">0x30</span><span class="sxs-lookup"><span data-stu-id="e177d-171">0x30</span></span> | <span data-ttu-id="e177d-172">傳回系統屬性的名稱。</span><span class="sxs-lookup"><span data-stu-id="e177d-172">Return only the names of system properties.</span></span> |
|`WBEM_FLAG_NONSYSTEM_ONLY` | <span data-ttu-id="e177d-173">0x40</span><span class="sxs-lookup"><span data-stu-id="e177d-173">0x40</span></span> | <span data-ttu-id="e177d-174">傳回非系統屬性的名稱。</span><span class="sxs-lookup"><span data-stu-id="e177d-174">Return only the names of non-system properties.</span></span> |

<span data-ttu-id="e177d-175">函式一律會配置新`SAFEARRAY`如果它傳回`WBEM_S_NO_ERROR`，和`pstrNames`一定會設定為指向它。</span><span class="sxs-lookup"><span data-stu-id="e177d-175">The function always allocates a new `SAFEARRAY` if it returns `WBEM_S_NO_ERROR`, and `pstrNames` is always set to point to it.</span></span> <span data-ttu-id="e177d-176">如果沒有屬性符合指定的篩選傳回的陣列有項目為 0。</span><span class="sxs-lookup"><span data-stu-id="e177d-176">The returned array can have 0 elements if no properties match the specified filters.</span></span> <span data-ttu-id="e177d-177">如果函數傳回的值以外`WBM_S_NO_ERROR`，新`SAFEARRAY`結構不會傳回。</span><span class="sxs-lookup"><span data-stu-id="e177d-177">If the function returns an value other than `WBM_S_NO_ERROR`, a new `SAFEARRAY` structure is not returned.</span></span>
 
## <a name="requirements"></a><span data-ttu-id="e177d-178">需求</span><span class="sxs-lookup"><span data-stu-id="e177d-178">Requirements</span></span>  
 <span data-ttu-id="e177d-179">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e177d-179">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e177d-180">**標頭：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="e177d-180">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="e177d-181">**.NET framework 版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="e177d-181">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e177d-182">請參閱</span><span class="sxs-lookup"><span data-stu-id="e177d-182">See also</span></span>  
[<span data-ttu-id="e177d-183">WMI 和效能計數器 （Unmanaged API 參考）</span><span class="sxs-lookup"><span data-stu-id="e177d-183">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)