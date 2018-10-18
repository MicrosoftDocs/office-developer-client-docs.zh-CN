---
<span data-ttu-id="48bcf-101"><<<<<<< 标头标题： Value 属性示例 （VC + +） TOCTitle: Value 属性示例 （VC + +） === 标题： Value 属性示例 （VC + +） TOCTitle: Value 属性示例 （VC + +）</span><span class="sxs-lookup"><span data-stu-id="48bcf-101"><<<<<<< HEAD title: Value Property Example (VC++) TOCTitle: Value Property Example (VC++) ======= title: Value property example (VC++) TOCTitle: Value property example (VC++)</span></span>
>>>>>>> <span data-ttu-id="48bcf-102">母版页 ms:assetid: d8a496f9-5864-ffd8-ca99-5a2f10dcdcb4 ms:mtpsurl: https://msdn.microsoft.com/library/JJ250092(v=office.15) ms:contentKeyID: 48548040 ms.date: 09/18/2015 mtps_version: office.15.aspx</span><span class="sxs-lookup"><span data-stu-id="48bcf-102">master ms:assetid: d8a496f9-5864-ffd8-ca99-5a2f10dcdcb4 ms:mtpsurl: https://msdn.microsoft.com/library/JJ250092(v=office.15) ms:contentKeyID: 48548040 ms.date: 09/18/2015 mtps_version: v=office.15</span></span>
---

<span data-ttu-id="48bcf-103"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="48bcf-103"><<<<<<< HEAD</span></span>
# <a name="value-property-example-vc"></a><span data-ttu-id="48bcf-104">Value 属性示例 (VC++)</span><span class="sxs-lookup"><span data-stu-id="48bcf-104">Value Property Example (VC++)</span></span>
=======
# <a name="value-property-example-vc"></a><span data-ttu-id="48bcf-105">Value 属性示例 （VC + +）</span><span class="sxs-lookup"><span data-stu-id="48bcf-105">Value property example (VC++)</span></span>
>>>>>>> <span data-ttu-id="48bcf-106">master</span><span class="sxs-lookup"><span data-stu-id="48bcf-106">master</span></span>


<span data-ttu-id="48bcf-107">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="48bcf-107">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="48bcf-108">此示例通过显示 ***Employees***（雇员）表的字段和属性值来演示 [Field](field-object-ado.md) 和 [Property](property-object-ado.md) 对象的 [Value](value-property-ado.md) 属性。</span><span class="sxs-lookup"><span data-stu-id="48bcf-108">This example demonstrates the [Value](value-property-ado.md) property with [Field](field-object-ado.md) and [Property](property-object-ado.md) objects by displaying field and property values for the ***Employees*** table.</span></span>

