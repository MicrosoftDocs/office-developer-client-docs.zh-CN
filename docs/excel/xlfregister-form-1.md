---
title: xlfRegister（窗体 1）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- xlfRegister
keywords:
- xlfregister 函数 [excel 2007]
localization_priority: Normal
ms.assetid: c730124c-1886-4a0f-8f06-79763025537d
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 3cd2e5072c8602fe301028e69592220a8345c211
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32303862"
---
# <a name="xlfregister-form-1"></a>xlfRegister（窗体 1）

**适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
可以从 DLL 或 XLL 命令调用，该命令本身已由 Microsoft Excel。 这等同于从 **XLM** 宏表Excel REGISTER。 
  
**xlfRegister** 可以调用两种形式： 
  
- xlfRegister (窗体 1) ：注册单个命令或函数。
    
- [xlfRegister (表单 2) ： ](xlfregister-form-2.md)加载并激活 XLL。
    
此函数在表单 1 中调用，使 DLL 函数或命令可供 Excel 使用，将它的使用计数设置为 1，并返回其注册 ID，稍后可使用 [xlUDF](xludf.md)或 **xlfCall** 函数调用该函数。 注册 ID 还用于使用 [xlfUnregister (表单 1 ](xlfunregister-form-1.md)) 。 如果函数已注册，再次调用 **xlfRegister** 将增加其使用计数。 
  
此形式的函数还定义一个隐藏名称，该名称是函数文本参数  _pxFunctionText_，计算结果为函数或命令的注册 ID。 注销函数时，使用 [xlfSetName 删除此名称](xlfsetname.md)。 有关详细信息，请参阅 [Excel XLL 开发中的已知问题](known-issues-in-excel-xll-development.md)。
  
```cs
Excel12(xlfRegister, LPXLOPER12 pxRes, int iCount,
    LPXLOPER12 pxModuleText,   LPXLOPER12 pxProcedure,
    LPXLOPER12 pxTypeText,     LPXLOPER12 pxFunctionText,
    LPXLOPER12 pxArgumentText, LPXLOPER12 pxMacroType,
    LPXLOPER12 pxCategory,     LPXLOPER12 pxShortcutText,
    LPXLOPER12 pxHelpTopic,    LPXLOPER12 pxFunctionHelp,
    LPXLOPER12 pxArgumentHelp1, LPXLOPER12 pxArgumentHelp2,
        ...);
```

## <a name="parameters"></a>参数

_pxModuleText_ (**xltypeStr**) 
  
包含 函数的 DLL 的名称。 如果注册的函数也位于当前执行的 DLL 中，则可以通过调用 XLL 函数 [xlGetName](xlgetname.md) 来获取此参数。 
  
_pxProcedure_ (**xltypeStr** 或 **xltypeNum**) 
  
如果是字符串，则表示在 DLL 代码中显示时要调用的函数的名称。 如果是数字，则表示要调用的函数的序号导出号。 为清楚起见，请始终使用字符串形式。
  
_pxTypeText_ (**xltypeStr**) 
  
一个可选字符串，指定函数的参数类型和函数的返回值类型。 有关详细信息，请参阅"备注"部分。 对于包含 [xlAutoRegister](xlautoregister-xlautoregister12.md) 函数或 **xlAutoRegister12** (XLL) DLL，可以省略此参数。 
  
> [!NOTE]
> **xlAutoRegister12** 仅在 Excel 2007 中受支持。 
  
如果调用 **xlfRegister** 时缺少此参数，Excel 将调用 **xlAutoRegister** 或 **xlAutoRegister12（** 如果指定的 DLL 中存在这两者），然后它应通过提供此信息正确注册函数。
  
_pxFunctionText_ (**xltypeStr**) 
  
显示在函数向导中的函数名称。 此参数是可选的;如果省略该函数，函数向导中将不可用，并且只能使用 **函数** 注册 ID 从 XLM 宏表中调用 CALL 函数。 因此，对于普通工作表的使用，应按需要处理此参数。 
  
