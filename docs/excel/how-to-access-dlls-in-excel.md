---
title: 在 Excel 中访问 DLL
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
keywords:
- 访问 [excel 2007] 的 dll，在 Excel 中访问 Dll [Excel 2007]
localization_priority: Normal
ms.assetid: e2bfd6ea-efa3-45c1-a5b8-2ccb8650c6ab
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: bfb562b6bbe824124c6b5a691745d076720ee004
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773753"
---
# <a name="access-dlls-in-excel"></a>在 Excel 中访问 DLL

**适用于** Excel 2013 | Office 2013 | Visual Studio 
  
您可以访问的 DLL 函数或几种方式在 Microsoft Excel 中的命令：
  
- 通过 Microsoft Visual Basic for Applications (VBA) 代码模块中的函数或命令进行了可使用**Declare**语句。 
    
- 通过使用**呼叫**或**注册**函数 XLM 宏表。 
    
- 直接从工作表或从自定义项中用户界面 (UI)。
    
本文档不适用于 XLM 函数。 建议您将使用其他两种方法。
  
要访问直接从工作表或在 UI 中的自定义项，函数或命令必须首先注册使用 Excel。 有关注册命令和函数的信息，请参阅[在 Excel 中访问 XLL 代码](accessing-xll-code-in-excel.md)。
  
## <a name="calling-dll-functions-and-commands-from-vba"></a>从 VBA 中调用的 DLL 函数和命令

可以使用**Declare**语句中访问 DLL 函数和 VBA 中的命令。 此语句包含一个语法的命令，另一个用于函数。 
  
- **语法 1-命令**
    
  ```vb
  [Public | Private] Declare Sub name Lib "libname" [Alias "aliasname"] [([arglist])]
  ```

- **语法 2-函数**
    
  ```vb
  [Public | Private] Declare Function name Lib "libname" [Alias "aliasname"] [([arglist])] [As type]
  ```

可选的**公用**和**专用**关键字指定导入函数的作用域： 整个 Visual Basic 项目或只是 Visual Basic 模块，分别。 名称是想要在 VBA 代码中使用的名称。 如果这与在 DLL 中的名称，您必须使用别名"aliasname"说明符，并应授予函数的名称，如 DLL 导出。 如果您想要访问的 DLL 函数引用一个 DLL 的序号，必须提供别名，即序号前缀**#**。
  
命令应返回**void**。 函数的 VBA 应返回类型可以识别**ByVal**。 这意味着，更轻松地通过修改就地参数返回某些类型： 字符串、 数组、 用户定义类型和对象。
  
> [!NOTE]
> VBA 无法检查参数列表和 Visual Basic 模块中所述的返回在 DLL 中编码的相同。 由于错误可能导致 Excel 崩溃，您应从仔细，检查此自己。 
  
不通过引用或指针传递函数或命令的参数，当他们前面必须有**arglist**声明中的**ByVal**关键字。 在 C/c + + 函数采用指针参数或 c + + 函数采用引用参数时，应将它们传递**ByRef**。 可以从参数省略**ByRef**关键字列出因为它是 VBA 中的默认值。 
  
### <a name="argument-types-in-cc-and-vba"></a>C/c + + 和 VBA 中的参数类型

比较 C/c + + 和 VBA 中的参数类型的声明时，您应注意以下。
  
- VBA**字符串**作为指针传递到字节字符串 BSTR 结构时传递 ByVal，和为指向时传递的指针的指针**ByRef**。
    
- VBA**变量**包含字符串作为指针传递到 Unicode 宽字符字符串 BSTR 结构时传递**ByVal**，和为指向时传递的指针的指针**ByRef**。
    
- VBA**整数**是等价于签名 short C/c + + 中一个 16 位类型。 
    
- VBA**长**是等价于签名 int C/c + + 中的 32 位类型。 
    
- VBA 和 C/c + + 允许用户定义的数据类型的定义分别使用**类型**和**结构**语句。 
    
- VBA 和 C/c + + 支持为 C/c + + 为 VARIANT Windows OLE/COM 头文件中定义的**Variant**数据类型。 
    
- VBA 数组是 OLE **SafeArrays**，定义 C/c + + Windows OLE/COM 头文件中为**SAFEARRAY**。
    
- 作为类型**CY**，在 Windows 标头文件 wtypes.h 中, 定义的结构传递 VBA**货币**数据类型时传递**ByVal**，并作为一个指向此时传递**ByRef**。
    
在 VBA 中，在用户定义的数据类型的数据元素而在 Visual Studio 中，默认情况下，它们被打包到 8 字节边界至 4 字节边界，打包。 因此，则必须将中的 C/c + + 结构定义`#pragma pack(4) … #pragma pack()`块，以避免要对齐的元素。 
  
下面是等效的用户类型定义的示例。
  
```vb
Type VB_User_Type
    i As Integer
    d As Double
    s As String
End Type

```

