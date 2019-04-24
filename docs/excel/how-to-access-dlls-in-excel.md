---
title: 在 Excel 中访问 DLL
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
keywords:
- 访问 dll [excel 2007], DLL [Excel 2007], 在 Excel 中访问
ms.assetid: e2bfd6ea-efa3-45c1-a5b8-2ccb8650c6ab
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
localization_priority: Priority
ms.openlocfilehash: fac4ad30048aa1bf3879009bc97ea46a112a9ce5
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32304009"
---
# <a name="access-dlls-in-excel"></a>在 Excel 中访问 DLL

**适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
可以通过以下几种方式在 Microsoft Excel 中访问 DLL 函数：
  
- 通过 Microsoft Visual Basic for Applications (VBA) 代码模块，其中可使用 **Declare** 语句使用函数或命令。 
    
- 通过使用 **CALL** 或 **REGISTER** 函数的 XLM 宏工作表。 
    
- 直接通过工作表或者通过用户界面 (UI) 中的自定义项。
    
本文档未介绍 XLM 函数。 建议你使用其他两种方法之一。
  
若要直接通过工作表或者 UI 中的自定义项访问，必须在 Excel 中注册函数或命令。 有关注册命令和函数的信息，请参阅[在 Excel 中访问 XLL 代码](accessing-xll-code-in-excel.md)。
  
## <a name="calling-dll-functions-and-commands-from-vba"></a>通过 VBA 调用 DLL 函数和命令

可以使用 **Declare** 语句访问 VBA 中的 DLL 函数和命令。 该语句中包含一个命令语法和一个函数语法。 
  
- **语法 1 - 命令**
    
  ```vb
  [Public | Private] Declare Sub name Lib "libname" [Alias "aliasname"] [([arglist])]
  ```

- **语法 2 - 函数**
    
  ```vb
  [Public | Private] Declare Function name Lib "libname" [Alias "aliasname"] [([arglist])] [As type]
  ```

可选**公用**和**专用**关键字用于指定所导入函数的范围：整个 Visual Basic 项目还是仅 Visual Basic 模块。 此名称为想要在 VBA 代码中使用的名称。 如果它与 DL 中的名称不同，则必须使用别名“aliasname”说明符，并且应赋予函数 DLL 所导出的名称。 如果想要通过引用 DLL 序号访问 DLL 函数，则必须提供别名（以 **#** 为前缀的序数）。
  
命令应返回 **void**。 函数应返回 VBA 可识别 **ByVal** 的类型。 这意味着，某些类型可以通过修改相应的参数更轻松地返回：字符串、数组、用户定义的类型和对象。
  
> [!NOTE]
> VBA 无法检查 Visual Basic 模块中的参数列表和返回内容是否与 DLL 中的代码相同。 需要你自己亲自仔细检查，因为如果出错，则会导致 Excel 崩溃。 
  
如果函数或命令的参数不是通过引用或指针传递，则它们必须以 **arglist** 声明中的 **ByVal** 关键字开头。 当 C/C++ 函数采用指针参数时，或者 C++ 函数采用引用参数时，它们应以 **ByRef** 传递。 参数列表中的关键字 **ByRef** 可以省略，因为它在 VBA 中为默认值。 
  
### <a name="argument-types-in-cc-and-vba"></a>C/C++ 和 VBA 中的参数类型

比较 C/C++ 和 VBA 中的参数类型声明时，应注意以下事项。
  
- VBA **String** 在传递 ByVal 时作为指针传递至字节字符串 BSTR 结构，而在传递 **ByRef** 时作为指针传递至指针。
    
- VBA **变体**包含一个字符串，该字符串在传递 **ByVal** 时作为指针传递至 Unicode 宽字符字符串 BSTR 结构，并在传递 **ByRef** 时作为指针传递至指针。
    
- VBA **Integer** 是一个 16 位类型的值，等同于 C/C++ 中的有符号短整。 
    
- VBA **Long** 是一个 32 位类型的值，等同于 C/C++ 中的有符号整数。 
    
- VBA 和 C/C++ 分别使用 **Type** 和 **struct** 语句支持用户定义的数据类型定义。 
    
- VBA 和 C/C++ 支持**变体**数据类型，它在 Windows OLE/COM 头文件的 C/C 中被定义为 VARIANT。 
    
- VBA 数组为 OLE **SafeArrays**，它在 Windows OLE/COM 头文件的 C/C 中被定义为 **SAFEARRAY**。
    
- VBA **Currency** 数据类型作为 **CY** 类型结构传递且在 Windows 头文件 wtypes.h 中定义（传递 **ByVal** 时），并作为指针传递至指针（传递 **ByRef** 时）。
    
在 VBA 中，用户定义的数据类型中的数据元素将打包为 4 字节边界，而在 Visual Studio 中，它们默认打包为 8 字节边界。 因此，必须将 `#pragma pack(4) … #pragma pack()` 块中的 C/C++ 结构定义括起来，以免元素未对齐。 
  
