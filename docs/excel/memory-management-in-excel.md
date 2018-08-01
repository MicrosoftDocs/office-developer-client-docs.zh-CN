---
title: Excel 中的内存管理
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
keywords:
- xloper12 内存 [excel 2007]，管理在 Excel 中的内存，Excel 堆栈，字符串 [Excel 2007]，管理内存，在 Excel 中，XLOPER 内存 [Excel 2007]，内存管理内存 [Excel 2007]，管理指南
localization_priority: Normal
ms.assetid: 3bf5195b-6235-43cf-8795-0c7b0a63a095
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 97c76d762fdc5e575c571804816e5581a7bec8bb
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773806"
---
# <a name="memory-management-in-excel"></a>Excel 中的内存管理

 **适用于** Excel 2013 | Office 2013 | Visual Studio 
  
内存管理是最重要的担心，如果您想要创建高效的和稳定 xll （英文）。 范围的 Microsoft Excel 中的问题会导致故障也管理内存 — 从低效的内存分配和初始化等小内存泄漏，例如 Excel 的不稳定的主要问题的小问题。
  
不当的内存严重添加在相关问题的最常见源。 因此，您应在内存管理生成的一致和良好-设计-通过策略与您的项目。 
  
内存管理变得 Microsoft Office Excel 2007 中引入了多线程的工作簿重新计算更复杂。 如果您想要创建并导出线程安全工作表函数，必须管理生成多个线程争夺访问时可能出现的冲突。
  
有以下三种数据结构类型的内存注意事项：
  
- **XLOPER**s 和**XLOPER12**s
    
- 不在**XLOPER**或**XLOPER12**的字符串
    
- **FP**和**FP12**阵列 
    
## <a name="xloperxloper12-memory"></a>XLOPER/XLOPER12 内存

**XLOPER**/ **XLOPER12**数据结构中有几个包含指向的内存，即 (**xltypeStr**) 字符串、 数组 (**xltypeMulti**) 和外部引用 (**xltypeRef**) 块的子类型。 还要注意**xltypeMulti**数组，可以包含字符串**XLOPER**/ **XLOPER12s**反过来指向其他块的内存。 
  
**XLOPER**/ **XLOPER12**可以创建以下几种方式： 
  
- 由 Excel 时准备参数传递给 XLL 函数
    
- 由 Excel C API 中返回一个**XLOPER**或**XLOPER12**时调用 
    
- 按创建参数传递给 C API 时您 DLL 调用
    
- 创建 XLL 函数返回值时 DLL
    
以下几种方式可以分配一块的内存中内存指向类型之一：
  
- 在这种情况下您无需分配或释放内存，它可以是任何函数在代码之外，您的 DLL 中的静态块。
    
- 它可以是静态块内您的 DLL 中一些函数代码，在这种情况下您无需分配或释放内存。
    
- 它可以动态分配和释放您的 DLL 通过多种可能的方式： **malloc**和**免费**、**新建**和**删除**，等等。
    
- 它可以由 Excel 动态分配。
    
为**XLOPER**给定可能来源数/ **XLOPER12**内存和数的情况**XLOPER**/ **XLOPER12**可能已经分配的内存、 is not 此主题可以令人惊讶看起来很难。 但是，复杂性，会大大降低如果您执行多个规则和指导原则。 
  
### <a name="rules-for-working-with-xloperxloper12"></a>使用 XLOPER/XLOPER12 规则

- 不要尝试以释放内存中或覆盖**XLOPERs**/ 作为参数传递给 XLL 函数的**XLOPER12**s。 您应当将此类参数视为只读的。 有关详细信息，请参阅"返回**XLOPER**或**XLOPER12**就地修改参数由" [Excel XLL 开发中的已知问题](known-issues-in-excel-xll-development.md)中。
    
- 如果 Excel 已为**XLOPER**分配内存/ **XLOPER12**返回为您的 DLL 与 C API 调用中： 
    
  - 您必须释放内存，当不再需要**XLOPER**/ **XLOPER12**使用[xlFree](xlfree.md)调用。 不要使用，任何其他方法，例如免费或删除释放的内存。
    
  - 如果返回的类型为**xltypeMulti**，不会覆盖任何**XLOPER**/ **XLOPER12**s 中的数组中，尤其是包含字符串，并特别是不其中您试图用字符串覆盖。
    
  - 如果您想要返回**XLOPER**/ 到 DLL 函数的返回值为 Excel**XLOPER12** ，您必须判断 Excel 是否完成后，必须释放 Excel 的内存。 
    
