---
title: NextRecordset 方法示例 (VC++)
TOCTitle: NextRecordset method example (VC++)
ms:assetid: e11feba0-07d2-3c6a-c5cd-b8712a02a6a1
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250143(v=office.15)
ms:contentKeyID: 48548252
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: fb51b22dd07c40c55a3e773cc186b14e527bd98c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32288579"
---
# <a name="nextrecordset-method-example-vc"></a><span data-ttu-id="a967a-102">NextRecordset 方法示例 (VC++)</span><span class="sxs-lookup"><span data-stu-id="a967a-102">NextRecordset method example (VC++)</span></span>


<span data-ttu-id="a967a-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="a967a-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="a967a-104">本示例使用 [NextRecordset](nextrecordset-method-ado.md) 方法来查看记录集中的数据，该方法使用由三个单独的 **SELECT** 语句构成的复合命令语句。</span><span class="sxs-lookup"><span data-stu-id="a967a-104">This example uses the [NextRecordset](nextrecordset-method-ado.md) method to view the data in a recordset that uses a compound command statement made up of three separate **SELECT** statements.</span></span>

```cpp 
 
// BeginNextRecordsetCpp 
#import "C:\Program Files\Common Files\System\ADO\msado15.dll" no_namespace rename("EOF", "EndOfFile") 
 
#include <stdio.h> 
#include <ole2.h> 
#include <conio.h> 
#include <stdlib.h> 
 
//Function Declaration. 
inline void TESTHR(HRESULT x) {if FAILED(x) _com_issue_error(x);}; 
void NextRecordsetX(void); 
void PrintProviderError(_ConnectionPtr pConnection); 
void PrintComError(_com_error &e); 
 
/////////////////////////////////////////////////////////// 
// // 
// Main Function // 
// // 
/////////////////////////////////////////////////////////// 
void main() 
{ 
 if(FAILED(::CoInitialize(NULL))) 
 return; 
 
 NextRecordsetX(); 
 
 ::CoUninitialize(); 
} 
 
////////////////////////////////////////////////// 
// // 
// NextRecordsetX Function // 
// // 
////////////////////////////////////////////////// 
 
void NextRecordsetX(void) 
{ 
 // Define ADO object pointers. 
 // Initialize pointers on define. 
 // These are in the ADODB:: namespace. 
 _RecordsetPtr pRstCompound = NULL; 
 
 // Define Other Variables 
 HRESULT hr = S_OK; 
 _variant_t index; 
 index.vt = VT_I2; 
 
 // Assign connection string to a variable. 
 _bstr_t strCnn("Provider='sqloledb';Data Source='MySqlServer';" 
 "Initial Catalog='pubs';Integrated Security='SSPI';"); 
 
 try 
 { 
 // Open recordset from Authors table. 
 TESTHR(pRstCompound.CreateInstance(__uuidof(Recordset))); 
 
 // Pass the Cursor type and Lock type to the Recordset. 
 pRstCompound->Open("SELECT * FROM authors; SELECT * FROM stores;" 
 "SELECT * FROM jobs", strCnn, adOpenForwardOnly, 
 adLockReadOnly, adCmdText); 
 
 // Display results from each SELECT statement. 
 int intCount = 1; 
 while(!(pRstCompound==NULL)) 
 { 
 printf("\n\nContents of recordset #%d\n", intCount); 
 
 while(!pRstCompound->EndOfFile) 
 { 
 index.iVal = 0; 
 printf("%s\t", (LPCSTR)(_bstr_t)pRstCompound-> GetFields()->GetItem(& index)->Value); 
 index.iVal = 1; 
 printf("%s\n", (LPCSTR)(_bstr_t)pRstCompound-> Fields->GetItem(& index)->Value); 
 
 pRstCompound->MoveNext(); 
 
 int intLine = intLine + 1; 
 if (intLine % 22 == 0) 
 { 
 printf("\nPress any key to continue..."); 
 getch(); 
 
 //Clear the screen for the next display. 
 system("cls"); 
 } 
 } 
 long lngRec = 0; 
 pRstCompound = pRstCompound-> 
 NextRecordset((VARIANT *)lngRec); 
 
 printf("\nPress any key to continue..."); 
 getch(); 
 intCount = intCount + 1; 
 } 
 } 
 catch(_com_error &e) 
 { 
 // Notify the user of errors if any. 
 // Pass a connection pointer accessed from the Recordset. 
 _variant_t vtConnect = pRstCompound->GetActiveConnection(); 
 
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
 if (pRstCompound) 
 if (pRstCompound->State == adStateOpen) 
 pRstCompound->Close(); 
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
 for(long i = 0; i < nCount; i++) 
 { 
 pErr = pConnection->Errors->GetItem(i); 
 printf("\t Error number: %x\t%s", pErr->Number, 
 (LPCSTR) pErr->Description); 
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
 
 // Print Com errors. 
 printf("Error\n"); 
 printf("\tCode = %08lx\n", e.Error()); 
 printf("\tCode meaning = %s\n", e.ErrorMessage()); 
 printf("\tSource = %s\n", (LPCSTR) bstrSource); 
 printf("\tDescription = %s\n", (LPCSTR) bstrDescription); 
} 
// EndNextRecordsetCpp 
```

