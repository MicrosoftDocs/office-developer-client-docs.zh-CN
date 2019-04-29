---
title: Excel 中的内存管理
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
keywords:
- xloper12 memory [excel 2007], 管理 excel 中的内存, excel 堆栈, 字符串 [excel 2007], 管理内存, excel 中的内存管理, XLOPER memory [excel 2007], memory [excel 2007], 管理准则
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
# <a name="memory-management-in-excel"></a>Excel 中的内存管理

 **适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
如果要创建高效而稳定的 xll, 则内存管理是最重要的考虑因素。 无法正常管理内存可能会导致 Microsoft Excel 中的一系列问题, 从很少的问题 (例如, 低内存分配和初始化和小内存泄漏) 到重大问题 (如 Excel destabilization)。
  
Mismanagement 的内存是严重的加载项相关问题最常见的来源。 因此, 应生成项目, 并在内存管理上采用一致且思维的策略。 
  
随着多线程工作簿的重新计算, 内存管理在 Microsoft Office Excel 2007 中变得更加复杂。 如果要创建和导出线程安全的工作表函数, 则必须管理在多个线程需要进行访问时可能发生的冲突。
  
对于以下三种数据结构类型, 存在内存注意事项:
  
- **XLOPER**s 和**XLOPER12**s
    
- 不在**XLOPER**或**XLOPER12**中的字符串
    
- **FP**和**FP12**数组 
    
## <a name="xloperxloper12-memory"></a>XLOPER/XLOPER12 内存

**XLOPER**/ **XLOPER12**数据结构具有一些子类型, 其中包含指向内存块的指针, 即字符串 (**xltypeStr**)、数组 (**xltypeMulti**) 和外部引用 (**xltypeRef**)。 另请注意, **xltypeMulti**数组可以包含 string **XLOPER**/ **XLOPER12s** , 后者又指向其他内存块。 
  
可以通过以下几种方式创建**XLOPER**/ **XLOPER12** : 
  
- 当准备要传递给 XLL 函数的参数时, Excel
    
- 在 C API 调用中返回**XLOPER**或**XLOPER12**时 Excel 
    
- 创建要传递给 C API 调用的参数时的 DLL
    
- 在创建 XLL 函数返回值时的 DLL
    
可以通过以下几种方式分配其中一种内存指向的类型中的内存块:
  
- 它可以是任何函数代码外部 DLL 中的静态块, 在这种情况下, 您不必分配或释放内存。
    
- 它可以是某些函数代码内 DLL 中的静态块, 在这种情况下, 您不必分配或释放内存。
    
- 可以通过几种可能的方式动态分配和释放 DLL: **malloc**和**free**、 **new**和**delete**等。
    
- 它可以由 Excel 动态分配。
    
给定**XLOPER**/ **XLOPER12**内存的可能来源, 以及**XLOPER**/ **XLOPER12**可能已分配该内存的情况数, 此主题不会令人吃惊看起来非常困难。 但是, 如果您遵循几个规则和准则, 则可以大大减少复杂性。 
  
### <a name="rules-for-working-with-xloperxloper12"></a>使用 XLOPER/XLOPER12 的规则

- 请勿尝试释放内存或覆盖作为参数传递给 XLL 函数的**XLOPERs**/ **XLOPER12**s。 应将此类参数视为只读。 有关详细信息, 请参阅[Excel XLL 开发中的已知问题](known-issues-in-excel-xll-development.md)中的 "通过修改参数就地返回**XLOPER**或**XLOPER12** "。
    
- 如果 Excel 已为**XLOPER**/ **XLOPER12**分配了内存, 并且在对 C API 的调用中返回到 DLL: 
    
  - 当不再需要使用对[xlFree](xlfree.md)的调用的**XLOPER**/ **XLOPER12**时, 必须释放内存。 请勿使用任何其他方法 (如 "免费" 或 "删除") 来释放内存。
    
  - 如果返回的类型为**xltypeMulti**, 请勿覆盖数组中的任何**XLOPER**/ **XLOPER12**s, 尤其是当它们包含字符串时, 尤其是您尝试使用字符串覆盖的位置。
    
  - 如果要将**XLOPER**/ **XLOPER12**作为 DLL 函数的返回值返回到 excel, 则必须告诉 excel, 它是 excel 在完成时必须释放的内存。 
    