- 必须仅**XLOPER**上调用**xlFree** / **XLOPER12**创建用作的 C API 调用的返回值。 
    
- 如果您的 DLL 已为**XLOPER**分配内存/ **XLOPER12**您想要返回到 Excel 作为您的 DLL 函数的返回值，您必须判断 Excel 是否存在 DLL 必须释放的内存。 
    
### <a name="guidelines-for-memory-management"></a>内存管理的指南

- 用于分配和释放内存的方法在 DLL 中保持一致。 避免混合方法。 一个好方法是换行内存类或结构，您可以在其中更改而不需要更改您的代码在多个位置使用的方法中使用的方法。
    
- 您的 DLL 中创建**xltypeMulti**数组时，需要对字符串分配内存的方式保持一致： 总是动态为其分配内存或始终使用静态内存。 如果这样做，当您要释放内存，您将知道，您必须始终或从不释放字符串。 
    
- 复制 Excel 创建**XLOPER**时创建的 Excel 分配内存的深度副本/ **XLOPER12**。
    
- 请勿将 Excel 分配字符串**XLOPER**/ **XLOPER12**s **xltypeMulti**数组中的。 字符串的深度副本并将指向副本存储数组中。 
    
## <a name="freeing-excel-allocated-xloperxloper12-memory"></a>释放 Excel 分配 XLOPER/XLOPER12 内存

请考虑以下 XLL 命令，其中使用**xlGetName**获取包含 DLL 的路径和文件名称的字符串，并将其显示在通知对话框中使用**xlcAlert**。
  
```cs
int WINAPI show_DLL_name(void)
{
    XLOPER12 xDllName;
    if(Excel12(xlfGetName, &xDllName, 0) == xlretSuccess)
    {
        // Display the name.
        Excel12(xlcAlert, 0, 1, &xDllName);
        // Free the memory that Excel allocated for the string.
        Excel12(xlFree, 0, 1, &xDllName);
    }
    return 1;
}

```

当函数不再需要通过**xDllName**指向的内存时，它可以释放其使用调用[xlFree 函数](xlfree.md)，仅 DLL C API 函数之一。 
  
**XlFree**函数完全函数引用一节介绍了 （请参阅[C API 函数，可以将调用只能从 DLL 或 XLL](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)），但要注意以下事项：
  
- 您可以将指针传递给多个**XLOPER**/ **XLOPER12**s **xlFree**，仅受 Excel (30 在 Excel 2003 中，从 Excel 2007 的 255) 运行版本中支持的函数参数数目限制将单个调用。
    
- **xlFree**将包含的指针设置为**NULL**以确保以尝试释放**XLOPER**/ 已释放的**XLOPER12**是安全的。 **xlFree**是唯一的 C API 函数的修改其参数。 
    
- 可以安全地在任何**XLOPER**上调用**xlFree** / **XLOPER12**用于 C API，无论其是否包含一个指向内存调用的返回值。 
    
## <a name="returning-xloperxloper12s-to-be-freed-by-excel"></a>返回 XLOPER/XLOPER12s 释放由 Excel

假设您要修改上一节中的示例命令，并将其更改为返回 DLL 路径和文件名传递**布尔值** **true**参数和 **# n/A**否则为时的工作表函数。 明确不能调用**xlFree**以返回到 Excel 之前版本的字符串内存。 但是，如果它不会释放某个时刻外, 接程序会发生内存泄漏每次调用该函数。 若要解决此问题，您可以设置一个位**XLOPER**的**xltype**字段中/ **XLOPER12**，定义为**xlbitXLFree** xlcall.h 中。 设置通知 Excel 的值复制完成它必须释放返回的内存。 
  
### <a name="example"></a>示例

下面的代码示例显示在上一节转换为 XLL 工作表函数 XLL 命令。
  
