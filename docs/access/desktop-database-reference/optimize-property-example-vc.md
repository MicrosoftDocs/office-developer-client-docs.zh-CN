---
title: Optimize 属性示例 (VC++)
TOCTitle: Optimize property example (VC++)
ms:assetid: f9e83365-93b2-3eb6-0347-8f8aec703d6f
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250273(v=office.15)
ms:contentKeyID: 48548825
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 7e4e595aea68b35ec6fec1515c5d80e5b721b891
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25885064"
---
# <a name="optimize-property-example-vc"></a>Optimize 属性示例 (VC++)


**适用于**： Access 2013、 Office 2013

本示例演示 [Field](field-object-ado.md) 对象动态 Optimize 属性。 ***Pubs***数据库中的***作者***表的***zip***字段不编制索引。 对***zip***字段[Optimize](optimize-property-dynamic-ado.md)属性设置为**True**授权 ADO 建立索引的提高性能的[Find](find-method-ado.md)方法。

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

