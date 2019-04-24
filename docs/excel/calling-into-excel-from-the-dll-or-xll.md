---
title: 从 DLL 或 XLL 调用 Excel
manager: soliver
ms.date: 08/22/2018
ms.audience: Developer
ms.topic: overview
keywords:
- 对话框 [excel 2007], 调用 excel 命令,DLL [Excel 2007], 调用 Excel,将参数传递到 C API 函数 [Excel 2007],命令 [Excel 2007], 使用对话框进行调用,命令 [Excel 2007], 可通过 DLL/XLL 访问,Excel4 函数 [Excel 2007],Excel12 函数 [Excel 2007],XLCallVer 函数 [Excel 2007],operRes 参数 [Excel 2007],函数 [Excel 2007], 可通过 DLL/XLL 进行访问,Excel12v 函数 [Excel 2007],仅 DLL 函数 [Excel 2007],C API [Excel 2007], 传递参数,参数计数 [Excel 2007],命令 [Excel 2007], 调用国际版本,仅 DLL 命令 [Excel 2007],国际版本 [Excel 2007], 调用函数和命令,XLL [Excel 2007], 调用 Excel,Excel 4v 函数 [Excel 2007],xlfn 参数 [Excel 2007],函数 [Excel 2007], 调用国际版本
ms.assetid: 616e3def-e4ec-4f3c-bc65-3b92710da1e6
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
localization_priority: Priority
ms.openlocfilehash: 8f2b63ba84b0a78bbf317c284913a8ec0986436f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32304156"
---
# <a name="calling-into-excel-from-the-dll-or-xll"></a>从 DLL 或 XLL 调用 Excel

**适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
借助 Microsoft Excel，DLL 可访问内置的 Excel 命令、工作表函数和宏表函数。 可按两种方式使用它们：通过从 Visual Basic for Applications (VBA) 调用的 DLL 命令和函数，以及通过 Excel 直接调用的已注册的 XLL 命令和函数。
  
## <a name="excel4-excel4v-excel12-and-excel12v-functions"></a>Excel4、Excel4v、Excel12 和 Excel12v 函数

借助 Excel，DLL 可通过回调函数 [Excel4](excel4-excel12.md)、[Excel4v](excel4v-excel12v.md)、[Excel12](excel4-excel12.md) 和 [Excel12v](excel4v-excel12v.md) 访问命令和函数。
  
Excel 版本 4 中引入了 **Excel4** 和 **Excel4v** 函数。 它们适用于 **XLOPER** 数据结构。 Excel 2007 引入了两个新的回调函数 **Excel12** 和 **Excel12v**，它们适用于 **XLOPER12** 数据结构。 **Excel4** 和 **Excel4v** 函数由 Xlcall32.lib 库导出，后者必须包含在 DLL 或 XLL 项目中。 **Excel12** 和 **Excel12v** 包含在 SDK C++ 源文件 Xlcall.cpp 中；如果想要通过 **XLOPER12** 结构访问 Excel 功能，则必须在项目中包含此文件。 
  
以下代码显示了上述 4 个函数的函数原型。 前三个参数相同，只是第二个参数是一个指针，它同时指向第一对中的 **XLOPER** 和第二对中的 **XLOPER12**。 **Excel4** 和 **Excel12** 中的调用约定是 **_cdecl**，它允许变量参数列表。 省略号表示指向 **Excel4** 的 **XLOPER** 值和 **Excel12** 的 **XLOPER12** 值的指针。 指针数量等于 _count_ 参数的值。 
  
**Excel 的所有版本**
  
 `int _cdecl Excel4(int xlfn, LPXLOPER operRes, int count,... );`
  
 `int pascal Excel4v(int xlfn, LPXLOPER operRes, int count, LPXLOPER opers[]);`
  
**自 Excel 2007 起**
  
 `int _cdecl Excel12(int xlfn, LPXLOPER12 operRes, int count,... );`
  
 `int pascal Excel12v(int xlfn, LPXLOPER12 operRes, int count, LPXLOPER12 opers[]);`
  
要让 DLL 能够调用 **Excel4**、**Excel4v**、**Excel12** 或 **Excel12v**，Excel 必须将控制权传递给 DLL。 这意味着，仅可在以下情况下调用 C API 回调：
  
