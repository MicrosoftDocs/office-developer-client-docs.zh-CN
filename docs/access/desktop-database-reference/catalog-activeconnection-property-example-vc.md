---
<span data-ttu-id="85546-101"><<<<<<< 标头标题： 目录 ActiveConnection 属性示例 （VC + +） TOCTitle： 目录 ActiveConnection 属性示例 （VC + +） === 标题： 目录 ActiveConnection 属性示例 （VC + +） TOCTitle： 目录 ActiveConnection属性示例 （VC + +）</span><span class="sxs-lookup"><span data-stu-id="85546-101"><<<<<<< HEAD title: Catalog ActiveConnection Property Example (VC++) TOCTitle: Catalog ActiveConnection Property Example (VC++) ======= title: Catalog ActiveConnection property example (VC++) TOCTitle: Catalog ActiveConnection property example (VC++)</span></span>
>>>>>>> <span data-ttu-id="85546-102">母版页 ms:assetid: 0e72ff1c-b894-a440-67cf-bba091e7cb8b ms:mtpsurl: https://msdn.microsoft.com/library/JJ248861(v=office.15) ms:contentKeyID: 48543246 ms.date: 09/18/2015 mtps_version: office.15.aspx</span><span class="sxs-lookup"><span data-stu-id="85546-102">master ms:assetid: 0e72ff1c-b894-a440-67cf-bba091e7cb8b ms:mtpsurl: https://msdn.microsoft.com/library/JJ248861(v=office.15) ms:contentKeyID: 48543246 ms.date: 09/18/2015 mtps_version: v=office.15</span></span>
---

<span data-ttu-id="85546-103"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="85546-103"><<<<<<< HEAD</span></span>
# <a name="catalog-activeconnection-property-example-vc"></a><span data-ttu-id="85546-104">Catalog 的 ActiveConnection 属性示例 (VC++)</span><span class="sxs-lookup"><span data-stu-id="85546-104">Catalog ActiveConnection Property Example (VC++)</span></span>
=======
# <a name="catalog-activeconnection-property-example-vc"></a><span data-ttu-id="85546-105">Catalog 的 ActiveConnection 属性示例 （VC + +）</span><span class="sxs-lookup"><span data-stu-id="85546-105">Catalog ActiveConnection property example (VC++)</span></span>
>>>>>>> <span data-ttu-id="85546-106">master</span><span class="sxs-lookup"><span data-stu-id="85546-106">master</span></span>


<span data-ttu-id="85546-107">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="85546-107">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="85546-p101">将 [ActiveConnection](activeconnection-property-adox.md) 属性设置为有效的打开连接将"打开"目录。从打开的目录中，可以访问该目录中包含的架构对象。</span><span class="sxs-lookup"><span data-stu-id="85546-p101">Setting the [ActiveConnection](activeconnection-property-adox.md) property to a valid, open connection "opens" the catalog. From an open catalog, you can access the schema objects contained within that catalog.</span></span>

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

