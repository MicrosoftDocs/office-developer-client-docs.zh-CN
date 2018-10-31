---
title: Create 方法示例 (VC++)
TOCTitle: Create method example (VC++)
ms:assetid: 8a826d78-7219-27de-8560-7cd4b8284751
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249609(v=office.15)
ms:contentKeyID: 48546195
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 50fb678cb9346641b38acc3ca4f3a9553fd2a1c2
ms.sourcegitcommit: 801b1b54786f7b0e5b0d35466e7ae8d1e840b26f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25862931"
---
# <a name="create-method-example-vc"></a>Create 方法示例 (VC++)


**适用于**： Access 2013 |Office 2013

下面的代码演示如何使用 [Create](create-method-adox.md) 方法创建新的 Microsoft Jet 数据库。

```cpp 
 
// BeginCreateDatabaseCpp 
#import "c:\Program Files\Common Files\system\ado\msadox.dll" no_namespace 
#import "c:\Program Files\Common Files\system\ado\msado15.dll" 
 
#define TESTHR(x) if FAILED(x) _com_issue_error(x); 
 
#include "iostream.h" 
#include "stdio.h" 
#include "conio.h" 
 
//Function declarations 
void CreateDatabaseX(void); 
 
//------------------------------------------------------------// 
//Main Function 
//Purpose: Test Driver 
//------------------------------------------------------------// 
void main() 
{ 
 HRESULT hr = S_OK; 
 
 hr = ::CoInitialize(NULL); 
 if(SUCCEEDED(hr)) 
 { 
 CreateDatabaseX(); 
 
 //Wait here for the user to see the output 
 printf("Press any key to continue..."); 
 getch(); 
 
 ::CoUninitialize(); 
 } 
} 
 
//------------------------------------------------------------// 
//CreateDatabaseX 
//Purpose: create a new Jet database with the Create method 
//------------------------------------------------------------// 
void CreateDatabaseX() 
{ 
 HRESULT hr = S_OK; 
 
 // Define ADOX object pointers. 
 // Initialize pointers on define. 
 // These are in the ADOX:: namespace. 
 
 _CatalogPtr m_pCatalog = NULL; 
 
 
 //Set ActiveConnection of Catalog to this string 
 _bstr_t strcnn("Provider='Microsoft.JET.OLEDB.4.0';" 
 "Data source = c:\\new.mdb"); 
 try 
 { 
 TESTHR(hr = m_pCatalog.CreateInstance(__uuidof (Catalog))); 
 m_pCatalog->Create(strcnn); 
 printf("Database 'c:\\new.mdb' is created.\n"); 
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
 cout << "Error occured in CreateDatabaseX...."<< endl; 
 } 
 
} 
// EndCreateDatabaseCpp 
```

