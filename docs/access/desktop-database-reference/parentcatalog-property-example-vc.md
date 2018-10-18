---
<span data-ttu-id="242d3-101"><<<<<<< 标头标题： ParentCatalog 属性示例 （VC + +） TOCTitle: ParentCatalog 属性示例 （VC + +） === 标题： ParentCatalog 属性示例 （VC + +） TOCTitle: ParentCatalog 属性示例 （VC + +）</span><span class="sxs-lookup"><span data-stu-id="242d3-101"><<<<<<< HEAD title: ParentCatalog Property Example (VC++) TOCTitle: ParentCatalog Property Example (VC++) ======= title: ParentCatalog property example (VC++) TOCTitle: ParentCatalog property example (VC++)</span></span>
>>>>>>> <span data-ttu-id="242d3-102">母版页 ms:assetid: fad6574f-698f-f48a-ba0b-59f048ae012c ms:mtpsurl: https://msdn.microsoft.com/library/JJ250281(v=office.15) ms:contentKeyID: 48548855 ms.date: 09/18/2015 mtps_version: office.15.aspx</span><span class="sxs-lookup"><span data-stu-id="242d3-102">master ms:assetid: fad6574f-698f-f48a-ba0b-59f048ae012c ms:mtpsurl: https://msdn.microsoft.com/library/JJ250281(v=office.15) ms:contentKeyID: 48548855 ms.date: 09/18/2015 mtps_version: v=office.15</span></span>
---

<span data-ttu-id="242d3-103"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="242d3-103"><<<<<<< HEAD</span></span>
# <a name="parentcatalog-property-example-vc"></a><span data-ttu-id="242d3-104">ParentCatalog 属性示例 (VC++)</span><span class="sxs-lookup"><span data-stu-id="242d3-104">ParentCatalog Property Example (VC++)</span></span>
=======
# <a name="parentcatalog-property-example-vc"></a><span data-ttu-id="242d3-105">ParentCatalog 属性示例 （VC + +）</span><span class="sxs-lookup"><span data-stu-id="242d3-105">ParentCatalog property example (VC++)</span></span>
>>>>>>> <span data-ttu-id="242d3-106">master</span><span class="sxs-lookup"><span data-stu-id="242d3-106">master</span></span>


<span data-ttu-id="242d3-107">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="242d3-107">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="242d3-p101">下面的代码演示如何在将表追加到目录之前使用 [ParentCatalog](parentcatalog-property-adox.md) 属性访问特定于提供程序的属性。该属性为 AutoIncrement，它在 Microsoft Jet 数据库中创建 AutoIncrement 字段。</span><span class="sxs-lookup"><span data-stu-id="242d3-p101">The following code demonstrates how to use the [ParentCatalog](parentcatalog-property-adox.md) property to access a provider-specific property prior to appending a table to a catalog. The property is AutoIncrement, which creates an AutoIncrement field in a Microsoft Jet database.</span></span>

```cpp 
 
// BeginCreateAutoIncrColumnCpp 
#import "c:\Program Files\Common Files\system\ado\msadox.dll" no_namespace 
#import "c:\Program Files\Common Files\system\ado\msado15.dll" 
 
#include "iostream.h" 
#include "stdio.h" 
#include "conio.h" 
 
//Function declarations 
inline void TESTHR(HRESULT x) {if FAILED(x) _com_issue_error(x);}; 
void CreateAutoIncrColumnX(void); 
 
////////////////////////////////////////////////////////// 
// // 
// Main Function // 
// // 
////////////////////////////////////////////////////////// 
void main() 
{ 
 if(FAILED(::CoInitialize(NULL))) 
 return; 
 
 CreateAutoIncrColumnX(); 
 
 ::CoUninitialize(); 
} 
 
////////////////////////////////////////////////////////// 
// // 
// CreateAutoIncrColumnX Function // 
// // 
////////////////////////////////////////////////////////// 
void CreateAutoIncrColumnX(void) 
{ 
 HRESULT hr = S_OK; 
 
 // Define ADOX object pointers. 
 // Initialize pointers on define. 
 // These are in the ADOX:: namespace. 
 _CatalogPtr m_pCatalog = NULL; 
 _TablePtr m_pTable = NULL; 
 
 // Define ADODB object pointers. 
 ADODB::_ConnectionPtr m_pCnn = NULL; 
 
 //Define string variables 
 _bstr_t strCnn("Provider='Microsoft.JET.OLEDB.4.0';" 
 "Data Source='c:\\Program Files\\Microsoft Office\\" 
 "Office\\Samples\\Northwind.mdb';"); 
 try 
 { 
 TESTHR(hr = m_pCnn.CreateInstance(__uuidof(ADODB::Connection))); 
 
 TESTHR(hr = m_pCatalog.CreateInstance(__uuidof (Catalog))); 
 
 TESTHR(hr = m_pTable.CreateInstance(__uuidof (Table))); 
 
 // Connect the catalog. 
 m_pCnn->Open (strCnn, "", "", NULL); 
 
 m_pCatalog->PutActiveConnection(variant_t((IDispatch *)m_pCnn)); 
 
 m_pTable->Name="MyContacts"; 
 m_pTable->ParentCatalog = m_pCatalog; 
 
 // Create fields and append them to the new Table object. 
 m_pTable->Columns->Append("ContactId", adInteger,0); 
 
 // Make the ContactId column and auto incrementing column 
 m_pTable->Columns->GetItem("ContactId")->Properties-> 
 GetItem("AutoIncrement")->Value = true; 
 m_pTable->Columns->Append("CustomerID", adVarWChar,0); 
 m_pTable->Columns->Append("FirstName", adVarWChar,0); 
 m_pTable->Columns->Append("LastName", adVarWChar,0); 
 m_pTable->Columns->Append("Phone", adVarWChar, 20); 
 m_pTable->Columns->Append("Notes", adLongVarWChar,0); 
 m_pCatalog->Tables->Append(_variant_t((IDispatch*)m_pTable)); 
 
 // Refresh the database. 
 m_pCatalog->Tables->Refresh(); 
 
 printf("Table 'MyContacts' is added.\n"); 
 
 // Delete new table, since this is only an example 
 m_pCatalog->Tables->Delete("MyContacts"); 
 
 printf("Table 'MyContacts' is deleted.\n"); 
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
 cout << "Error occured in CreateAutoIncrColumnX...."<< endl; 
 } 
 
 m_pCatalog = NULL; 
} 
// EndCreateAutoIncrColumnCpp 
```

