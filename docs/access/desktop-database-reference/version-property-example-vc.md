---
<span data-ttu-id="7239a-101"><<<<<<< 标头标题： Version 属性示例 （VC + +） TOCTitle: Version 属性示例 （VC + +） === 标题： Version 属性示例 （VC + +） TOCTitle: Version 属性示例 （VC + +）</span><span class="sxs-lookup"><span data-stu-id="7239a-101"><<<<<<< HEAD title: Version Property Example (VC++) TOCTitle: Version Property Example (VC++) ======= title: Version property example (VC++) TOCTitle: Version property example (VC++)</span></span>
>>>>>>> <span data-ttu-id="7239a-102">母版页 ms:assetid: deda3998-52cd-0068-7f8c-e58c71802226 ms:mtpsurl: https://msdn.microsoft.com/library/JJ250130(v=office.15) ms:contentKeyID: 48548201 ms.date: 09/18/2015 mtps_version: office.15.aspx</span><span class="sxs-lookup"><span data-stu-id="7239a-102">master ms:assetid: deda3998-52cd-0068-7f8c-e58c71802226 ms:mtpsurl: https://msdn.microsoft.com/library/JJ250130(v=office.15) ms:contentKeyID: 48548201 ms.date: 09/18/2015 mtps_version: v=office.15</span></span>
---

<span data-ttu-id="7239a-103"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="7239a-103"><<<<<<< HEAD</span></span>
# <a name="version-property-example-vc"></a><span data-ttu-id="7239a-104">Version 属性示例 (VC++)</span><span class="sxs-lookup"><span data-stu-id="7239a-104">Version Property Example (VC++)</span></span>
=======
# <a name="version-property-example-vc"></a><span data-ttu-id="7239a-105">Version 属性示例 （VC + +）</span><span class="sxs-lookup"><span data-stu-id="7239a-105">Version property example (VC++)</span></span>
>>>>>>> <span data-ttu-id="7239a-106">master</span><span class="sxs-lookup"><span data-stu-id="7239a-106">master</span></span>


<span data-ttu-id="7239a-107">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="7239a-107">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="7239a-p101">此示例使用 [Connection](version-property-ado.md) 对象的 [Version](connection-object-ado.md) 属性来显示当前的 ADO 版本。它还使用多个动态属性来显示以下内容：</span><span class="sxs-lookup"><span data-stu-id="7239a-p101">This example uses the [Version](version-property-ado.md) property of a [Connection](connection-object-ado.md) object to display the current ADO version. It also uses several dynamic properties to show:</span></span>

  - <span data-ttu-id="7239a-110">当前的 DBMS 名称和版本。</span><span class="sxs-lookup"><span data-stu-id="7239a-110">the current DBMS name and version.</span></span>

  - <span data-ttu-id="7239a-111">OLE DB 版本。</span><span class="sxs-lookup"><span data-stu-id="7239a-111">OLE DB version.</span></span>

  - <span data-ttu-id="7239a-112">提供程序名称和版本。</span><span class="sxs-lookup"><span data-stu-id="7239a-112">provider name and version.</span></span>

  - <span data-ttu-id="7239a-113">ODBC 版本。</span><span class="sxs-lookup"><span data-stu-id="7239a-113">ODBC version.</span></span>

  - <span data-ttu-id="7239a-114">ODBC 驱动程序名称和版本。</span><span class="sxs-lookup"><span data-stu-id="7239a-114">ODBC driver name and version.</span></span>

<!-- end list -->

```cpp 
 
// BeginVersionCpp 
#import "c:\Program Files\Common Files\System\ADO\msado15.dll" no_namespace rename("EOF", "EndOfFile") 
 
#include <ole2.h> 
#include <stdio.h> 
#include <conio.h> 
 
// Function declarations 
inline void TESTHR(HRESULT x) {if FAILED(x) _com_issue_error(x);}; 
void VersionX(void); 
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
 
 VersionX(); 
 
 ::CoUninitialize(); 
} 
 
////////////////////////////////////////////////////////// 
// // 
// VersionX Function // 
// // 
////////////////////////////////////////////////////////// 
void VersionX(void) 
{ 
 HRESULT hr = S_OK; 
 
 // Define string variables. 
 _bstr_t strCnn("driver={SQL Server};server='MySqlServer';" 
 "user id='MyUserId';password='MyPassword';database='pubs';"); 
 
 // Define ADO object pointers. 
 // Initialize pointers on define. 
 // These are in the ADODB:: namespace. 
 _ConnectionPtr pConnection = NULL; 
 
 try 
 { 
 // Open connection. 
 TESTHR(pConnection.CreateInstance(__uuidof(Connection))); 
 pConnection->Open (strCnn, "", "", adConnectUnspecified); 
 
 printf("ADO Version : %s\n\n",(LPCSTR) pConnection->Version); 
 printf("DBMS Name : %s\n\n",(LPCSTR) (_bstr_t) 
 pConnection->Properties->GetItem("DBMS Name")->Value); 
 printf("DBMS Version : %s\n\n",(LPCSTR) (_bstr_t) 
 pConnection->Properties->GetItem("DBMS Version")->Value); 
 printf("OLE DB Version : %s\n\n",(LPCSTR) (_bstr_t) 
 pConnection->Properties->GetItem("OLE DB Version")->Value); 
 printf("Provider Name : %s\n\n",(LPCSTR) (_bstr_t) 
 pConnection->Properties->GetItem("Provider Name")->Value); 
 printf("Provider Version : %s\n\n",(LPCSTR) (_bstr_t) 
 pConnection->Properties->GetItem("Provider Version")->Value); 
 printf("Driver Name : %s\n\n",(LPCSTR) (_bstr_t) 
 pConnection->Properties->GetItem("Driver Name")->Value); 
 printf("Driver Version : %s\n\n",(LPCSTR) (_bstr_t) 
 pConnection->Properties->GetItem("Driver Version")->Value); 
 printf("Driver ODBC Version : %s\n\n",(LPCSTR) (_bstr_t) 
 pConnection->Properties->GetItem("Driver ODBC Version")->Value); 
 
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
// EndVersionCpp 
```

