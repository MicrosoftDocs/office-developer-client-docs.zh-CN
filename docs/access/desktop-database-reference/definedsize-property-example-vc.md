---
<span data-ttu-id="85af6-101"><<<<<<< 标头标题： DefinedSize 属性示例 （VC + +） TOCTitle: DefinedSize 属性示例 （VC + +） === 标题： DefinedSize 属性示例 （VC + +） TOCTitle: DefinedSize 属性示例 （VC + +）</span><span class="sxs-lookup"><span data-stu-id="85af6-101"><<<<<<< HEAD title: DefinedSize Property Example (VC++) TOCTitle: DefinedSize Property Example (VC++) ======= title: DefinedSize property example (VC++) TOCTitle: DefinedSize property example (VC++)</span></span>
>>>>>>> <span data-ttu-id="85af6-102">母版页 ms:assetid: eac03770-4e6a-90fd-3e0e-89246b61d403 ms:mtpsurl: https://msdn.microsoft.com/library/JJ250192(v=office.15) ms:contentKeyID: 48548474 ms.date: 09/18/2015 mtps_version: office.15.aspx</span><span class="sxs-lookup"><span data-stu-id="85af6-102">master ms:assetid: eac03770-4e6a-90fd-3e0e-89246b61d403 ms:mtpsurl: https://msdn.microsoft.com/library/JJ250192(v=office.15) ms:contentKeyID: 48548474 ms.date: 09/18/2015 mtps_version: v=office.15</span></span>
---

<span data-ttu-id="85af6-103"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="85af6-103"><<<<<<< HEAD</span></span>
# <a name="definedsize-property-example-vc"></a><span data-ttu-id="85af6-104">DefinedSize 属性示例 (VC++)</span><span class="sxs-lookup"><span data-stu-id="85af6-104">DefinedSize Property Example (VC++)</span></span>
=======
# <a name="definedsize-property-example-vc"></a><span data-ttu-id="85af6-105">DefinedSize 属性示例 （VC + +）</span><span class="sxs-lookup"><span data-stu-id="85af6-105">DefinedSize property example (VC++)</span></span>
>>>>>>> <span data-ttu-id="85af6-106">master</span><span class="sxs-lookup"><span data-stu-id="85af6-106">master</span></span>


<span data-ttu-id="85af6-107">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="85af6-107">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="85af6-108">本示例演示 [Column](definedsize-property-adox.md) 的 [DefinedSize](column-object-adox.md) 属性。</span><span class="sxs-lookup"><span data-stu-id="85af6-108">This example demonstrates the [DefinedSize](definedsize-property-adox.md) property of a [Column](column-object-adox.md).</span></span> <span data-ttu-id="85af6-109">代码会重新定义的 FirstName 列中的**Employees**表*Northwind*数据库的大小。</span><span class="sxs-lookup"><span data-stu-id="85af6-109">The code will redefine the size of the FirstName column of the **Employees** table of the *Northwind* database.</span></span> <span data-ttu-id="85af6-110">然后，基于 [Employees](field-object-ado.md) （雇员）表的 [Recordset](recordset-object-ado.md) 的 FirstName（名字） **Field** 中值的变化将显现出来。</span><span class="sxs-lookup"><span data-stu-id="85af6-110">Then, the change in the values of the FirstName [Field](field-object-ado.md) of a [Recordset](recordset-object-ado.md) based on the **Employees** table is displayed.</span></span> <span data-ttu-id="85af6-111">注意，默认情况下，在重新定义 **DefinedSize** 属性之后，FirstName（名字）字段中将填补空格。</span><span class="sxs-lookup"><span data-stu-id="85af6-111">Note that by default, the FirstName field becomes padded with spaces after you redefine the **DefinedSize** property.</span></span>

