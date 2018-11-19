---
title: GetObjectOwner 和 SetObjectOwner 方法示例 (VC++)
TOCTitle: GetObjectOwner and SetObjectOwner methods example (VC++)
ms:assetid: af38cc5c-4475-20fa-edcd-a439e1ffbf99
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249835(v=office.15)
ms:contentKeyID: 48547096
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 2245ddca1dc71027887f99127f599e405a0782c2
ms.sourcegitcommit: 45feafb3b55de0402dddf5548c0c1c43a0eabafd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2018
ms.locfileid: "26026419"
---
# <a name="getobjectowner-and-setobjectowner-methods-example-vc"></a>GetObjectOwner 和 SetObjectOwner 方法示例 (VC++)


**适用于**： Access 2013、 Office 2013

本示例演示 [GetObjectOwner](getobjectowner-method-adox.md) 和 [SetObjectOwner](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/setobjectowner-method-adox) 方法。 此代码假定存在的组 Accounting （请参阅[组和用户 Append、 ChangePassword 方法示例 （VC + +）](groups-and-users-append-changepassword-methods-example-vc.md)以了解如何将该组添加到系统）。 Categories（类别）表的所有者设置为 Accounting。

```cpp 
 
// BeginOwnersCpp 
#import "c:\Program Files\Common Files\system\ado\msadox.dll" no_namespace 
 
#include "iostream.h" 
#include "stdio.h" 
#include "conio.h" 
 
//Function declarations 
inline void TESTHR(HRESULT x) {if FAILED(x) _com_issue_error(x);}; 
void OwnersX(void); 
 
////////////////////////////////////////////////////////// 
// // 
// Main Function // 
// // 
////////////////////////////////////////////////////////// 
void main() 
{ 
 if(FAILED(::CoInitialize(NULL))) 
 return; 
 
 OwnersX(); 
 
 ::CoUninitialize(); 
} 
 
////////////////////////////////////////////////////////// 
// // 
// OwnersX Function // 
// // 
////////////////////////////////////////////////////////// 
void OwnersX() 
{ 
 HRESULT hr = S_OK; 
 
 // Define ADOX object pointers. 
 // Initialize pointers on define. 
 // These are in the ADOX:: namespace. 
 _TablePtr m_pTable = NULL; 
 _CatalogPtr m_pCatalog = NULL; 
 
 try 
 { 
 TESTHR(hr = m_pCatalog.CreateInstance(__uuidof(Catalog))); 
 TESTHR(hr = m_pTable.CreateInstance(__uuidof(Table))); 
 
 //Open the Catalog. 
 m_pCatalog->PutActiveConnection( 
 "Provider='Microsoft.JET.OLEDB.4.0';" "data source='c:\\Program Files\\Microsoft Office\\" 
 "Office\\Samples\\Northwind.mdb';" 
 "jet oledb:system database='c:\\Program Files\\Microsoft Office\\" 
 "Office\\system.mdw'"); 
 
 //Print the original owner of Categories 
 _bstr_t strOwner = m_pCatalog->GetObjectOwner("Categories", 
 adPermObjTable); 
 cout << "Owner of Categories: " << strOwner << "\n" << endl; 
 int iLineCnt = 2; 
 
 //Create and append new group with a string. 
 m_pCatalog->Groups->Append("Accounting"); 
 
 //Set the owner of Categories to Accounting. 
 m_pCatalog->SetObjectOwner("Categories", 
 adPermObjTable,"Accounting"); 
 
 _variant_t vIndex; 
 //List the owners of all tables and columns in the catalog. 
 for (long iIndex = 0; iIndex < m_pCatalog->Tables->Count; iIndex++) 
 { 
 vIndex = iIndex; 
 m_pTable = m_pCatalog->Tables->GetItem(vIndex); 
 cout << "Table: " << m_pTable->Name << endl; 
 cout << " Owner: " << m_pCatalog-> 
 GetObjectOwner(m_pTable->Name,adPermObjTable) << endl; 
 if (iLineCnt%16 == 0) 
 { 
 printf("\nPress any key to continue...\n"); 
 getch(); 
 } 
 iLineCnt = iLineCnt + 2; 
 } 
 
 //Restore the original owner of Categories 
 m_pCatalog->SetObjectOwner("Categories",adPermObjTable,strOwner); 
 
 //Delete Accounting 
 m_pCatalog->Groups->Delete("Accounting"); 
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
// EndOwnersCpp 
```