```cpp
#pragma pack(4)
struct C_user_type
{
    short iVal;
    double dVal;
    BSTR bstr; // VBA String type is a byte string
}
#pragma pack() // restore default

```

VBA 支持更大的范围的值在某些情况下不是 Excel 支持。 双 VBA 为 IEEE 兼容，支持 subnormal 是当前向下舍入为工作表上零的数字。 VBA**日期**类型可以表示为使用负序列化的日期的 1-Jan-0100年早日期。 大于或等于零，则 Excel 将只允许序列化的日期。 VBA**货币**类型 — 扩展的 64 位整数 — 可以实现准确性不支持 8 字节双精度数，并因此不匹配工作表中。 
  
Excel 仅将下列类型的变量传递到 VBA 用户定义函数。
  
|**VBA 数据类型**|**C/c + + 变量类型的位标志**|**说明**|
|:-----|:-----|:-----|
|双精度数  <br/> |**VT_R8** <br/> ||
|Boolean  <br/> |**VT_BOOL** <br/> ||
|Date  <br/> |**VT_DATE** <br/> ||
|字符串  <br/> |**VT_BSTR** <br/> |OLE Bstr 字节字符串  <br/> |
|Range  <br/> |**VT_DISPATCH** <br/> |范围和单元格引用  <br/> |
|包含数组的 variant  <br/> |**VT_ARRAY** | **VT_VARIANT** <br/> |字面数组  <br/> |
|Ccy  <br/> |**VT_CY** <br/> |扩展允许的准确性的 4 个小数位的 64 位整数。  <br/> |
|包含错误的 variant  <br/> |**VT_ERROR** <br/> ||
||**VT_EMPTY** <br/> |空单元格或省略的参数  <br/> |
   
之处在于此函数返回的范围的值，如果调用时带有引用的类型，您可以检查在 VBA 中使用**VarType**，传入的 Variant 的类型。 若要确定**变量****范围**reference 对象，您可以使用**IsObject**函数。 
  
您可以创建通过将其**Value**属性分配给**Variant**包含在**范围**中的 VBA 变量型数组的**变量**。 任何源区域中的单元格时使用的区域设置中强制标准的货币格式设置格式转换为**货币**类型的数组元素。 任何格式设置为日期转换为**日期**类型的数组元素的单元格。 单元格包含字符串转换为宽字符**BSTR**变量。 含有错误的单元格均转换为**VT_ERROR**类型的**变量**。 包含**布尔值** **True**或**False**的单元格均转换为**VT_BOOL**类型的**变量**。 
  
> [!NOTE]
> **Variant 类型的值**将存储**True**为-1 和**False**作为 0。 不是日期格式数字或货币金额会转换为的类型**VT_R8**变体。 
  
### <a name="variant-and-string-arguments"></a>Variant 类型的值和字符串参数

Excel 适用于内部的宽字符 Unicode 字符串。 当 VBA 用户定义函数声明为采用**字符串**参数时，Excel 提供将字符串转换为字节字符串的特定于区域设置的方式。 如果您希望您传递一个 Unicode 字符串的函数，您 VBA 用户定义函数应接受**Variant**而不是**字符串**参数。 您的 DLL 函数然后可以接受从 VBA 的**Variant** BSTR 宽字符 string。 
  
若要从 DLL VBA 返回 Unicode 字符串，您应修改就地**Variant**字符串参数。 为此，您必须声明为**Variant**和在 C/c + + 代码中，采用指针的 DLL 函数和声明为 VBA 代码中的参数`ByRef varg As Variant`。 应释放的旧的字符串内存，并使用仅在 DLL 中的 OLE Bstr 字符串函数创建新的字符串值。
  
若要从 DLL VBA 返回一个字节的字符串，您应修改就地字节字符串 BSTR 参数。 为此，您必须声明为指针指向 BSTR 和 C/c + + 代码，采用指针的 DLL 函数并声明中作为**ByRef varg As String**VBA 代码的参数。
  
仅应处理传递 VBA 中的以下方式使用 OLE BSTR 字符串函数以避免出现内存相关问题的字符串。 例如，您必须调用**SysFreeString**之前覆盖中传递的字符串，并**SysAllocStringByteLen**或**只能**为一个新字符串分配空间释放内存。 
  
您可以通过**CVerr**函数使用下表中所示的参数为**变量**在 VBA 中创建 Excel 工作表错误。 工作表错误还可返回到 VBA 从 DLL 的**ulVal**字段中使用**变体**类型**VT_ERROR**，并具有以下值。 
  
|**Error**|**Variant ulVal 值**|**CVerr 参数**|
|:-----|:-----|:-----|
|#NULL!  <br/> |2148141008  <br/> |2000  <br/> |
|#DIV/0!  <br/> |2148141015  <br/> |2007  <br/> |
|#VALUE!  <br/> |2148141023  <br/> |2015  <br/> |
|#REF!  <br/> |2148141031  <br/> |2023  <br/> |
|#NAME?  <br/> |2148141037  <br/> |2029  <br/> |
|#NUM!  <br/> |2148141044  <br/> |2036  <br/> |
|#N/A  <br/> |2148141050  <br/> |2042  <br/> |
   
