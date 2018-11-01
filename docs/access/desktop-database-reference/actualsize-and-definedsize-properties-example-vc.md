---
title: ActualSize 和 DefinedSize 属性示例 (VC++)
TOCTitle: ActualSize and DefinedSize properties example (VC++)
ms:assetid: 90b7a53f-c9b1-f3c1-f769-e6a340c90eba
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249638(v=office.15)
ms:contentKeyID: 48546328
ms.date: 10/16/2018
mtps_version: v=office.15
ms.openlocfilehash: 795d07827be74a5eff335483550d22bf3e9bd899
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25870616"
---
# <a name="actualsize-and-definedsize-properties-example-vc"></a><span data-ttu-id="935e2-102">ActualSize 和 DefinedSize 属性示例 (VC++)</span><span class="sxs-lookup"><span data-stu-id="935e2-102">ActualSize and DefinedSize properties example (VC++)</span></span>


<span data-ttu-id="935e2-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="935e2-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="935e2-104">此示例使用 [ActualSize](actualsize-property-ado.md) 和 [DefinedSize](definedsize-property-ado.md) 属性来显示字段的定义大小和实际大小。</span><span class="sxs-lookup"><span data-stu-id="935e2-104">This example uses the [ActualSize](actualsize-property-ado.md) and [DefinedSize](definedsize-property-ado.md) properties to display the defined size and actual size of a field.</span></span>

```cpp 
 
// BeginActualSizeCpp 
#import "C:\Program Files\Common Files\System\ADO\msado15.dll" no_namespace rename("EOF", "EndOfFile") 
 
#include <ole2.h> 
#include <stdio.h> 
#include "conio.h" 
 
//Function declarations 
inline void TESTHR(HRESULT x) {if FAILED(x) _com_issue_error(x);}; 
void ActualSizeX(VOID); 
void PrintProviderError(_ConnectionPtr pConnection); 
 
/////////////////////////////////////////////////////////// 
// // 
// Main Function // 
// // 
/////////////////////////////////////////////////////////// 
void main() 
{ 
 if(FAILED(::CoInitialize(NULL))) 
 return; 
 ActualSizeX(); 
 ::CoUninitialize(); 
} 
 
/////////////////////////////////////////////////////////// 
// // 
// ActualSizeX Function // 
// // 
/////////////////////////////////////////////////////////// 
VOID ActualSizeX(VOID) 
{ 
 HRESULT hr = S_OK; 
 
 // Define ADO object pointers. 
 // Initialize pointers on define. 
 // These are in the ADODB:: namespace. 
 _RecordsetPtr pRstStores = NULL; 
 
 //Define Other variables 
 _bstr_t strMessage; 
 _bstr_t strCnn("Provider='sqloledb';Data Source='MySqlServer';" 
 "Initial Catalog='pubs';Integrated Security='SSPI';"); 
 
 try 
 { 
 //Open a recordset for the stores table. 
 TESTHR(pRstStores.CreateInstance(__uuidof(Recordset))); 
 
 //You have to explicitly pass the Cursor type and LockType 
 //to the Recordset here. 
 hr = pRstStores->Open("stores", 
 strCnn,adOpenForwardOnly,adLockReadOnly,adCmdTable); 
 
 //Loop through the recordset displaying the contents 
 //of the stor_name field, the field's defined size, 
 //and its actual size. 
 
 pRstStores->MoveFirst(); 
 
 while(!(pRstStores->EndOfFile)) 
 { 
 strMessage = "Store Name: "; 
 strMessage += (_bstr_t)pRstStores->Fields-> 
 Item["stor_name"]->Value + "\n"; 
 strMessage += "Defined Size: "; 
 strMessage += (_bstr_t)pRstStores->Fields-> 
 Item["stor_name"]->DefinedSize + "\n"; 
 strMessage += "Actual Size: "; 
 strMessage += (_bstr_t) pRstStores->Fields-> 
 Item["stor_name"]->ActualSize + "\n"; 
 
 printf("%s\n",(LPCSTR)strMessage); 
 printf("Press any key to continue..."); 
 getch(); 
 //Clear the screen for the next display 
 system("cls"); 
 pRstStores->MoveNext(); 
 } 
 } 
 catch(_com_error &e) 
 { 
 _variant_t vtConnect = pRstStores->GetActiveConnection(); 
 
 // GetActiveConnection returns connect string if connection 
 // is not open, else returns Connection object. 
 switch(vtConnect.vt) 
 { 
 case VT_BSTR: 
 printf("Error:\n"); 
 printf("Code = %08lx\n", e.Error()); 
 printf("Message = %s\n", e.ErrorMessage()); 
 printf("Source = %s\n", (LPCSTR) e.Source()); 
 printf("Description = %s\n", (LPCSTR) e.Description()); 
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
 if (pRstStores) 
 if (pRstStores->State == adStateOpen) 
 pRstStores->Close(); 
} 
 
/////////////////////////////////////////////////////////// 
// // 
// PrintProviderError Function // 
// // 
/////////////////////////////////////////////////////////// 
 
VOID PrintProviderError(_ConnectionPtr pConnection) 
{ 
 // Print Provider Errors from Connection object. 
 // pErr is a record object in the Connection's Error collection. 
 ErrorPtr pErr = NULL; 
 long nCount = 0; 
 long i = 0; 
 
 if( (pConnection->Errors->Count) > 0) 
 { 
 nCount = pConnection->Errors->Count; 
 // Collection ranges from 0 to nCount -1. 
 for(i = 0; i < nCount; i++) 
 { 
 pErr = pConnection->Errors->GetItem(i); 
 printf("\t Error number: %x\t%s", pErr->Number,(LPCSTR ) pErr->Description); 
 } 
 } 
} 
// EndActualSizeCpp 
```

