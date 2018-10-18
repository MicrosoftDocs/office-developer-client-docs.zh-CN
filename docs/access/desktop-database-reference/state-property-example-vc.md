---
<span data-ttu-id="c645f-101"><<<<<<< 标头标题： State 属性示例 （VC + +） TOCTitle: State 属性示例 （VC + +） === 标题： State 属性示例 （VC + +） TOCTitle: State 属性示例 （VC + +）</span><span class="sxs-lookup"><span data-stu-id="c645f-101"><<<<<<< HEAD title: State Property Example (VC++) TOCTitle: State Property Example (VC++) ======= title: State property example (VC++) TOCTitle: State property example (VC++)</span></span>
>>>>>>> <span data-ttu-id="c645f-102">母版页 ms:assetid: aedc50d8-81cd-1acd-6d57-48af71369da8 ms:mtpsurl: https://msdn.microsoft.com/library/JJ249830(v=office.15) ms:contentKeyID: 48547085 ms.date: 09/18/2015 mtps_version: office.15.aspx</span><span class="sxs-lookup"><span data-stu-id="c645f-102">master ms:assetid: aedc50d8-81cd-1acd-6d57-48af71369da8 ms:mtpsurl: https://msdn.microsoft.com/library/JJ249830(v=office.15) ms:contentKeyID: 48547085 ms.date: 09/18/2015 mtps_version: v=office.15</span></span>
---

<span data-ttu-id="c645f-103"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="c645f-103"><<<<<<< HEAD</span></span>
# <a name="state-property-example-vc"></a><span data-ttu-id="c645f-104">State 属性示例 (VC++)</span><span class="sxs-lookup"><span data-stu-id="c645f-104">State Property Example (VC++)</span></span>
=======
# <a name="state-property-example-vc"></a><span data-ttu-id="c645f-105">State 属性示例 （VC + +）</span><span class="sxs-lookup"><span data-stu-id="c645f-105">State property example (VC++)</span></span>
>>>>>>> <span data-ttu-id="c645f-106">master</span><span class="sxs-lookup"><span data-stu-id="c645f-106">master</span></span>


<span data-ttu-id="c645f-107">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="c645f-107">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="c645f-108">本示例使用 [State](state-property-ado.md) 属性在异步打开连接和异步执行命令时显示一条消息。</span><span class="sxs-lookup"><span data-stu-id="c645f-108">This example uses the [State](state-property-ado.md) property to display a message while asynchronous connections are opening and asynchronous commands are executing.</span></span>

```cpp 
 
// BeginStateCpp 
#import "c:\Program Files\Common Files\System\ADO\msado15.dll" no_namespace rename("EOF", "EndOfFile") 
 
#include <ole2.h> 
#include <stdio.h> 
#include <conio.h> 
 
// Function declarations 
inline void TESTHR(HRESULT x) {if FAILED(x) _com_issue_error(x);}; 
void StateX(void); 
void PrintProviderError(_ConnectionPtr pConnection); 
void PrintComError(_com_error &e); 
 
/////////////////////////////////////////////// 
// // 
// Main Function // 
// // 
/////////////////////////////////////////////// 
void main() 
{ 
 if(FAILED(::CoInitialize(NULL))) 
 return; 
 
 StateX(); 
 
 ::CoUninitialize(); 
} 
 
/////////////////////////////////////////////// 
// // 
// StateX Function // 
// // 
/////////////////////////////////////////////// 
void StateX(void) 
{ 
 HRESULT hr = S_OK; 
 
 // Define string variables. 
 _bstr_t strSQLChange("UPDATE Titles SET Type = " 
 "'self_help' WHERE Type = 'psychology'"); 
 _bstr_t strSQLRestore("UPDATE Titles SET Type = " 
 "'psychology' WHERE Type = 'self_help'"); 
 _bstr_t strCnn("Provider='sqloledb';Data Source='MySqlServer';" 
 "Initial Catalog='pubs';Integrated Security='SSPI';"); 
 
 // Define ADO object pointers. 
 // Initialize pointers on define. 
 // These are in the ADODB:: namespace. 
 _ConnectionPtr pConnection = NULL; 
 _ConnectionPtr pConnection2 = NULL; 
 _CommandPtr pCmdChange = NULL; 
 _CommandPtr pCmdRestore = NULL; 
 
 try 
 { 
 // Open two asynchronous connections,displaying 
 // a message while connecting. 
 TESTHR(pConnection.CreateInstance(__uuidof(Connection))); 
 TESTHR(pConnection2.CreateInstance(__uuidof(Connection))); 
 
 pConnection->Open (strCnn, "", "", adAsyncConnect); 
 while(pConnection->State == adStateConnecting) 
 { 
 printf("Opening first connection....\n\n"); 
 } 
 
 pConnection2->Open (strCnn, "", "", adAsyncConnect); 
 while(pConnection2->State == adStateConnecting) 
 { 
 printf("Opening second connection....\n\n"); 
 } 
 
 // Create two command objects. 
 TESTHR(pCmdChange.CreateInstance(__uuidof(Command))); 
 pCmdChange->ActiveConnection = pConnection; 
 pCmdChange->CommandText = strSQLChange; 
 
 TESTHR(pCmdRestore.CreateInstance(__uuidof(Command))); 
 pCmdRestore->ActiveConnection = pConnection2; 
 pCmdRestore->CommandText = strSQLRestore; 
 
 // Executing the commands,displaying a message 
 // while they are executing. 
 pCmdChange->Execute(NULL,NULL,adAsyncExecute); 
 while(pCmdChange->State == adStateExecuting) 
 { 
 printf("Change command executing...\n\n"); 
 } 
 
 pCmdRestore->Execute(NULL,NULL,adAsyncExecute); 
 while(pCmdRestore->State == adStateExecuting) 
 { 
 printf("Restore command executing...\n\n"); 
 } 
 } 
 catch (_com_error &e) 
 { 
 // Notify the user of errors if any. 
 PrintProviderError(pConnection); 
 PrintComError(e); 
 } 
 
 if (pConnection) 
 if (pConnection->State == adStateOpen) 
 pConnection->Close(); 
 if (pConnection2) 
 if (pConnection2->State == adStateOpen) 
 pConnection2->Close(); 
} 
 
/////////////////////////////////////////////// 
// // 
// PrintProviderError Function // 
// // 
/////////////////////////////////////////////// 
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
 
/////////////////////////////////////////////// 
// // 
// PrintComError Function // 
// // 
/////////////////////////////////////////////// 
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
// EndStateCpp 
```

