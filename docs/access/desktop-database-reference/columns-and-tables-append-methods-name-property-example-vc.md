---
title: Columns 和 Tables 的 Append 方法、 Name 属性示例 （VC + +）
TOCTitle: Columns and Tables Append Methods, Name property example (VC++)
ms:assetid: 6586aaed-2556-1d33-c1ab-135a598f7d13
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249392(v=office.15)
ms:contentKeyID: 48545322
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: f592b4015d073c05fcd050350bec4ebafdb6eb54
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25882201"
---
# <a name="columns-and-tables-append-methods-name-property-example-vc"></a><span data-ttu-id="616c6-102">Columns 和 Tables 的 Append 方法、 Name 属性示例 （VC + +）</span><span class="sxs-lookup"><span data-stu-id="616c6-102">Columns and Tables Append Methods, Name property example (VC++)</span></span>


<span data-ttu-id="616c6-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="616c6-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="616c6-104">下面的代码演示如何创建新表。</span><span class="sxs-lookup"><span data-stu-id="616c6-104">The following code demonstrates how to create a new table.</span></span>

```cpp 
 
// BeginCreateTableCpp 
#import "c:\Program Files\Common Files\system\ado\msadox.dll" no_namespace 
 
#include "iostream.h" 
#include "stdio.h" 
#include "conio.h" 
 
//Function declarations 
inline void TESTHR(HRESULT x) {if FAILED(x) _com_issue_error(x);}; 
void CreateTableX(void); 
 
////////////////////////////////////////////////////////// 
// // 
// Main Function // 
// // 
////////////////////////////////////////////////////////// 
void main() 
{ 
 if(FAILED(::CoInitialize(NULL))) 
 return; 
 
 CreateTableX(); 
 
 ::CoUninitialize(); 
} 
 
////////////////////////////////////////////////////////// 
// // 
// CreateTableX Function // 
// // 
////////////////////////////////////////////////////////// 
void CreateTableX() 
{ 
 HRESULT hr = S_OK; 
 
 // Define ADOX object pointers. 
 // Initialize pointers on define. 
 // These are in the ADOX:: namespace. 
 _CatalogPtr m_pCatalog = NULL; 
 _TablePtr m_pTable = NULL; 
 
 try 
 { 
 TESTHR(hr = m_pCatalog.CreateInstance(__uuidof(Catalog))); 
 
 //Open the catalog 
 m_pCatalog->PutActiveConnection( 
 "Provider='Microsoft.JET.OLEDB.4.0';" "data source='c:\\Program Files\\Microsoft Office" 
 "\\Office\\Samples\\Northwind.mdb';"); 
 
 TESTHR(hr = m_pTable.CreateInstance(__uuidof(Table))); 
 m_pTable->PutName("MyTable"); 
 m_pTable->Columns->Append("Column1",adInteger,0); 
 m_pTable->Columns->Append("Column2",adInteger,0); 
 m_pTable->Columns->Append("Column3",adVarWChar,50); 
 m_pCatalog->Tables->Append( 
 _variant_t((IDispatch *)m_pTable)); 
 printf("Table 'MyTable' is added.\n"); 
 
 // Delete the table as this is a demonstration. 
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
 cout << "Error occured in include files...."<< endl; 
 } 
} 
// EndCreateTableCpp 
```

