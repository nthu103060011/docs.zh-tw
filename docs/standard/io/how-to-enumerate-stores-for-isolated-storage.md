---
title: 如何：列舉隔離儲存區的存放區
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- enumerating stores
- data storage using isolated storage, enumerating stores
- storing data using isolated storage, enumerating stores
- stores, enumerating
- isolated storage, enumerating stores
- data stores, enumerating
ms.assetid: 0fcf279a-f241-48f0-8034-2e3d331f1fcb
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 77f6053cad85b5012a455a1fc020e0f559defdc9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-enumerate-stores-for-isolated-storage"></a>如何：列舉隔離儲存區的存放區
您可以使用 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A?displayProperty=nameWithType> 靜態方法，列舉目前使用者的所有隔離存放區。 這個方法會使用 <xref:System.IO.IsolatedStorage.IsolatedStorageScope> 值並傳回 <xref:System.IO.IsolatedStorage.IsolatedStorageFile> 列舉值。 若要列舉存放區，您必須擁有指定 <xref:System.Security.Permissions.IsolatedStorageContainment.AdministerIsolatedStorageByUser> 值的 <xref:System.Security.Permissions.IsolatedStorageFilePermission> 權限。 如果您使用 <xref:System.IO.IsolatedStorage.IsolatedStorageScope.User> 值呼叫 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A> 方法，它會傳回針對目前使用者定義之 <xref:System.IO.IsolatedStorage.IsolatedStorageFile> 物件的陣列。  
  
## <a name="example"></a>範例  
 下列程式碼範例會取得使用者和組件所隔離的存放區、建立一些檔案，然後使用 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A> 方法擷取這些檔案。  
  
 [!code-csharp[Conceptual.IsolatedStorage#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source2.cs#2)]
 [!code-vb[Conceptual.IsolatedStorage#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source2.vb#2)]  
  
## <a name="see-also"></a>請參閱  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile>  
 [隔離儲存區](../../../docs/standard/io/isolated-storage.md)
