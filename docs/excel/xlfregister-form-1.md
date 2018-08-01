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
ms.openlocfilehash: 4fb4e8656b4f27105a30764cdda020849a07645e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773849"
---
# <a name="xlfregister-form-1"></a>xlfRegister（窗体 1）

**适用于** Excel 2013 | Office 2013 | Visual Studio 
  
可从 DLL 或 XLL 命令的本身已调用由 Microsoft Excel 进行调用。 这相当于调用从 Excel XLM 宏工作表的**注册**。 
  
可在两个窗体中调用**xlfRegister** : 
  
- xlfRegister (窗体 1): 注册单个命令或函数。
    
- [xlfRegister (窗体 2)](xlfregister-form-2.md): 加载并激活 XLL。
    
此函数调用窗体 1 中，在使 DLL 函数或命令可用于 Excel、 其使用计数设置为 1，并返回其注册 ID，它可用于更高版本使用[xlUDF](xludf.md)或**xlfCall**函数调用的函数。 注册 ID 还用于注销使用[xlfUnregister (窗体 1)](xlfunregister-form-1.md)的函数。 如果已注册的函数，再次调用**xlfRegister**增加其使用计数。 
  
这种形式的函数还为注册的函数或命令 ID 定义隐藏的名称即函数文本参数， _pxFunctionText_，并对其进行计算。 当您注销函数时，请删除使用[xlfSetName](xlfsetname.md)此名称。 有关详细信息，请参阅[Excel XLL 开发中的已知问题](known-issues-in-excel-xll-development.md)。
  
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
  
包含该函数的 DLL 名称。 这可以通过调用仅 XLL 函数[xlGetName](xlgetname.md)如果注册该函数也是当前正在执行 DLL 中获得。 
  
_pxProcedure_（**xltypeStr**或**xltypeNum**）
  
如果是字符串，则 DLL 代码中出现时调用的函数的名称。 如果一个号码，序号导出要调用的函数的数量。 为清楚起见，始终使用字符串形式。
  
_pxTypeText_(**xltypeStr**)
  
一个可选的字符串，指定函数的参数的类型和函数的返回值的类型。 有关详细信息，请参阅"备注"部分。 可以省略该参数为独立 DLL (XLL) 包含[xlAutoRegister 函数](xlautoregister-xlautoregister12.md)或**xlAutoRegister12**。 
  
> [!NOTE]
> 在 Excel 2007 中仅支持**xlAutoRegister12** 。 
  
如果缺少此参数与调用**xlfRegister** ，则 Excel 调用**xlAutoRegister**或**xlAutoRegister12**，如果存在于指定的 DLL，应然后正确注册功能通过提供此信息。
  
_pxFunctionText_(**xltypeStr**)
  
函数名称将显示在函数向导。 此参数是可选的。如果省略，该函数不可用函数向导中，并仅可通过使用使用从 XLM 宏工作表函数注册 ID 的**调用**的函数调用。 因此，用于一般工作表，应处理所需此参数。 
  
_pxArgumentText_(**xltypeStr**)
  
一个描述了函数的参数的可选文本字符串。 用户将看到此函数向导中。 如果省略，Excel 构造从_pxTypeText_的基本说明。
  
_pxMacroType_（**xltypeNum**或**xltypeInt**）
  
指向可选参数，指示 XLL 条目的类型。 如果省略，默认值为 1。
  
|||||
|:-----|:-----|:-----|:-----|
| _pxMacroType 值_ <br/> |0  <br/> |1  <br/> |2  <br/> |
|可从工作表进行调用  <br/> |可访问  <br/> |可访问  <br/> |否  <br/> |
|可以从宏表调用  <br/> |可访问  <br/> |可访问  <br/> |可访问  <br/> |
|可从已定义的名称定义调用  <br/> |可访问  <br/> |可访问  <br/> |可访问  <br/> |
|可从条件格式表达式调用  <br/> |可访问  <br/> |可访问  <br/> |否  <br/> |
|列出在函数向导的工作表函数  <br/> |否  <br/> |可访问  <br/> |否  <br/> |
|列出在函数向导的宏工作表函数  <br/> |否  <br/> |可访问  <br/> |可访问  <br/> |
   
