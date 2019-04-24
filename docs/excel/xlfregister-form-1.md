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
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 3cd2e5072c8602fe301028e69592220a8345c211
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32303862"
---
# <a name="xlfregister-form-1"></a>xlfRegister（窗体 1）

**适用于** Excel 2013 | Office 2013 | Visual Studio 
  
可从 DLL 或 XLL 命令调用, 该命令本身已由 Microsoft Excel 调用。 这相当于从 Excel XLM 宏表调用**REGISTER** 。 
  
可以在两种形式中调用**xlfRegister** : 
  
- xlfRegister (窗体 1): 注册单个命令或函数。
    
- [xlfRegister (窗体 2)](xlfregister-form-2.md): 加载并激活 XLL。
    
在 Form 1 中调用, 此函数使 DLL 函数或命令可供 Excel 使用, 并将其使用计数设置为 1, 并返回其注册 ID, 该 ID 可用于稍后使用[xlUDF](xludf.md)或**xlfCall**函数调用函数。 注册 ID 还用于使用[xlfUnregister (窗体 1)](xlfunregister-form-1.md)注销函数。 如果该函数已注册, 则再次调用**xlfRegister**会增加其使用次数。 
  
这种形式的函数还定义了一个隐藏名称, 该名称是函数文本参数_pxFunctionText_, 其计算结果为函数或命令的注册 ID。 在注销函数时, 请使用[xlfSetName](xlfsetname.md)删除此名称。 有关详细信息，请参阅 [Excel XLL 开发中的已知问题](known-issues-in-excel-xll-development.md)。
  
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

_pxModuleText_(**xltypeStr**)
  
包含函数的 DLL 的名称。 如果注册的函数也在当前正在执行的 DLL 中, 则可以通过调用 XLL 函数[xlGetName](xlgetname.md)来获取此功能。 
  
_pxProcedure_(**xltypeStr**或**xltypeNum**)
  
如果为字符串, 则为要调用的函数的名称, 因为它出现在 DLL 代码中。 如果为数字, 则为要调用的函数的序号导出编号。 为清楚起见, 请始终使用字符串形式。
  
_pxTypeText_(**xltypeStr**)
  
一个可选字符串, 指定函数的参数类型和函数的返回值的类型。 有关更多信息，请参见“注释”部分。 对于包含[xlAutoRegister 函数](xlautoregister-xlautoregister12.md)或**xlAutoRegister12**的独立 DLL (XLL), 可以省略此参数。 
  
> [!NOTE]
> **xlAutoRegister12**仅在 Excel 2007 中受支持。 
  
如果在使用此参数时调用**xlfRegister** , 则 Excel 将调用**xlAutoRegister**或**xlAutoRegister12**(如果存在) 在指定的 DLL 中, 这样就可以通过提供此信息正确地注册该函数。
  
_pxFunctionText_(**xltypeStr**)
  
将在函数向导中显示的函数名称。 此参数是可选的;如果省略该函数, 则函数在函数向导中不可用, 并且只能使用来自 XLM 宏表中的函数注册 ID 的**CALL**函数调用该函数。 因此, 对于普通工作表使用, 应根据需要处理此参数。 
  
_pxArgumentText_(**xltypeStr**)
  
一个可选的文本字符串, 用于描述函数的参数。 用户将在 "函数向导" 中看到此功能。 如果省略该方法, 则 Excel 将从_pxTypeText_构造基本说明。
  
_pxMacroType_(**xltypeNum**或**xltypeInt**)
  
一个指示 XLL 入口点的类型的可选参数。 如果省略, 则默认值为1。
  
|||||
|:-----|:-----|:-----|:-----|
| _pxMacroType 值_ <br/> |0  <br/> |1  <br/> |双面  <br/> |
|可从工作表中调用  <br/> |是  <br/> |是  <br/> |否  <br/> |
|可从宏表中调用  <br/> |是  <br/> |是  <br/> |是  <br/> |
|可从定义的名称定义中调用  <br/> |是  <br/> |是  <br/> |是  <br/> |
|可从条件格式表达式中调用  <br/> |是  <br/> |是  <br/> |否  <br/> |
|在工作表函数的函数向导中列出  <br/> |否  <br/> |是  <br/> |否  <br/> |
|"函数向导" 中列出的宏表函数  <br/> |否  <br/> |是  <br/> |是  <br/> |
   
在实践中, 您应使用1作为工作表函数, 1 用于要从工作表中调用**#** 的宏表等效函数 (注册为类型), 并2表示命令。 
  