```cpp 
 
// BeginDefinedSizeCpp 
#import "c:\Program Files\Common Files\system\ado\msadox.dll" no_namespace 
#import "C:\Program Files\Common Files\System\ADO\msado15.dll" rename("EOF", "EndOfFile") 
 
#include "iostream.h" 
#include "stdio.h" 
#include "conio.h" 
 
// Function declarations 
inline void TESTHR(HRESULT x) {if FAILED(x) _com_issue_error(x);}; 
void DefinedSizeX(void); 
 
////////////////////////////////////////////////////////// 
// // 
// Main Function // 
// // 
////////////////////////////////////////////////////////// 
void main() 
{ 
 if(FAILED(::CoInitialize(NULL))) 
 return; 
 
 DefinedSizeX(); 
 
 ::CoUninitialize(); 
} 
 
////////////////////////////////////////////////////////// 
// // 
// DefinedSizeX Function // 
// // 
////////////////////////////////////////////////////////// 
void DefinedSizeX(void) 
{ 
 HRESULT hr = S_OK; 
 
 // Define ADOX object pointers. 
 // Initialize pointers on define. 
 // These are in the ADOX:: namespace. 
 _CatalogPtr m_pCatNorthwind = NULL; 
 _ColumnPtr m_pColFirstName = NULL; 
 _ColumnPtr m_pColNewFirstName = NULL; 
 
 // Define ADODB object pointers 
 ADODB::_RecordsetPtr m_pRstEmployees = NULL; 
 
 // Define string variables. 
 _bstr_t strCnn("Provider='Microsoft.JET.OLEDB.4.0';data source=" 
 "'c:\\Program Files\\Microsoft Office\\Office\\Samples\\" 
 "Northwind.mdb';"); 
 _bstr_t aryFirstName[10]; 
 
 try 
 { 
 // Open a Recordset for the Employees table. 
 TESTHR(hr = m_pRstEmployees.CreateInstance( 
 __uuidof(ADODB::Recordset))); 
 TESTHR(hr = m_pCatNorthwind.CreateInstance(__uuidof (Catalog))); 
 TESTHR(hr = m_pColNewFirstName.CreateInstance(__uuidof(Column))); 
 
 m_pRstEmployees->Open("Employees",strCnn,ADODB::adOpenKeyset, 
 ADODB::adLockReadOnly,ADODB::adCmdTable); 
 
 long lngSize = m_pRstEmployees->RecordCount; 
 aryFirstName[lngSize]; 
 
 // Open a catalog for the Northwind database, 
 // using same connection as rstEmployees. 
 m_pCatNorthwind->PutActiveConnection(m_pRstEmployees-> 
 GetActiveConnection()); 
 
 // Loop through the recordset displaying the contents, 
 // of the FirstName field, the field's defined size, 
 // and its actual size. 
 // Also store FirstName values in aryFirstName array. 
 m_pRstEmployees->MoveFirst(); 
 printf("\nOriginal Defined Size and Actual Size"); 
 int iCount=0; 
 while (!(m_pRstEmployees->EndOfFile)) 
 { 
 printf("\nEmployee Name:"); 
 printf("%s ",(LPSTR)(_bstr_t)m_pRstEmployees->Fields-> 
 GetItem("FirstName")->Value); 
 printf("%s\n",(LPSTR)(_bstr_t)m_pRstEmployees->Fields-> 
 GetItem("LastName")->Value); 
 printf(" FirstName Defined size: %d\n",m_pRstEmployees-> 
 Fields->GetItem("FirstName")->DefinedSize) ; 
 printf(" FirstName Actual size: %d\n",m_pRstEmployees-> 
 Fields->GetItem("FirstName")->ActualSize); 
 aryFirstName[iCount] = (_bstr_t) m_pRstEmployees->Fields-> 
 GetItem("FirstName")->Value; 
 m_pRstEmployees->MoveNext(); 
 iCount++; 
 if(iCount%5==0) 
 { 
 printf("Press any key to continue..."); 
 getch(); 
 system("cls"); 
 } 
 } 
 m_pRstEmployees->Close(); 
 
 // Redefine the DefinedSize of FirstName in the catalog. 
 m_pColFirstName = m_pCatNorthwind->Tables->GetItem("Employees")-> 
 Columns->GetItem("FirstName"); 
 m_pColNewFirstName->Name = m_pColFirstName->Name; 
 m_pColNewFirstName->Type = m_pColFirstName->Type; 
 m_pColNewFirstName->DefinedSize = 
 (m_pColFirstName->DefinedSize) + 1; 
 
 // Append new FirstName column to catalog. 
 m_pCatNorthwind->Tables->GetItem("Employees")->Columns-> 
 Delete(m_pColFirstName->Name); 
 m_pCatNorthwind->Tables->GetItem("Employees")->Columns-> 
 Append(_variant_t((IDispatch*)m_pColNewFirstName,true), 
 adVarWChar,m_pColNewFirstName->DefinedSize); 
 
 // Open Employee table in Recordset for updating. 
 m_pRstEmployees->Open("Employees",m_pCatNorthwind-> 
 GetActiveConnection(),ADODB::adOpenKeyset, 
 ADODB::adLockOptimistic,ADODB::adCmdTable); 
 
 // Loop through the recordset displaying the contents 
 // of the FirstName field,the field's defined size, 
 // and its actual size. 
 // Also restore FirstName values from aryFirstName. 
 printf("Press any key to continue..."); 
 getch(); 
 system("cls"); 
 m_pRstEmployees->MoveFirst(); 
 printf("\n\nNew Defined Size and Actual Size"); 
 iCount=0; 
 while (!(m_pRstEmployees->EndOfFile)) 
 { 
 m_pRstEmployees->Fields->GetItem("FirstName")->Value = 
 aryFirstName[iCount]; 
 printf("\nEmployee Name: "); 
 printf("%s ",(LPSTR) (_bstr_t)m_pRstEmployees->Fields-> 
 GetItem("FirstName")->Value); 
 printf("%s\n",(LPSTR)(_bstr_t)m_pRstEmployees->Fields-> 
 GetItem("LastName")->Value); 
 printf(" FirstName Defined size: %d\n",m_pRstEmployees-> 
 Fields->GetItem("FirstName")->DefinedSize ); 
 printf(" FirstName Actual size: %d\n",m_pRstEmployees-> 
 Fields->GetItem("FirstName")->ActualSize ); 
 m_pRstEmployees->MoveNext(); 
 iCount++; 
 if(iCount%5==0) 
 { 
 printf("Press any key to continue..."); 
 getch(); 
 system("cls"); 
 } 
 } 
 m_pRstEmployees->Close(); 
 
 // Restore original FirstName column to catalog 
 m_pCatNorthwind->Tables->GetItem("Employees")->Columns-> 
 Delete(m_pColNewFirstName->Name); 
 
 m_pCatNorthwind->Tables->GetItem("Employees")->Columns-> 
 Append(_variant_t((IDispatch*)m_pColFirstName,true), 
 adVarWChar,m_pColFirstName->DefinedSize); 
 
 // Restore original FirstName values to Employees table. 
 m_pRstEmployees->Open("Employees",m_pCatNorthwind-> 
 GetActiveConnection(),ADODB::adOpenKeyset, 
 ADODB::adLockOptimistic,ADODB::adCmdTable); 
 
 m_pRstEmployees->MoveFirst(); 
 iCount = 0; 
 while(!(m_pRstEmployees->EndOfFile)) 
 { 
 m_pRstEmployees->Fields->GetItem("FirstName")->Value = 
 aryFirstName[iCount]; 
 m_pRstEmployees->MoveNext(); 
 iCount++; 
 } 
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
 cout << "Error occured in DefinedSizeX...."<< endl; 
 } 
 
 if (m_pRstEmployees) 
 if (m_pRstEmployees->State == 1) 
 m_pRstEmployees->Close(); 
 
 m_pCatNorthwind = NULL; 
} 
// EndDefinedSizeCpp 
```