实际上，应使用的工作表函数，1 宏表等效函数 1 (注册类型为**#**) 您想要从工作表和 2 调用命令。 
  
> [!NOTE]
> XLL 命令是隐藏的并且不显示在运行宏的对话框中，尽管可以任意位置输入其名称都必须有有效的命令名称。 
  
_pxCategory_（**xltypeStr**或**xltypeNum**）
  
可选参数，使您能够指定新的函数或命令应所属的类别。 函数向导函数除以类型 （类别）。 您可以指定的类别名称或序号，其中 number 是在函数向导显示类别的位置。 有关详细信息，请参阅"类别名称"部分。 如果省略，则假定用户定义的类别。
  
_pxShortcutText_(**xltypeStr**)
  
一个单字符、 区分大小写的字符串，指定分配给此命令的控件键。 例如，"A"将此命令分配给控件 + SHIFT + A。 此参数是可选的用于仅命令。
  
_pxHelpTopic_(**xltypeStr**)
  
可选的帮助文件 （.chm 或.hlp） 以显示当用户单击帮助按钮 （时显示您的自定义函数） 引用。 可以在窗体中`filepath!HelpContextID`或`http://address/path_to_file_in_site!0`。 之前和之后的两个部分"！"所需。  *HelpContextID*不得包含单引号，并将由 Excel 转换为 long，十进制窗体中的 4 个字节无符号整数。 当使用 URL 窗体，Excel 将打开仅引用的帮助文件。 
  
_pxFunctionHelp_(**xltypeStr**)
  
介绍您自定义的函数，其函数向导中选择时为可选字符串。
  
_pxArgumentHelp1_(**xltypeStr**)
  
可选。 函数向导中选择该函数时描述自定义函数的参数的字符串的第一个。 在 Excel 2003 和更早版本， **xlfRegister**可以获得最 30 个参数，以便您可以提供此帮助您函数参数仅在第一个 20。 从 Excel 2007 开始， **xlfRegister**可以采用最多 255 个参数，以便您可以提供此帮助用于达 245 函数参数。 
  
## <a name="property-valuereturn-value"></a>属性值/返回值

如果成功注册，此函数返回的函数 (**xltypeNum**)，可在调用**xlUDF**和**xlfUnregister** DLL 或**呼叫**并**注销**XLM 宏工作表中的注册 ID。 否则，它返回 #VALUE ！ 错误。 
  
## <a name="remarks"></a>说明

### <a name="data-types"></a>数据类型

_PxTypeText_参数指定返回的值的数据类型和 DLL 函数或代码资源的所有参数的数据类型。 _PxTypeText_的第一个字符指定的返回值的数据类型。 剩余的字符指示所有参数的数据类型。 例如，返回浮点数和整数和浮点数采用作为参数的 DLL 函数需要"书目" _pxTypeText_参数。 
  
以下两个表中总结了数据类型和使用 Excel 与 Xll 交换数据的结构。
  
第一个表格列出了 Excel 的所有版本中受支持的类型。
  
|**数据类型**|**按值传递**|**Ref （指针） 通过传递**|**Comments**|
|:-----|:-----|:-----|:-----|
|Boolean  <br/> |A  <br/> |L  <br/> |short [int] (0 = false 或 1 = true)  <br/> |
|double  <br/> |B  <br/> |E  <br/> ||
|char\*  <br/> ||C F  <br/> |Null 结尾的 ASCII 字节字符串  <br/> |
|无符号的字符\*  <br/> ||D、 G  <br/> |盘点的 ASCII 字节字符串  <br/> |
|无符号的 short [int]  <br/> |H  <br/> ||16 位 WORD  <br/> |
|[签名] short [int]  <br/> |I  <br/> |M  <br/> |16 位有符号的整数  <br/> |
|[签名长] int  <br/> |J  <br/> |N  <br/> |32 位有符号的整数  <br/> |
|FP  <br/> ||K  <br/> |浮点数组结构  <br/> |
|数组  <br/> ||O  <br/> |三个参数传递：<br/>-未签署的简短 int\*<br/>-未签署的简短 int\*<br/>-double]  <br/> |
|XLOPER  <br/> ||P  <br/> |变量类型工作表值和阵列  <br/> |
|||R  <br/> |值、 数组和区域引用  <br/> |
   
下面的数据类型引入 Excel 2007 中支持的较大网格和长 Unicode 字符串。
  
