---
title: Save 和 Open 方法示例 (VC++)
TOCTitle: Save and Open methods example (VC++)
ms:assetid: 83e9647e-5dbd-2c59-4fff-2a3df79ab93c
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249574(v=office.15)
ms:contentKeyID: 48546019
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 54fb42ade164ce49cd09ce5a71b342342026a0a2
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28722408"
---
# <a name="save-and-open-methods-example-vc"></a><span data-ttu-id="21fb8-102">Save 和 Open 方法示例 (VC++)</span><span class="sxs-lookup"><span data-stu-id="21fb8-102">Save and Open methods example (VC++)</span></span>


<span data-ttu-id="21fb8-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="21fb8-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="21fb8-104">以下三个示例演示了如何将 [Save](save-method-ado.md) 和 **Open** 方法结合起来使用。</span><span class="sxs-lookup"><span data-stu-id="21fb8-104">These three examples demonstrate how the [Save](save-method-ado.md) and **Open** methods can be used together.</span></span>

<span data-ttu-id="21fb8-p101">假设您正准备出差并希望携带数据库中的某个表。在出发前，您以 [Recordset](recordset-object-ado.md) 的形式访问数据并将其保存在便携表单中。到达目的地后，您将 **Recordset** 作为本地的已断开 **Recordset** 进行访问。您对 **Recordset** 进行更改，然后再次保存它。最后，您回家之后再次连接到数据库，并用出差时所做的更改更新该数据库。</span><span class="sxs-lookup"><span data-stu-id="21fb8-p101">Assume you are going on a business trip and want to take along a table from a database. Before you go, you access the data as a [Recordset](recordset-object-ado.md) and save it in a transportable form. When you arrive at your destination, you access the **Recordset** as a local, disconnected **Recordset**. You make changes to the **Recordset**, then save it again. Finally, when you return home, you connect to the database again and update it with the changes you made on the road.</span></span>