> [!NOTE]
> XLL 命令是隐藏的, 并且不会显示在运行宏的对话框中, 尽管它们的名称可以在需要有效命令名称的任何位置输入。 
  
_pxCategory_(**xltypeStr**或**xltypeNum**)
  
一个可选参数, 可用于指定新函数或命令所属的类别。 函数向导按类型 (类别) 划分函数。 您可以指定类别名称或顺序编号, 其中的数字是类别在函数向导中显示的位置。 有关详细信息, 请参阅 "Category Names" 一节。 如果省略该方法, 则假定为用户定义的类别。
  
_pxShortcutText_(**xltypeStr**)
  
一个字符的、区分大小写的字符串, 用于指定分配给此命令的控制键。 例如, "A" 分配此命令来控制 + SHIFT + A。 此参数是可选的, 仅用于命令。
  
_pxHelpTopic_(**xltypeStr**)
  
一个可选的对帮助文件 (.chm 或 .hlp) 的引用, 当用户单击 "帮助" 按钮 (显示您的自定义函数时) 时显示。 可以是格式`filepath!HelpContextID` , 也`https://address/path_to_file_in_site!0`可以是。 "!" 前后的两个部分都是必需的。  值*id*为不能包含单引号, Excel 将由 Excel 转换为4个字节的无符号整数 (以十进制格式表示)。 使用 URL 表单时, Excel 仅打开引用的帮助文件。 
  
_pxFunctionHelp_(**xltypeStr**)
  
在 "函数向导" 中选择自定义函数时描述该函数的可选字符串。
  
_pxArgumentHelp1_(**xltypeStr**)
  
可选。 在函数向导中选择函数时, 描述函数的自定义参数的第一个字符串。 在 Excel 2003 和早期版本中, **xlfRegister**最多可以获取30个参数, 以便您可以仅为函数参数的前20个函数参数提供此帮助。 从 Excel 2007 开始, **xlfRegister**最长可占用255个参数, 以便您可以为最长为245函数参数提供此帮助。 
  
## <a name="property-valuereturn-value"></a>属性值/返回值

如果注册成功, 此函数将返回函数的 register ID (**xltypeNum**), 它可用于对 DLL 中的**xlUDF**和**xlfUnregister**的调用, 或者在 XLM 宏表中**调用**和**注销**。 否则, 它将返回一个 #VALUE! 误差. 
  
## <a name="remarks"></a>注解

### <a name="data-types"></a>数据类型

_pxTypeText_参数指定返回值的数据类型, 以及 DLL 函数或代码资源的所有参数的数据类型。 _pxTypeText_的第一个字符指定返回值的数据类型。 其余字符指示所有参数的数据类型。 例如, 返回浮点数并采用整数和浮点数作为参数的 DLL 函数对_pxTypeText_参数需要 "BIB"。 
  
Excel 用于与 xll 交换数据的数据类型和结构在以下两个表中汇总。
  
第一个表列出了在所有版本的 Excel 中支持的类型。
  
|**数据类型**|**按值传递**|**按引用传递（指针）**|**Comments**|
|:-----|:-----|:-----|:-----|
|Boolean  <br/> |A  <br/> |L  <br/> |short [int] (0 = false 或 1 = true)  <br/> |
|double  <br/> |B  <br/> |E  <br/> ||
|char \*  <br/> ||C、F  <br/> |以 null 结尾的 ASCII 字节字符串  <br/> |
|unsigned char \*  <br/> ||D、G  <br/> |计数的 ASCII 字节字符串  <br/> |
|unsigned short [int]  <br/> |H  <br/> ||16位字  <br/> |
|[signed] short [int]  <br/> |I  <br/> |M  <br/> |16位带符号整数  <br/> |
|[signed long] int  <br/> |J  <br/> |N  <br/> |32位带符号整数  <br/> |
|FP  <br/> ||K  <br/> |浮点数组结构  <br/> |
|Array  <br/> ||O  <br/> |传递了三个参数:<br/>-无符号短 int\*<br/>-无符号短 int\*<br/>-double []  <br/> |
|XLOPER  <br/> ||P  <br/> |变量类型工作表值和数组  <br/> |
|||R  <br/> |值、数组和范围引用  <br/> |
   
在 Excel 2007 中, 引入了以下数据类型来支持更大的网格和长 Unicode 字符串。
  