- 您只能在作为返回值为 C API 调用而创建的**XLOPER**/ **XLOPER12**上调用**xlFree** 。 
    
- 如果您的 dll 已为**XLOPER**/ **XLOPER12**分配了内存, 而您希望以 dll 函数的返回值的形式返回到 excel, 则必须告诉 Excel dll 必须释放的内存。 
    
### <a name="guidelines-for-memory-management"></a>内存管理指南

- 在您用于分配和释放内存的方法中的 DLL 中保持一致。 避免混合方法。 一种很好的方法是包装您在内存类或结构中使用的方法, 在该方法中您可以更改使用的方法, 而无需在很多位置更改代码。
    
- 在 DLL 中创建**xltypeMulti**数组时, 应在为字符串分配内存的方式中保持一致: 始终为它们动态分配内存或始终使用静态内存。 如果执行此操作, 则释放内存时, 您将知道必须始终或从不释放字符串。 
    
- 复制 excel 创建的**XLOPER**/ **XLOPER12**时, 请制作 excel 分配的内存的深层副本。
    
- 请勿将 Excel 分配的字符串**XLOPER**/ **XLOPER12**s 放在**xltypeMulti**数组中。 制作字符串的深层副本并将指针存储到数组中的副本。 
    
## <a name="freeing-excel-allocated-xloperxloper12-memory"></a>释放 Excel 分配的 XLOPER/XLOPER12 内存

请考虑以下 XLL 命令, 该命令使用**xlGetName**获取包含 DLL 的路径和文件名的字符串, 并使用**xlcAlert**将其显示在警报对话框中。
  
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

当函数不再需要**xDllName**所指向的内存时, 它可以使用对[xlFree 函数](xlfree.md)(仅限 DLL 的 C API 函数之一) 的调用来释放它。 
  
"函数引用" 一节中对**xlFree**函数进行了充分说明 (请参阅只能[从 DLL 或 XLL 调用的 C API 函数](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)), 但请注意以下几点:
  
- 可以在对**xlFree**的一次调用中将指针传递给多个**XLOPER**/ **XLOPER12**s, 这只受运行版本的 excel 中支持的函数参数数 (在 excel 2003 中为 30, 255 从 excel 2007 开始)。
    
- **xlFree**将包含的指针设置为**NULL** , 以确保释放已释放的**XLOPER**/ **XLOPER12**的尝试是安全的。 **xlFree**是修改其参数的唯一 C API 函数。 
    
- 您可以在任何**XLOPER**/ **XLOPER12**上安全地调用**xlFree** , 以用于对 C API 的调用的返回值, 而不管它是否包含指向内存的指针。 
    
## <a name="returning-xloperxloper12s-to-be-freed-by-excel"></a>返回要由 Excel 释放的 XLOPER/XLOPER12s

假设您想要修改上一节中的示例命令, 并将其更改为在传递**布尔****值 true**参数时返回 DLL 路径和文件名的工作表函数, 否则 **#N/a** 。 很明显, 在将字符串内存返回到 Excel 之前, 无法调用**xlFree**以释放字符串内存。 但是, 如果在某些情况下, 加载项将在每次调用函数时泄漏内存。 若要解决此问题, 您可以在**XLOPER**/ **XLOPER12**的 " **xltype** " 字段中设置一个位, 在 xlcall.h 中定义为**xlbitXLFree** 。 设置它告诉 Excel 它必须在完成复制值后释放返回的内存。 
  
### <a name="example"></a>示例

下面的代码示例显示了前一节中转换为 xll 工作表函数的 XLL 命令。
  
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