```cs
LPXLOPER12 WINAPI get_DLL_name(int calculation_trigger)
{
    static XLOPER12 xRtnValue; // Not thread-safe
    Excel12(xlfGetName, &xRtnValue, 0);
// If xlfGetName failed, xRtnValue will be #VALUE!
    if(xRtnValue.xltype == xltypeStr)
    {
// Tell Excel to free the string memory after
// it has copied out the return value.
        xRtnValue.xltype |= xlbitXLFree;
    }
    return &xRtnValue;
}
```

使用**XLOPER**XLL 函数/ **XLOPER12**s 必须声明为笔记记录和返回**XLOPER**指针/ **XLOPER12**s。 在此示例中的静态**XLOPER12**函数中使用不安全的线程。 您无法将此函数不正确注册为线程安全的但将风险**xRtnValue**一个线程另一个线程具有与其完成之前被覆盖。 
  
您必须为其分配的 Excel 回调调用后设置**xlbitXLFree** 。 如果您将其设置在此之前，它将被覆盖，并且没有所需效果。 如果您打算使用作为对其他 C API 函数的调用中的参数的值，返回到工作表之前，您应任何此类呼叫后设置此位。 否则，将将不执行检查**XLOPER**之前屏蔽此位的功能混淆/ **XLLOPER12**类型。 
  
## <a name="returning-xloperxloper12s-to-be-freed-by-the-dll"></a>返回 XLOPER/XLOPER12s 释放由 DLL

类似于以下问题出现时您 XLL 已为**XLOPER**分配内存/ **XLOPER12**并想将它返回到 Excel。 Excel 识别可以设置**XLOPER** **xltype**字段中的另一位/ **XLOPER12**，定义为**xlbitDLLFree** xlcall.h 中。 
  
Excel 时接收**XLOPER**/ **XLOPER12**与此设置的位，它会尝试调用的函数，应通过调用[xlAutoFree](xlautofree-xlautofree12.md) （对于**XLOPER**s) 或**xlAutoFree12** （对于**XLOPER12**s) XLL 导出。 函数引用中更详细地描述此函数 （请参阅[加载项管理器和 XLL 接口函数](add-in-manager-and-xll-interface-functions.md)），但此处提供了示例最少实现。 其用途是以释放**XLOPER**/ **XLOPER12**内存与如何最初分配一致的方式。 
  
### <a name="examples"></a>示例

下面的示例函数将作用相同为以前函数之处在于它包含文本"此 dll 的完整路径名 is"DLL 名称之前。
  
```cs
#include <string.h>
LPXLOPER12 WINAPI get_DLL_name_2(int calculation_trigger)
{
    static XLOPER12 xRtnValue; // Not thread-safe
    Excel12(xlfGetName, &xRtnValue, 0);
// If xlfGetName failed, xRtnValue will be #VALUE!
    if(xRtnValue.xltype != xltypeStr)
        return &xRtnValue;
// Make a copy of the DLL path and file name.
    wchar_t *leader = L"The full pathname for this DLL is ";
    size_t leader_len = wcslen(leader);
    size_t dllname_len = xRtnValue.val.str[0];
    size_t msg_len = leader_len + dllname_len;
    wchar_t *msg_text = (wchar_t *)malloc(msg_len + 1);
    wcsncpy_s(msg_text + 1, leader, leader_len);
    wcsncpy_s(msg_text + 1 + leader_len, xRtnValue.val.str + 1,
        dllname_len);
    msg_text[0] = msg_len;
// Now the original string has been copied Excel can free it.
    Excel12(xlFree, 0, 1, &xRtnValue);
// Now reuse the XLOPER12 for the new string.
    xRtnValue.val.str = msg_text;
// Tell Excel to call back into the DLL to free the string
// memory after it has copied out the return value.
    xRtnValue.xltype     = xltypeStr | xlbitDLLFree;
    return &xRtnValue;
}
```

**XlAutoFree12**中导出以前的功能的 XLL 的至少具有足够实现将如下所示。 
  
```cs
void WINAPI xlAutoFree12(LPXLOPER12 p_oper)
{
    if(p_oper->xltype == (xltypeStr | xlbitDLLFree))
        free(p_oper->val.str);
}
```