|**数据类型**|**按值传递**|**按引用传递（指针）**|**Comments**|
|:-----|:-----|:-----|:-----|
|无符号短\*  <br/> ||C%、F%  <br/> |以 Null 结尾的 Unicode 宽字符字符串  <br/> |
|无符号短\*  <br/> ||D%、G%  <br/> |计数的 Unicode 宽字符字符串  <br/> |
|FP12  <br/> ||K%  <br/> |较大的网格浮点数组结构  <br/> |
|数组  <br/> ||O%  <br/> |传递了三个参数:<br/>-有符号\*整数/RW\*<br/>-已签名\*的 int/COL\*<br/>-double []  <br/> |
|XLOPER12  <br/> ||Q  <br/> |变量类型工作表值和数组  <br/> |
|||U  <br/> |值、数组和范围引用  <br/> |
   
从 Excel 2010 开始, 引入了以下数据类型:
  
|**数据类型**|**按值传递**|**按引用传递（指针）**|**Comments**|
|:-----|:-----|:-----|:-----|
|XLOPER12  <br/> ||X  <br/> |异步句柄用于跟踪 Excel 和 XLL 的挂起的异步函数调用。类型字符串中的参数类型是否存在也将该函数指定为异步。有关异步函数的详细信息, 请参阅[异步用户定义函数](asynchronous-user-defined-functions.md)。  <br/> |
   
下列字符串类型用于就地修改的参数：**F**、**F%**、**G** 和 **G%**。 
  
使用上表中显示的数据类型时, 请注意以下事项:
  
- C 语言声明假定编译器使用8字节双精度、2字节短整数, 默认情况下为4字节长整数。
    
- dll 和代码资源中的所有函数都是使用 **__stdcall**调用约定调用的。 
    
- 任何按引用返回数据类型的函数, 即, 返回指向某项的指针的任何函数都可以安全地返回 null 指针。 Excel 将 null 指针解释为 #NUM! 误差.
    
## <a name="additional-data-type-information"></a>其他数据类型信息

本节包含有关**E**、 **f**、 **f%**、 **g**、 **g%**、 **K**、 **O**、 **P**、 **Q**、 **R**和**U**数据类型的详细信息, 以及有关 pxTypeText 的其他信息。 __ 参数。 
  
### <a name="e-data-type"></a>E 数据类型

Excel 期望使用 E 数据类型的 DLL 将指针传递到堆栈上的浮点数。 这可能会导致某些语言 (例如, Borland c + +) 出现问题, 预计在协处理器仿真程序堆栈上传递数字。 解决方法是将指针传递给协处理器堆栈上的数字。 下面的示例演示如何从 Borland c + + 返回一个双精度型。
  
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

### <a name="f-f-g-and-g-data-types"></a>f、f%、g 和 G% 数据类型

使用**f**、 **f%**、 **g**和**g%** 的数据类型, 函数可以修改由 Excel 分配的字符串缓冲区。 如果返回值类型代码是这两种类型之一, Excel 将忽略函数返回的值。 相反, Excel 会在函数参数列表中搜索第一个相应的数据类型 (**F**、 **f%**、 **g**或**g%**), 然后将分配的字符串缓冲区的当前内容作为返回值。 excel 的所有版本都会为**f**和**g** ASCII 字符串分配256个字节, 并为**f%** 和**g%** unicode 字符串分配在 excel 2007 65536 字节的开头, 足以满足 unicode 字符。 请注意, 缓冲区必须包含 count 字符 (类型**g**和**G%**) 或 null 终止字符 (类型**F**和**F%**), 以使实际的最大字符串长度为255和32767。 Unicode 字符串, 因此类型**F%** 和**G%** 参数仅适用于 Excel 中的 C API。 
  
### <a name="k-and-k-data-types"></a>k% 和 k% 的数据类型

**k**和**K%** 数据类型分别使用指向可变大小的 FP 和 FP12 结构的指针。 这些结构是在 XLLCALL 中定义的。水平. 仅支持在 Excel 2007 中启动 FP12 结构, 因此 type **K%** 参数。 
  
### <a name="o-and-o-data-types"></a>o 和 o% 的数据类型

**o**和**o%** 的数据类型仅可用于参数, 而不能返回值, 但可以返回的值是将**o**或**o%** type 参数就地修改。 每个都传递三个项: 指向数组中的行数的指针、指向数组中的列数的指针以及指向二维浮点数数组的指针。 
  
若要修改由 O 或 o% 的数据类型传递的数组, 可以使用 ">O" 或 ">O%" 作为_pxTypeText_参数。 有关修改数组的详细信息, 请参阅本主题中的 "就地修改: 函数声明为 Void" 一节。 
  
**O**数据类型是为与 Fortran dll 的直接兼容性创建的, 后者通过引用传递参数。 
  
**O%** 支持在 excel 2007 中启动, 并适应 excel 支持的更大行数。 
  
### <a name="p-and-q-data-types"></a>P 和 Q 数据类型