```cpp 
 
// BeginValueCpp 
#import "c:\Program Files\Common Files\System\ADO\msado15.dll" no_namespace rename("EOF", "EndOfFile") 
 
#include <ole2.h> 
#include <stdio.h> 
#include <conio.h> 
 
// Function declarations 
inline void TESTHR(HRESULT x) {if FAILED(x) _com_issue_error(x);}; 
void ValueX(void); 
void PrintProviderError(_ConnectionPtr pConnection); 
void PrintComError(_com_error &e); 
 
////////////////////////////////////////////////////////// 
// // 
// Main Function // 
// // 
////////////////////////////////////////////////////////// 
 
void main() 
{ 
 if(FAILED(::CoInitialize(NULL))) 
 return; 
 
 ValueX(); 
 
 ::CoUninitialize(); 
} 
 
////////////////////////////////////////////////////////// 
// // 
// ValueX Function // 
// // 
////////////////////////////////////////////////////////// 
void ValueX(void) 
{ 
 HRESULT hr = S_OK; 
 
 // Define string variables. 
 _bstr_t strCnn("Provider='sqloledb';Data Source='MySqlServer';" 
 "Initial Catalog='pubs';Integrated Security='SSPI';"); 
 
 // Define ADO object pointers. 
 // Initialize pointers on define. 
 // These are in the ADODB:: namespace. 
 _RecordsetPtr pRstEmployees = NULL; 
 FieldsPtr pFldLoop = NULL; 
 PropertiesPtr pPrpLoop = NULL; 
 _variant_t vtIndex; 
 vtIndex.vt = VT_I2; 
 
 try 
 { 
 // Open recordset with data from Employee table. 
 TESTHR(pRstEmployees.CreateInstance(__uuidof(Recordset))); 
 pRstEmployees->Open ("employee",strCnn , 
 adOpenForwardOnly, adLockReadOnly, adCmdTable); 
 
 printf("Field values in rstEmployees\n\n"); 
 
 // Enumerate the Fields collection of the Employees table. 
 pFldLoop = pRstEmployees->GetFields(); 
 
 for (int intFields = 0; intFields < (int)pFldLoop->GetCount(); intFields++) 
 { 
 vtIndex.iVal = intFields; 
 
 // Because Value is the default property of a 
 // Field object,the use of the actual keyword 
 // here is optional. 
 printf(" %s = %s\n\n" , 
 (LPCSTR) pFldLoop->GetItem(vtIndex)->GetName(), 
 (LPCSTR) (_bstr_t) pFldLoop->GetItem(vtIndex)->Value); 
 } 
 
 printf("Press any key to continue...\n\n"); 
 getch(); 
 printf("Property values in rstEmployees\n\n"); 
 
 // Enumerate the Properties collection of the Recordset object. 
 pPrpLoop = pRstEmployees->GetProperties(); 
 int intLine = 0; 
 
 for (int intProperties = 0; intProperties < (int)pPrpLoop-> 
 GetCount(); intProperties++) 
 { 
 vtIndex.iVal = intProperties; 
 
 // Because Value is the default property of a 
 // Property object,the use of the actual keyword 
 // here is optional. 
 _variant_t propValue = pPrpLoop->GetItem(vtIndex)->Value; 
 switch(propValue.vt) 
 { 
 
 case (VT_BOOL): 
 if(propValue.boolVal) 
 { 
 printf(" %s = True\n\n",(LPCSTR) pPrpLoop-> 
 GetItem(vtIndex)->GetName()); 
 } 
 else 
 { 
 printf(" %s = False\n\n",(LPCSTR) pPrpLoop-> 
 GetItem(vtIndex)->GetName()); 
 } 
 break; 
 
 case (VT_I4): 
 printf(" %s = %d\n\n",(LPCSTR) pPrpLoop-> 
 GetItem(vtIndex)->GetName(), 
 pPrpLoop->GetItem(vtIndex)->Value.lVal); 
 break; 
 
 case (VT_EMPTY): 
 printf(" %s = \n\n",(LPCSTR) pPrpLoop-> 
 GetItem(vtIndex)->GetName()); 
 break; 
 
 default: 
 break; 
 } 
 
 intLine++; 
 if (intLine % 10 == 0) 
 { 
 printf("\nPress any key to continue..."); 
 getch(); 
 
 //Clear the screen for the next display 
 system("cls"); 
 } 
 } 
 } 
 catch (_com_error &e) 
 { 
 // Notify the user of errors if any. 
 // Pass a connection pointer accessed from the Recordset. 
 _variant_t vtConnect = pRstEmployees->GetActiveConnection(); 
 
 // GetActiveConnection returns connect string if connection 
 // is not open, else returns Connection object. 
 switch(vtConnect.vt) 
 { 
 case VT_BSTR: 
 PrintComError(e); 
 break; 
 case VT_DISPATCH: 
 PrintProviderError(vtConnect); 
 break; 
 default: 
 printf("Errors occured."); 
 break; 
 } 
 } 
 
 if (pRstEmployees) 
 if (pRstEmployees->State == adStateOpen) 
 pRstEmployees->Close(); 
} 
 
////////////////////////////////////////////////////////// 
// // 
// PrintProviderError Function // 
// // 
////////////////////////////////////////////////////////// 
void PrintProviderError(_ConnectionPtr pConnection) 
{ 
 // Print Provider Errors from Connection object. 
 // pErr is a record object in the Connection's Error collection. 
 ErrorPtr pErr = NULL; 
 
 if( (pConnection->Errors->Count) > 0) 
 { 
 long nCount = pConnection->Errors->Count; 
 // Collection ranges from 0 to nCount -1. 
 for(long i = 0; i < nCount; i++) 
 { 
 pErr = pConnection->Errors->GetItem(i); 
 printf("Error number: %x\t%s\n", pErr->Number, 
 (LPCSTR) pErr->Description); 
 } 
 } 
} 
 
////////////////////////////////////////////////////////// 
// // 
// PrintComError Function // 
// // 
////////////////////////////////////////////////////////// 
void PrintComError(_com_error &e) 
{ 
 _bstr_t bstrSource(e.Source()); 
 _bstr_t bstrDescription(e.Description()); 
 
 // Print Com errors. 
 printf("Error\n"); 
 printf("\tCode = %08lx\n", e.Error()); 
 printf("\tCode meaning = %s\n", e.ErrorMessage()); 
 printf("\tSource = %s\n", (LPCSTR) bstrSource); 
 printf("\tDescription = %s\n", (LPCSTR) bstrDescription); 
} 
// EndValueCpp 
```