使用**XLOPER**/ **XLOPER12**s 的 XLL 函数必须声明为采用 XLOPER XLOPER12 s, 并将指针返回到****/ **** s。 此函数中的静态**XLOPER12**在此示例中的用法不是线程安全的。 您可能会错误地将此函数注册为线程安全, 但在另一个线程完成前一个线程将会将风险**xRtnValue**重写。 
  
在调用分配它的 Excel 回调之后, 必须设置**xlbitXLFree** 。 如果您设置此设置, 则它将被覆盖, 并且不会产生所需的效果。 如果要在将值返回到工作表之前在调用另一 C API 函数的同时将该值用作参数, 应在任何此类调用之后设置此位。 否则, 在检查**XLOPER**/ **XLLOPER12**类型之前, 不会混淆不屏蔽此位的函数。 
  
## <a name="returning-xloperxloper12s-to-be-freed-by-the-dll"></a>返回要由 DLL 释放的 XLOPER/XLOPER12s

当 XLL 为**XLOPER**/ **XLOPER12**分配了内存并希望将其返回到 Excel 时, 会发生类似的问题。 Excel 可识别可在**XLOPER**/ **XLOPER12**的 " **xltype** " 字段中设置的另一位, 在 xlcall.h 中定义为**xlbitDLLFree** 。 
  
当 Excel 收到具有此位集的**XLOPER**/ **XLOPER12**时, 它会尝试调用一个函数, 该函数应由称为[xlAutoFree](xlautofree-xlautofree12.md) (对于**XLOPER**s) 或**xlAutoFree12** (对于**XLOPER12**s) 的 XLL 导出。 函数引用中更全面地描述了此函数 (请参阅[外接程序管理器和 XLL 接口函数](add-in-manager-and-xll-interface-functions.md)), 但此处提供了示例最少实现。 其目的是按照与最初分配的方式一致的方式释放**XLOPER**/ **XLOPER12**内存。 
  
### <a name="examples"></a>示例

下面的示例函数与 previous 函数的作用相同, 不同之处在于它包含的文本 "此 dll 的完整路径名是 dll 名称之前"。
  
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

导出 previous 函数的 XLL 中至少有足够的**xlAutoFree12**实现将如下所示。 
  
```cs
void WINAPI xlAutoFree12(LPXLOPER12 p_oper)
{
    if(p_oper->xltype == (xltypeStr | xlbitDLLFree))
        free(p_oper->val.str);
}
```

仅当 XLL 仅返回**XLOPER12**字符串, 并且仅使用**malloc**分配这些字符串时, 此实现才足够。 请注意, 测试 
  
 ` if(p_oper->xltype == xltypeStr) `
  
在这种情况下会失败, 因为设置了**xlbitDLLFree** 。 
  
通常情况下, 应实现**xlAutoFree**和**xlAutoFree12** , 以便它们释放与 XLL 创建的**xltypeMulti**数组和**xltypeRef**外部引用关联的内存。 
  
您可以决定实现 XLL 函数, 以便它们都返回动态分配的**XLOPER**s 和**XLOPER12**s。 在这种情况下, 无论子类型如何, 都需要在所有此类**XLOPER**s 和**XLOPER12**s 上设置**xlbitDLLFree** 。 此外, 还需要实现**xlAutoFree**和**xlAutoFree12** , 以便在**XLOPER**/ **XLOPER12**中释放该内存, 也将其指向任何内存。 此方法是使返回值为安全的返回值的一种方法。 例如, 可以重写 previous 函数, 如下所示。
  
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

有关**xlAutoFree**和**xlAutoFree12**的详细信息, 请参阅[xlAutoFree/xlAutoFree12](xlautofree-xlautofree12.md)。
  
## <a name="returning-modify-in-place-arguments"></a>返回 "就地修改" 参数

Excel 允许 XLL 函数通过就地修改参数来返回值。 仅可以使用作为指针传入的参数执行此操作。 若要执行此操作, 必须注册该函数, 告知 Excel 将修改哪个参数。 
  