以下示例所示为等效用户类型定义。
  
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

在某些情况下，VBA 比 Excel 支持的值范围更大。 VBA 双精度符合 IEEE 标准，支持工作表中当前已四舍五入为零的次正规数。 VBA **Date** 类型可使用负序列化日期表示早至 0100 年 1 月 1 日的日期。 Excel 仅支持大于或等于零的序列化日期。 VBA **Currency** 类型（成比例的 64 位整数）可以实现 8 字节双精度上不支持的精度，这也与工作表不匹配。 
  
Excel 仅可将以下类型的变体传递至 VBA 用户定义的函数。
  
|**VBA 数据类型**|**C/C++ 变体类型位标志**|**说明**|
|:-----|:-----|:-----|
|双精度  <br/> |**VT_R8** <br/> ||
|布尔值  <br/> |**VT_BOOL** <br/> ||
|日期  <br/> |**VT_DATE** <br/> ||
|字符串  <br/> |**VT_BSTR** <br/> |OLE Bstr 字节字符串  <br/> |
|区域  <br/> |**VT_DISPATCH** <br/> |区域和单元格引用  <br/> |
|包含数组的变体  <br/> |**VT_ARRAY** | **VT_VARIANT** <br/> |文本数组  <br/> |
|Ccy  <br/> |**VT_CY** <br/> |64 位成比例整数，支持 4 位小数位数的精度。  <br/> |
|包含错误的变体  <br/> |**VT_ERROR** <br/> ||
||**VT_EMPTY** <br/> |空单元格或已省略的参数  <br/> |
   
可以使用 **VarType** 检查 VBA 中的传入变体类型，通过引用调用时返回区域值类型的函数除外。 若要确定**变体****区域**引用对象，可以使用 **IsObject** 函数。 
  
可以从**区域**创建 VBA 中包含变体数组的**变体**，方法是将其**值**属性指定为**变量**。 源区域中使用当时的区域设置中的标准货币格式的所有单元格均将转换为**货币**类型的数组元素。 采用日期格式的所有单元格均将转换为**日期**类型的数组元素。 包含字符串的单元格将转换为宽字符 **BSTR** 变体。 包含错误的单元格将转换为 **VT_ERROR** 类型的**变体**。 包含**布尔表达式** **True** 或 **False** 的单元格将转换为 **VT_BOOL** 类型的**变体**。 
  
> [!NOTE]
> **变体**将 **True** 存储为 -1，将 **False** 存储为 0。 未采用日期或货币金额格式的数字将转化为 **VT_R8** 类型的变体。 
  
### <a name="variant-and-string-arguments"></a>变体和字符串参数

Excel 从内部使用宽字符 Unicode 字符串。 如果 VBA 用户定义的函数被声明为采用**字符串**参数，则 Excel 将以特定于区域设置的方式将提供的字符串转换为字节字符串。 如果想要函数传递为 Unicode 字符串，则 VBA 用户定义的函数应接受**变体**而不是**字符串**参数。 DLL 函数随后可接受 VBA 中的**变体** BSTR 宽字符字符串。 
  
若要将 Unicode 字符串从 DLL 返回至 VBA，应相应地修改**变体**字符串参数。 为此，必须将 DLL 函数声明为将指针指向**变体**和 C/C++ 代码，并将 VBA 代码中的参数声明为 `ByRef varg As Variant`。 应擦除原先的字符串内存，并且使用 OLE Bstr 字符串函数创建的新字符串只能在 DLL 中运行。
  
若要将字节字符串从 DLL 返回至 VBA，应相应地修改字节字符串 BSTR 参数。 为此，必须将 DLL 函数声明为将指针指向 BSTR 指针和 C/C++ 代码，并将 VBA 代码中的参数声明为“**ByRef varg As String**”。
  
应仅使用 OLE BSTR 字符串函数处理以这些方式从 VBA 传递的字符串，以免出现与内存相关的问题。 例如，必须先调用 **SysFreeString** 以释放内存，然后再覆盖传入的字符串，并调用 **SysAllocStringByteLen** 或 **SysAllocStringLen** 为新字符串分配空间。 
  
可以结合使用 **CVerr** 函数和下表中所示的参数，以在 VBA 中创建如**变体**一样的 Excel 工作表错误。 此外，还可以使用 **VT_ERROR** 类型的**变体**以及以下**ulVal**字段值，将工作表错误返回至 VBA。 
  
|**错误**|**变体 ulVal 值**|**CVerr参数**|
|:-----|:-----|:-----|
|#NULL!  <br/> |2148141008  <br/> |2000  <br/> |
|#DIV/0!  <br/> |2148141015  <br/> |2007  <br/> |
|#VALUE!  <br/> |2148141023  <br/> |2015  <br/> |
|#REF!  <br/> |2148141031  <br/> |2023  <br/> |
|#NAME?  <br/> |2148141037  <br/> |2029  <br/> |
|#NUM!  <br/> |2148141044  <br/> |2036  <br/> |
|#N/A  <br/> |2148141050  <br/> |2042  <br/> |
   