如果 XLL 仅返回**XLOPER12**字符串，并且仅使用**malloc**分配这些字符串，此实现才足够。 请注意，测试 
  
 ` if(p_oper->xltype == xltypeStr) `
  
在这种情况下会失败，因为**xlbitDLLFree**设置。 
  
一般情况下， **xlAutoFree**和**xlAutoFree12**应实现，以便他们释放内存 XLL 创建**xltypeMulti**数组和**xltypeRef**外部引用相关联。 
  
您可能决定实施 XLL 函数，以便他们都返回动态分配**XLOPER**s 和**XLOPER12**s。 在这种情况下，您需要在所有此类**XLOPER**s 和子类型无论**XLOPER12**s 上设置**xlbitDLLFree** 。 您还需要实施**xlAutoFree**和**xlAutoFree12**以便释放的此内存和也任何内存指向内**XLOPER**/ **XLOPER12**。 此方法是一种方法使返回值线程安全的。 例如，以前的功能可重写，如下所示。
  
```cs
#include <string.h>
LPXLOPER12 WINAPI get_DLL_name_3(int calculation_trigger)
{
// Thread-safe
    LPXLOPER12 pxRtnValue = (LPXLOPER12)malloc(sizeof(XLOPER12));
    Excel12(xlfGetName, pxRtnValue, 0);
// If xlfGetName failed, pxRtnValue will be #VALUE!
    if(pxRtnValue->xltype != xltypeStr)
    {
// Even though an error type does not point to memory,
// Excel needs to pass this oper to xlAutoFree12 to
// free pxRtnValue itself.
        pxRtnValue->xltype |= xlbitDLLFree;
        return pxRtnValue;
    }
// Make a copy of the DLL path and file name.
    wchar_t *leader = L"The full pathname for this DLL is ";
    size_t leader_len = wcslen(leader);
    size_t dllname_len = pxRtnValue->val.str[0];
    size_t msg_len = leader_len + dllname_len;
    wchar_t *msg_text = (wchar_t *)malloc(msg_len + 1);
    wcsncpy_s(msg_text + 1, leader, leader_len);
    wcsncpy_s(msg_text + 1 + leader_len, pxRtnValue->val.str + 1,
        dllname_len);
    msg_text[0] = msg_len;
// Now the original string has been copied Excel can free it.
    Excel12(xlFree, 0, 1, pxRtnValue);
// Now reuse the XLOPER12 for the new string.
    pxRtnValue->val.str = msg_text;
    pxRtnValue->xltype = xltypeStr | xlbitDLLFree;
    return pxRtnValue;
}
void WINAPI xlAutoFree12(LPXLOPER12 p_oper)
{
    if(p_oper->xltype == (xltypeStr | xlbitDLLFree))
        free(p_oper->val.str);
    free(p_oper);
}
```

有关**xlAutoFree**和**xlAutoFree12**的详细信息，请参阅[xlAutoFree/xlAutoFree12](xlautofree-xlautofree12.md)。
  
## <a name="returning-modify-in-place-arguments"></a>返回修改就地参数

Excel 允许通过修改就地参数返回一个值，XLL 函数。 您可以仅处理此参数中传递作为指针。 以类似，必须以告知 Excel 哪些参数将被修改一种注册的函数。 
  
返回一个值，此方法可通过指针传递的所有数据类型都支持，但对于以下类型的特别有用：
  
- 长度计数和 null 结尾 ASCII 字节字符串
    
- 长度计数和空结尾 Unicode 宽字符字符串 （在 Excel 2007 中从开始）
    
- **FP**浮点数组 
    
- **FP12**浮点数组 （在 Excel 2007 中从开始） 
    
> [!NOTE]
> 不应尝试这种方式返回**XLOPER**s 或**XLOPER12**s。 有关详细信息，请参阅[Excel XLL 开发中的已知问题](known-issues-in-excel-xll-development.md)。 
  
使用此技术，而不只需使用返回的语句的好处是 Excel 的返回值分配的内存。 完成后读取返回的数据的 Excel，它释放内存。 这将内存离开 XLL 函数的管理任务。 线程安全利用此方法是： 如果同时调用在不同线程上由 Excel，每个线程上的每个函数调用具有自己的缓冲区。
  