_pxArgumentText_ (**xltypeStr**) 
  
描述函数参数的可选文本字符串。 用户在函数向导中会看到此参数。 如果省略它，则Excel _pxTypeText 构造基本说明_。
  
_pxMacroType_ (**xltypeNum** 或 **xltypeInt**) 
  
指示 XLL 入口点类型的可选参数。 如果省略默认值，则默认值为 1。
  
|||||
|:-----|:-----|:-----|:-----|
| _pxMacroType 值_ <br/> |0  <br/> |1  <br/> |2  <br/> |
|可以从工作表调用  <br/> |是  <br/> |是  <br/> |否  <br/> |
|可以从宏表调用  <br/> |是  <br/> |是  <br/> |是  <br/> |
|可以从定义的名称定义调用  <br/> |是  <br/> |是  <br/> |是  <br/> |
|可以从条件格式表达式调用  <br/> |是  <br/> |是  <br/> |否  <br/> |
|工作表函数的函数向导中列出  <br/> |否  <br/> |是  <br/> |否  <br/> |
|宏工作表函数的函数向导中列出  <br/> |否  <br/> |是  <br/> |是  <br/> |
   
实际上，应该对工作表函数使用 1，对宏表等效函数使用 1 (注册为类型 **#**) 从工作表调用，2 用于命令。 
  
> [!NOTE]
> XLL 命令处于隐藏状态，不会显示在用于运行宏的对话框中，尽管可以在任何需要有效命令名称的地方输入它们的名称。 
  
_pxCategory_ (**xltypeStr** 或 **xltypeNum**) 
  
一个可选参数，允许您指定新函数或命令应属于哪个类别。 函数向导按类型划分函数 (类别) 。 可以指定类别名称或顺序编号，其中数字是类别在"函数向导"中的显示位置。 有关详细信息，请参阅"类别名称"部分。 如果省略它，则假定为"用户定义"类别。
  
_pxShortcutText_ (**xltypeStr**) 
  
一个字符的区分大小写的字符串，指定分配给此命令的控制键。 例如，"A"将此命令分配给 CONTROL+Shift+A。 此参数是可选的，仅用于命令。
  
_pxHelpTopic_ (**xltypeStr**) 
  
对帮助文件 (.chm 或 .hlp) 的可选引用，当用户单击"帮助"按钮 (显示自定义函数时将显示) 。 可以是 或  `filepath!HelpContextID`  `https://address/path_to_file_in_site!0` 格式。 "！"之前和之后都需要两个部分。  *HelpContextID* 不得包含单引号，并且将Excel小数形式转换为 4 个字节的无符号整数。 使用 URL 表单时，Excel仅打开引用的帮助文件。 
  
_pxFunctionHelp_ (**xltypeStr**) 
  
在函数向导中选择自定义函数时描述该函数的可选字符串。
  
_pxArgumentHelp1_ (**xltypeStr**) 
  
可选。 在函数向导中选择函数时描述函数自定义参数的第一个字符串。 在 Excel 2003 及更早版本中 **，xlfRegister** 最多可以使用 30 个参数，以便你可以仅为前 20 个函数参数提供此帮助。 从 Excel 2007 开始 **，xlfRegister** 最多可以使用 255 个参数，以便你可以为最多 245 个函数参数提供此帮助。 
  
## <a name="property-valuereturn-value"></a>属性值/返回值

如果注册成功，此函数将返回函数 (**xltypeNum**) 的注册 ID，该 ID 可用于在 DLL 中调用 **xlUDF** 和 **xlfUnregister，** 或在 XLM 宏表中与 **CALL** 和 **UNREGISTER** 一起使用。 否则，它将返回一#VALUE！ error。 
  
## <a name="remarks"></a>备注

### <a name="data-types"></a>数据类型

_pxTypeText_ 参数指定数据类型值的默认值以及 DLL 函数或代码资源的所有参数的数据类型。 _pxTypeText 的第一个字符_ 指定数据类型值的值。 其余字符指示所有参数的数据类型。 例如，返回浮点数并采用整数和浮点数作为参数的 DLL 函数需要  _pxTypeText_ 参数的"BIB"。 
  
以下两个表中汇总了 Excel 用于与 XLL 交换数据的数据类型和结构。
  
第一个表列出了所有版本的 Excel。
  
|**数据类型**|**按值传递**|**按引用传递（指针）**|**备注**|
|:-----|:-----|:-----|:-----|
|Boolean  <br/> |A  <br/> |L  <br/> |short [int] (0=false 或 1=true)   <br/> |
|double  <br/> |B  <br/> |E  <br/> ||
|char \*  <br/> ||C、F  <br/> |以 null 结尾的 ASCII 字节字符串  <br/> |
|unsigned char \*  <br/> ||D、G  <br/> |计数的 ASCII 字节字符串  <br/> |
|unsigned short [int]  <br/> |H  <br/> ||16 位 WORD  <br/> |
|[signed] short [int]  <br/> |I  <br/> |M  <br/> |16 位有符号整数  <br/> |
|[signed long] int  <br/> |J  <br/> |N  <br/> |32 位有符号整数  <br/> |
|FP  <br/> ||K  <br/> |浮点数组结构  <br/> |
|Array  <br/> ||O  <br/> |传递三个参数：<br/>- 无符号短 int \*<br/>- 无符号短 int \*<br/>- double []  <br/> |
|XLOPER  <br/> ||P  <br/> |变量类型工作表值和数组  <br/> |
|||R  <br/> |值、数组和范围引用  <br/> |
   
在 Excel 2007 年，引入了以下数据类型以支持更大的网格和长 Unicode 字符串。
  
|**数据类型**|**按值传递**|**按引用传递（指针）**|**备注**|
|:-----|:-----|:-----|:-----|
|无符号短 \*  <br/> ||C%、F%  <br/> |以 Null 结尾的 Unicode 宽字符字符串  <br/> |
|无符号短 \*  <br/> ||D%、G%  <br/> |计数型 Unicode 宽字符字符串  <br/> |
|FP12  <br/> ||K%  <br/> |较大的网格浮点数组结构  <br/> |
|数组  <br/> ||O%  <br/> |传递三个参数：<br/>- signed int \* / RW \*<br/>- signed int \* / COL \*<br/>- double []  <br/> |
|XLOPER12  <br/> ||Q  <br/> |变量类型工作表值和数组  <br/> |
|||U  <br/> |值、数组和范围引用  <br/> |
   
从 2010 Excel起，引入了以下数据类型：
  
|**数据类型**|**按值传递**|**按引用传递（指针）**|**备注**|
|:-----|:-----|:-----|:-----|
|XLOPER12  <br/> ||X  <br/> |异步句柄用于跟踪 Excel 和 XLL 的挂起异步函数调用。类型字符串中参数类型的存在还将函数指定为异步。有关异步函数详细信息，请参阅[Asynchronous User-Defined Functions。](asynchronous-user-defined-functions.md)  <br/> |
   
下列字符串类型用于就地修改的参数：**F**、**F%**、**G** 和 **G%**。 
  
使用上表中显示的数据类型时，请注意以下几点：
  
- C 语言声明假定编译器默认使用 8 字节双精度、2 字节短整型和 4 字节长整型。
    
- DLL 和代码资源的所有函数都使用调用约定__stdcall **调用。** 
    
- 通过引用返回数据类型返回指针的任何函数（即返回指向某些对象的指针）都可以安全地返回空指针。 Excel空指针解释为空#NUM！ error。
    
## <a name="additional-data-type-information"></a>其他数据类型信息

本节包含有关E、F、F%、G、G%、K、O、P、Q、R和  **U** 数据类型的详细信息，以及有关 _pxTypeText_ 参数的其他信息。     
  
### <a name="e-data-type"></a>E 数据类型

Excel期望使用 E 数据类型的 DLL 将指针传递到堆栈上的浮点数。 这可能会导致某些语言问题 (，例如，用于) C++ 代码，希望数字在协处理器仿真器堆栈上传递。 解决方法是将指针传递给协处理器堆栈上的数字。 以下示例显示如何从管理中心 C++ 返回双精度值。
  
```cpp
typedef double * lpDbl;
extern "C" lpDbl __stdcall AddDbl(double D1,
    double D2, WORD npDbl)
{
    lpDbl Result;
    Result = (lpDbl)MK_FP(_SS, npDbl);
    *Result = D1 + D2;
    return (Result);
}
```

### <a name="f-f-g-and-g-data-types"></a>F、F%、G 和 G% 数据类型

使用 **F、F%、G** 和 **G%** 数据类型，函数可以修改由 Excel 分配的字符串缓冲区。  如果返回值类型代码是这些类型之一，Excel函数返回的值。 相反，Excel搜索第一个对应的 数据类型 (**F、F%、G** 或 **G%**) 的函数参数列表，然后将已分配的字符串缓冲区的当前内容作为返回值。 所有版本的 Excel 都为 **F** 和 **G** ASCII 字符串分配 256 个字节，从 Excel 2007 年 65，536 字节开始分配，足以为 **F%** 和 **G%** Unicode 字符串分配 32，768 个 Unicode 字符。 请记住，缓冲区必须包含计数字符 (类型 **G** 和 **G%**) 或空终止字符 (类型 **为 F** 和 **F%**) ，因此实际的最大字符串长度为 255 和 32，767。 Unicode 字符串（因此类型 **为 F%** 和 **G%** 参数）仅可通过 Excel 中的 C API 使用。 
  
### <a name="k-and-k-data-types"></a>K 和 K% 数据类型

**K 和** **K%** 数据类型分别使用指向可变大小的 FP 和 FP12 结构的指针。 这些结构在 XLLCALL.H 中定义。 FP12 结构（因此类型 **为 K%** 参数）仅在 2007 年 2 Excel受支持。 
  
### <a name="o-and-o-data-types"></a>O 和 O% 数据类型

**O** 和 **O%** 数据类型只能用于参数，不能用于返回值，尽管可以返回值来修改 O 或 **O%** 类型参数。  每个传递三个项目：一个指向数组中的行数的指针、一个指向数组中列数的指针和一个指向浮点数的二维数组的指针。 
  
若要修改由 O 或 O% 数据类型的数组，可以使用">O"或">O%"作为  _pxTypeText_ 参数。 有关修改数组的详细信息，请参阅本主题中的"就地修改：声明为 Void 的函数"部分。 
  
**O** 数据类型是为了与 Fortran DLL 直接兼容而创建的，这些 DLL 通过引用传递参数。 
  
**O%** 自 2007 Excel起受支持，并可容纳更多的 Excel行。 
  
### <a name="p-and-q-data-types"></a>P 和 Q 数据类型

当 DLL 函数参数注册为采用 **类型 P** XLOPER 或类型 **Q** XLOPER12 时，Excel 在准备这些参数时会将单单元格引用转换为简单值，并将多单元格引用转换为数组。 换句话说 **，P** 和 **Q** 类型将始终作为以下类型之一进入函数：xltypeNum、xltypeStr、xltypeBool、xltypeErr、xltypeMulti、xltypeMissing 或 **xltypeNil，** 但不能作为 **xltypeRef** 或 **xltypeSRef** 到达，因为它们始终被取消引用。     仅从 2007 年12 月起才支持 **XLOPER12（** 因此类型 Q 参数Excel）。 
  
如果 **类型 xltypeMissing** 或 **xltypeNil** 用于返回值，则将其解释为Excel零。 **当调用方省略参数时，将传递 xltypeMissing。** 当调用方传递对空单元格的引用时，将传递 **xltypeNil。** 当单元格区域转换为 **xltypeMulti** 以作为 **类型 P** 或 **Q** 传递时，区域内的任何空白单元格将转换为 **xltypeNil** 数组元素。 文本数组中缺少的元素同样作为 **xltypeNil 元素** 传递。 
  
### <a name="volatile-functions-and-recalculation"></a>可变函数和重新计算

在工作表上，可以使 DLL 函数或代码资源可变，以便它每次重新计算工作表时重新计算。 为此，在  _pxTypeText_ 参数中的最后一个参数 (！) 添加感叹号。 
  
> [!NOTE]
> 默认情况下，类型为 **R** XLOPER 或类型 **U** XLOPER12 且注册为宏表等效项 (类型的函数;请参阅下一节) 在 Excel 中作为可变函数 **#** 处理。 
  
### <a name="functions-declared-as-void"></a>声明为 void 的函数

有两种情况需要将函数声明为返回 void。 在这两种情况下，该函数通过其他方式返回其结果。
  
#### <a name="modifying-in-place"></a>就地修改

可以在 _pxTypeText_ 中将单个数字 _n_ 用于返回类型代码，其中 _n_ 是 1 到 9 的数字。 这将Excel _pxTypeText_ 中的 _n_th 参数指向的位置中的变量值作为返回值。 这也称为就地修改。 _n_th 参数必须为按 引用数据 类型 (C、D、E、F、F%、G、G%、K、K%L、M、N、O、O%、P、Q、R 或 U) 。 DLL 函数或代码资源还必须使用 C/C++ 语言中的 **void** 关键字或 pascal 语言 (procedure 关键字进行声明) 。 
  
例如，采用以 null 结尾的字符串和两个指向整数的指针作为参数的 DLL 函数可以就地修改字符串。 使用"1FMM"作为  _pxTypeText_ 参数，将函数声明为 void。 
  
早期版本的 Excel 在 **\>** _pxTypeText_ 的起始处使用，以表明该函数已声明为 void，并且第一个参数将就地修改，除了第一个参数外，其他任何参数均无法修改。 在当前 **\>** 版本中，等价 _于 n_ = 1 Excel并且仅在向后兼容时支持在同步函数 **\>** 中使用此 。 
  
#### <a name="asynchronous-functions"></a>异步函数

在 **pxTypeText** 中，使用 X 类型的参数表示的异步函数不会从初始函数调用中返回其结果。 相反，必须将异步函数声明为 void，稍后外接程序通过回调返回结果。 必须在 pxTypeText 的起始部分使用 注册 **\>** **异步函数**。 在异步函数中，表示函数声明为 void，但不表示就地修改了 **\>** 第一个参数。 有关异步函数详细信息，请参阅[Asynchronous User-Defined Functions。](asynchronous-user-defined-functions.md) 

### <a name="registering-worksheet-functions-as-macro-sheet-equivalents-handling-uncalculated-cells"></a>将工作表函数注册为宏表等效 (处理未计算单元格) 

将字符 **#** 放在  _pxTypeText_ 中的最后一个参数代码之后会为函数提供与宏表上的函数相同的调用权限。 这些任务如下： 
  
- 函数可以检索在此重新计算周期中尚未计算的单元格的值。
    
- 该函数可以在类 2 (调用任何 XLM) ，例如 **，xlfGetCell**。
    
- 如果不存在数字符号 (#) ：计算未计算单元格会导致 **xlretUncalced** 错误，并且计算该单元格后，将再次调用当前函数;调用除 **xlfCaller** 外的任何 XLM 信息函数都会导致 **xlretInvXlfn** 错误。 
    
### <a name="registering-worksheet-functions-as-thread-safe"></a>将工作表函数注册为线程安全

从 2007 Excel，Excel执行多线程工作簿重新计算。 这意味着它可以将线程安全函数的不同实例分配给并发线程以重新计算。 从 2007 Excel开始，大多数内置工作表函数都是线程安全的。 从 2007 Excel，Excel还允许 XLL 将工作表函数注册为线程安全函数。 为此，在 **$**  _pxTypeText_ 中的最后一个参数代码后添加一个字符。 
  
> [!NOTE]
> 只有工作表函数可以声明为线程安全。 Excel宏表等效函数不为线程安全函数，因此不能将 和 字符追加到 **#** **$** _pxTypeText_ 参数。 
  
如果你已将函数注册为线程安全函数，则必须确保它以线程安全方式运行，尽管 Excel 通过 C API 拒绝任何非线程安全调用。 例如，如果线程安全函数尝试调用 **xlfGetCell，** 调用将失败，并出现 **xlretNotThreadSafe** 错误。 
  
### <a name="registering-worksheet-functions-as-cluster-safe"></a>将工作表函数注册为群集安全

从 2010 Excel，Excel将函数调用卸载到指定的计算群集提供程序。 有关详细信息，请参阅群集保险箱[函数](cluster-safe-functions.md)。 注册为群集安全的所有 XLL 工作表函数都参与卸载（如果群集可用）。 群集安全函数的注册方法为在 **&amp;**  _pxTypeText_ 参数中最后一个参数代码之后添加字符。 
  
如果你将函数注册为群集安全函数，则必须确保它以群集安全方式运行。 有关详细信息，请参阅群集保险箱[函数](cluster-safe-functions.md)。
  
> [!NOTE]
> 只有工作表函数可以声明为群集安全。 Excel函数不将宏表等效函数作为群集安全函数，因此不能同时将 和 字符追加到 **#** **&amp;** _pxTypeText_ 参数。 工作表函数可以声明为群集安全函数和线程安全函数。 在这种情况下，Excel在禁用群集卸载时允许这些函数参与多线程重新计算。 
  
### <a name="category-names"></a>类别名称

使用以下指南确定要放入 XLL 函数的类别。
  
- 如果函数执行用户可作为加载项用户界面的一部分执行某些操作，则应该将函数放在"命令 **"类别中。** 
    
- 如果函数返回有关加载项状态的信息或其他任何有用信息，则应该将此函数放在"信息 **"类别中。** 
    
- 外接程序永远不应向用户定义的类别添加函数 **或** 命令。 此类别专供最终用户使用。 
    
类别使用  _pxCategory_ 参数指定给 **xlfRegister**。 它可以是对应于硬编码标准类别之一或 DLL 指定的新类别的文本的一个数字或文本。 如果给定的文本不存在，则Excel该名称创建一个新类别。
  
下表列出了在工作表中查看"粘贴函数"对话框时可见的标准类别。 
  
|**Number**|**Text**|
|:-----|:-----|
|1  <br/> |金融  <br/> |
|2  <br/> |日期 &amp; 时间  <br/> |
|3  <br/> |数学 &amp; 三角函数  <br/> |
|4   <br/> |文本  <br/> |
|5   <br/> |逻辑  <br/> |
|6   <br/> |查找 &amp; 参考  <br/> |
|7   <br/> |Database  <br/> |
|8   <br/> |统计  <br/> |
|9   <br/> |信息  <br/> |
|14   <br/> |用户定义  <br/> |
||从 (2007 Excel开始进行工程)   <br/> |
||多维数据集 (2007 Excel起)   <br/> |
   
此外，当您从宏工作表中查看"粘贴函数"对话框时，这些类别也可见。 
  
|**Number**|**Text**|
|:-----|:-----|
|10    <br/> |命令  <br/> |
|11  <br/> |DDE/External  <br/> |
|12   <br/> |自定义  <br/> |
|13  <br/> |宏控件  <br/> |
   
### <a name="example"></a>示例

请参阅 中的 **xlAutoOpen** 函数的代码  `\SAMPLES\GENERIC\GENERIC.C` 。
  
## <a name="see-also"></a>另请参阅

- [REGISTER.ID](xlfregisterid.md)
- [UNREGISTER](xlfunregister-form-1.md)
- [实用的基本 C API XLM 函数](essential-and-useful-c-api-xlm-functions.md)

