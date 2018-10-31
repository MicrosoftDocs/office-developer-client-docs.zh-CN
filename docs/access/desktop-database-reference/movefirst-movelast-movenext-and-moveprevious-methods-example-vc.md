---
title: MoveFirst、MoveLast、MoveNext 和 MovePrevious 方法示例 (VC++)
TOCTitle: MoveFirst, MoveLast, MoveNext, and MovePrevious methods example (VC++)
ms:assetid: c4abacfa-724a-dbfd-5bdd-0e34e45093d7
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249962(v=office.15)
ms:contentKeyID: 48547596
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 2fb858e7e763cb5118e8e64af87f98fc66c6b13e
ms.sourcegitcommit: 801b1b54786f7b0e5b0d35466e7ae8d1e840b26f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25862137"
---
# <a name="movefirst-movelast-movenext-and-moveprevious-methods-example-vc"></a><span data-ttu-id="710d6-102">MoveFirst、MoveLast、MoveNext 和 MovePrevious 方法示例 (VC++)</span><span class="sxs-lookup"><span data-stu-id="710d6-102">MoveFirst, MoveLast, MoveNext, and MovePrevious methods example (VC++)</span></span>


<span data-ttu-id="710d6-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="710d6-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="710d6-p101">本示例使用 [MoveFirst](movefirst-movelast-movenext-and-moveprevious-methods-ado.md)、[MoveLast](movefirst-movelast-movenext-and-moveprevious-methods-ado.md)、[MoveNext](movefirst-movelast-movenext-and-moveprevious-methods-ado.md) 和 [MovePrevious](movefirst-movelast-movenext-and-moveprevious-methods-ado.md) 方法基于提供的命令移动 [Recordset](recordset-object-ado.md) 的记录指针。若要使该过程运行，需要 MoveAny 函数。</span><span class="sxs-lookup"><span data-stu-id="710d6-p101">This example uses the [MoveFirst](movefirst-movelast-movenext-and-moveprevious-methods-ado.md), [MoveLast](movefirst-movelast-movenext-and-moveprevious-methods-ado.md), [MoveNext](movefirst-movelast-movenext-and-moveprevious-methods-ado.md), and [MovePrevious](movefirst-movelast-movenext-and-moveprevious-methods-ado.md) methods to move the record pointer of a [Recordset](recordset-object-ado.md) based on the supplied command. The MoveAny function is required for this example to run.</span></span>

