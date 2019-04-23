---
title: ActiveCommand 属性示例 (VC++)
TOCTitle: ActiveCommand property example (VC++)
ms:assetid: 35ebe533-73bb-0fe5-ef94-973e124b25cd
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249118(v=office.15)
ms:contentKeyID: 48544157
ms.date: 10/17/2018
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 11e7cecc48ea8908b3784796416dfc3a4af95cdf
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32280675"
---
# <a name="activecommand-property-example-vc"></a><span data-ttu-id="257c4-102">ActiveCommand 属性示例 (VC++)</span><span class="sxs-lookup"><span data-stu-id="257c4-102">ActiveCommand property example (VC++)</span></span>

<span data-ttu-id="257c4-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="257c4-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="257c4-104">此示例演示 [ActiveCommand](activecommand-property-ado.md) 属性。</span><span class="sxs-lookup"><span data-stu-id="257c4-104">This example demonstrates the [ActiveCommand](activecommand-property-ado.md) property.</span></span>

<span data-ttu-id="257c4-105">将向子例程提供一个 [Recordset](recordset-object-ado.md) 对象，该对象的 **ActiveCommand** 属性用于显示创建 **Recordset** 的命令文本和参数。</span><span class="sxs-lookup"><span data-stu-id="257c4-105">A subroutine is given a [Recordset](recordset-object-ado.md) object whose **ActiveCommand** property is used to display the command text and parameter that created the **Recordset**.</span></span>

