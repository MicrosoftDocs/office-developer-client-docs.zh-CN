---
title: 内存管理Excel
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
keywords:
- xloper12 memory [excel 2007]，managing memory in Excel，Excel stack，strings [Excel 2007]， managing memory，memory management in Excel，XLOPER memory [Excel 2007]，memory [Excel 2007]， management guidelines
localization_priority: Normal
ms.assetid: 3bf5195b-6235-43cf-8795-0c7b0a63a095
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: f129dac2971f01c8ada15f0028958132b1945746
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33419539"
---
# <a name="memory-management-in-excel"></a>内存管理Excel

 **适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
如果要创建高效且稳定的 XLL，内存管理是最重要的问题。 未能很好地管理内存可能导致 Microsoft Excel 中出现一系列问题，从低效率的内存分配和初始化和小内存泄漏等次要问题，到主要问题（如 Excel 的不稳定）。
  
内存管理不当是严重加载项相关问题的最常见来源。 因此，应在内存管理方面制定一致且经过思考的策略来构建项目。 
  
随着多线程工作簿重新计算Microsoft Office Excel 2007 年，内存管理变得更加复杂。 如果要创建和导出线程安全工作表函数，则必须管理在多个线程竞争访问时生成的冲突。
  
对于以下三种数据结构类型，存在内存注意事项：
  
- **XLOPER** 和 **XLOPER12** s
    
- 不在 XLOPER 或 **XLOPER12 中的字符串**
    
- **FP** 和 **FP12** 数组 
    
## <a name="xloperxloper12-memory"></a>XLOPER/XLOPER12 内存

**XLOPER** XLOPER12 数据结构具有一些子类型，其中包含指向内存块的指针，即字符串 /   (**xltypeStr**) 、数组 (**xltypeMulti**) 和外部引用 (**xltypeRef**) 。 另请注意 **，xltypeMulti** 数组可以包含字符串 **XLOPER** /  **XLOPER12，** 而字符串又指向其他内存块。 
  
可通过 **多种方式创建** /  **XLOPER XLOPER12：** 
  
- By Excel when preparing arguments to be passed to an XLL function
    
- By Excel when returning an **XLOPER** or **XLOPER12** in a C API call 
    
- 通过 DLL 创建要传递给 C API 调用的参数
    
- 通过 DLL 创建 XLL 函数返回值
    
可以通过多种方式分配其中一种内存指向类型中的内存块：
  
- 它可以是 DLL 中任何函数代码之外的静态块，在这种情况下，你不需要分配或释放内存。
    
- 它可以是 DLL 中某些函数代码内的静态块，在这种情况下，你不需要分配或释放内存。
    
- DLL 可以通过几种可能的方式动态分配和释放它：**用户** 分配和释放、新建和删除等。  
    
- 它可以由用户动态Excel。
    
鉴于 /  **XLOPER XLOPER12** 内存的可能来源数量以及 **XLOPER** /  **XLOPER12** 可能分配了该内存的情况数，此主题似乎很难理解，这并不奇怪。 但是，如果您遵循多个规则和准则，复杂性可能会大大降低。 
  
### <a name="rules-for-working-with-xloperxloper12"></a>使用 XLOPER/XLOPER12 的规则

- 不要尝试释放内存或覆盖作为参数传递给 XLL 函数的 **XLOPERs** /  **XLOPER12。** 您应将此类参数视为只读。 有关详细信息，请参阅 XLL 开发中的已知问题中的"通过修改就地参数返回 **XLOPER** [Excel XLOPER12"。](known-issues-in-excel-xll-development.md) 
    