对于可以通过指针传递的所有数据类型, 返回值的方法均受支持, 但对于以下类型尤其有用:
  
- 长度计数和以 null 结尾的 ASCII 字节字符串
    
- 长度计数和 null 终止的 Unicode 宽字符字符串 (在 Excel 2007 中启动)
    
- **FP**浮点数组 
    
- **FP12**浮点数组 (从 Excel 2007 中开始) 
    
> [!NOTE]
> 您不应尝试以这种方式返回**XLOPER**s 或**XLOPER12**s。 有关详细信息，请参阅 [Excel XLL 开发中的已知问题](known-issues-in-excel-xll-development.md)。 
  
使用此技术 (而不是仅使用 return 语句) 的优势在于, Excel 会为返回值分配内存。 Excel 读完返回的数据后, 将释放内存。 这将使内存管理任务远离 XLL 函数。 此技术是线程安全的: 如果 Excel 在不同线程上同时调用, 则每个线程上的每个函数调用都有自己的缓冲区。
  
这对以前列出的数据类型很有用, 具体是因为用于回调 DLL 以释放为**XLOPER**/ **XLOPER12**提供的释放内存后返回的机制对于简单字符串和**FP** / 不存在。**FP12**数组。 因此, 当返回 DLL 创建的字符串或浮点数组时, 您有以下几种选择: 
  
- 将永久指针设置为动态分配的缓冲区, 返回指针。 在下一次调用函数 (1) 时, 检查指针是否不为 null, (2) 释放在上一个调用中分配的资源, 并将指针重置为 null, (3) 重用指针以获取新分配的内存块。
    
- 在不需要释放的静态缓冲区中创建字符串和数组, 并返回指向该字符串的指针。
    
- 将参数就地修改, 将字符串或数组直接写入空格设置的 Excel 中。
    
否则, 必须创建一个**XLOPER**/ **XLOPER12**, 并使用**xlbitDLLFree**和**xlAutoFree**/ **xlAutoFree12**释放这些资源。 
  
在传递与返回值类型相同的参数的情况下, 最后一个选项可能是最简单的。 要记住的关键点是缓冲区大小受到限制, 您必须非常小心地避免溢出。 此错误可能导致 Excel 崩溃。 接下来讨论字符串和**FP**/ **FP12**数组的缓冲区大小。 
  
## <a name="strings"></a>字符串

在应用程序和外接程序中, 管理字符串内存的问题最常见的原因是不稳定的原因。在给定了处理字符串的各种方式的情况下, 它可能是可理解的: null-终止或长度计数 (或两者);静态或动态缓冲区;固定长度或几乎无限制的长度;操作系统托管内存 (例如 OLE Bstr) 或非托管字符串;等。
  
c/c + + 程序员最熟悉以 null 结尾的字符串。 标准 C 库设计为可处理此类字符串。 代码中的静态字符串将编译为以 null 结尾的字符串。 或者, Excel 处理的长度计数字符串不是一般的以 null 结尾的字符串。 这些事实的组合要求 DLL/XLL 内的清晰且一致的方法, 有关如何处理字符串和字符串内存。
  
最常见的问题如下:
  
- 将 null 或无效指针传递给需要有效指针的函数, 但不会检查指针的有效性本身。
    
- 函数的界限的 overrunning, 该函数不能根据所写入的字符串的长度检查缓冲区长度, 也不能检查缓冲区长度。
    
- 尝试释放静态或已释放的字符串缓冲区内存, 或者不是以与释放方式一致的方式分配的。
    
- 由于无法分配或释放字符串而导致的内存泄漏, 通常位于频繁调用的函数中。
    
### <a name="rules-for-strings"></a>字符串规则

与**XLOPER**/ **XLOPER**s 一样, 应遵循一些规则和准则。 准则与上一节中给出的准则相同。 下面的规则是特定于字符串的规则的扩展。
  
 **原则**
  
- 请勿尝试释放内存或覆盖作为参数传递给 XLL 函数的字符串**XLOPER**/ **XLOPER12**s 或简单的长度计数或以 null 结尾的字符串。 应将此类参数视为只读。
    