如果将 DLL 函数参数注册为采用类型**P** XLOPERs 或 type **Q** XLOPER12s, Excel 在准备这些参数时, 会将单个单元格引用转换为简单值和数组多单元格引用。 换言之, **P**和**Q**类型始终会作为以下类型之一到达您的函数: **xltypeNum**、 **xltypeStr**、 **xltypeBool**、 **xltypeErr**、 **xltypeMulti**、 **xltypeMissing**或**xltypeNil**, 而不是**xltypeRef**或**xltypeSRef** , 因为它们总是取消引用。 仅支持在 Excel 2007 中启动**XLOPER12**s, 并因此键入**Q**参数。 
  
如果将**xltypeMissing**或**xltypeNil**类型用于返回值, 则 Excel 会将它们解释为数值零。 当调用方省略参数时, 将传递**xltypeMissing** 。 当调用方传递对空单元格的引用时, 将传递**xltypeNil** 。 当单元格区域转换为作为**P**或**Q**类型传递的**xltypeMulti**时, 该区域中的任何空白单元格都将转换为**xltypeNil**数组元素。 文本数组中缺少的元素类似于作为**xltypeNil**元素传递。 
  
### <a name="volatile-functions-and-recalculation"></a>可变函数和重新计算

在工作表上, 您可以使 DLL 函数或代码资源变得可变, 以便在每次重新计算工作表时进行重新计算。 若要执行此操作, 请在_pxTypeText_参数中的最后一个参数代码后面添加感叹号 (!)。 
  
> [!NOTE]
> 默认情况下, 采用类型为**R** XLOPERs 或 type **U** XLOPER12s 的函数以及注册为宏表等效项的**#** 函数 (类型; 请参阅下一部分) 在 Excel 中处理为可变的。 
  
### <a name="functions-declared-as-void"></a>声明为 void 的函数

在两种情况下, 会调用将函数声明为返回 void 的情况。 在这两种情况下, 函数都通过其他方式返回其结果。
  
#### <a name="modifying-in-place"></a>就地修改

您可以对_pxTypeText_中的返回类型代码使用一个数字_n_ , 其中_n_是从1到9的数字。 这将指示 Excel 采用_pxTypeText_中的 _n_th 参数所指向的位置中的变量值作为返回值。 这也称为就地修改。 _n_th 参数必须是一个按引用传递的数据类型 (C、D、E、f、f%、g、g%、k、k%、L、M、n、o、o%、P、Q、R 或 U)。 DLL 函数或代码资源还必须使用 C/c + + 语言中的**void**关键字 (或 Pascal 语言中的**procedure**关键字) 声明。 
  
例如, 如果 DLL 函数采用以 null 结尾的字符串, 而将两个指针指向作为参数的整数, 则可以就地修改该字符串。 使用 "1FMM" 作为_pxTypeText_参数, 并将函数声明为 void。 
  
早期版本的 Excel 在**\>** _pxTypeText_开始时使用, 以表明该函数被声明为 void, 并且必须就地修改第一个参数, 而没有办法修改除第一个参数之外的任何参数。 在当前 Excel 版本中, 等效于 n = 1, 并且仅支持**\>** 在同步函数中使用, 以实现向后兼容性。 __ **\>** 
  
#### <a name="asynchronous-functions"></a>异步函数

使用**pxTypeText**中 X 类型的参数表示的异步函数不从初始函数调用返回其结果。 相反, 您必须将异步函数声明为 void, 随后加载项将通过回调返回结果。 异步函数必须使用**\>** **pxTypeText**的开头进行注册。 在异步函数中**\>** , 表示将函数声明为 void, 但并不指示将第一个参数就地修改。 有关异步函数的详细信息, 请参阅[异步用户定义函数](asynchronous-user-defined-functions.md)。 

### <a name="registering-worksheet-functions-as-macro-sheet-equivalents-handling-uncalculated-cells"></a>将工作表函数注册为宏表等效项 (处理未计算所得的单元格)

在 pxTypeText **#** 中的最后一个参数代码后面__ 放置一个字符, 可为函数提供与宏工作表上的函数相同的调用权限。 这些任务如下： 
  
- 函数可以检索尚未在此重新计算周期中计算的单元格的值。
    
- 函数可以调用任何 XLM 信息 (Class 2) 函数, 例如, **xlfGetCell**。
    