- 从 Excel 直接调用或通过 VBA 调用的 XLL 命令内部。
    
- 从 Excel 直接调用或通过 VBA 调用的 XLL 工作表或宏表函数内部。
    
不可在以下情况下调用 Excel C API：
  
- 通过操作系统事件（例如，通过 [DllMain](https://docs.microsoft.com/windows/desktop/dlls/dllmain) 函数）。 
    
- 通过 DLL 创建的后台线程。
    
### <a name="return-values"></a>返回值

上述 4 个函数均返回一个整数值，它通知调用方是否成功调用函数或命令。 返回的值可为下述任一值：
  
|**返回值**|**在 Xlcall.h 中定义为**|**说明**|
|:-----|:-----|:-----|
|0  <br/> |**xlretSuccess** <br/> |函数或命令已成功执行。 这并非表示操作不出错。 例如，调用 **FIND** 函数时，即使求值得到 **#VALUE!**，**Excel4** 也可能返回 **xlretSuccess**， 原因是找不到搜索文本。 应检查所返回的 **XLOPER/XLOPER12** 的类型和值（若可能）。  <br/> |
|1  <br/> |**xlretAbort** <br/> |用户已通过单击“**取消**”按钮或按 Esc 键停止命令宏。  <br/> |
|2  <br/> |**xlretInvXlfn** <br/> |所提供的函数或命令代码无效。 当调用函数无权调用函数或命令时，可能出现此错误。 例如，工作表函数无法调用宏表信息函数或命令函数。  <br/> |
|4  <br/> |**xlretInvCount** <br/> |调用中提供的参数数目不正确。  <br/> |
|8  <br/> |**xlretInvXloper** <br/> |一个或多个参数 **XLOPER** 或 **XLOPER12** 值构建或填充错误。  <br/> |
|16  <br/> |**xlretStackOvfl** <br/> |Excel 检测到存在操作可能溢出其堆栈的风险，因此未调用函数。  <br/> |
|32  <br/> |**xlretFailed** <br/> |命令或函数因任一其他返回值未描述的原因而失败。 例如，需要过多内存的操作会失败且出现此错误。 在尝试通过 [xlCoerce](xlcoerce.md) 函数将较大型引用转换为 **xltypeMulti** 数组时，可能发生此问题。  <br/> |
|64  <br/> |**xlretUncalced** <br/> |操作尝试检索未计算的单元格的值。 要在 Excel 中保留重算完整性，工作表函数不可执行此操作。 但是，注册为宏表函数的 XLL 命令和函数可访问未计算的单元格值。  <br/> |
|128  <br/> |**xlretNotThreadSafe** <br/> |（自 Excel 2007 起）注册为线程安全的 XLL 工作表函数尝试调用非线程安全的 C API 函数。 例如，线程安全函数无法调用 XLM 函数 **xlfGetCell**。  <br/> |
|256  <br/> |**xlRetInvAsynchronousContext** <br/> |（自 Excel 2010 起）异步函数句柄无效。  <br/> |
|512  <br/> |**xlretNotClusterSafe** <br/> |（自 Excel 2010 起）群集上不支持此调用。  <br/> |
   
如果函数返回表中的某一失败值（即，不返回 **xlretSuccess**），则 **XLOPER** 或 **XLOPER12** 返回值也将设置为 **#VALUE!**。 在某些情况下，检查此项可能足以测试是否成功，但应注意，调用可同时返回 **xlretSuccess** 和 **#VALUE!**。
  
如果对 C API 的调用导致 **xlretUncalced** 或 **xlretAbort**，则 DLL 或 XLL 代码应将控制权归还给 Excel，然后再进行任何其他 C API 调用（而不是调用 [xlfree](xlfree.md) 函数来释放 **XLOPER** 和 **XLOPER12** 值中由 Excel 分配的内存资源。 
  
### <a name="command-or-function-enumeration-argument-xlfn"></a>命令或函数枚举参数：xlfn

_xlfn_ 参数是回调函数的第一个参数，它是一个 32 位带符号整数。 其值应为 SDK 头文件 Xlcall.h 中定义的函数或命令枚举之一，如下例中所示。 
  
```cs
// Excel function numbers. 
#define xlfCount 0
#define xlfIsna 2
#define xlfIserror 3
#define xlfSum 4
#define xlfAverage 5
#define xlfMin 6
#define xlfMax 7
#define xlfRow 8
#define xlfColumn 9
#define xlfNa 10
...
// Excel command numbers. 
#define xlcBeep (0 | xlCommand)
#define xlcOpen (1 | xlCommand)
#define xlcOpenLinks (2 | xlCommand)
#define xlcCloseAll (3 | xlCommand)
#define xlcSave (4 | xlCommand)
#define xlcSaveAs (5 | xlCommand)
#define xlcFileDelete (6 | xlCommand)
#define xlcPageSetup (7 | xlCommand)
#define xlcPrint (8 | xlCommand)
#define xlcPrinterSetup (9 | xlCommand)
...
```

所有工作表和宏表函数均介于 0 (**xlfCount**) 至 0x0fff 十六进制数之间的范围，但 Excel 2013 中分配的最大数为 547 小数、0x0223 十六进制数 (**xlfFloor_precise**)。
  
所有命令函数均介于 0x8000 十六进制数 (**xlcBeep**) 至 0x8fff 十六进制数，但 Excel 2013 中分配的最大数为 0x8328 十六进制数 (**xlcHideallInkannots**)。 这些在头文件中定义为 `(n | xlCommand)`，其中 `n` 是大于等于 0 的小数，**xlCommand** 定义为 0x8000 十六进制数。 
  
### <a name="invoking-excel-commands-that-use-dialog-boxes"></a>调用使用对话框的 Excel 命令

一些命令代码与 Excel 中使用对话框的操作相对应。 例如，**xlcFileDelete** 采用单一参数：文件名或掩码。 这可通过对话框进行调用，因此用户可取消或修改“删除”操作。 也可在不使用对话框的情况下调用它，此时删除一个或多个文件，但不进行任何后续交互，其中假定文件已存在且调用方具有相关权限。 若要在其对话框形式中调用此类命令，则必须使用按位 OR 操作和 0x1000 (**xlPrompt**) 来组合命令枚举。
  
以下代码示例删除了当前目录中与 mask my_data\*.bak 匹配的文件，仅在参数为 true 时显示对话框。
  
```cs
bool delete_my_backup_files(bool show_dialog)
{
    XLOPER12 xResult, xFilter;
    xFilter.xltype = xltypeStr;
    xFilter.val.str = L"\014my_data*.bak"; // String length: 14 octal
    int cmd;
    if(show_dialog)
        cmd = xlcFileDelete | xlPrompt;
    else
        cmd = xlcFileDelete;
// xResult should be Boolean TRUE if successful, in which
// case return true; otherwise, false.
    return (Excel12(cmd, &xResult, 1, &xFilter) == xlretSuccess
        && xResult.xltype == xltypeBool
        && xResult.val.xbool == 1);
}
```

### <a name="calling-functions-and-commands-in-international-versions"></a>在国际版本中调用函数和命令

可配置 Excel，以按各种语言显示函数和 XLM 命令名称。 某些 C API 命令和函数对解释为函数或命令名称的字符串进行操作。 例如，**xlcFormula** 采用要置于指定的单元格中的字符串参数。 要使加载项适用于所有语言设置，可提供英语字符串名称并在函数或命令枚举中设置位数 0x2000 (**xlIntl**)。
  
以下代码示例在活动工作表的单元格 A2 中放置 `=SUM(X1:X100)` 的等效项。 请注意，它使用框架函数 **TempActiveRef** 来创建临时外部引用 **XLOPER**。 公式将按由区域设置确定的适当语言在 A2 中显示（如果语言为法语，则为 `=SOMME(X1:X100)`）。 
  
```cs
int WINAPI InternationlExample(void)
{
    XLOPER12 xSum, xResult;
    xSum.xltype = xltypeStr;
    xSum.val.str = L"\015=SUM(X1:X100)";
    Excel12(xlcFormula | xlIntl, &xResult, 2,
        &xSum, TempActiveRef(2,2,1,1));
    return 1;
}

```

> [!NOTE]
> 由于对 **Excel12** 的调用的结果不是必需的，则可传递 0 (NULL) 作为第二个参数，而不是传递 **xResult** 的地址。 此内容将在下一部分中详细介绍。 
  
### <a name="dll-only-functions-and-commands"></a>仅 DLL 函数和命令

Excel 支持少量仅可通过 DLL 或 XLL 访问的函数。 这些函数在头文件中定义为 `(n | xlSpecial)`，其中 `n` 是大于等于 0 的小数，`xlSpecial` 定义为 0x4000 十六进制数。 这些函数在下表中列出且记录在 [API 函数引用](excel-xll-sdk-api-function-reference.md)中。
  
||||
|:-----|:-----|:-----|
|[xlFree](xlfree.md) <br/> |0 | xlSpecial  <br/> |释放由 Excel 分配的内存资源。  <br/> |
|[xlStack](xlstack.md) <br/> |1 | xlSpecial  <br/> |返回 Excel 堆栈上的空闲空间。  <br/> |
|[xlCoerce](xlcoerce.md) <br/> |2 | xlSpecial  <br/> |在 **XLOPER** 和 **XLOPER12** 类型之间转换  <br/> |
|[xlSet](xlset.md) <br/> |3 | xlSpecial  <br/> |提供用于设置单元格值的快捷方式。  <br/> |
|[xlSheetId](xlsheetid.md) <br/> |4 | xlSpecial  <br/> |从其内部 ID 获取工作表名称。  <br/> |
|[xlSheetNm](xlsheetnm.md) <br/> |5 | xlSpecial  <br/> |从其名称中获取工作表内部 ID。  <br/> |
|[xlAbort](xlabort.md) <br/> |6 | xlSpecial  <br/> |验证用户是否已单击“**取消**”按钮或按 Esc 键。  <br/> |
|[xlGetInst](xlgetinst.md) <br/> |7 | xlSpecial  <br/> |获取 Excel 实例句柄。  <br/> |
|[xlGetHwnd](xlgethwnd.md) <br/> |8 | xlSpecial  <br/> |获取 Excel 主窗口句柄。  <br/> |
|[xlGetName](xlgetname.md) <br/> |9 | xlSpecial  <br/> |获取 DLL 的路径和文件名。  <br/> |
|[xlEnableXLMsgs](xlenablexlmsgs.md) <br/> |10 | xlSpecial  <br/> |此函数已弃用，因此无需再调用。  <br/> |
|[xlDisableXLMsgs](xldisablexlmsgs.md) <br/> |11 | xlSpecial  <br/> |此函数已弃用，因此无需再调用。  <br/> |
|[xlDefineBinaryName](xldefinebinaryname.md) <br/> |12 | xlSpecial  <br/> |指定一个永久二进制存储名称。  <br/> |
|[xlGetBinaryName](xlgetbinaryname.md) <br/> |13 | xlSpecial  <br/> |获取永久二进制存储名称的数据。  <br/> |
   
## <a name="return-value-xloperxloper12-operres"></a>返回值 XLOPER/XLOPER12：operRes

_operRes_ 参数是回调的第二个参数，并且是一个指向 **XLOPER**（**Excel4** 和 **Excel4v**）或 **XLOPER12**（**Excel12** 和 **Excel12v**）的指针。 成功调用后，它包含函数或命令的返回值。 如果无需返回值，则可将 **operRes** 设置为 0（NULL 指针）。 已覆盖 **operRes** 的先前内容，因此在调用之前必须释放之前指向的所有内存，以避免内存泄露。 
  
如果无法调用函数或命令（例如，在参数错误的情况下），**operRes** 设置为错误 **#VALUE!**。 命令始终返回**布尔值**：如果成功，则返回 **TRUE**如果失败或用户取消此操作，则返回 **FALSE**。 
  
## <a name="number-of-subsequent-arguments-count"></a>后续参数数量：count

_count_ 是回调的第三个参数，它是一个 32 位的带符号整数。 应将其设置为后续参数数量（从 1 开始计数）。 如果函数或命令不采用任何参数，则应设置为 0。 在 Microsoft Office Excel 2003 中，任意函数可采用的参数不得超过 30 个，但大多数函数使用更少的参数。 自 Excel 2007 起，任意函数可采用的参数数目上限增加至 255 个。 
  
使用 **Excel4** 和 **Excel12** 时，_count_ 是指向正在传递的 **XLOPER** 或 **XLOPER12** 值的指针数量。 应小心谨慎，不要传递比 _count_ 所设值更少的参数。 否则，会导致 Excel 先于堆栈进行读取并尝试处理无效的 **XLOPER** 或 **XLOPER12** 值，而这会导致应用程序崩溃。 
  
使用 **Excel4v** 和 **Excel12v** 时，_count_ 是指向要传递为下一个且最后一个参数的 **XLOPER** 或 **XLOPER12** 值的数组大小。 同样，应注意不要传递大小小于 _count_ 元素的数组，因此这会导致溢出数组边界。 
  
## <a name="passing-arguments-to-c-api-functions"></a>向 C API 函数传递参数

**Excel4** 和 **Excel12** 均在 _count_ 后面使用变量长度参数列表，它们被分别解释为指向 **XLOPER** 和 **XLOPER12** 值的指针。 **Excel4v** 和 **Excel12v** 在 _count_ 后面使用单个参数，它是指向 **XLOPER** 值（若为 **Excel4v**）和指向 **XLOPER12** 值（若为 **Excel12v**）的指针数组。
  
借助 **Excel4v** 和 **Excel12v** 数组形式，可在参数数目是一个变量时明确编码对 C API 的调用。 下例显示了一个函数，它采用由变量确定大小的数字数组，并通过 C API 使用 Excel 工作表函数计算总和、平均值、最大值和最小值。 
  
```cs
void Excel12v_example(double *dbl_array, int size, double &sum, double &average, double &min, double &max)
{
// 30 is the limit in Excel 2003. 255 is the limit in Excel 2007.
// Use the lower limit to be safe, although it is better to make
// the function version-aware and use the correct limit.
    if(size < 1 || size > 30)
        return;
// Create an array of XLOPER12 values.
    XLOPER12 *xOpArray = (XLOPER12 *)malloc(size * sizeof(XLOPER12));
// Create an array of pointers to XLOPER12 values.
    LPXLOPER12 *xPtrArray =
        (LPXLOPER12 *)malloc(size * sizeof(LPXLOPER12));
// Initialize and populate the array of XLOPER12 values
// and set up the pointers in the pointer array.
    for(int i = 0; i < size; i++)
    {
        xOpArray[i].xltype = xltypeNum;
        xOpArray[i].val.num = dbl_array[i];
        xPtrArray[i] = xOpArray + i;
    }
    XLOPER12 xResult;
    int retval;
    int fn[4] = {xlfSum, xlfAverage, xlfMin, xlfMax};
    double *result_ptr[4] = {&sum, &average, &min, &max};
    for(i = 0; i < 4; i++)
    {
        retval = Excel12v(fn[i], &xResult, size, xPtrArray);
        if(retval == xlretSuccess && xResult.xltype == xltypeNum)
            *result_ptr[i] = xResult.val.num;
    }
    free(xPtrArray);
    free(xOpArray);
}

```

如果在先前代码中将对 **XLOPER12** 值的引用替换为 **XLOPER**，并将 **Excel12v** 替换为 **Excel4v**，则会导致出现一个适合所有 Excel 版本的函数。 Excel 函数 **SUM**、**AVERAGE**、**MIN** 和 **MAX** 的此操作足够简单，因此可使用 C 更高效地编码它们，同时避免因准备参数和调用 Excel 而产生的开销。 但是，Excel 包含的很多函数更加复杂，这使得此方法在某些情况下很有用。 
  
[xlfRegister](xlfregister-form-1.md) 主题另外提供了一个 **Excel4v** 和 **Excel12v** 使用示例。 注册 XLL 工作表函数时，可为“**粘贴函数**”对话框中的使用的每个参数应用描述性字符串。 因此，要应用于 **xlfRegister** 的参数总数由 XLL 函数使用的参数数量而定，且随函数而异。 
  
如果始终调用具有相同参数数量的 C API 或命令，则需要避免额外的步骤（即，为这些参数创建指针数组）。 在这些情况下，使用 **Excel4** 和 **Excel12** 时操作更简单、界面更清晰。 例如，注册 XLL 函数和命令时，需要提供 DLL 或 XLL 的完整路径和文件名称。 可通过对 **xlfGetName** 的调用获取文件名，然后通过对 **xlFree** 的调用释放它，如 **Excel4** 和 **Excel12** 的下述示例所示。
  
```cs
XLOPER xDllName;
if(Excel4(xlfGetName, &xDllName, 0) == xlretSuccess)
{
    // Use the name, and 
    // then free the memory that Excel allocated for the string.
    Excel4(xlFree, 0, 1, &xDllName);
}
XLOPER12 xDllName;
if(Excel12(xlfGetName, &xDllName, 0) == xlretSuccess)
{
    // Use the name, and
    // then free the memory that Excel allocated for the string.
    Excel12(xlFree, 0, 1, &xDllName);
}

```

实际上，通过创建一个 **xltypeMulti** **XLOPER12** 参数并使用 **Excel12** 调用 C API，可更高效地对函数 **Excel12v_example** 进行编码，如下例所示。
  
```cs
void Excel12_example(double *dbl_array, int size, double &sum, double &average, double &min, double &max)
{
// In this implementation, the upper limit is the largest
// single column array (equals 2^20, or 1048576, rows in Excel 2007).
    if(size < 1 || size > 1048576)
        return;
// Create an array of XLOPER12 values.
    XLOPER12 *xOpArray = (XLOPER12 *)malloc(size * sizeof(XLOPER12));
// Create and initialize an xltypeMulti array
// that represents a one-column array.
    XLOPER12 xOpMulti;
    xOpMulti.xltype = xltypeMulti;
    xOpMulti.val.array.lparray = xOpArray;
    xOpMulti.val.array.columns = 1;
    xOpMulti.val.array.rows = size;
// Initialize and populate the array of XLOPER12 values.
    for(int i = 0; i < size; i++)
    {
        xOpArray[i].xltype = xltypeNum;
        xOpArray[i].val.num = dbl_array[i];
    }
    XLOPER12 xResult;
    int fn[4] = {xlfSum, xlfAverage, xlfMin, xlfMax};
    double *result_ptr[4] = {&sum, &average, &min, &max};
    for(i = 0; i < 4; i++)
    {
        Excel12(fn[i], &xResult, 1, &xOpMulti);
        if(xResult.xltype == xltypeNum)
            *result_ptr[i] = xResult.val.num;
    }
    free(xOpArray);
}

```

> [!NOTE]
> 在本例中，将忽略 **Excel12** 的返回值。 代码改为检查所返回的 **XLOPER12** 是否为 **xltypeNum**，从而确定调用是否成功。 
  
## <a name="xlcallver"></a>XLCallVer

除了回调 **Excel4**、**Excel4v**、**Excel12** 和 **Excel12v**，Excel 还将导出函数 **XLCallVer**，它会返回 C API 当前正在运行的版本。
  
函数原型如下：
  
 `int pascal XLCallVer(void);`
  
可通过任意 XLL 命令或函数调用此函数（它是线程安全的）。
  
在 Excel 97 至 Excel 2003 中，**XLCallVer** 返回 1280 = 0x0500 hex = 5 x 256，它表示 Excel 版本 5。 自 Excel 2007 起，它返回 3072 = 0x0c00 hex = 12 x 256，这表示版本 12。
  
虽然可使用此项来确定能否在运行时使用新的 C API，但你可能偏向于使用 `Excel4(xlfGetWorkspace, &version, 1, &arg)` 来检测正在运行的 Excel 版本，其中 `arg` 是一个设置为 2 的数值 **XLOPER**。 该函数返回一个字符串 **XLOPER**，它表示版本且随后可强制转换为整数。 依赖于 Excel 版本而非 C API 版本的原因在于，加载项同样可能需要检测的 Excel 2000、Excel 2002 和 Excel 2003 之间存在差异。 例如，部分统计函数的准确性进行了更改。
  
## <a name="see-also"></a>另请参阅

- [创建 XLL](creating-xlls.md)  
- [在 Excel 中访问 XLL 代码](accessing-xll-code-in-excel.md)  
- [Excel XLL SDK API 函数引用](excel-xll-sdk-api-function-reference.md)  
- [C API 回调函数 Excel4、Excel12](c-api-callback-functions-excel4-excel12.md)  
- [开发 Excel XLL](developing-excel-xlls.md)

