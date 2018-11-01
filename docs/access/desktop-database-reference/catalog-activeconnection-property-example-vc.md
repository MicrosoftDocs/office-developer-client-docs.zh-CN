---
title: Catalog 的 ActiveConnection 属性示例 (VC++)
TOCTitle: Catalog ActiveConnection property example (VC++)
ms:assetid: 0e72ff1c-b894-a440-67cf-bba091e7cb8b
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248861(v=office.15)
ms:contentKeyID: 48543246
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 55faf280d56b90f6033aaba700d3b9fa7a7e2724
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25869188"
---
# <a name="catalog-activeconnection-property-example-vc"></a>Catalog 的 ActiveConnection 属性示例 (VC++)


**适用于**： Access 2013、 Office 2013

将 [ActiveConnection](activeconnection-property-adox.md) 属性设置为有效的打开连接将"打开"目录。从打开的目录中，可以访问该目录中包含的架构对象。

```cpp 
 
// BeginActiveConnectionCpp 
#import "c:\Program Files\Common Files\system\ado\msado15.dll" 
#import "c:\Program Files\Common Files\system\ado\msadox.dll" no_namespace 
 
#include "iostream.h" 
#include "stdio.h" 
#include "conio.h" 
 
// Function declarations 
inline void TESTHR(HRESULT x) {if FAILED(x) _com_issue_error(x);}; 
void OpenConnectionX(void); 
void OpenConnectionWithStringX(void); 
 
////////////////////////////////////////////////////////// 
// // 
// Main Function // 
// // 
////////////////////////////////////////////////////////// 
void main() 
{ 
 if(FAILED(::CoInitialize(NULL))) 
 return; 
 
 OpenConnectionX(); 
 
 OpenConnectionWithStringX(); 
 
 ::CoUninitialize(); 
} 
 
////////////////////////////////////////////////////////// 
// // 
// OpenConnectionX Function // 
// // 
////////////////////////////////////////////////////////// 
void OpenConnectionX(void) 
{ 
 HRESULT hr = S_OK; 
 
 // Define ADOX object pointers. 
 // Initialize pointers on define. 
 // These are in the ADOX:: namespace. 
 _CatalogPtr m_pCatalog = NULL; 
 
 //Define ADODB object pointers 
 ADODB::_ConnectionPtr m_pCnn = NULL; 
 
 // Define string variables. 
 _bstr_t strcnn("Provider='Microsoft.JET.OLEDB.4.0';" 
 "Data source = 'c:\\Program Files\\Microsoft Office\\" 
 "Office\\Samples\\Northwind.mdb';"); 
 
 try 
 { 
 TESTHR(hr = m_pCnn.CreateInstance(__uuidof(ADODB::Connection))); 
 TESTHR(hr = m_pCatalog.CreateInstance(__uuidof (Catalog))); 
 m_pCnn->Open(strcnn,"","",NULL); 
 m_pCatalog->PutActiveConnection(_variant_t((IDispatch *) m_pCnn)); 
 _variant_t vIndex = (short) 0; 
 cout<<m_pCatalog->Tables->GetItem(vIndex)->Type<<endl; 
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
 cout << "Error occured in OpenConnectionX...."<< endl; 
 } 
 
 if (m_pCnn) 
 if (m_pCnn->State == 1) 
 m_pCnn->Close(); 
} 
 
////////////////////////////////////////////////////////// 
// // 
// OpenConnectionWithStringX Function // 
// // 
////////////////////////////////////////////////////////// 
void OpenConnectionWithStringX(void) 
{ 
 HRESULT hr = S_OK; 
 
 // Define ADOX object pointers. 
 // Initialize pointers on define. 
 // These are in the ADOX:: namespace. 
 _CatalogPtr m_pCatalog = NULL; 
 
 // Define string variables. 
 _bstr_t strcnn("Provider='Microsoft.JET.OLEDB.4.0';" 
 "Data source = 'c:\\Program Files\\Microsoft Office\\" 
 "Office\\Samples\\Northwind.mdb';"); 
 
 try 
 { 
 TESTHR(hr = m_pCatalog.CreateInstance(__uuidof (Catalog))); 
 m_pCatalog->PutActiveConnection(strcnn); 
 _variant_t vIndex = (short) 0; 
 cout<<m_pCatalog->Tables->GetItem(vIndex)->Type<<endl; 
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
 cout << "Error occured in OpenConnectionWithStringX...."<< endl; 
 } 
} 
// EndActiveConnectionCpp 
```