- 如果Excel在调用 C API 时为返回到 DLL 的 /  **XLOPER XLOPER12** 分配了内存： 
    
  - 当不再需要 **XLOPER** /  **XLOPER12** 时，必须使用对 [xlFree 的](xlfree.md)调用释放内存。 请勿使用任何其他方法（如释放或删除）释放内存。
    
  - 如果返回的类型是 **xltypeMulti**，请不要覆盖数组内的任何 /  **XLOPER XLOPER12，** 尤其是在它们包含字符串时，尤其是在您尝试用字符串覆盖的位置。
    
  - 如果要将 /  **XLOPER XLOPER12** 返回到 Excel 作为 DLL 函数的返回值，则必须告诉 Excel有一些内存Excel完成后必须释放。 
    
- 只能对作为 C API 调用的返回值创建的 **XLOPER** XLOPER12 调用 **xlFree。** /   
    
- 如果 DLL 为 **要** 作为 DLL 函数的返回值返回到 Excel 的 /  **XLOPER XLOPER12** 分配了内存，则必须告诉 Excel存在 DLL 必须释放的内存。 
    
### <a name="guidelines-for-memory-management"></a>内存管理指南

- 在用于分配和释放内存的方法的 DLL 中保持一致。 避免混合方法。 一个好方法是将所使用的方法包装在内存类或结构中，可以在其中更改所使用的方法，而无需在许多位置更改代码。
    
- 在 DLL 内创建 **xltypeMulti** 数组时，为字符串分配内存的方式保持一致：始终为字符串动态分配内存或始终使用静态内存。 如果这样做，在释放内存时，你将知道必须始终释放或从不释放字符串。 
    
- 复制已Excel **XLOPER** /  **XLOPER12** Excel分配的内存的深层副本。
    
- 不要将Excel的字符串 **XLOPER** /  **XLOPER12** 置于 **xltypeMulti** 数组中。 创建字符串的深层副本，并存储指向数组中副本的指针。 
    
## <a name="freeing-excel-allocated-xloperxloper12-memory"></a>释放Excel-Allocated XLOPER/XLOPER12 内存

请考虑以下 XLL 命令，该命令使用 **xlGetName** 获取包含 DLL 的路径和文件名的字符串，并使用 **xlcAlert** 在警报对话框中显示它。
  
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

当函数不再需要 **xDllName** 指向的内存时，它可以使用对 [xlFree](xlfree.md)函数（一个仅 DLL C API 函数）的调用释放它。 
  
**xlFree** 函数完全记录在函数引用部分 (请参阅 [C API Functions That Can Be Called Only from a DLL or XLL](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)) ， but be aware of the following：
  
