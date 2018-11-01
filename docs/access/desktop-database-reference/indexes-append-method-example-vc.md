---
title: Indexes 的 Append 方法示例 (VC++)
TOCTitle: Indexes Append method example (VC++)
ms:assetid: fd7a020e-19bd-db14-bcdf-d34b23002e44
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250302(v=office.15)
ms:contentKeyID: 48548918
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 7ceef55e583df5c824e74ddeef3f2cafd78cde54
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25884889"
---
# <a name="indexes-append-method-example-vc"></a><span data-ttu-id="93d18-102">Indexes 的 Append 方法示例 (VC++)</span><span class="sxs-lookup"><span data-stu-id="93d18-102">Indexes Append method example (VC++)</span></span>


<span data-ttu-id="93d18-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="93d18-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="93d18-p101">下面的代码示例演示如何创建新索引。该索引针对表中的两列而编制。</span><span class="sxs-lookup"><span data-stu-id="93d18-p101">The following code demonstrates how to create a new index. The index is on two columns in the table.</span></span>

```cpp 
 
// BeginCreateIndexCpp 
#import "c:\Program Files\Common Files\system\ado\msadox.dll" no_namespace 
 
#include "iostream.h" 
#include "stdio.h" 
#include "conio.h" 
 
// Function declarations 
inline void TESTHR(HRESULT x) {if FAILED(x) _com_issue_error(x);}; 
void CreateIndexX(void); 
 
////////////////////////////////////////////////////////// 
// // 
// Main Function // 
// // 
////////////////////////////////////////////////////////// 
void main() 
{ 
 if(FAILED(::CoInitialize(NULL))) 
 return; 
 
 CreateIndexX(); 
 
 ::CoUninitialize(); 
} 
 
////////////////////////////////////////////////////////// 
// // 
// CreateIndexX Function // 
// // 
////////////////////////////////////////////////////////// 
void CreateIndexX(void) 
{ 
 HRESULT hr = S_OK; 
 
 // Define ADOX object pointers. 
 // Initialize pointers on define. 
 // These are in the ADOX:: namespace. 
 _TablePtr m_pTable = NULL; 
 _IndexPtr m_pIndex = NULL; 
 _CatalogPtr m_pCatalog = NULL; 
 
 //Define other variables 
 _bstr_t strcnn("Provider='Microsoft.JET.OLEDB.4.0';" 
 "Data source = 'c:\\Program Files\\Microsoft Office\\" 
 "Office\\Samples\\Northwind.mdb';"); 
 try 
 { 
 TESTHR(hr = m_pTable.CreateInstance(__uuidof(Table))); 
 TESTHR(hr = m_pIndex.CreateInstance(__uuidof(Index))); 
 TESTHR(hr = m_pCatalog.CreateInstance(__uuidof (Catalog))); 
 
 // Open the catalog. 
 m_pCatalog->PutActiveConnection(strcnn); 
 
 // Define the table and append it to the catalog. 
 m_pTable->Name = "MyTable"; 
 m_pTable->Columns->Append("Column1",adInteger,0); 
 m_pTable->Columns->Append("Column2",adInteger,0); 
 m_pTable->Columns->Append("Column3",adVarWChar,50); 
 m_pCatalog->Tables->Append(_variant_t((IDispatch *)m_pTable)); 
 printf("Table 'MyTable' is appended.\n"); 
 
 // Define a multi-column index. 
 m_pIndex->Name = "multicolidx"; 
 m_pIndex->Columns->Append("Column1",adInteger,0); 
 m_pIndex->Columns->Append("Column2",adInteger,0); 
 
 // Append the index to the table. 
 m_pTable->Indexes->Append(_variant_t((IDispatch *)m_pIndex)); 
 printf("Index 'multicolidx' is appended.\n"); 
 
 // Delete the table. 
 m_pCatalog->Tables->Delete("MyTable"); 
 printf("Table 'MyTable' is deleted.\n"); 
 } 
 catch(_com_error &e) 
 { 
 // Notify the user of errors if any. 
 _bstr_t bstrSource(e.Source()); 
 _bstr_t bstrDescription(e.Description()); 
 
 printf("\n\tSource : %s \n\tdescription : %s \n ", 
 (LPCSTR)bstrSource,(LPCSTR)bstrDescription); 
 } 
 catch(...) 
 { 
 cout << "Error occured in CreateIndexX...."<< endl; 
 } 
} 
// EndCreateIndexCpp 
```