- Excel 为 string **XLOPER**/ **XLOPER12**分配内存对于 C API 回调函数的返回值, 请使用**xlFree**将其释放, 如果将其从 XLL 函数返回到 Excel, 则将其设置为**xlbitXLFree** 。 
    
- 您的 DLL 动态分配**XLOPER**/ **XLOPER12**的字符串缓冲区, 请使用与完成时的分配方式一致的方式将其释放, 或者在将**** 其从 XLL 函数返回到 Excel 中时将其释放, 或者在**xlAutoFree**/  **xlAutoFree12**。
    
- 如果 Excel 已为在对 C API 的调用中返回到 DLL 的**xltypeMulti**数组分配内存, 请勿覆盖该数组中的任何字符串**XLOPER**/ **XLOPER12**s。 此类数组必须仅使用**xlFree**释放, 或者在 XLL 函数返回时通过设置**xlbitXLFree**来释放。
    
### <a name="string-types-supported"></a>支持的字符串类型

**C API xltypeStr XLOPER/XLOPER12s**

|* * 字节字符串: * * XLOPER * * * *|* * 宽字符字符串: * * XLOPER12 * * * *|
|:-----|:-----|
|Excel 的所有版本  <br/> |自 Excel 2007 起  <br/> |
|最大长度: 255 扩展 ASCII 字节  <br/> |最大长度 32767 Unicode 字符  <br/> |
|First (无符号) 字节 = 长度  <br/> |第一个 Unicode 字符 = 长度  <br/> |
   
> [!IMPORTANT]
> 请勿假定**XLOPER**或**XLOPER12**字符串的 null 终止。 
  
**c/c + + 字符串**

|**字节字符串**|**宽字符字符串**|
|:-----|:-----|
|以 Null 结尾 (**char** *) "C" 最大长度: 255 扩展 ASCII 字节  <br/> |以 Null 结尾 (**wchar_t** *) "C%" 最大长度 32767 Unicode 字符  <br/> |
|Length 计数 (**无符号 char** *) "D"  <br/> |长度计数 (**wchar_t** *) "D%"  <br/> |
   
### <a name="strings-in-xltypemulti-xloperxloper12-arrays"></a>xltypeMulti XLOPER/XLOPER12 数组中的字符串

在几种情况下, Excel 将创建一个**xltypeMulti**数组, 以便在 DLL/XLL 中使用。 其中几个 XLM 信息函数返回此类数组。 例如, 当传递参数*44*时, C API 函数**xlfGetWorkspace**返回一个包含描述所有当前注册的 DLL 过程的字符串的数组。 C API 函数**xlfDialogBox**返回其 array 参数的修改副本, 其中包含字符串的深层副本。 在 xll 遇到**xltypeMulti**数组的最常见方法是, 它已作为参数传递给 XLL 函数, 或者已通过区域引用强制转换为此类型。 在这些情况下, Excel 会在源单元格中创建字符串的深层副本, 并指向数组中的这些副本。 
  
若要在 DLL 中修改这些字符串, 应制作自己的深层副本。 当您创建自己的**xltypeMulti**数组时, 不应在其中放置 Excel 分配的字符串**XLOPER**/ **XLOPER12**s。 这种风险稍后不会正确释放它们, 也不会将其全部释放。 此外, 还应制作字符串的深层副本并将指针存储到数组中的副本。
  
 **示例**
  
下面的示例函数创建长度计数的 Unicode 字符串的动态分配副本。 请注意, 调用方必须最终使用**delete**[] 释放在此示例中分配的内存, 并且源字符串未假定为 null 终止。 如果需要安全, 则将截断复制字符串, 且不能终止 null。
  
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

