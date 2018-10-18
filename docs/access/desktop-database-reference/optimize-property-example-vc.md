---
<span data-ttu-id="5b335-101"><<<<<<< 标头标题： 优化属性示例 （VC + +） TOCTitle： 优化属性示例 （VC + +） === 标题： Optimize 属性示例 （VC + +） TOCTitle: Optimize 属性示例 （VC + +）</span><span class="sxs-lookup"><span data-stu-id="5b335-101"><<<<<<< HEAD title: Optimize Property Example (VC++) TOCTitle: Optimize Property Example (VC++) ======= title: Optimize property example (VC++) TOCTitle: Optimize property example (VC++)</span></span>
>>>>>>> <span data-ttu-id="5b335-102">母版页 ms:assetid: f9e83365-93b2-3eb6-0347-8f8aec703d6f ms:mtpsurl: https://msdn.microsoft.com/library/JJ250273(v=office.15) ms:contentKeyID: 48548825 ms.date: 09/18/2015 mtps_version: office.15.aspx</span><span class="sxs-lookup"><span data-stu-id="5b335-102">master ms:assetid: f9e83365-93b2-3eb6-0347-8f8aec703d6f ms:mtpsurl: https://msdn.microsoft.com/library/JJ250273(v=office.15) ms:contentKeyID: 48548825 ms.date: 09/18/2015 mtps_version: v=office.15</span></span>
---

<span data-ttu-id="5b335-103"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="5b335-103"><<<<<<< HEAD</span></span>
# <a name="optimize-property-example-vc"></a><span data-ttu-id="5b335-104">Optimize 属性示例 (VC++)</span><span class="sxs-lookup"><span data-stu-id="5b335-104">Optimize Property Example (VC++)</span></span>
=======
# <a name="optimize-property-example-vc"></a><span data-ttu-id="5b335-105">Optimize 属性示例 （VC + +）</span><span class="sxs-lookup"><span data-stu-id="5b335-105">Optimize property example (VC++)</span></span>
>>>>>>> <span data-ttu-id="5b335-106">master</span><span class="sxs-lookup"><span data-stu-id="5b335-106">master</span></span>


<span data-ttu-id="5b335-107">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="5b335-107">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="5b335-108">本示例演示 [Field](field-object-ado.md) 对象动态 Optimize 属性。</span><span class="sxs-lookup"><span data-stu-id="5b335-108">This example demonstrates the [Field](field-object-ado.md) object dynamic Optimize property.</span></span> <span data-ttu-id="5b335-109">***Pubs***数据库中的***作者***表的***zip***字段不编制索引。</span><span class="sxs-lookup"><span data-stu-id="5b335-109">The ***zip*** field of the ***Authors*** table in the ***Pubs*** database is not indexed.</span></span> <span data-ttu-id="5b335-110">对***zip***字段[Optimize](optimize-property-dynamic-ado.md)属性设置为**True**授权 ADO 建立索引的提高性能的[Find](find-method-ado.md)方法。</span><span class="sxs-lookup"><span data-stu-id="5b335-110">Setting the [Optimize](optimize-property-dynamic-ado.md) property to **True** on the ***zip*** field authorizes ADO to build an index that improves the performance of the [Find](find-method-ado.md) method.</span></span>

```cpp 
 
// BeginOptimizeCpp 
#import "c:\Program Files\Common Files\System\ADO\msado15.dll" no_namespace rename("EOF", "EndOfFile") 
 
#include <ole2.h> 
#include <stdio.h> 
#include <conio.h> 
 
// Function declarations 
inline void TESTHR(HRESULT x) {if FAILED(x) _com_issue_error(x);}; 
void OptimizeX(void); 
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
 
 OptimizeX(); 
 
 ::CoUninitialize(); 
} 
 
////////////////////////////////////////////////////////// 
// // 
// OptimizeX Function // 
// // 
////////////////////////////////////////////////////////// 
void OptimizeX(void) 
{ 
 HRESULT hr = S_OK; 
 
 // Define string variables. 
 _bstr_t strCnn("Provider='sqloledb';Data Source='MySqlServer';" 
 "Initial Catalog='pubs';Integrated Security='SSPI';"); 
 // Define ADO object pointers. 
 // Initialize pointers on define. 
 // These are in the ADODB:: namespace. 
 _RecordsetPtr pRst = NULL; 
 
 try 
 { 
 TESTHR(pRst.CreateInstance(__uuidof(Recordset))); 
 
 // Enable Index creation. 
 pRst->CursorLocation = adUseClient; 
 pRst->Open ("SELECT * FROM authors", strCnn, 
 adOpenStatic, adLockReadOnly, adCmdText); 
 
 // Create the index 
 pRst->Fields->GetItem("zip")->Properties-> 
 GetItem("Optimize")->PutValue("True"); 
 
 // Find Akiko Yokomoto 
 pRst->Find("zip = '94595'",1,adSearchForward); 
 printf("\n%s %s %s %s %s\n", 
 (LPSTR) (_bstr_t) pRst->Fields->GetItem("au_fname")->Value, 
 (LPSTR) (_bstr_t) pRst->Fields->GetItem("au_lname")->Value, 
 (LPSTR) (_bstr_t) pRst->Fields->GetItem("address")->Value, 
 (LPSTR) (_bstr_t) pRst->Fields->GetItem("city")->Value, 
 (LPSTR) (_bstr_t) pRst->Fields->GetItem("state")->Value); 
 
 // Delete the index 
 pRst->Fields->GetItem("zip")->Properties-> 
 GetItem("Optimize")->PutValue("False"); 
 } 
 catch (_com_error &e) 
 { 
 // Notify the user of errors if any. 
 // Pass a connection pointer accessed from the Recordset. 
 _variant_t vtConnect = pRst->GetActiveConnection(); 
 
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
 
 // Clean up objects before exit. 
 if (pRst) 
 if (pRst->State == adStateOpen) 
 pRst->Close(); 
} 
 
/////////////////////////////////////////////////////////// 
// // 
// PrintProviderError Function // 
// // 
/////////////////////////////////////////////////////////// 
void PrintProviderError(_ConnectionPtr pConnection) 
{ 
 // Print Provider Errors from Connection object. 
 // pErr is a record object in the Connection's Error collection. 
 ErrorPtr pErr = NULL; 
 
 if( (pConnection->Errors->Count) > 0) 
 { 
 long nCount = pConnection->Errors->Count; 
 
 // Collection ranges from 0 to nCount -1. 
 for(long i = 0;i < nCount;i++) 
 { 
 pErr = pConnection->Errors->GetItem(i); 
 printf("\t Error number: %x\t%s", pErr->Number, 
 pErr->Description); 
 } 
 } 
} 
 
/////////////////////////////////////////////////////////// 
// // 
// PrintComError Function // 
// // 
/////////////////////////////////////////////////////////// 
void PrintComError(_com_error &e) 
{ 
 _bstr_t bstrSource(e.Source()); 
 _bstr_t bstrDescription(e.Description()); 
 
 // Print COM errors. 
 printf("Error\n"); 
 printf("\tCode = %08lx\n", e.Error()); 
 printf("\tCode meaning = %s\n", e.ErrorMessage()); 
 printf("\tSource = %s\n", (LPCSTR) bstrSource); 
 printf("\tDescription = %s\n", (LPCSTR) bstrDescription); 
} 
// EndOptimizeCpp 
```