|**数据类型**|**按值传递**|**Ref （指针） 通过传递**|**Comments**|
|:-----|:-----|:-----|:-----|
|无符号的 short\*  <br/> ||C %，F %  <br/> |Null 结尾的 Unicode 宽字符字符串  <br/> |
|无符号的 short\*  <br/> ||D %，G %  <br/> |盘点的 Unicode 宽字符的字符串  <br/> |
|FP12  <br/> ||K %  <br/> |大网格浮点数组结构  <br/> |
|数组  <br/> ||O %  <br/> |三个参数传递：<br/>-签名 int \* / RW\*<br/>-签名 int \* / COL\*<br/>-double]  <br/> |
|XLOPER12  <br/> ||Q  <br/> |变量类型工作表值和阵列  <br/> |
|||U  <br/> |值、 数组和区域引用  <br/> |
   
启动 Excel 2010 中的以下数据引入类型：
  
|**数据类型**|**按值传递**|**Ref （指针） 通过传递**|**Comments**|
|:-----|:-----|:-----|:-----|
|XLOPER12  <br/> ||X  <br/> |异步句柄用于 Excel 和 XLL 跟踪挂起的异步函数调用。存在的类型字符串中的参数类型还指定为异步的函数。有关异步函数的详细信息，请参阅[Asynchronous User-Defined 函数](asynchronous-user-defined-functions.md)。  <br/> |
   
**F**、 **F %**、 **G**、 和**G %** 的字符串类型用于修改就地的参数。 
  
处理上表中显示的数据类型时，应注意下列选项：
  
- C 语言声明假定您编译器默认情况下使用 8 字节的双精度型 2 字节短整数和 4 字节的长整数。
    
- 使用 **__stdcall**调用约定称为 Dll 和代码资源中的所有功能。 
    
- 返回为返回一个指针，数据类型的引用，即，任何函数可以安全地返回空的指针。 Excel 将 null 指针解释为 #NUM ！ 错误。
    
## <a name="additional-data-type-information"></a>其他数据类型信息

此部分包含有关**E**、 **F**、 **F %**、 **G**、 **G %**、 **K**、 **O**、 **P**、 **Q**、 **R**和**U**数据类型的详细的信息以及有关_pxTypeText 其他信息_参数。 
  
### <a name="e-data-type"></a>E 数据类型

Excel 要求使用电子数据类型将指针传递给浮点数，在堆栈 DLL。 这可能会导致问题期望的数目协处理器仿真程序堆栈上传递某些语言版本 （例如，高 c + +）。 解决方法是协处理器堆栈上将指针传递给数。 下面的示例演示如何从高 c + + 中返回一个 double，它。
  
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

### <a name="f-f-g-and-g-data-types"></a>F、 F %、 G、 和 G %数据类型

**F**、 **F %**、 **G**、 和**G %** 数据类型，函数可修改字符串缓冲区分配由 Excel。 如果其中一种类型的返回值类型代码，Excel 会忽略函数返回的值。 而是 Excel 的第一个相应数据类型 （**F**、 **F %**、 **G**、 或**G %**） 的函数参数列表中搜索，然后所需的返回值为分配的字符串缓冲区的当前内容。 所有版本的 Excel **F**和**G** ASCII 字符串，为都分配 256 字节，并从 Excel 2007 65536年字节的分配，足够 32,768 个 Unicode 字符， **F %** 和**G %unicode**字符串。 请记住缓冲区必须包括计数字符 （ **G**类型和**G %**） 或 null 终止字符 （类型**F**和**F %**），以便实际的最大字符串长度为 255 和 32767。 Unicode 字符串，因此类型**F %** 和**G %** 参数是只能通过 C API 在 Excel 中可用。 
  
### <a name="k-and-k-data-types"></a>K 和 K %数据类型

**K**和**K %** 数据类型分别使用指向大小可变的 FP 和 FP12 结构的指针。 这些结构 XLLCALL 中定义。H。 FP12 结构，因此类型**K %** 参数，仅支持 Excel 2007 中启动。 
  
### <a name="o-and-o-data-types"></a>O 和 O %数据类型

**O**和**O %** 数据类型仅可用于参数，不返回的值，但我修改就地**O**或**O %type**参数可以返回的值。 每个传入三项： 指向的数组的数组中的列数的指针中的行数和指向浮点数一个二维数组。 
  
若要修改数组传递的 O 或 O %数据类型就地，您无法使用"> O"或"> O %"作为_pxTypeText_参数。 有关修改数组的详细信息，请参阅本主题中的"修改中位置:: 函数声明为 Void"部分。 
  
**O**数据类型创建直接与的兼容性 Fortran Dll，将参数传递的引用。 
  
**O %** 支持在 Excel 2007 中，启动和可容纳更大的 Excel 支持的行数。 
  