非常有用的前面列出的数据类型特别是因为后调用以释放内存的 DLL 的机制后返回存在**XLOPER**/ 简单字符串和**FP**不存在**XLOPER12**s/ **FP12**数组。 因此，当返回 DLL 创建字符串或浮点数组，您有以下选择： 
  
- 设置为动态分配缓冲区的持久的指针，则返回指针。 在下次调用函数 （1） 检查指针不为 null，（2） 免费资源分配上以前的呼叫，将指针重置为 null，重复 （3） 使用的内存新分配块的指针。
    
- 在不需要释放，并返回一个指针的静态缓冲区中创建您的字符串和数组。
    
- 修改就地情况下，直接到由 Excel 设置留出空间编写您的字符串或阵列的参数。
    
否则，您必须创建**XLOPER**/ **XLOPER12**，以及使用**xlbitDLLFree**和**xlAutoFree**/ **xlAutoFree12**以释放资源。 
  
可能在这些情况下，其中您正在相同类型的参数作为传递返回值的最简单的最后一个选项。 要记住的关键点是缓冲区大小被限制，并且必须谨慎以溢出它们。 获取此错误可能会崩溃 Excel。 缓冲区大小的字符串和**FP**/ **FP12**数组的后面进行讨论。 
  
## <a name="strings"></a>字符串

字符串内存管理问题可以说是在应用程序和加载项的不稳定的最常见原因。它易于理解可能是，提供的各种方法中处理字符串： 空终止或长度计数 （或两者）;静态或动态缓冲区;固定的长度或几乎不限的长度;操作系统托管内存 (例如，OLE Bstr) 或非托管的字符串;等等。
  
C/c + + 程序员熟悉最 null 结尾的字符串。 标准 C 库旨在处理此类字符串。 在代码中的静态字符串编译为 null 结尾的字符串。 此外，Excel 适用于是不通常 null 结尾的长度计数的字符串。 这些信息的组合需要有关如何处理字符串和字符串内存您 DLL/XLL 中清除和一致的方法。
  
最常见的问题如下所示：
  
- 到需要有效指针和不或无法检查指针的有效性本身的函数为 null 或无效指针传递。
    
- 致使溢出的字符串缓冲区的边界由一个函数不或无法检查针对写入的字符串的长度缓冲区的长度。
    
- 尝试释放字符串缓冲区内存的是静态、 已，已释放或未分配与如何释放一致的方式。
    
- 内存泄漏字符串被分配，然后不释放，通常在经常调用的函数的结果。
    
### <a name="rules-for-strings"></a>字符串规则

**XLOPER**与/ **XLOPER**s 有规则，您应遵循的准则。 上一节中，准则是与给定相同。 下面的规则是专为字符串的规则的一种扩展。
  
 **规则：**
  
- 不要尝试以释放内存中或覆盖字符串**XLOPER**/ **XLOPER12**s 或简单的长度计数或空结尾字符串作为参数传递给 XLL 函数。 您应当将此类参数视为只读的。
    
- Excel 字符串**XLOPER**分配内存的其中/ **XLOPER12**的 C API 回调函数，返回值使用**xlFree**忙，或如果从 XLL 函数返回到 Excel 设置**xlbitXLFree** 。 
    
- 其中 DLL 动态字符串的一个缓冲区分配**XLOPER**/ **XLOPER12**，忙时进行设置，或如果从 XLL 函数返回到 Excel 设置**xlbitDLLFree**分配方式与一致的方式，然后释放中**xlAutoFree**/  **xlAutoFree12**。
    
- 如果 Excel 已返回到 C API 调用 DLL **xltypeMulti**数组分配内存，不会覆盖任何字符串**XLOPER**/ 在阵列中的**XLOPER12**s。 此类数组才必须释放即可使用**xlFree**，或者，如果正在 XLL 函数返回，通过设置**xlbitXLFree**。
    
### <a name="string-types-supported"></a>支持的字符串类型

**C API xltypeStr XLOPER/XLOPER12s**