- 如果数字符号 (#) 不存在, 则计算未计算的单元格将导致**xlretUncalced**错误, 并且在计算完单元格后, 会再次调用当前函数。调用任何 XLM 信息函数而不是**xlfCaller**将导致**xlretInvXlfn**错误。 
    
### <a name="registering-worksheet-functions-as-thread-safe"></a>将工作表函数注册为线程安全的

从 excel 2007 开始, excel 可以执行多线程工作簿重新计算。 这意味着它可以将线程安全函数的不同实例分配给并发线程以进行重新计算。 从 Excel 2007 开始, 大多数内置工作表函数都是线程安全的。 从 excel 2007 开始, excel 还允许 xll 将工作表函数注册为线程安全的。 若要执行此操作, **$** 请在_pxTypeText_中的最后一个参数代码之后添加一个字符。 
  
> [!NOTE]
> 只有工作表函数可以声明为线程安全的。 Excel 不会认为宏表等效函数是线程安全的, 因此不能将这两个**#** 和**$** 一个字符追加到_pxTypeText_参数。 
  
如果将某个函数注册为线程安全的, 则必须确保它以线程安全方式行为, 但 Excel 会通过 C API 拒绝任何不安全的调用。 例如, 如果线程安全函数尝试调用**xlfGetCell**, 则调用将失败, 并出现**xlretNotThreadSafe**错误。 
  
### <a name="registering-worksheet-functions-as-cluster-safe"></a>将工作表函数注册为群集安全

从 excel 2010 开始, excel 可以将函数调用卸载到指定的计算群集提供程序。 有关详细信息, 请参阅[群集安全函数](cluster-safe-functions.md)。 如果群集可用, 则任何被注册为群集安全的 XLL 工作表函数都会进入卸载过程中。 通过在 pxTypeText 参数中的最后一个参数**&amp;** 代码后面添加字符, 可以注册群集__ 安全函数。 
  
如果已将某个函数注册为群集安全的, 则必须确保它以群集安全的方式行为。 有关详细信息, 请参阅[群集安全函数](cluster-safe-functions.md)。
  
> [!NOTE]
> 只有工作表函数可以声明为群集安全的。 Excel 不会认为宏表等效函数是群集安全的, 因此不能将这两个**#** 和**&amp;** 一个字符追加到_pxTypeText_参数。 工作表函数既可声明为群集安全的, 也可声明为线程安全。 在这种情况下, 在禁用群集卸载时, Excel 将允许这些函数参与多线程计算。 
  
### <a name="category-names"></a>类别名称

使用以下准则确定要在其中放置 XLL 函数的类别。
  
- 如果该函数执行的操作可能是用户作为加载项用户界面的一部分, 则应将该函数放在 "**命令**" 类别中。 
    
- 如果函数返回有关加载项状态的信息或任何其他有用的信息, 应将该函数放置在**信息**类别中。 
    
- 外接程序永远不应将函数或命令添加到**用户定义**的类别。 此类别用于以独占方式使用最终用户。 
    
使用**xlfRegister**的_pxCategory_参数指定类别。 它可以是与硬编码的标准类别之一相对应的数字或文本, 也可以是 DLL 指定的新类别的文本。 如果给定的文本尚不存在, 则 Excel 将使用该名称创建一个新类别。
  
下表列出了从工作表中查看 "**粘贴函数**" 对话框时可见的标准类别。 
  
|**Number**|**Text**|
|:-----|:-----|
|1  <br/> |财务  <br/> |
|双面  <br/> |日期&amp;时间  <br/> |
|第三章  <br/> |数学&amp;三角函数  <br/> |
|4  <br/> |文本  <br/> |
|5  <br/> |合理  <br/> |
|型  <br/> |查找&amp;引用  <br/> |
|步  <br/> |Database  <br/> |
|utf-8  <br/> |统计学  <br/> |
|第  <br/> |信息  <br/> |
|日  <br/> |用户定义  <br/> |
||工程 (从 Excel 2007 开始)  <br/> |
||多维数据集 (从 Excel 2007 中开始)  <br/> |
   
此外, 当您在宏表中查看 "**粘贴函数**" 对话框时, 也会看到这些类别。 
  
|**Number**|**Text**|
|:-----|:-----|
|10  <br/> |命令  <br/> |
|11x17  <br/> |DDE/外部  <br/> |
|12  <br/> |个性化  <br/> |
|13  <br/> |宏控件  <br/> |
   
### <a name="example"></a>示例

请参阅中`\SAMPLES\GENERIC\GENERIC.C`的**xlAutoOpen**函数的代码。
  
## <a name="see-also"></a>另请参阅

- [REGISTER.ID](xlfregisterid.md)
- [注销](xlfunregister-form-1.md)
- [实用的基本 C API XLM 函数](essential-and-useful-c-api-xlm-functions.md)