### <a name="p-and-q-data-types"></a>P 和 Q 数据类型

当 DLL 函数参数为采用类型**P** XLOPERs 注册或键入**Q** XLOPER12s 时，Excel 将准备这些参数时转换简单值的单个单元格引用和数组多单元格的引用。 换句话说， **P**和**Q**类型将始终在函数中作为到达这些类型之一： **xltypeNum**、 **xltypeStr**、 **xltypeBool**、 **xltypeErr**、 **xltypeMulti**、 **xltypeMissing**或**xltypeNil**，但不是**xltypeRef**或**xltypeSRef**因为这些始终取消引用。 **XLOPER12**s，因此类型**Q**参数，仅支持 Excel 2007 中启动。 
  
如果类型**xltypeMissing**或**xltypeNil**用于返回值，它们是由 Excel 解释为数值零。 当呼叫者省略参数传递**xltypeMissing** 。 当呼叫者将传递空单元格的引用传递**xltypeNil** 。 当单元格区域转换为**xltypeMulti**作为类型**P**或**Q**传递时，任何空白单元格范围内的会转换为**xltypeNil**数组元素。 同样作为**xltypeNil**元素传递字面数组中缺少的元素。 
  
### <a name="volatile-functions-and-recalculation"></a>可变函数和重新计算

在工作表中，您可以 DLL 函数或代码资源可变，以使重新计算每次重新计算工作表。 若要执行此操作，请_pxTypeText_参数中的最后一个参数代码后添加感叹号 （！）。 
  
