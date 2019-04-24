---
title: Groups 和 Users 的 Append、ChangePassword 方法示例 (VC++)
TOCTitle: Groups and Users Append, ChangePassword methods example (VC++)
ms:assetid: 4eaaed4f-f5bf-38d0-b984-8e3f344923c5
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249252(v=office.15)
ms:contentKeyID: 48544759
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 5bf0c89dc588ba710b14f3753af889beba8d5b24
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32292081"
---
# <a name="groups-and-users-append-changepassword-methods-example-vc"></a>Groups 和 Users 的 Append、ChangePassword 方法示例 (VC++)


**适用于**：Access 2013、Office 2013

本示例演示 [Groups](append-method-adox-groups.md) 的 [Append](groups-collection-adox.md) 方法，以及 [Users](append-method-adox-users.md) 的 [Append](users-collection-adox.md) 方法，演示方法为将一个新的 [Group](group-object-adox.md) 和一个新的 [User](user-object-adox.md) 添加到系统。接下来将新的 **Group** 追加到新 **User** 的 **Groups** 集合。最终结果是，将新 **User** 添加到该 **Group** 中。此外， [ChangePassword](changepassword-method-adox.md) 方法用于指定 **User** 密码。

```cpp 
 
// BeginGroupCpp 
#import "c:\Program Files\Common Files\system\ado\msadox.dll" no_namespace 
 
#include "iostream.h" 
#include "stdio.h" 
#include "conio.h" 
 
//Function declarations 
void GroupX(void); 
inline void TESTHR(HRESULT x) {if FAILED(x) _com_issue_error(x);}; 
 
////////////////////////////////////////////////////////// 
// // 
// Main Function // 
// // 
////////////////////////////////////////////////////////// 
void main() 
{ 
 if(FAILED(::CoInitialize(NULL))) 
 return; 
 
 GroupX(); 
 
 ::CoUninitialize(); 
} 
 
////////////////////////////////////////////////////////// 
// // 
// GroupX Function // 
// // 
////////////////////////////////////////////////////////// 
void GroupX(void) 
{ 
 HRESULT hr = S_OK; 
 
 // Define ADOX object pointers. 
 // Initialize pointers on define. 
 // These are in the ADOX:: namespace. 
 _CatalogPtr m_pCatalog = NULL; 
 _UserPtr m_pUserNew = NULL; 
 _UserPtr m_pUser = NULL; 
 _GroupPtr m_pGroup = NULL; 
 
 // Define String Variables. 
 _bstr_t strCnn("Provider='Microsoft.JET.OLEDB.4.0';" 
 "Data source = 'c:\\Program Files\\Microsoft Office\\" 
 "Office\\Samples\\Northwind.mdb';" 
 "jet oledb:system database='c:\\Program Files\\Microsoft Office\\" 
 "Office\\system.mdw'"); 
 
 try 
 { 
 TESTHR(hr = m_pCatalog.CreateInstance(__uuidof (Catalog))); 
 m_pCatalog->PutActiveConnection(strCnn); 
 
 // Create and append new group with a string. 
 m_pCatalog->Groups->Append("Accounting"); 
 
 // Create and append new user with an object. 
 TESTHR(hr = m_pUserNew.CreateInstance(__uuidof(User))); 
 m_pUserNew->PutName("Pat Smith"); 
 m_pUserNew->ChangePassword("","Password1"); 
 m_pCatalog->Users->Append( 
 _variant_t((IDispatch *)m_pUserNew),""); 
 
 // Make the user Pat Smith a member of the 
 // Accounting group by creating and adding the 
 // appropriate Group object to the user's Groups 
 // collection.The same is accomplished if a User 
 // object representing Pat Smith is created and 
 // appended to the Accounting group Users collection 
 m_pUserNew->Groups->Append("Accounting"); 
 
 // Enumerate all User objects in the 
 // catalog's Users collection. 
 long lUsrIndex; 
 long lGrpIndex; 
 _variant_t vIndex; 
 for (lUsrIndex=0; lUsrIndex<m_pCatalog->Users->Count; lUsrIndex++) 
 { 
 vIndex = lUsrIndex; 
 m_pUser = m_pCatalog->Users->GetItem(vIndex); 
 cout<<" "<<m_pUser->Name <<endl; 
 cout<<" Belongs to these groups:"<<endl; 
 
 // Enumerate all Group objects in each User 
 // object's Groups collection. 
 if(m_pUser->Groups->Count != 0) 
 { 
 for(lGrpIndex=0;lGrpIndex<m_pUser->Groups->Count;lGrpIndex++) 
 { 
 vIndex = lGrpIndex; 
 m_pGroup = m_pUser->Groups->GetItem(vIndex); 
 cout<<" "<< m_pGroup->Name<<endl; 
 } 
 } 
 else 
 cout<<" [None]"<<endl; 
 } 
 
 // Enumerate all Group objects in the default 
 // workspace's Groups collection. 
 for (lGrpIndex=0; lGrpIndex<m_pCatalog->Groups->Count; lGrpIndex++) 
 { 
 vIndex = lGrpIndex; 
 m_pGroup = m_pCatalog->Groups->GetItem(vIndex); 
 cout<<" "<< m_pGroup->Name <<endl; 
 cout<<" Has as its members:"<<endl; 
 
 // Enumerate all User objects in each Group 
 // object's Users Collection. 
 if(m_pGroup->Users->Count != 0) 
 { 
 for (lUsrIndex=0; lUsrIndex<m_pGroup->Users->Count; lUsrIndex++) 
 { 
 vIndex = lUsrIndex; 
 m_pUser = m_pGroup->Users->GetItem(vIndex); 
 cout<<" "<<m_pUser->Name<<endl; 
 } 
 } 
 else 
 cout<<" [None]"<<endl; 
 } 
 
 // Delete new User and Group object because this 
 // is only a demonstration. 
 m_pCatalog->Users->Delete("Pat Smith"); 
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
// EndGroupCpp 
```