然后, 可以安全地使用此函数复制**XLOPER12**, 如下面的可导出 XLL 函数中所示, 该函数返回其参数的副本 (如果它是字符串)。 所有其他类型都以零长度字符串的形式返回。 请注意, 区域不会得到处理—函数将返回 **#VALUE!**。 函数必须注册为采用类型 U 参数, 以便以值的形式传递引用。 这与内置工作表函数**T ()** 等效, 除了**AsText**也将错误转换为零长度字符串。 此代码示例假定**xlAutoFree12**使用**delete**释放传入的指针以及它的内容。
  
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

注册为**F**、 **g**、 **F%** 和**G%** 类型的参数可以就地修改。 Excel 在为这些类型准备字符串参数时, 将创建最大长度缓冲区。 然后, 它将参数字符串复制到该字符串中, 即使该字符串要短得多。 这使 XLL 函数能够将其返回值直接写入同一内存中。 
  
为这些类型单独设置的缓冲区大小如下所示:
  
- **字节字符串:** 256 个字节, 包括长度计数器 (type G) 或 null 终止 (F 类型)。 
    
- **Unicode 字符串:** 32768 宽字符 (65536 个字节), 包括长度计数器 (type G%)或 null-终止 (类型为 F%)。 
    
> [!NOTE]
> 您无法直接从 Visual Basic for Applications (VBA) 调用这样的函数, 因为您无法确保已分配足够大的缓冲区。 如果显式传递足够大的缓冲区, 则只能从另一个 DLL 安全地调用这样的函数。 
  
下面的示例展示了 XLL 函数, 该函数使用标准库函数**wcsrev**反转传入的以 null 结尾的宽字符字符串。 此示例中的参数将注册为类型**F%**。
  
```cs
void WINAPI reverse_text_xl12(wchar_t *text)
{
    _wcsrev(text);
}
```

## <a name="persistent-storage-binary-names"></a>永久性存储 (二进制名称)

二进制名称定义并与二进制块 (即非结构化的数据与工作簿一起存储) 相关联。 它们是使用函数[xlDefineBinaryName](xldefinebinaryname.md)创建的, 并使用函数[xlGetBinaryName](xlgetbinaryname.md)检索数据。 函数引用中更详细地介绍了这两个函数 (请参阅[只能从 DLL 或 XLL 调用的 C API 函数](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)), 并且两者都使用**xltypeBigData** **XLOPER**/ **XLOPER12**。 
  
有关限制二进制名称的实际应用程序的已知问题的信息, 请参阅[Excel XLL 开发中的已知问题](known-issues-in-excel-xll-development.md)。
  
## <a name="excel-stack"></a>Excel 堆栈

Excel 将与它所加载的所有 dll 共享其堆栈空间。 堆栈空间通常不足以满足普通使用, 并且只要您遵循几条准则, 就不必担心它。 
  
- 不要通过堆栈上的值将非常大的结构作为参数传递给函数。 改为传递指针或引用。
    
- 不要在堆栈上返回大型结构。 将指针返回到静态或动态分配的内存, 或使用通过引用传递的参数。
    
- 不要在函数代码中声明非常大的自动变量结构。 如果需要, 请将它们声明为静态。
    
- 请勿以递归方式调用函数, 除非您确信递归的深度始终为浅。 请尝试改为使用循环。
    
当 DLL 使用 C API 回调 excel 时, Excel 首先检查堆栈中是否有足够的空间, 可以进行最差的使用情况调用。 如果它认为可能没有足够的聊天室, 则该调用将无法安全, 即使该特定调用可能有足够的空间。 在这种情况下, 回调将返回代码**xlretFailed**。 对于 c api 和堆栈的普通使用, 不太可能导致 c api 调用失败。
  
如果您关注或只是想要避免由于不可解释的故障而导致堆栈空间不足, 则可以使用对[xlStack](xlstack.md)函数的调用来查明堆栈空间的数量。 
  
## <a name="see-also"></a>另请参阅



[Excel 中的多线程重新计算](multithreaded-recalculation-in-excel.md)
  
[Excel 中的多线程和内存争用](multithreading-and-memory-contention-in-excel.md)
  
[开发 Excel XLL](developing-excel-xlls.md)