> [!NOTE]
> 默认情况下，函数采用类型**R** XLOPERs 或键入**U** XLOPER12s 并程序注册为宏的工作表的等效项 (类型**#**; 请参阅下一节) 为在 Excel 中的可变处理。 
  
### <a name="functions-declared-as-void"></a>声明为无效的函数

有两种情况下声明为返回 void 函数调用的。 在这两种情况下，此函数返回由其他手段其结果。
  
#### <a name="modifying-in-place"></a>就地修改

您可用于单个数字_n_ _pxTypeText_中的返回类型代码其中_n_是从 1 到 9 的数字。 这指示 Excel 才能变量的值由_pxTypeText_用作的返回值中的 _n_th 参数指向的位置。 这也称为就地修改。 _N_th 参数必须是通过引用传递数据类型 （C、 D、 E、 F、 F %、 G、 G %、 K、 K %、 L、 M、 N、 O、 O %、 P、 Q、 R 或 U）。 此外必须使用**void**关键字的 C/c + + 语言 （或 Pascal 语言中的**过程**关键字） 中声明的 DLL 函数或代码资源。 
  
例如，参数可以修改就地字符串为整数采用以 null 结尾的字符串和两个指针的 DLL 函数。 使用"1FMM"作为_pxTypeText_参数，并声明为无效的函数。 
  
早期版本的 Excel 使用**\>** 开头的_pxTypeText_以表示该函数被声明为 void 和第一个参数是就地修改 — 无法修改任何之外的第一个参数。 **\>** 等效_n_ = 1 中当前的 Excel 版本和此使用**\>** 同步函数中支持向后兼容性。 
  
#### <a name="asynchronous-functions"></a>异步函数

从初始函数调用打头**pxTypeText**中, 使用的参数类型为 X 的异步函数不返回其结果。 相反，您必须声明为 void 异步函数和更高版本的加载项返回的结果通过回拨。 必须使用注册的异步函数**\>** **pxTypeText**开头。 在异步函数中，**\>** 表示该函数声明为无效，但并不表示的第一个参数，被修改就地。 有关异步函数的详细信息，请参阅[Asynchronous User-Defined 函数](asynchronous-user-defined-functions.md)。 

### <a name="registering-worksheet-functions-as-macro-sheet-equivalents-handling-uncalculated-cells"></a>注册为宏工作表等效 （处理未计算的单元格） 的工作表函数

发出**#** 字符后_pxTypeText_中的最后一个参数代码为函数相同的呼叫权限功能提供的宏工作表上。 这些如下所示： 
  
- 该函数可以检索尚未计算此重新计算的周期中的单元格的值。
    
- 该函数可以调用任何 XLM 信息 (类 2) 函数，如**xlfGetCell**。
    
- 如果井号 （#） 不存在： 评估出错**xlretUncalced**和当前函数中未计算的单元格结果后已计算的单元格; 再次调用调用**xlfCaller**之外的任何 XLM 信息函数会导致**xlretInvXlfn**错误。 
    
### <a name="registering-worksheet-functions-as-thread-safe"></a>注册为线程安全的工作表函数

从 Excel 2007 开始，Excel 可以执行多线程的工作簿重新计算。 这意味着，它可以将线程安全的函数的不同实例分配给并发线程重新计算。 启动 Excel 2007 中内置的工作表函数中的大多数是线程安全的。 Excel 启动 Excel 2007 中，还允许 Xll 注册为线程安全的工作表函数。 若要执行此操作，包括**$** 字符后_pxTypeText_中的最后一个参数代码。 
  
> [!NOTE]
> 可以将仅工作表函数声明为线程安全。 Excel 不考虑宏工作表等效功能，以便不能将追加同时为线程安全的**#** 和**$** _pxTypeText_参数的字符。 
  
如果您作为线程安全注册一个函数，您必须确保其行为以线程安全的方式，尽管 Excel 拒绝所有线程不安全的呼叫通过 C API。 例如，如果尝试调用**xlfGetCell**线程安全的函数，呼叫将失败并**xlretNotThreadSafe**错误。 
  
### <a name="registering-worksheet-functions-as-cluster-safe"></a>注册为群集安全的工作表函数

启动 Excel 2010 中 Excel 可以卸载到指定的计算群集提供程序的函数调用。 有关详细信息，请参阅[群集安全函数](cluster-safe-functions.md)。 注册为群集安全任何 XLL 工作表函数参加卸载群集时可用。 群集安全函数注册通过包括**&amp;** 字符后_pxTypeText_参数中的最后一个参数代码。 
  
如果您注册为群集安全函数，您必须确保其行为以群集安全的方式。 有关详细信息，请参阅[群集安全函数](cluster-safe-functions.md)。
  
> [!NOTE]
> 可以将仅工作表函数声明为群集安全。 Excel 不考虑宏工作表等效功能，以便不能将追加同时为群集安全**#** 和**&amp;** _pxTypeText_参数的字符。 可以将工作表函数声明为群集安全和线程安全。 在这种情况下，Excel 将允许这些函数可以参加多线程的重新计算群集卸载禁用时。 
  
### <a name="category-names"></a>类别名称

使用以下准则可确定哪些类别放置您 XLL 函数中。
  
- 如果该函数执行内容无法由用户完成作为外接程序用户界面的一部分，应将该函数置于**命令**类别。 
    
- 如果函数将返回有关加载项的状态信息或其他任何有用的信息，应将该函数置于**信息**类别。 
    
- 外接程序应永远不会添加函数或命令为**用户定义的**类别。 最终用户独占使用此类别。 
    
使用**xlfRegister** _pxCategory_参数指定类别。 这可以是数量硬编码标准类别之一对应的文本或新类别指定 DLL 的文本。 如果尚不存在给定的文本，Excel 将新建同名的新类别。
  
下表列出了当您查看工作表中的**粘贴函数**对话框中都能看到的标准类别。 
  
|**编号**|**Text**|
|:-----|:-----|
|1  <br/> |财务  <br/> |
|2  <br/> |日期&amp;时间  <br/> |
|3  <br/> |数学&amp;三角等式  <br/> |
|4  <br/> |文本  <br/> |
|5  <br/> |逻辑  <br/> |
|6  <br/> |查找&amp;参考 （英文）  <br/> |
|7  <br/> |Database  <br/> |
|8  <br/> |统计  <br/> |
|9  <br/> |信息  <br/> |
|14  <br/> |用户定义  <br/> |
||工程 （在 Excel 2007 中从开始）  <br/> |
||多维数据集 （在 Excel 2007 中从开始）  <br/> |
   
此外，这些类别都是可见时查看宏工作表中**粘贴函数**对话框中。 
  
|**编号**|**Text**|
|:-----|:-----|
|10  <br/> |命令  <br/> |
|11  <br/> |DDE/外部  <br/> |
|12  <br/> |自定义  <br/> |
|13  <br/> |宏控件  <br/> |
   
### <a name="example"></a>示例

请参阅**xlAutoOpen**函数中的代码`\SAMPLES\GENERIC\GENERIC.C`。
  
## <a name="see-also"></a>另请参阅

- [REGISTER.ID](xlfregisterid.md)
- [注销](xlfunregister-form-1.md)
- [基本的有用 C API XLM 函数](essential-and-useful-c-api-xlm-functions.md)

