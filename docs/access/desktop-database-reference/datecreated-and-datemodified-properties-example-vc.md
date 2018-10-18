---
<span data-ttu-id="c7b2e-101"><<<<<<< 标头标题： DateCreated 和 DateModified 属性示例 （VC + +） TOCTitle: DateCreated 和 DateModified 属性示例 （VC + +） === 标题： DateCreated 和 DateModified 属性示例 （VC + +） TOCTitle:DateCreated 和 DateModified 属性示例 （VC + +）</span><span class="sxs-lookup"><span data-stu-id="c7b2e-101"><<<<<<< HEAD title: DateCreated and DateModified Properties Example (VC++) TOCTitle: DateCreated and DateModified Properties Example (VC++) ======= title: DateCreated and DateModified properties example (VC++) TOCTitle: DateCreated and DateModified properties example (VC++)</span></span>
>>>>>>> <span data-ttu-id="c7b2e-102">母版页 ms:assetid: 1c92e8f5-2fed-55dc-2cdd-51dfa16ecd84 ms:mtpsurl: https://msdn.microsoft.com/library/JJ248962(v=office.15) ms:contentKeyID: 48543573 ms.date: 09/18/2015 mtps_version: office.15.aspx</span><span class="sxs-lookup"><span data-stu-id="c7b2e-102">master ms:assetid: 1c92e8f5-2fed-55dc-2cdd-51dfa16ecd84 ms:mtpsurl: https://msdn.microsoft.com/library/JJ248962(v=office.15) ms:contentKeyID: 48543573 ms.date: 09/18/2015 mtps_version: v=office.15</span></span>
---

<span data-ttu-id="c7b2e-103"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="c7b2e-103"><<<<<<< HEAD</span></span>
# <a name="datecreated-and-datemodified-properties-example-vc"></a><span data-ttu-id="c7b2e-104">DateCreated 和 DateModified 属性示例 (VC++)</span><span class="sxs-lookup"><span data-stu-id="c7b2e-104">DateCreated and DateModified Properties Example (VC++)</span></span>
=======
# <a name="datecreated-and-datemodified-properties-example-vc"></a><span data-ttu-id="c7b2e-105">DateCreated 和 DateModified 属性示例 （VC + +）</span><span class="sxs-lookup"><span data-stu-id="c7b2e-105">DateCreated and DateModified properties example (VC++)</span></span>
>>>>>>> <span data-ttu-id="c7b2e-106">master</span><span class="sxs-lookup"><span data-stu-id="c7b2e-106">master</span></span>


<span data-ttu-id="c7b2e-107">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="c7b2e-107">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="c7b2e-p101">本示例演示 [DateCreated](datecreated-property-adox.md) 以及 [DateModified](datemodified-property-adox.md) 属性，演示方法是将一个新的 [Column](column-object-adox.md) 添加到现有 [Table](table-object-adox.md) 中，以及创建一个新的 **Table** 。运行本示例需要用到 DateOutput 过程。</span><span class="sxs-lookup"><span data-stu-id="c7b2e-p101">This example demonstrates the [DateCreated](datecreated-property-adox.md) and [DateModified](datemodified-property-adox.md) properties by adding a new [Column](column-object-adox.md) to an existing [Table](table-object-adox.md) and by creating a new **Table**. The DateOutput procedure is required for this example to run.</span></span>

```cpp 
 
// BeginDateCreatedCpp 
#import "c:\Program Files\Common Files\system\ado\msadox.dll" no_namespace 
#import "c:\Program Files\Common Files\system\ado\msado15.dll" 
 
#include "iostream.h" 
#include "stdio.h" 
#include "conio.h" 
 
//Function declarations 
inline void TESTHR(HRESULT x) {if FAILED(x) _com_issue_error(x);}; 
void DateCreatedX(void); 
void DateOutPut(_bstr_t strTemp , _TablePtr tblTemp); 
 
////////////////////////////////////////////////////////// 
// // 
// Main Function // 
// // 
////////////////////////////////////////////////////////// 
void main() 
{ 
 if(FAILED(::CoInitialize(NULL))) 
 return; 
 
 DateCreatedX(); 
 
 ::CoUninitialize(); 
} 
 
////////////////////////////////////////////////////////// 
// // 
// DateCreatedX Function // 
// // 
////////////////////////////////////////////////////////// 
void DateCreatedX() 
{ 
 HRESULT hr = S_OK; 
 
 // Define ADOX object pointers. 
 // Initialize pointers on define. 
 // These are in the ADOX:: namespace. 
 _CatalogPtr m_pCatalog = NULL; 
 _TablePtr m_pTblEmployees = NULL; 
 _TablePtr m_pTblNew = NULL; 
 
 //Set ActiveConnection of Catalog to this string 
 _bstr_t strCnn("Provider='Microsoft.JET.OLEDB.4.0';" 
 "Data Source= 'c:\\Program Files\\Microsoft Office\\" 
 "Office\\Samples\\Northwind.mdb';"); 
 
 try 
 { 
 TESTHR(hr = m_pCatalog.CreateInstance(__uuidof (Catalog))); 
 
 // Connect the catalog. 
 m_pCatalog->PutActiveConnection(strCnn); 
 
 m_pTblEmployees = m_pCatalog->Tables->GetItem("Employees"); 
 
 // Print current information about the Employees table. 
 DateOutPut((_bstr_t)"Current properties", m_pTblEmployees); 
 
 // Create and append column to the Employees table. 
 m_pTblEmployees->Columns->Append("NewColumn", adInteger,0); 
 
 m_pCatalog->Tables->Refresh(); 
 
 // Print new information about the Employees table. 
 DateOutPut((_bstr_t)"After creating a new column", 
 m_pTblEmployees); 
 
 // Delete new column because this is a demonstration. 
 m_pTblEmployees->Columns->Delete("NewColumn"); 
 
 // Create and append new Table object to the Northwind database. 
 TESTHR(hr = m_pTblNew.CreateInstance(__uuidof(Table))); 
 
 m_pTblNew->Name = "NewTable"; 
 m_pTblNew->Columns->Append("NewColumn", adInteger,0); 
 m_pCatalog->Tables->Append(_variant_t((IDispatch*)m_pTblNew)); 
 m_pCatalog->Tables->Refresh(); 
 
 //Print information about the new Table object. 
 DateOutPut((_bstr_t)"After creating a new table", m_pCatalog-> 
 Tables->GetItem("NewTable")); 
 
 // Delete new Table object because this is a demonstration. 
 m_pCatalog->Tables->Delete(m_pTblNew->Name); 
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
 
////////////////////////////////////////////////////////// 
// // 
// DateOutPut Function // 
// // 
////////////////////////////////////////////////////////// 
void DateOutPut(_bstr_t strTemp , _TablePtr tblTemp) 
{ 
 // Print DateCreated and DateModified information about 
 // specified Table object. 
 cout << strTemp << endl; 
 cout << " Table: " << tblTemp->GetName() << endl; 
 cout << " DateCreated = " << (_bstr_t)tblTemp-> 
 GetDateCreated() << endl; 
 cout << " DateModified = " << (_bstr_t)tblTemp-> 
 GetDateModified() << endl; 
} 
// EndDateCreatedCpp 
```

