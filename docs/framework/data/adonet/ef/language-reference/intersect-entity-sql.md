---
title: INTERSECT (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 93c6fe33-f341-4b52-911e-adf503891951
ms.openlocfilehash: 98515ccf111bf78f49347f744a1226ca1957fbb6
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/03/2018
---
# <a name="intersect-entity-sql"></a>INTERSECT (Entity SQL)
傳回 INTERSECT 運算元左右兩側之查詢運算式都會傳回的任何相異值集合。 所有運算式都必須具有與 `expression`相同的型別或是共同基底型別或衍生型別。  
  
## <a name="syntax"></a>語法  
  
```  
expression INTERSECT expression  
```  
  
## <a name="arguments"></a>引數  
 `expression`  
 任何有效的查詢運算式，該運算式會傳回要與另一個查詢運算式傳回之集合相比較的集合。  
  
## <a name="return-value"></a>傳回值  
 具有與 `expression`相同的型別或是共同基底類型或衍生型別的集合。  
  
## <a name="remarks"></a>備註  
 INTERSECT 是其中一個 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 設定運算子。 所有 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 設定運算子都會從左到右評估。 優先順序資訊[!INCLUDE[esql](../../../../../../includes/esql-md.md)]設定運算子，請參閱[EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md)。  
  
## <a name="example"></a>範例  
 下列 Entity SQL 查詢會使用 INTERSECT 運算元，傳回 INTERSECT 運算元左右兩側之查詢運算式都傳回的任何相異值集合。 此查詢是根據 AdventureWorks Sales Model。 若要編譯及執行此查詢，請遵循以下步驟：  
  
1.  遵循 [如何：執行可傳回 StructuralType 結果的查詢](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)中的程序進行。  
  
2.  將下列查詢當成引數，傳遞至 `ExecuteStructuralTypeQuery` 方法：  
  
 [!code-csharp[DP EntityServices Concepts 2#INTERSECT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#intersect)]  
  
## <a name="see-also"></a>另請參閱  
 [Entity SQL 參考](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