```cpp 
 
// BeginActiveCommandCpp 
#import "C:\Program Files\Common Files\System\ADO\msado15.dll" no_namespace rename("EOF", "EndOfFile") 
 
 
#include <ole2.h> 
#include <stdio.h> 
#include <conio.h> 
#include "ActiveCommandX.h" 
 
// Function declarations 
inline void TESTHR(HRESULT x) {if FAILED(x) _com_issue_error(x);}; 
void ActiveCommandX(void); 
void ActiveCommandXprint(_RecordsetPtr pRst); 
void PrintProviderError(_ConnectionPtr pConnection); 
void PrintComError(_com_error &e); 
inline char* mygets(char* strDest, int n) 
{ 
 char strExBuff[10]; 
 char* pstrRet = fgets(strDest, n, stdin); 
 
 if (pstrRet == NULL) 
 return NULL; 
 
 if (!strrchr(strDest, '\n')) 
 // Exhaust the input buffer. 
 do 
 { 
 fgets(strExBuff, sizeof(strExBuff), stdin); 
 }while (!strrchr(strExBuff, '\n')); 
 else 
 // Replace '\n' with '\0' 
 strDest[strrchr(strDest, '\n') - strDest] = '\0'; 
 
 return pstrRet; 
} 
 
////////////////////////////////////////////////////////// 
// // 
// Main Function // 
// // 
////////////////////////////////////////////////////////// 
 
void main() 
{ 
 if(FAILED(::CoInitialize(NULL))) 
 return; 
 
 ActiveCommandX(); 
 
 ::CoUninitialize(); 
} 
 
////////////////////////////////////////////////////////// 
// // 
// ActiveCommandX Function // 
// // 
////////////////////////////////////////////////////////// 
 
void ActiveCommandX(void) 
{ 
 
 HRESULT hr = S_OK; 
 
 // Define ADO object pointers. 
 // Initialize pointers on define. 
 // These are in the ADODB:: namespace. 
 _ConnectionPtr pConnection = NULL; 
 _CommandPtr pCmd = NULL; 
 _RecordsetPtr pRstAuthors = NULL; 
 
 //Definitions of other variables 
 _bstr_t strCnn("Provider='sqloledb';Data Source='MySqlServer';" 
 "Initial Catalog='pubs';Integrated Security='SSPI';"); 
 _bstr_t strPrompt; 
 _bstr_t strName; 
 CHAR strcharName[50]; 
 
 
 try 
 { 
 // Open connection. 
 TESTHR(pConnection.CreateInstance(__uuidof(Connection))); 
 
 TESTHR(pRstAuthors.CreateInstance(__uuidof(Recordset))); 
 
 TESTHR(pCmd.CreateInstance(__uuidof(Command))); 
 
 printf ("ActiveCommandX Example\n\n"); 
 strPrompt = "Enter an author's name (e.g., Ringer): "; 
 printf(strPrompt); 
 mygets(strcharName, 50); 
 char *tempStr = strtok(strcharName, " \t"); 
 strName = tempStr; 
 
 pCmd->CommandText = "SELECT * FROM authors WHERE au_lname = ?"; 
 pCmd->Parameters->Append(pCmd->CreateParameter("LastName", adChar, adParamInput, 20, strName)); 
 
 pConnection->Open (strCnn, "", "", adConnectUnspecified); 
 
 pCmd->PutActiveConnection(_variant_t((IDispatch*)pConnection)); 
 
 pRstAuthors = pCmd->Execute(NULL,NULL,adCmdText); 
 
 ActiveCommandXprint(pRstAuthors); 
 
 } // End Try statement. 
 catch(_com_error &e) 
 { 
 // Notify the user of errors if any. 
 // Pass a connection pointer accessed from the Recordset. 
 PrintProviderError(pConnection); 
 PrintComError(e); 
 } 
 
 // Clean up objects before exit. 
 if (pRstAuthors) 
 if (pRstAuthors->State == adStateOpen) 
 pRstAuthors->Close(); 
 if (pConnection) 
 if (pConnection->State == adStateOpen) 
 pConnection->Close(); 
} 
 
 
////////////////////////////////////////////////////////// 
// // 
// ActiveCommandXprint Function // 
// // 
////////////////////////////////////////////////////////// 
 
void ActiveCommandXprint(_RecordsetPtr pRst = NULL) 
{ 
 // Varible Declaraion & initialization 
 IADORecordBinding *picRs = NULL; //Interface Pointer declared. 
 CAuthorsRs autrs; //C++ class object 
 _bstr_t strName; 
 
 //Open an IADORecordBinding interface pointer which 
 //we'll use for Binding Recordset to a class 
 TESTHR(pRst->QueryInterface(__uuidof(IADORecordBinding),(LPVOID*)&picRs)); 
 
 //Bind the Recordset to a C++ Class here 
 TESTHR(picRs->BindToRecordset(&autrs)); 
 
 strName = ((_CommandPtr)pRst->GetActiveCommand())->GetParameters()->GetItem("LastName")->Value; 
 printf("Command text = '%s'\n", (LPCSTR)((_CommandPtr)pRst->GetActiveCommand())->CommandText); 
 printf("Parameter = '%s'\n", (LPCSTR)strName); 
 
 if (pRst->BOF) 
 printf("Name = '%s'not found.", (LPCSTR)strName); 
 else 
 { 
 printf ("Name = '%s %s' author ID = '%s'", 
 autrs.lau_fnameStatus == adFldOK ? autrs.m_au_fname : "<NULL>", 
 autrs.lau_lnameStatus == adFldOK ? autrs.m_au_lname : "<NULL>", 
 autrs.lau_idStatus == adFldOK ? autrs.m_au_id : "<NULL>"); 
 } 
 
 //Release IADORecordset Interface 
 if (picRs) 
 picRs->Release(); 
 
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
 long nCount = 0; 
 long i = 0; 
 
 if( (pConnection->Errors->Count) > 0) 
 { 
 nCount = pConnection->Errors->Count; 
 // Collection ranges from 0 to nCount -1. 
 for(i = 0; i < nCount; i++) 
 { 
 pErr = pConnection->Errors->GetItem(i); 
 printf("\t Error number: %x\t%s\n", pErr->Number, (LPCSTR)pErr->Description); 
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
// EndActiveCommandCpp 
 
ActiveCommandX.h 
// BeginActiveCommandH 
#include "icrsint.h" 
 
 
// This Class extracts id, fname, lname from authors table. 
 
class CAuthorsRs : public CADORecordBinding 
{ 
BEGIN_ADO_BINDING(CAuthorsRs) 
 
 // Column au_id is the 1st field in the recordset 
 ADO_VARIABLE_LENGTH_ENTRY2(1, adVarChar, m_au_id, 
 sizeof(m_au_id), lau_idStatus, TRUE) 
 
 // Column au_fname is the 2nd field in the recordset 
 ADO_VARIABLE_LENGTH_ENTRY2(2, adVarChar, m_au_fname, 
 sizeof(m_au_fname), lau_fnameStatus, TRUE) 
 
 // Column au_lname is the 3rd field in the recordset 
 ADO_VARIABLE_LENGTH_ENTRY2(3, adVarChar, m_au_lname, 
 sizeof(m_au_lname), lau_lnameStatus, TRUE) 
 
END_ADO_BINDING() 
 
public: 
 
 char m_au_id[21]; 
 ULONG lau_idStatus; 
 char m_au_fname[41]; 
 ULONG lau_fnameStatus; 
 char m_au_lname[41]; 
 ULONG lau_lnameStatus; 
 
}; 
// EndActiveCommandH 
```

