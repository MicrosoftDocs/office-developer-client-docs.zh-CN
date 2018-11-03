---
title: Visual C++ Extensions 示例
TOCTitle: Visual C++ Extensions Example
ms:assetid: fe57868f-5707-3c5b-cb93-4121732d67cc
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250305(v=office.15)
ms:contentKeyID: 48548934
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 2f7bbcdc4f3ddcadfd45ba627873945ec1a3adfe
ms.sourcegitcommit: 558d09fad81f8d80b5ad0edd21934fc09c098f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25946908"
---
# <a name="visual-c-extensions-example"></a><span data-ttu-id="b622a-102">Visual C++ Extensions 示例</span><span class="sxs-lookup"><span data-stu-id="b622a-102">Visual C++ Extensions example</span></span>


<span data-ttu-id="b622a-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="b622a-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="b622a-104">此程序显示如何从字段检索值，并将其转换为 C/C++ 变量。</span><span class="sxs-lookup"><span data-stu-id="b622a-104">This program shows how values are retrieved from fields and converted to C/C++ variables.</span></span>

<span data-ttu-id="b622a-105">此示例还利用"智能指针"，可以自动处理呼叫和引用**IADORecordBinding**接口的计数的 COM 特定详细信息。</span><span class="sxs-lookup"><span data-stu-id="b622a-105">This example also takes advantage of "smart pointers," which automatically handle the COM-specific details of calling and reference counting for the **IADORecordBinding** interface.</span></span>

<span data-ttu-id="b622a-106">如果不使用智能指针，则应编码为：</span><span class="sxs-lookup"><span data-stu-id="b622a-106">Without smart pointers, you would code:</span></span>

```cpp 
 
IADORecordBinding *picRs = NULL; 
... 
TESTHR(pRs->QueryInterface( 
 __uuidof(IADORecordBinding), (LPVOID*)&picRs)); 
... 
if (picRs) picRs->Release(); 
```

<span data-ttu-id="b622a-107">使用智能指针，从 IADORecordBinding 接口与此语句的类型从派生 IADORecordBindingPtr 类型：</span><span class="sxs-lookup"><span data-stu-id="b622a-107">With smart pointers, you derive the IADORecordBindingPtr type from the type from the IADORecordBinding interface with this statement:</span></span>

```cpp 
 
_COM_SMARTPTR_TYPEDEF(IADORecordBinding, __uuidof(IADORecordBinding)); 
```

<span data-ttu-id="b622a-108">并实例化指针，如下所示：</span><span class="sxs-lookup"><span data-stu-id="b622a-108">And instantiate the pointer like this:</span></span>

```cpp 
 
IADORecordBindingPtr picRs(pRs); 
```

<span data-ttu-id="b622a-109">Visual c + + Extensions 由**Recordset**对象实现的因为智能指针，picRs 的构造函数采用\_RecordsetPtr 指针，prs:。</span><span class="sxs-lookup"><span data-stu-id="b622a-109">Because the Visual C++ Extensions are implemented by the **Recordset** object, the constructor for the smart pointer, picRs , takes the \_RecordsetPtr pointer, pRs .</span></span> <span data-ttu-id="b622a-110">构造函数调用 QueryInterface prs： 用于查找所执行的\_RecordsetPtr 指针，prs:。</span><span class="sxs-lookup"><span data-stu-id="b622a-110">The constructor calls QueryInterface using pRs to find the , takes the \_RecordsetPtr pointer, pRs .</span></span> <span data-ttu-id="b622a-111">构造函数调用 QueryInterface prs： 用于查找 IADORecordBinding 接口。</span><span class="sxs-lookup"><span data-stu-id="b622a-111">The constructor calls QueryInterface using pRs to find the IADORecordBinding interface.</span></span>

```cpp 
 
// Visual C++ Extensions Example 
#import "c:\Program Files\Common Files\System\ADO\msado15.dll" no_namespace rename("EOF", "EndOfFile") 
 
#include <stdio.h> 
#include <icrsint.h> 
_COM_SMARTPTR_TYPEDEF(IADORecordBinding, __uuidof(IADORecordBinding)); 
 
inline void TESTHR(HRESULT _hr) { if FAILED(_hr) _com_issue_error(_hr); } 
 
class CCustomRs : public CADORecordBinding 
{ 
BEGIN_ADO_BINDING(CCustomRs) 
 ADO_VARIABLE_LENGTH_ENTRY2(2, adVarChar, m_ch_fname, 
 sizeof(m_ch_fname), m_ul_fnameStatus, false) 
 ADO_VARIABLE_LENGTH_ENTRY2(4, adVarChar, m_ch_lname, 
 sizeof(m_ch_lname), m_ul_lnameStatus, false) 
END_ADO_BINDING() 
public: 
 CHAR m_ch_fname[22]; 
 CHAR m_ch_lname[32]; 
 ULONG m_ul_fnameStatus; 
 ULONG m_ul_lnameStatus; 
}; 
 
void main(void) 
{ 
 ::CoInitialize(NULL); 
 try 
 { 
 _RecordsetPtr pRs("ADODB.Recordset"); 
 CCustomRs rs; 
 IADORecordBindingPtr picRs(pRs); 
 
 pRs->Open("SELECT * FROM Employee ORDER BY lname", 
 "dsn=pubs;uid=sa;pwd=;", 
 adOpenStatic, adLockOptimistic, adCmdText); 
 
 TESTHR(picRs->BindToRecordset(&rs)); 
 
 while (!pRs->EndOfFile) 
 { 
 // Process data in the CCustomRs C++ instance variables. 
 printf("Name = %s %s\n", 
 (rs.m_ul_fnameStatus == adFldOK ? rs.m_ch_fname: "<Error>"), 
 (rs.m_ul_lnameStatus == adFldOK ? rs.m_ch_lname: "<Error>")); 
 
 // Move to the next row of the Recordset. 
 // Fields in the new row will automatically be 
 // placed in the CCustomRs C++ instance variables. 
 
 pRs->MoveNext(); 
 } 
 } 
 catch (_com_error &e ) 
 { 
 printf("Error:\n"); 
 printf("Code = %08lx\n", e.Error()); 
 printf("Meaning = %s\n", e.ErrorMessage()); 
 printf("Source = %s\n", (LPCSTR) e.Source()); 
 printf("Description = %s\n", (LPCSTR) e.Description()); 
 } 
 ::CoUninitialize(); 
} 
```