- 可以在对 xlFree 的单个调用中将指针传递给多个 /  **XLOPER XLOPER12，** 这仅受 Excel 2003 年 200) 7 年 Excel 年 255 年 2003 年 255 年 Excel (30 的运行版本所支持的函数参数数限制。
    
- **xlFree** 将包含的指针设置为 **NULL，** 以确保释放已释放的 **XLOPER** /  **XLOPER12** 的尝试是安全的。 **xlFree** 是唯一一个修改其参数的 C API 函数。 
    
- 你可以安全地在用于 C API 调用的返回值的任何 **XLOPER XLOPER12** 上调用 **xlFree，** 无论它是否包含指向内存的 /  指针。 
    
## <a name="returning-xloperxloper12s-to-be-freed-by-excel"></a>返回 XLOPER/XLOPER12s 以由 Excel

假设您要修改上一节中的示例命令，并更改为在传递 **布尔** **true** 参数时返回 DLL 路径和文件名的工作表函数 **，#N/A。** 很明显，在将字符串内存返回到字符串内存之前，无法调用 **xlFree** Excel。 但是，如果在某些时候未释放它，则每次调用函数时，外接程序都会泄漏内存。 若要解决此问题，可以在 **XLOPER** XLOPER12 的 **xltype** 字段中设置位，在 /  xlcall.h 中定义为 **xlbitXLFree。** 设置此设置Excel复制完值后必须释放返回的内存。 
  
### <a name="example"></a>示例

以下代码示例演示上一节中转换为 XLL 工作表函数的 XLL 命令。
  
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

使用 **XLOPER** XLOPER12 的 XLL 函数必须声明为采用并返回指向 /  **XLOPER** /  **XLOPER12** 的指针。 此示例中对函数中的静态 **XLOPER12** 的使用不是线程安全的。 你可以错误地将此函数注册为线程安全函数，但存在在另一个线程完成之前被一个线程覆盖 **xRtnValue** 的风险。 
  
必须在调用 **分配 xlbitXLFree** 的 Excel设置 xlbitXLFree。 如果在之前设置它，它将被覆盖，并且没有你需要的效果。 如果你打算在将值返回到工作表之前，在调用另一个 C API 函数时将该值用作参数，应在任何此类调用后设置此位。 否则，在检查 **XLOPER** /  **XLLOPER12** 类型之前，将混淆未屏蔽此位的函数。 
  
## <a name="returning-xloperxloper12s-to-be-freed-by-the-dll"></a>返回 DLL 要释放的 XLOPER/XLOPER12

当 XLL 为 **XLOPER XLOPER12** 分配了内存，并且想要将内存返回到 /  **XLOPER12** 时，会出现与此类似的Excel。 Excel可在 **XLOPER XLOPER12** 的 **xltype** 字段中设置的另一位，在 /  xlcall.h 中定义为 **xlbitDLLFree。** 
  
当 Excel 收到具有此位集的 **XLOPER** XLOPER12 时，它会尝试调用一个应由 XLL 导出的函数，称为 /  [xlAutoFree](xlautofree-xlautofree12.md) (的 **XLOPER**) 或 **xlAutoFree12** (for **XLOPER12** s) 。 此函数在函数参考中进行了更全面 (请参阅加载项管理器和 [XLL](add-in-manager-and-xll-interface-functions.md) 接口函数) ，但此处提供了一个最小实现示例。 它的目的是以与 **最初分配** 方式一致的方式释放 /  **XLOPER XLOPER12** 内存。 
  
### <a name="examples"></a>示例

以下示例函数执行与上一函数相同的操作，只不过它在 DLL 名称之前包含文本"此 DLL 的完整路径名是"。
  
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

导出上一函数的 **XLL 中 xlAutoFree12** 的最少足够实现如下所示。 
  
```cs
void WINAPI xlAutoFree12(LPXLOPER12 p_oper)
{
    if(p_oper->xltype == (xltypeStr | xlbitDLLFree))
        free(p_oper->val.str);
}
```

此实现仅在 XLL 仅返回 **XLOPER12** 字符串，并且这些字符串仅使用可能oc 进行 **分配时才足够**。 请注意，测试 
  
 ` if(p_oper->xltype == xltypeStr) `
  
在这种情况下将失败，因为已设置 **xlbitDLLFree。** 
  
通常， **应实现 xlAutoFree** 和 **xlAutoFree12，** 以便它们释放与 XLL 创建的 **xltypeMulti** 数组和 **xltypeRef** 外部引用关联的内存。 
  
你可能决定实现 XLL 函数，以便它们全部返回动态分配的 **XLOPER** 和 **XLOPER12。** 在这种情况下，你需要在所有此类 XLOPER 和 **XLOPER12** 上设置 **xlbitDLLFree，** 而不管子类型如何。 你还需要实现 **xlAutoFree** 和 **xlAutoFree12，** 以便释放此内存以及 **指向 XLOPER** /  **XLOPER12** 内的任何内存。 此方法是保证返回值线程安全的一种方法。 例如，可以按如下方式重写上一个函数。
  
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

有关 **xlAutoFree** 和 **xlAutoFree12** 的信息，请参阅 [xlAutoFree/xlAutoFree12。](xlautofree-xlautofree12.md)
  
## <a name="returning-modify-in-place-arguments"></a>返回就地修改参数

Excel XLL 函数通过就地修改参数来返回值。 只能使用作为指针传入的参数来这样做。 若要如此工作，必须注册函数，以告知用户Excel将修改哪个参数。 
  
此方法返回值的方法受可通过指针传递的所有数据类型的支持，但对于以下类型尤其有用：
  
- 长度计数字符串和以 null 结束的 ASCII 字节字符串
    
- 自 2007 年 7 (起，长度计数字符串和以 null Excel Unicode 宽字符) 
    
- **FP** 浮点数组 
    
- **FP12** 浮点数组 (2007 Excel起)  
    
> [!NOTE]
> 不应尝试以此方式返回 **XLOPER** 或 **XLOPER12。** 有关详细信息，请参阅 [Excel XLL 开发中的已知问题](known-issues-in-excel-xll-development.md)。 
  
使用此技术（而不只是使用 return 语句）的优点是，Excel为返回值分配内存。 一Excel读取完返回的数据后，它将释放内存。 这会将内存管理任务从 XLL 函数中消失。 此技术是线程安全的：如果由不同线程上的Excel调用，则每个线程上的每个函数调用都有其自己的缓冲区。
  
它尤其适用于前面列出的数据类型，因为对于简单字符串和 /  **FP** FP12 数组，不存在用于调用回 DLL 以释放 XLOPER **XLOPER12** s 的内存回发机制。 /   因此，当返回 DLL 创建的字符串或浮点数组时，有以下选择： 
  
- 将永久性指针设置为动态分配的缓冲区，返回指针。 下次调用函数 (1) 时，检查指针是否为空， (2) 释放上一次调用中分配的资源，将指针重置为 null， (3) 将指针重新用于新分配的内存块。
    
- 在不需要释放的静态缓冲区创建字符串和数组，并返回指向该缓冲区的指针。
    
- 就地修改参数，将字符串或数组直接写入由 Excel。
    
否则，必须创建 **XLOPER** /  **XLOPER12**，并使用 **xlbitDLLFree** 和 **xlAutoFree** /  **xlAutoFree12** 释放资源。 
  
在向传递的参数类型与返回值类型相同的情况下，最后一个选项可能最简单。 需要记住的关键点是，缓冲区大小有限，你必须非常小心，不要溢出它们。 如果出错，可能会Excel。 接下来将讨论字符串和 /  **FP FP12** 数组的缓冲区大小。 
  
## <a name="strings"></a>字符串

字符串内存管理问题可能是应用程序和外接程序中不稳定的最常见原因。鉴于处理字符串的方式有多种，可能可以理解：以 null 结束或长度计算 (或两) ;静态或动态缓冲区;固定长度或几乎无限制长度;操作系统托管内存 (例如，OLE Bstr) 或非托管字符串;等。
  
C/C++ 程序员最熟悉以 null 结束的字符串。 标准 C 库旨在处理此类字符串。 代码中的静态字符串文本编译为以 null 结尾的字符串。 或者，Excel使用长度计数字符串，这些字符串通常不以 null 结束。 这些事实的组合需要 DLL/XLL 中关于如何处理字符串和字符串内存的清晰且一致的方法。
  
最常见的问题如下所示：
  
- 将空指针或无效指针传递给需要有效指针的函数，并且不会或不能检查指针本身的有效性。
    
- 不或无法根据要写入的字符串的长度检查缓冲区长度的函数溢出字符串缓冲区边界。
    
- 尝试释放静态或已释放或未按照与释放方式一致的方式分配字符串缓冲区内存。
    
- 通常，在经常调用的函数中，由于字符串被分配然后没有释放，内存会泄漏。
    
### <a name="rules-for-strings"></a>字符串的规则

与 **XLOPER** /  **XLOPER** 一样，应遵循一些规则和准则。 指南与上一节中提供的准则相同。 此处的规则是专门针对字符串的规则扩展。
  
 **规则：**
  
- 不要尝试释放内存或覆盖字符串 **XLOPER** /  **XLOPER12** s 或作为参数传递给 XLL 函数的简单长度计数字符串或以 null 结尾的字符串。 您应将此类参数视为只读。
    
- 其中Excel为字符串 **XLOPER** XLOPER12 分配内存作为 C API 回调函数的返回值，使用 xlFree 释放它，或设置 /  **xlbitXLFree（** 如果从 XLL 函数返回到 Excel）。  
    
- 当 DLL 为 **XLOPER** XLOPER12 动态分配字符串缓冲区时，按照完成时分配的方式释放该缓冲区;如果从 XLL 函数将 /  xlbitDLLFree 返回到 Excel，然后在 **xlAutoFree** xlAutoFree12 中释放它，则设置 **xlbitDLLFree。** /  
    
- 如果Excel为调用 C API 时返回到 DLL 的 **xltypeMulti** 数组分配了内存，请不要覆盖数组内的任何字符串 **XLOPER** /  **XLOPER12。** 此类数组只能使用 **xlFree** 释放，或者，如果由 XLL 函数返回，则通过设置 **xlbitXLFree** 释放。
    
### <a name="string-types-supported"></a>支持的字符串类型

**C API xltypeStr XLOPER/XLOPER12s**

|**字节字符串：**XLOPER****|**宽字符字符串：**XLOPER12****|
|:-----|:-----|
|Excel 的所有版本  <br/> |自 Excel 2007 起  <br/> |
|最大长度：255 个扩展的 ASCII 字节  <br/> |最大长度 32，767 Unicode 字符  <br/> |
|First (unsigned) byte = length  <br/> |第一个 Unicode 字符 = 长度  <br/> |
   
> [!IMPORTANT]
> 不要假定 XLOPER 或 **XLOPER12** 字符串的 null 终止。  
  
**C/C++ 字符串**

|**字节字符串**|**宽字符串**|
|:-----|:-----|
|以 Null (**字符** *) "C" 最大长度：255 个扩展的 ASCII 字节  <br/> |以 Null (wchar_t ***)** "C%" 最大长度 32，767 Unicode 字符  <br/> |
|长度计数 (无符号 **字符** *) "D"  <br/> |长度计算 **(wchar_t** *) "D%"  <br/> |
   
### <a name="strings-in-xltypemulti-xloperxloper12-arrays"></a>xltypeMulti XLOPER/XLOPER12 数组中的字符串

在某些情况下，Excel创建用于 DLL/XLL 的 **xltypeMulti** 数组。 一些 XLM 信息函数将返回此类数组。 例如，C API 函数 **xlfGetWorkspace** 在传递参数  *44*  时返回一个包含字符串的数组，该字符串描述所有当前注册的 DLL 过程。 C API 函数 **xlfDialogBox** 返回其数组参数的修改副本，其中包含字符串的深层副本。 XLL 遇到 **xltypeMulti** 数组的最常见方式可能是，它作为参数传递给 XLL 函数，或者它已通过范围引用强制转换为此类型。 在后一种情况下，Excel在源单元格中创建字符串的深层副本，并指向数组中的这些字符串。 
  
在要修改 DLL 中的这些字符串的地方，应制作自己的深层副本。 当您创建自己的 **xltypeMulti** 数组时，不应将Excel的 **字符串 XLOPER** /  **XLOPER12** 放在其中。 这有风险：你以后无法正确释放它们，或者完全无法释放它们。 同样，应制作字符串的深层副本，并存储指向数组中副本的指针。
  
 **示例**
  
以下示例函数创建长度计数型 Unicode 字符串的动态分配副本。 请注意，调用方最终必须使用 **delete**[] 释放此示例中分配的内存，并且不会假定源字符串以 null 结尾。 出于安全需要，复制字符串将被截断，并且不会以 null 结尾。
  
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

然后，可以安全地使用此函数复制 **XLOPER12，** 如下面的可导出 XLL 函数所示，该函数返回其参数的副本（如果它是字符串）。 所有其他类型作为零长度字符串返回。 请注意，不处理范围 - 函数返回 **#VALUE！。** 该函数必须注册为采用类型 U 参数，以便引用作为值传入。 这相当于内置工作表函数 **T ()****除了 AsText** 还会将错误转换为零长度字符串。 此代码示例假定 **xlAutoFree12** 使用 delete 释放传入指针及其 **内容**。
  
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

### <a name="returning-modify-in-place-string-arguments"></a>返回就地修改字符串参数

注册为类型 **F、G、F%** 和 **G%** 的参数可以就地进行修改。  当Excel为这些类型准备字符串参数时，它将创建最大长度缓冲区。 然后它将参数字符串复制到该字符串中，即使此字符串要短得多。 这使 XLL 函数能够直接将返回值写入同一内存。 
  
为这些类型设置的缓冲区大小如下所示：
  
- **字节字符串** ：256 个字节，包括长度计数器 (类型 G) 或 null-termination (类型 F) 。 
    
- **Unicode** 字符串：32，768 个宽字符 (65，536 字节) 包括长度计数器 (类型 G%) 或空终止 (类型 F%) 。 
    
> [!NOTE]
> 您无法直接从 VBA Visual Basic for Applications (调用此类) ，因为您无法确保已分配了一个非常大的缓冲区。 只有在显式传递了足够大的缓冲区时，才能安全地从另一个 DLL 调用此类函数。 
  
下面是一个 XLL 函数示例，该函数使用标准库函数 **wcsrev** 反向传递以 null 结尾的宽字符串。 本例中的参数将注册为 **F% 类型**。
  
```cs
void WINAPI reverse_text_xl12(wchar_t *text)
{
    _wcsrev(text);
}
```

## <a name="persistent-storage-binary-names"></a>持久存储 (二进制) 

二进制名称定义并关联到二进制块，即与工作簿一起存储的非结构化数据。 它们使用 [xlDefineBinaryName](xldefinebinaryname.md)函数创建，并且使用 [函数 xlGetBinaryName](xlgetbinaryname.md)检索数据。 这两个函数在函数参考 (请参阅 [C API Functions That Can Be Called Only from a DLL or XLL](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)) ， and both use the **xltypeBigData** **XLOPER** /  **XLOPER12**. 
  
有关限制二进制名称的实际应用程序的已知问题的信息，请参阅[XLL](known-issues-in-excel-xll-development.md)开发中的已知Excel问题。
  
## <a name="excel-stack"></a>Excel堆栈

Excel加载的所有 DLL 共享其堆栈空间。 堆栈空间通常足以供普通使用，只要你遵循以下准则，就无需担心它： 
  
- 不要将非常大的结构作为参数传递给堆栈上的值函数。 传递指针或引用。
    
- 请勿在堆栈上返回大型结构。 返回指向静态或动态分配的内存的指针，或使用通过引用传递的参数。
    
- 请勿在函数代码中声明非常大的自动变量结构。 如果需要，请将其声明为静态。
    
- 除非确定递归深度始终浅表，否则不要以递归调用函数。 请尝试改为使用循环。
    
当 DLL 使用 C API Excel回调用时，Excel首先检查堆栈上是否有足够的空间进行可能进行的最差情况使用调用。 如果它认为空间可能不足，则即使该特定呼叫实际上可能有足够的空间，呼叫也将无法安全。 在这种情况下，回调返回代码 **xlretFailed**。 对于 C API 和堆栈的普通使用，这不太可能是 C API 调用失败的原因。
  
如果你担心或只是想知道，或者希望消除堆栈空间不足作为未说明故障的原因，可以通过调用 [xlStack](xlstack.md) 函数来了解存在多少堆栈空间。 
  
## <a name="see-also"></a>另请参阅



[Excel 中的多线程重新计算](multithreaded-recalculation-in-excel.md)
  
[线程中的多线程和内存Excel](multithreading-and-memory-contention-in-excel.md)
  
[开发 Excel XLL](developing-excel-xlls.md)