|* * 字节字符串: * * XLOPER ***|* * 宽字符的字符串: * * XLOPER12 ***|
|:-----|:-----|
|所有版本的 Excel  <br/> |从 Excel 2007  <br/> |
|最大长度： 255 扩展 ASCII 字节  <br/> |最大长度 32767 Unicode 字符数  <br/> |
|（无符号） 的第一个字节 = 长度  <br/> |第一个 Unicode 字符 = 长度  <br/> |
   
> [!IMPORTANT]
> 请假定 null 终止**XLOPER**或**XLOPER12**字符串。 
  
**C/c + + 字符串**

|**字节字符串**|**宽字符的字符串**|
|:-----|:-----|
|Null 结尾 (**char** *)"C"最大长度： 255 扩展 ASCII 字节  <br/> |Null 结尾 (**wchar_t** *)"C %"最大长度 32767 Unicode 字符数  <br/> |
|长度计数 (**未签署的 char** *)"D"  <br/> |长度计数 (**wchar_t** *)"D %"  <br/> |
   
### <a name="strings-in-xltypemulti-xloperxloper12-arrays"></a>XltypeMulti XLOPER/XLOPER12 数组中的字符串

在某些情况下，Excel 将新建用于 DLL/XLL **xltypeMulti**数组。 有几个 XLM 信息函数返回这样的数组。 例如，C API 函数**xlfGetWorkspace**，当传递参数*44*中，返回包含所有当前注册的 DLL 过程描述的字符串数组。 C API 函数**xlfDialogBox**返回包含字符串的深层副本其数组参数修改的副本。 可能 XLL 遇到**xltypeMulti**数组的最常见方式是，它具有已作为参数传递给 XLL 函数，或它具有已强制转换为此类型从区域引用。 在这些后的情况下，Excel 将新建深入份中的源单元格和指向这些数组中的字符串。 
  
想要修改在 DLL，这些字符串应创建您自己深入的副本。 当您正在创建您自己**xltypeMulti**数组时，不应将 Excel 分配字符串**XLOPER**/ 其中**XLOPER12**s。 此风险您没有释放它们正确更高版本，或不根本释放。 同样，您应创建的字符串的深度副本和数组中存储的副本的指针。
  
 **示例**
  
下面的示例函数创建动态分配的长度计数 Unicode 字符串的副本。 请注意，呼叫者最终必须释放在此示例中使用**删除**[]，分配的内存和源字符串不假定为 null 终止。 该副本字符串被截断为了安全，必要时，不为 null 终止。
  
```cs
#include <string.h>
#define MAX_V12_STRBUFFLEN    32678
    
wchar_t * deep_copy_wcs(const wchar_t *p_source)
{
    if(!p_source)
        return NULL;
    size_t source_len = p_source[0];
    bool truncated = false;
    if(source_len >= MAX_V12_STRBUFFLEN)
    {
        source_len = MAX_V12_STRBUFFLEN - 1; // Truncate the copy
        truncated = true;
    }
    wchar_t *p_copy = new wchar_t[source_len + 1];
    wcsncpy_s(p_copy, p_source, source_len + 1);
    if(truncated)
        p_copy[0] = source_len;
    return p_copy;
}
```

此函数可然后安全地用于复制**XLOPER12**，如下面的可导出 XLL 函数的返回其参数的副本，如果它是一个字符串中所示。 所有其他类型为零长度字符串返回。 请注意，不会处理区域 — 此函数返回 **#VALUE ！**。 为采用类型 U 参数，以便引用中传递的值必须注册的函数。 这是等价于内置工作表函数**T()** ，之处在于**AsText**还将错误转换为零长度字符串。 此代码示例假定该**xlAutoFree12**释放传入的指针，以及其内容，使用**删除**。
  
```cs
LPXLOPER12 WINAPI AsText(LPXLOPER12 pArg)
{
    LPXLOPER12 pRtnVal = new XLOPER12;
// If the input was an array, only operate on the top-left element.
    LPXLOPER *pTemp;
    if(pArg->xltype == xltypeMulti)
        pTemp = pArg->val.array.lparray;
    else
        pTemp = pArg;
    switch(pTemp->xltype)
    {
        case xltypeErr:
        case xltypeNum:
        case xltypeMissing:
        case xltypeNil:
        case xltypeBool:
            pRtnVal->xltype = xltypeStr | xlbitDLLFree;
            pRtnVal->val.str = deep_copy_wcs(L"\000");
            return pRtnVal;
        case xltypeStr:
            pRtnVal->xltype = xltypeStr | xlbitDLLFree;
            pRtnVal->val.str = deep_copy_wcs(pTemp->val.str);
            return pRtnVal;
        
        default: // xltypeSRef, xltypeRef, xltypeFlow, xltypeInt
            pRtnVal->xltype = xltypeErr | xlbitDLLFree;
            pRtnVal->val.err = xlerrValue;
            return pRtnVal;
    }
}
```

