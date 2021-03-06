---
title: 選擇性的值的選擇性參數的型別&lt;parametername&gt;不符合 CLS 標準
ms.date: 07/20/2015
f1_keywords:
- BC40042
- vbc40042
helpviewer_keywords:
- BC40042
ms.assetid: 1d6eae29-4ad3-4434-bde4-a53b6051adf5
ms.openlocfilehash: dd77cd8cbd36f7681e2597d908dd8e55bf249392
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
---
# <a name="type-of-optional-value-for-optional-parameter-ltparameternamegt-is-not-cls-compliant"></a>選擇性的值的選擇性參數的型別&lt;parametername&gt;不符合 CLS 標準
程序已標記為 `<CLSCompliant(True)>`，但所宣告的 [Optional](../../../visual-basic/language-reference/modifiers/optional.md) 參數卻具有不符合標準之型別的預設值。  
  
 程序必須只使用符合 CLS 標準的型別，才能夠符合[語言獨立性以及與語言無關的元件](../../../standard/language-independence-and-language-independent-components.md) (CLS) 標準。 這適用於參數型別、傳回型別及其所有區域變數的型別。 它也適用於選擇性參數的預設值。  
  
 下列 Visual Basic 資料類型不符合 CLS 標準：  
  
-   [SByte 資料類型](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
-   [UInteger 資料類型](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
-   [ULong 資料類型](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
-   [UShort 資料類型](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 將 <xref:System.CLSCompliantAttribute> 屬性套用至程式設計項目時，請將屬性的 `isCompliant` 參數設定為 `True` 或 `False` ，表示符合標準或不符合標準。 這個參數沒有預設值，您必須提供值。  
  
 如果您未將 <xref:System.CLSCompliantAttribute> 套用至項目，則視為不符合標準。  
  
 根據預設，這個訊息是一個警告。 如需隱藏警告或將警告視為錯誤的相關資訊，請參閱 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)。  
  
 **錯誤識別碼：**BC40042  
  
## <a name="to-correct-this-error"></a>更正這個錯誤  
  
-   如果選擇性參數必須有這個特定類型的預設值，移除<xref:System.CLSCompliantAttribute>。 程序不符合 CLS 規範。  
  
-   如果程序必須符合 CLS 標準，請將這個預設值的型別變更為最符合 CLS 標準的型別。 例如，如果您不需要 2,147,483,647 以上的值範圍，而且不使用 `UInteger` ，則可能可以使用 `Integer` 。 如果您需要擴充範圍，則可以將 `UInteger` 取代為 `Long`。  
  
-   如果您要與 Automation 或 COM 物件進行互動，請記住，某些型別的資料寬度會與在 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 中的資料寬度不同。 例如，`int` 在其他環境中通常是 16 位元。 如果您接受這類元件從 16 位元整數，將它宣告為`Short`而不是`Integer`受管理的 Visual Basic 程式碼。