请注意，给定的 Variant **ulVal**值等于**CVerr**参数值以及 x800A0000 十六进制。 
  
## <a name="calling-dll-functions-directly-from-the-worksheet"></a>直接从工作表中调用 DLL 函数

您无法访问 Win32 DLL 函数从工作表中没有，例如，使用 VBA 或 XLM 接口，或又不允许 Excel 事先知道函数，它的参数以及它的返回类型。 此操作的过程称为注册。
  
Dll 函数可以访问工作表中的方法如下所示：
  
- 声明在 VBA 中的函数，如前面所述并访问通过 VBA 用户定义函数。
    
- 调用 XLM 宏表，使用呼叫的 DLL 函数和访问通过 XLM 用户定义函数。
    
- 使用 XLM 或 VBA 命令调用 XLM**注册**的函数，它提供了 Excel 工作表单元格中输入时识别函数所需的信息。 
    
- 将变成 XLL DLL 并注册 XLL 被激活时使用 C API **xlfRegister**函数的函数。 
    
是独立的第四个方法： 注册函数的代码和函数代码都包含在相同的代码项目中。 对加载项进行的更改不涉及到 XLM 工作表或 VBA 代码模块进行更改。 若要同时仍保持中的 C api 的功能完善管理方式执行此操作，必须将变成 XLL DLL 并加载生成加载项使用加载项管理器。 这使 Excel 调用的函数，您的 DLL 公开外接程序加载或时激活，从其可以注册的所有包含您 XLL 的功能和任何其他 DLL 初始化执行。
  
## <a name="calling-dll-commands-directly-from-excel"></a>直接从 Excel 调用 DLL 命令

Win32 DLL 命令将无法访问直接从 Excel 对话框和菜单不存在一个接口，如 VBA，或不提前注册的命令。
  
您可以在其中访问 DLL 的命令的方法如下所示：
  
- 声明 VBA 中的命令，如前面所述并访问通过 VBA 宏。
    
- 调用 XLM 宏表，使用**调用**DLL 命令并访问通过 XLM 宏。 
    
- 使用 XLM 或 VBA 命令调用 XLM**注册**的函数，它提供的信息 Excel 需要识别该命令时输入到一个对话框，需要宏命令的名称。 
    
- 将变成 XLL DLL 并注册使用 C API **xlfRegister**函数的命令。 
    
如前面的 DLL 函数上下文中所述，第四个方法是最独立，保持最新的命令代码附近的注册代码。 若要执行此操作，必须将变成 XLL DLL 并加载生成加载项使用的加载项管理器。 在这种方式中注册命令还可以将命令附加到的用户界面，例如自定义菜单，元素或设置事件陷阱调用该命令的给定的键击或其他事件。
  
使用 Excel 中注册的所有 XLL 命令都假定 Excel 的以下形式。
  
```cpp
int WINAPI my_xll_cmd(void)
{
// Function code...
    return 1;
}
```

> [!NOTE]
> 除非调用从 XLM 宏工作表，在其中案例的返回值转换为**TRUE**或**FALSE**，则 Excel 会忽略返回值。 如果它失败或已被用户取消，因此应返回 1 如果您的命令执行成功和 0。 
  
## <a name="dll-memory-and-multiple-dll-instances"></a>DLL 内存和多个 DLL 实例

当应用程序加载 DLL 时，该 DLL 可执行代码加载到全局堆，以便它可以运行，并在其数据结构全局堆分配的空间。 Windows 使用内存映射以使显示如同它们位于应用程序的过程中，以便应用程序可以访问这些这些领域的内存。
  
如果第二个应用程序然后加载 DLL，Windows 不会创建 DLL 的可执行代码，另一个副本，如内存是只读的。 Windows 将 DLL 可执行代码内存映射到两个应用程序的过程。 但是，它执行分配第二个空格的 DLL 的数据结构的私有副本并将此副本映射到第二个进程。 这样可确保不应用程序可能会干扰 DLL 的其他数据。
  
这意味着 DLL 开发人员不必担心静态和全局变量和多个应用程序或多个实例的同一应用程序正在访问的数据结构。 每个应用程序的每个实例获取其自己的 DLL 数据副本。
  
DLL 开发人员需要为长短相同的应用程序从不同的线程，调用其 DLL 多次实例，因为这可能会导致争夺该实例的数据。 有关详细信息，请参阅[在 Excel 中进行内存管理](memory-management-in-excel.md)。
  
## <a name="see-also"></a>另请参阅

- [开发 DLL](developing-dlls.md) 
- [从 DLL 或 XLL 调用 Excel](calling-into-excel-from-the-dll-or-xll.md)