```cpp 
 
// BeginMoveFirstCpp 
#include <ole2.h> 
#include <stdio.h> 
 
#import "c:\Program Files\Common Files\System\ADO\msado15.dll" no_namespace rename("EOF", "EndOfFile") 
 
// Function declarations 
inline void TESTHR(HRESULT x) {if FAILED(x) _com_issue_error(x);}; 
void MoveFirstX(); 
void MoveAny(int intChoice, _RecordsetPtr pRstTemp); 
void PrintProviderError(_ConnectionPtr pConnection); 
void PrintComError(_com_error &e); 
 
///////////////////////////////// 
// Main Function // 
///////////////////////////////// 
 
void main() 
{ 
 if(FAILED(::CoInitialize(NULL))) 
 return; 
 
 MoveFirstX(); 
 
 ::CoUninitialize(); 
} 
 
////////////////////////////////////// 
// MoveFirstX Function // 
////////////////////////////////////// 
 
void MoveFirstX() 
{ 
 HRESULT hr = S_OK; 
 _RecordsetPtr pRstAuthors = NULL; 
 _bstr_t strCnn("Provider='sqloledb';Data Source='MySqlServer';" 
 "Initial Catalog='pubs';Integrated Security='SSPI';"); 
 _bstr_t strMessage("UPDATE Titles SET Type = " 
 "'psychology' WHERE Type = 'self_help'"); 
 int intCommand = 0; 
 
 // Temporary string variable for type conversion for printing. 
 _bstr_t bstrFName; 
 _bstr_t bstrLName; 
 
 try 
 { 
 // Open recordset from Authors table. 
 TESTHR(pRstAuthors.CreateInstance(__uuidof(Recordset))); 
 pRstAuthors->CursorType = adOpenStatic; 
 
 // Use client cursor to enable AbsolutePosition property. 
 pRstAuthors->CursorLocation = adUseClient; 
 pRstAuthors->Open("Authors", strCnn, adOpenStatic, 
 adLockBatchOptimistic, adCmdTable); 
 
 // Show current record information and get user's method choice. 
 while (true) // Continuous loop. 
 { 
 // Convert variant string to convertable string type. 
 bstrFName = pRstAuthors->Fields->Item["au_fName"]->Value; 
 bstrLName = pRstAuthors->Fields->Item["au_lName"]->Value; 
 
 printf("Name: %s %s\n Record %d of %d\n\n", 
 (LPCSTR) bstrFName, 
 (LPCSTR) bstrLName, 
 pRstAuthors->AbsolutePosition, 
 pRstAuthors->RecordCount); 
 printf("[1 - MoveFirst, 2 - MoveLast, \n"); 
 printf(" 3 - MoveNext, 4 - MovePrevious, 5 - Quit]\n"); 
 
 scanf("%d", &intCommand); 
 
 if ((intCommand < 1) || (intCommand > 4)) 
 break; // Out of range entry exits program loop. 
 
 // Call method based on user's input. 
 MoveAny(intCommand, pRstAuthors); 
 } 
 } 
 catch (_com_error &e) 
 { 
 // Notify the user of errors if any. 
 // Pass a connection pointer accessed from the Recordset. 
 _variant_t vtConnect = pRstAuthors->GetActiveConnection(); 
 
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
 if (pRstAuthors) 
 if (pRstAuthors->State == adStateOpen) 
 pRstAuthors->Close(); 
} 
 
///////////////////////////////// 
// MoveAny Function // 
///////////////////////////////// 
 
void MoveAny(int intChoice, _RecordsetPtr pRstTemp) 
{ 
 // Use specified method, trapping for BOF and EOF 
 try 
 { 
 switch(intChoice) 
 { 
 case 1: 
 pRstTemp->MoveFirst(); 
 break; 
 case 2: 
 pRstTemp->MoveLast(); 
 break; 
 case 3: 
 pRstTemp->MoveNext(); 
 if (pRstTemp->EndOfFile) 
 { 
 printf("\nAlready at end of recordset!\n"); 
 pRstTemp->MoveLast(); 
 } //End If 
 break; 
 case 4: 
 pRstTemp->MovePrevious(); 
 if (pRstTemp->BOF) 
 { 
 printf("\nAlready at beginning of recordset!\n"); 
 pRstTemp->MoveFirst(); 
 } 
 break; 
 default: 
 ; 
 } 
 } 
 
 catch(_com_error &e) 
 { 
 // Notify the user of errors if any. 
 // Pass a connection pointer accessed from the Recordset. 
 _variant_t vtConnect = pRstTemp->GetActiveConnection(); 
 
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
} 
 
//////////////////////////////////////////// 
// PrintProviderError Function // 
//////////////////////////////////////////// 
 
void PrintProviderError(_ConnectionPtr pConnection) 
{ 
 // Print Provider Errors from Connection object. 
 
 // pErr is a record object in the Connection's Error collection. 
 ErrorPtr pErr = NULL; 
 
 if( (pConnection->Errors->Count) > 0) 
 { 
 long nCount = pConnection->Errors->Count; 
 // Collection ranges from 0 to nCount - 1. 
 for(long i = 0; i < nCount; i++) 
 { 
 pErr = pConnection->Errors->GetItem(i); 
 printf("\t Error number: %x\t%s", pErr->Number, 
 pErr->Description); 
 } 
 } 
} 
 
////////////////////////////////////// 
// PrintComError Function // 
////////////////////////////////////// 
 
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
// EndMoveFirstCpp 
```