### <a name="returning-modify-in-place-string-arguments"></a>返回修改就地字符串参数

**F**、 **G**、 **%f%**，参数注册为类型，并可以就地修改**G %** 。 在 Excel 准备这些类型的字符串参数时，它会创建的最大长度缓冲区。 然后它将复制的参数字符串到，即使此字符串是很大程度较短。 这样，XLL 函数，直接将其返回值写入同一内存。 
  
缓冲区大小分开为这些类型如下所示：
  
- **字节字符串：** 256 字节包括长度计数器 （类型 G） 或 null 终止 （F 类型）。 
    
- **Unicode 字符串：** 32,768 个宽字符 （65536 字节） 包括长度计数器 （类型 G %） 或 null 终止 （F 类型 %）。 
    
> [!NOTE]
> 不能调用此类函数直接从 Visual Basic for Applications (VBA) 因为您不能确保已分配足够大缓冲区。 您只能调用此类函数从另一个 DLL 安全地如果显式过去足够大缓冲区。 
  
下面是一个反转传入的 null 结尾宽字符字符串使用标准库函数**wcsrev**XLL 函数的示例。 参数在此情况下将注册键入**F %**。
  
```cs
void WINAPI reverse_text_xl12(wchar_t *text)
{
    _wcsrev(text);
}
```

## <a name="persistent-storage-binary-names"></a>永久存储 （二进制名称）

二进制名称定义和关联的二进制文件，即，与工作簿一起存储的非结构化数据块。 它们使用函数[xlDefineBinaryName](xldefinebinaryname.md)中，创建和使用函数[xlGetBinaryName](xlgetbinaryname.md)检索数据。 函数参考中的更详细地介绍这两个函数 （请参阅[C API 函数，可以将调用只能从 DLL 或 XLL](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)），并同时使用**xltypeBigData** **XLOPER**/ **XLOPER12**。 
  
有关限制的二进制名称的实际应用程序的已知问题的信息，请参阅[Excel XLL 开发中的已知问题](known-issues-in-excel-xll-development.md)。
  
## <a name="excel-stack"></a>Excel 堆栈

Excel 与它已加载的所有 Dll 共享其堆栈空间。 堆栈空间通常是多个适用于普通的使用，并不需要是长短它，只要您遵循的一些准则： 
  
- 不非常大的结构作为参数传递给函数的值堆栈上。 应传递指针或引用。
    
- 不在堆栈返回大型结构。 返回到静态或动态分配内存的指针，或使用参数传递的引用。
    
- 不要声明中的函数代码非常大自动变量结构。 如果需要它们，则将这些声明为静态。
    
- 不要调用函数以递归方式，除非您确信的递归深度将始终为浅表。 转为尝试使用循环。
    
当 DLL 到 Excel 中使用 C API 回拨时，Excel 将首先检查无法所做的最长使用率调用堆栈上是否有足够的空间。 如果它认为可能没有足够的空间，它将失败呼叫为安全起见，尽管可能实际上没有足够的空间用于该特定的呼叫。 在这种情况下，回调返回代码**xlretFailed**。 对于普通使用 C API 和堆栈，这是不可能的 C API 调用失败的原因。
  
如果您是担心，还是只好奇，或您想要消除堆栈空间不足作为不清楚失败的原因，您可以找到出多少堆栈空间是对[xlStack](xlstack.md)函数的调用。 
  
## <a name="see-also"></a>另请参阅



[Excel 中的多线程重新计算](multithreaded-recalculation-in-excel.md)
  
[Excel 中的多线程处理和内存争用](multithreading-and-memory-contention-in-excel.md)
  
[Developing Excel XLLs](developing-excel-xlls.md)