```cpp 
 
// BeginSaveCpp 
#import "c:\Program Files\Common Files\system\ado\msado15.dll" no_namespace rename("EOF", "EndOfFile") 
 
#include <ole2.h> 
#include <stdio.h> 
#include <conio.h> 
#include <io.h> 
 
//Function declarations 
inline void TESTHR(HRESULT x) {if FAILED(x) _com_issue_error(x);}; 
bool FileExists(void); 
void SaveX1(void); 
void SaveX2(void); 
void SaveX3(void); 
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
 
 //If File exists in the specified directory, then display error 
 if (!FileExists()) 
 { 
 SaveX1(); 
 SaveX2(); 
 SaveX3(); 
 } 
 
 ::CoUninitialize(); 
} 
 
////////////////////////////////////////////////////////// 
// // 
// SaveX1 Function // 
// // 
////////////////////////////////////////////////////////// 
 
//First, access and save the authors table. 
void SaveX1() 
{ 
 HRESULT hr = S_OK; 
 
 // Define ADO object pointers. 
 // Initialize pointers on define. 
 // These are in the ADODB:: namespace. 
 _RecordsetPtr pRstAuthors = NULL; 
 
 //Definitions of other variables 
 _bstr_t strCnn("Provider='sqloledb';Data Source='MySqlServer';" 
 "Initial Catalog='pubs';Integrated Security='SSPI';"); 
 
 try 
 { 
 TESTHR(pRstAuthors.CreateInstance(__uuidof(Recordset))); 
 
 pRstAuthors->Open("SELECT * FROM authors",strCnn, 
 adOpenDynamic,adLockBatchOptimistic,adCmdText); 
 
 // For sake of illustration, save the Recordset to a diskette 
 // in XML format. 
 pRstAuthors->Save("c:\\pubs.xml",adPersistXML); 
 } 
 catch(_com_error &e) 
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
 
 if (pRstAuthors) 
 if (pRstAuthors->State == adStateOpen) 
 pRstAuthors->Close(); 
} 
 
////////////////////////////////////////////////////////// 
// // 
// SaveX2 Function // 
// // 
////////////////////////////////////////////////////////// 
//At this point, you have arrived at your destination. 
//You will access the authors table as a local, disconnected Recordset. 
//Don't forget you must have the MSPersist provider on the machine you 
//are using in order to access the saved file, c:\pubs.xml. 
void SaveX2() 
{ 
 HRESULT hr = S_OK; 
 
 // Define ADO object pointers. 
 // Initialize pointers on define. 
 // These are in the ADODB:: namespace. 
 _RecordsetPtr pRstAuthors = NULL; 
 
 try 
 { 
 TESTHR(pRstAuthors.CreateInstance(__uuidof(Recordset))); 
 
 //For sake of illustration, we specify all parameters. 
 pRstAuthors->Open("c:\\pubs.xml","Provider='MSPersist';", 
 adOpenForwardOnly,adLockBatchOptimistic,adCmdFile); 
 
 //Now you have a local, disconnected Recordset. 
 //Edit it as you desire. 
 //(In this example, the change makes no difference). 
 pRstAuthors->Find("au_lname = 'Carson'",NULL,adSearchForward); 
 if (pRstAuthors->EndOfFile) 
 { 
 printf("Name not found ...\n"); 
 pRstAuthors->Close(); 
 return; 
 } 
 pRstAuthors->GetFields()->GetItem("City")->PutValue("Chicago"); 
 pRstAuthors->Update(); 
 
 // Save changes in ADTG format this time, purely for sake of 
 // illustration. Note that the previous version is still on the 
 // diskette as c:\pubs.xml. 
 pRstAuthors->Save("c:\\pubs.adtg",adPersistADTG); 
 } 
 catch(_com_error &e) 
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
 
 if (pRstAuthors) 
 if (pRstAuthors->State == adStateOpen) 
 pRstAuthors->Close(); 
} 
 
////////////////////////////////////////////////////////// 
// // 
// SaveX3 Function // 
// // 
////////////////////////////////////////////////////////// 
//Finally, you return home. Now update the database with 
//your changes. 
void SaveX3() 
{ 
 HRESULT hr = S_OK; 
 
 // Define ADO object pointers. 
 // Initialize pointers on define. 
 // These are in the ADODB:: namespace. 
 _RecordsetPtr pRstAuthors = NULL; 
 _ConnectionPtr pCnn = NULL; 
 
 //Definitions of other variables 
 _bstr_t strCnn("Provider='sqloledb';Data Source='MySqlServer';" 
 "Initial Catalog='pubs';Integrated Security='SSPI';"); 
 
 try 
 { 
 TESTHR(pCnn.CreateInstance(__uuidof(Connection))); 
 
 TESTHR(pRstAuthors.CreateInstance(__uuidof(Recordset))); 
 
 //If there is no ActiveConnection, you can open with defaults. 
 pRstAuthors->Open("c:\\pubs.adtg","Provider=MSPersist;", 
 adOpenForwardOnly,adLockBatchOptimistic,adCmdFile); 
 
 //Connect to the database, associate the Recordset with 
 //the connection, then update the database table with the 
 //changed Recordset. 
 pCnn->Open(strCnn,"","",NULL); 
 
 pRstAuthors->PutActiveConnection(_variant_t((IDispatch *) pCnn)); 
 pRstAuthors->UpdateBatch(adAffectAll); 
 } 
 catch(_com_error &e) 
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
 
 
 if (pRstAuthors) 
 if (pRstAuthors->State == adStateOpen) 
 pRstAuthors->Close(); 
 if (pCnn) 
 if (pCnn->State == adStateOpen) 
 pCnn->Close(); 
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
 printf("Error number: %x\t%s\n", pErr->Number, 
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
 
 // Print COM errors. 
 printf("Error\n"); 
 printf("\tCode = %08lx\n", e.Error()); 
 printf("\tCode meaning = %s\n", e.ErrorMessage()); 
 printf("\tSource = %s\n", (LPCSTR) bstrSource); 
 printf("\tDescription = %s\n", (LPCSTR) bstrDescription); 
} 
 
bool FileExists() 
{ 
 struct _finddata_t xml_file; 
 long hFile; 
 
 if( (hFile = _findfirst("c:\\pubs.xml", &xml_file )) != -1L) 
 { 
 printf( "File already exists!\n" ); 
 return(true); 
 } 
 else 
 return (false); 
} 
// EndSaveCpp 
```