请注意，提供的变体 **ulVal** 值等于 **CVerr** 参数值加上 x800A0000 十六进制值。 
  
## <a name="calling-dll-functions-directly-from-the-worksheet"></a>直接从工作表调用 DLL 函数

例如，如果没有将 VBA 或 XLM 用作接口，或者没有让 Excel 提前知道气焊、其参数及其返回类型，则无法从工作表返回 Win32 DLL 函数。 此操作过程称为注册。
  
可在工作表中访问 DLL 函数的方式如下所示：
  
- 按上面所述在 VBA 中声明函数，然后通过 VBA 用户定义的函数访问它。
    
- 使用 XLM 宏工作表上的 CALL 调用 DLL 函数，然后通过 XLM 用户定义的函数访问它。
    
- 使用 XLM 或 VBA 命令调用 XLM **REGISTER** 函数，这将会提供 Excel 识别函数（在函数被输入到工作表单元格时）所需的信息。 
    
- 将 DLL 变为 XLL 并在 XLL 激活时使用 C API **xlfRegister** 函数注册函数。 
    
第四种方法为独立方法：用于注册函数和函数代码的代码包含于同一代码项目中。 更改加载项并不涉及更改 XLM 工作表或 VBA 代码模块。 若要以管理良好的方式完成此操作，同时保持 C API 的功能，则必须使用加载项管理器将 DLL 变为 XLL 并加载生成的加载项。 这使 Excel 能够在加载或激活加载项时调用 DLL 公开的函数，这样你就可以注册 XLL 包含的所有函数，并执行任何其他 DLL 初始化。
  
## <a name="calling-dll-commands-directly-from-excel"></a>直接通过 Excel 调用 DLL

在没有接口（如 VBA）或没有提前注册命令的情况下，无法直接通过 Excel 对话框和菜单访问 Win32 DLL 命令。
  
可用于访问 DLL 命令的方式如下所示：
  
- 按上面所述在 VBA 中声明函数，然后通过 VBA 宏访问它。
    
- 使用 XLM 宏工作表上的 **CALL** 调用 DLL，然后通过 XLM 宏访问它。 
    
- 使用 XLM 或 VBA 命令调用 XLM **REGISTER** 函数，这将会提供 Excel 识别命令（在命令被输入到期望获得宏命令名称的对话框时）所需的信息。 
    
- 将 DLL 变为 XLL 并使用 C API **xlfRegister** 函数注册命令。 
    
如前面的 DLL 函数上下文所述，第四种方法最独立，使注册代码与命令代码接近。 若要执行此操作，必须使用加载项管理器将 DLL 变为 XLL 并加载生成的加载项。 如果使用此方式注册命令，则还可以将命令附加到某个用户界面元素，如自定义菜单，或者设置事件陷进，以在指定击键或其他事件时调用此命令。
  
Excel 假定使用 Excel 注册的所有 XLL 命令采用以下形式。
  
```cpp
int WINAPI my_xll_cmd(void)
{
// Function code...
    return 1;
}
```

> [!NOTE]
> Excel 将忽略返回值，除非是通过 XLM 宏工作表调用该值，在此情况下，返回值将转换为 **TRUE** 或 **FALSE**。 因此，如果命令执行成功，则应返回 1，如果失败或者被用户取消，则返回 0。 
  
## <a name="dll-memory-and-multiple-dll-instances"></a>DLL 内存和多个 DLL 实例

应用程序加载 DLL 时，此 DLL 的可执行代码将加载到全局堆中，以便运行该代码，并且将会在全局堆中为其数据结构分配空间。 Windows 使用内存映射使这些内存区域看上去像位于应用程序进程中一样，这样一来应用程序就可访问它们。
  
如果另一个应用程序随后加载 DLL，则 Windows 不会生成另一个 DLL 可执行代码副本，因为该内存为只读。 Windows 会将此 DLL 可执行代码内存映射至两个应用程序的进程。 但是，它会为 DLL 数据结构专用副本分配另一个空间，并且只会将此副本映射至第二个进程。 这可确保两个应用程序的 DLL 数据不会相互干扰。
  
这意味着，DLL 开发人员无需在意静态和全局变量及数据结构被多个应用程序或相同应用程序的多个实例访问。 每个应用程序的每个实例均有自己的 DLL 数据副本。
  
DLL 开发人员必须考虑应用程序的相同实例从不同线程多次调用 DLL，因为这会导致该实例的数据被争用。 有关更多信息，请参阅 [Excel 中的内存管理](memory-management-in-excel.md)。
  
## <a name="see-also"></a>另请参阅

- [开发 DLL](developing-dlls.md) 
- [从 DLL 或 XLL 调用 Excel](calling-into-excel-from-the-dll-or-xll.md)

