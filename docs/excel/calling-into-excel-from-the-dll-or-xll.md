---
title: 从 DLL 或 XLL 调用 Excel
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
keywords:
- 对话框 [excel 2007]，调用 excel 命令、 Dll [Excel 2007]，导入 Excel，向 C API 函数 [Excel 2007]，传递参数调用命令 [Excel 2007] 中，调用带有对话框，命令 [Excel 2007]，可以从 DLL/XLL，Excel4 访问函数 [Excel 2007 中]，Excel12 函数 [Excel 2007，] XLCallVer 函数 [Excel 2007]，operRes 参数 [Excel 2007]、 函数 [Excel 2007]，可以从 DLL/XLL，Excel12v 访问函数 [Excel 2007] 中，仅 DLL 传递函数 [Excel 2007]，C API [Excel 2007]参数计数参数 [Excel 2007]、 国际版本中调用命令 [Excel 2007，]、 仅 DLL 命令 [Excel 2007]、 国际版本 [Excel 2007]、 调用函数和命令，将调用 Excel，Excel 4v 函数 [Xll [Excel 2007]Excel 2007] xlfn 参数 [Excel 2007]，[Excel 2007]，函数调用国际版本中
localization_priority: Normal
ms.assetid: 616e3def-e4ec-4f3c-bc65-3b92710da1e6
description: ���÷�Χ�� Excel 2013?| Office 2013?| Visual Studio
ms.openlocfilehash: 3f36d2f59b7f5bef9f9ffdca4d13e95c788bf113
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773689"
---
# <a name="calling-into-excel-from-the-dll-or-xll"></a>从 DLL 或 XLL 调用 Excel

**适用于**： Excel 2013 |Office 2013 |Visual Studio 
  
Microsoft Excel 使您能够访问内置 Excel 命令、 工作表功能和宏工作表函数的 DLL。 这些是可同时从 DLL 命令和从 Visual Basic for Applications (VBA)，并从注册的 XLL 命令和由 Excel 直接调用的函数调用的函数。
  
## <a name="excel4-excel4v-excel12-and-excel12v-functions"></a>Excel4、 Excel4v、 Excel12 和 Excel12v 函数

Excel 启用 DLL 以通过[Excel4](excel4-excel12.md)、 [Excel4v](excel4v-excel12v.md)、 [Excel12](excel4-excel12.md)和[Excel12v](excel4v-excel12v.md)的回调函数中访问的命令和功能。
  
Excel 版本 4 中引入的**Excel4**和**Excel4v**函数。 他们使用**XLOPER**数据结构。 Excel 2007 中引入的两个新回调函数， **Excel12**和**Excel12v**，使用**XLOPER12**数据结构。 由库 Xlcall32.lib，必须包括在您的 DLL 或 XLL 项目导出的**Excel4**和**Excel4v**函数。 在 SDK c + + 源文件 Xlcall.cpp，如果您想要使用**XLOPER12**结构访问 Excel 功能必须包含在您的项目中包含**Excel12**和**Excel12v** 。 
  
下面的代码演示以下四个函数的函数的原型。 第二个参数是一个指向中的第一对**XLOPER**和一个指向中的第二个对**XLOPER12**处在于前, 三个参数都是相同的。 调用约定 **_cdecl** **Excel4**和**Excel12**允许变量参数列表中。 省略号表示为**Excel4** **XLOPER**值和**Excel12** **XLOPER12**值的指针。 指针数等于_计数_参数的值。 
  
**所有版本的 Excel**
  
 `int _cdecl Excel4(int xlfn, LPXLOPER operRes, int count,... );`
  
 `int pascal Excel4v(int xlfn, LPXLOPER operRes, int count, LPXLOPER opers[]);`
  
**从 Excel 2007**
  
 `int _cdecl Excel12(int xlfn, LPXLOPER12 operRes, int count,... );`
  
 `int pascal Excel12v(int xlfn, LPXLOPER12 operRes, int count, LPXLOPER12 opers[]);`
  
为了能够调用**Excel4**、 **Excel4v**、 **Excel12**或**Excel12v**DLL，Excel 必须对 DLL 通过控件。 这意味着这些 C API 回调，可以调用仅在以下方案：
  
- 从 Excel XLL 命令呼叫直接或通过 VBA。
    
- 从 XLL 工作表或宏工作表函数中的 Excel 呼叫直接或通过 VBA。
    
在下列情况下，不能调用 Excel C API:
  
- 从操作系统事件 （例如，从[DllMain](http://msdn.microsoft.com/library/base.dllmain%28Office.15%29.aspx)函数）。 
    
- 从您的 DLL 创建后台线程。
    
### <a name="return-values"></a>返回值

所有四个这些函数都返回一个整数值，以告知呼叫者的函数或命令是否成功调用。 返回的值可以是以下任一项：
  
|**返回值**|**作为 Xlcall.h 中定义**|**说明**|
|:-----|:-----|:-----|
|0  <br/> |**xlretSuccess** <br/> |该函数或命令成功执行。 这并不意味着执行已出现错误。 例如， **Excel4**无法返回**xlretSuccess**时调用的函数**查找**，即使为将对它求值 **#VALUE ！** 因为找不到搜索文本。 您应该检查的类型和值返回**XLOPER/XLOPER12**这种可能性。  <br/> |
|1  <br/> |**xlretAbort** <br/> |用户单击**取消**按钮，或按 ESC 键停止命令宏。  <br/> |
|2  <br/> |**xlretInvXlfn** <br/> |提供的函数或命令代码无效。 调用函数没有调用的函数或命令的权限时，会发生此错误。 例如，工作表函数不能调用宏工作表信息函数或命令函数。  <br/> |
|4  <br/> |**xlretInvCount** <br/> |不正确的调用中提供的参数数目。  <br/> |
|8  <br/> |**xlretInvXloper** <br/> |一个或多个参数**XLOPER**或**XLOPER12**值是不正确地形成或填充。  <br/> |
|16  <br/> |**xlretStackOvfl** <br/> |Excel 检测到风险操作可能溢出其堆栈和，因此，不调用此函数。  <br/> |
|32  <br/> |**xlretFailed** <br/> |命令或函数失败原因不描述其他返回值之一。 操作需要太多的内存，例如，将失败并出现此错误。 这可能是在试图将一个非常大**xltypeMulti**数组引用转换使用[xlCoerce](http://msdn.microsoft.com/library/guid_9d47c16c-a7e7-4998-b594-9cf001827b7b%28Office.15%29.aspx)函数。  <br/> |
|64  <br/> |**xlretUncalced** <br/> |尝试检索未计算的单元格的值的操作。 若要保留在 Excel 中的重新计算完整性，工作表函数不允许这样做。 但是，XLL 命令和函数注册为宏工作表函数允许访问未计算的单元格的值。  <br/> |
|128  <br/> |**xlretNotThreadSafe** <br/> |（在 Excel 2007 中从开始）注册为线程安全的 XLL 工作表函数尝试调用的 C API 函数，不是线程安全。 例如，线程安全函数不能调用 XLM 函数**xlfGetCell**。  <br/> |
|256  <br/> |**xlRetInvAsynchronousContext** <br/> |（从开始在 Excel 2010 中）无效的异步函数句柄。  <br/> |
|512  <br/> |**xlretNotClusterSafe** <br/> |（从开始在 Excel 2010 中）在群集上不支持呼叫。  <br/> |
   
如果该函数返回故障值之一表中 （即，它不会返回**xlretSuccess**），也将被**XLOPER**或**XLOPER12**返回值设置为 **#VALUE ！**。 在某些情况下，检查的这可能是足够测试的成功，但应注意呼叫可以返回两个**xlretSuccess**和 **#VALUE ！**。
  
如果**xlretUncalced**或**xlretAbort**中的 C API 结果调用，DLL 或 XLL 代码应返回控件联接 Excel （而非[xlfree](http://msdn.microsoft.com/library/guid_8ce2eef2-0138-495d-b6cb-bbb727a3cda4%28Office.15%29.aspx)函数调用发布 Excel 分配内存的任何其他 C API 调用之前资源中**XLOPER**和**XLOPER12**值）。 
  
### <a name="command-or-function-enumeration-argument-xlfn"></a>命令或函数枚举参数： xlfn

_Xlfn_参数是第一个参数给回调函数和是 32 位有符号的整数。 下面的示例中所示，其值应为 Xlcall.h，SDK 标头文件中定义的函数或命令枚举之一。 
  
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

所有的工作表和宏工作表函数位于范围为 0 (**xlfCount**) 通过 0x0fff 十六进制，虽然，最大分配 Excel 2013 中的号码是 547 小数，0x0223 十六进制 (**xlfFloor_precise**)。
  
所有命令函数都是介于 0x8000 十六进制 (**xlcBeep**) 通过 0x8fff 十六进制，尽管 Excel 2013 中的最大分配的数字 0x8328 十六进制 (**xlcHideallInkannots**)。 这些为标头文件中定义`(n | xlCommand)`其中`n`是十进制数大于或等于 0 和**xlCommand**定义为 0x8000 十六进制。 
  
### <a name="invoking-excel-commands-that-use-dialog-boxes"></a>调用 Excel 命令使用对话框

一些命令代码对应于在 Excel 中使用对话框的操作。 例如， **xlcFileDelete**采用单个参数： 文件名或掩码。 这可以调用与对话框中，以便用户有机会取消或修改删除操作。 它还可以调用对话框的情况下没有任何进一步的交互，假定存在和呼叫者具有的权限在这种情况下删除的文件。 若要在其对话框窗体中调用此类命令，必须按 0x1000 (**xlPrompt**) 中使用按位 OR 运算组合枚举的命令。
  
下面的代码示例删除匹配掩码 my_data 在当前目录中的文件\*.bak，参数为 true 时才显示一个对话框。
  
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

### <a name="calling-functions-and-commands-in-international-versions"></a>调用的函数和国际版本中的命令

您可以配置 Excel 以多种语言显示函数和 XLM 命令名称。 某些 C API 命令和函数运行对解释为函数或命令名称的字符串。 例如， **xlcFormula**采用字符串参数的旨在放置在指定的单元格。 为您外接程序来处理所有语言设置，可以提供英语字符串名称和函数或命令枚举中设置的位 0x2000 (**xlIntl**)。
  
下面的代码示例将放在的等效项`=SUM(X1:X100)`活动工作表的单元格 A2 中。 请注意，它使用框架函数， **TempActiveRef**，来创建的临时外部引用**XLOPER**。 公式中 A2 显示正确的区域设置确定语言 (例如，`=SOMME(X1:X100)`如果语言是法语)。 
  
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
> 到**Excel12**调用的结果不是必需的因为无法作为第二个参数，而不是**xResult**的地址传递零 (NULL)。 这是详细讨论一节中。 
  
### <a name="dll-only-functions-and-commands"></a>仅 DLL 函数和命令

Excel 支持函数只能从 DLL 或 XLL 可访问的一个小数字。 这些为标头文件中定义`(n | xlSpecial)`其中`n`是十进制数大于或等于 0 和`xlSpecial`定义为 0x4000 十六进制。 下表中列出并[API 函数引用](excel-xll-sdk-api-function-reference.md)中记录这些函数。
  
||||
|:-----|:-----|:-----|
|[xlFree](xlfree.md) <br/> |0 | xlSpecial  <br/> |释放 Excel 分配内存资源。  <br/> |
|[xlStack](xlstack.md) <br/> |1 | xlSpecial  <br/> |返回 Excel 堆栈上的可用空间。  <br/> |
|[xlCoerce](xlcoerce.md) <br/> |2 | xlSpecial  <br/> |**XLOPER**和**XLOPER12**类型之间进行转换  <br/> |
|[xlset，则](xlset.md) <br/> |3 | xlSpecial  <br/> |提供快速设置单元格的值的方法。  <br/> |
|[xlSheetId](xlsheetid.md) <br/> |4 | xlSpecial  <br/> |从内部 ID 获取工作表名称  <br/> |
|[xlSheetNm](xlsheetnm.md) <br/> |5 | xlSpecial  <br/> |从其名称中获取工作表内部 ID。  <br/> |
|[xlAbort](xlabort.md) <br/> |6 | xlSpecial  <br/> |验证用户是否单击**取消**按钮，或者按 ESC 键。  <br/> |
|[xlGetInst](xlgetinst.md) <br/> |7 | xlSpecial  <br/> |获取 Excel 实例句柄。  <br/> |
|[xlGetHwnd](xlgethwnd.md) <br/> |8 | xlSpecial  <br/> |获取 Excel 主窗口句柄。  <br/> |
|[xlGetName](xlgetname.md) <br/> |9 | xlSpecial  <br/> |获取 DLL 的路径和文件名称。  <br/> |
|[xlEnableXLMsgs](xlenablexlmsgs.md) <br/> |10 | xlSpecial  <br/> |此函数已被弃用，并且不再需要调用。  <br/> |
|[xlDisableXLMsgs](xldisablexlmsgs.md) <br/> |11 | xlSpecial  <br/> |此函数已被弃用，并且不再需要调用。  <br/> |
|[xlDefineBinaryName](xldefinebinaryname.md) <br/> |12 | xlSpecial  <br/> |定义持久二进制存储名称。  <br/> |
|[xlGetBinaryName](xlgetbinaryname.md) <br/> |13 | xlSpecial  <br/> |获取的持久性二进制存储区名称数据。  <br/> |
   
## <a name="return-value-xloperxloper12-operres"></a>返回值 XLOPER/XLOPER12: operRes

_OperRes_参数是回调到第二个参数，并且指向**XLOPER** （**Excel4**和**Excel4v**） 或**XLOPER12** （**Excel12**和**Excel12v**） 的指针。 成功调用后，它包含的函数或命令的返回值。 如果没有返回值，则需要，可以是**operRes**设置为零 （NULL 指针）。 以前的**operRes**内容将覆盖以便必须呼叫以避免出现内存泄漏之前释放以前指向任何内存。 
  
**OperRes**如果 （例如，如果参数不正确），则不能调用的函数或命令，将设置为错误 **#VALUE ！**。 如果成功，或**FALSE**如果失败或用户取消该命令始终返回**布尔值** **，则返回 TRUE** 。 
  
## <a name="number-of-subsequent-arguments-count"></a>随后参数数目错误： 计数

_Count_参数是回调的第三个参数，并且是 32 位有符号的整数。 它应设置为后续参数，从 1 开始计数的数目。 如果函数或命令不采用任何参数，它应设置为零。 在 Microsoft Office Excel 2003 中，可以采取任何函数的参数的最大数目是 30，但是大部分采用少于这。 从 Excel 2007 开始，可以执行任何函数的参数的最大数量增加到 255。 
  
使用**Excel4**和**Excel12**， _count_是指向**XLOPER**或**XLOPER12**传递的值的数目。 您应该谨慎以传递的_计数_的值比少参数设置为。 这会导致 Excel 读取提前堆栈和尝试处理无效**XLOPER**或**XLOPER12**值，可能会导致应用程序崩溃。 
  
使用**Excel4v**和**Excel12v**， _count_是数组的作为下一个和最后一个参数传递的指向**XLOPER**或**XLOPER12**值的大小。 同样，您应该谨慎以传递较小比大小的_count_元素数组，因为这将导致的数组正在溢出边界。 
  
## <a name="passing-arguments-to-c-api-functions"></a>向 C API 函数传递参数

**Excel4**和**Excel12**采用可变长度参数列表后_计数_，其分别解释为指向**XLOPER**和**XLOPER12**值。 **Excel4v**和**Excel12v**采用单个参数后_计数_，它是一个指向的指针到**Excel4v**，对于**XLOPER**值和对于**Excel12v** **XLOPER12**值的数组。
  
数组窗体、 **Excel4v**和**Excel12v**，使您能够变量的参数数目时完全代码 C API 调用。 下面的示例演示一个函数，采用大小可变的数组的号码，并使用 Excel 工作表函数，通过 C API，计算 sum、 平均、 最小和最大。 
  
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

替换**XLOPER**，并使用**Excel4v** **Excel12v** **XLOPER12**值的引用，在前面的代码将导致在将处理所有版本的 Excel 函数中。 此操作的 Excel 函数**SUM**、**平均**、**最小值**，和**最大**相当简单，就像它们中 C 的代码，并避免准备参数和调用 Excel 的开销更有效。 但是，许多 Excel 中包含的功能是更复杂，使有用在某些情况下，此方法。 
  
[XlfRegister](http://msdn.microsoft.com/library/guid_c730124c-1886-4a0f-8f06-79763025537d%28Office.15%29.aspx)主题提供了使用**Excel4v**和**Excel12v**的另一个示例。 当注册 XLL 工作表函数，您可以提供**粘贴函数**对话框中使用的每个参数的描述性字符串。 因此，要提供给**xlfRegister**的总参数数目取决于 XLL 函数的参数数目，并且将因到下一个函数。 
  
如果您始终调用的 C API 函数或命令具有相同数量的参数，您想要避免创建数组为这些参数的指针的额外的步骤。 在这种情况下，会使用**Excel4**和**Excel12**更加简练。 例如，当注册 XLL 函数和命令，您需要提供的 DLL 或 XLL 的完整路径和文件名称。 您可以获取**xlfGetName**调用中的文件名称，然后将它与**xlFree**，调用释放如**Excel4**和**Excel12**下面的示例中所示。
  
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

实际上，该函数， **Excel12v_example**，无法通过创建单个**xltypeMulti** **XLOPER12**参数，并使用**Excel12**，调用 C API，如下面的示例中所示更有效地编码。
  
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
> 在这种情况下， **Excel12**返回值将被忽略。 该代码改为检查返回的**XLOPER12**是**xltypeNum**确定呼叫是否成功。 
  
## <a name="xlcallver"></a>XLCallVer

除了回调**Excel4**、 **Excel4v**、 **Excel12**和**Excel12v**Excel 导出函数**XLCallVer**，它返回当前正在运行的 C API 的版本。
  
函数原型如下所示：
  
 `int pascal XLCallVer(void);`
  
您可以调用此函数，它是线程安全的从任何 XLL 命令或函数。
  
在 Excel 97 至 Excel 2003， **XLCallVer**返回 1280 = 0x0500 十六进制 = 5 x 256，这表明 Excel 版本 5。 从 Excel 2007 开始，返回 3072 = 0x0c00 十六进制 = 12 x 256，同样指示版本 12。
  
尽管您可以使用此方法来确定新的 C API 在运行时是否可用，但您可能希望使用检测正在运行的 Excel 版本`Excel4(xlfGetWorkspace, &version, 1, &arg)`，其中`arg`是**XLOPER**设置为 2 的数字。 此函数返回字符串**XLOPER**，版本，然后可以强制为一个整数值。 依赖的 Excel 版本，而不是 C API 版本的原因是 Excel 2000、 Excel 2002 和 Excel 2003 的加载项可能还需要检测之间的差异。 例如，更改的统计信息功能的一些准确性。
  
## <a name="see-also"></a>另请参阅



[创建 xll （英文）](creating-xlls.md)
  
[在 Excel 中访问 XLL 代码](accessing-xll-code-in-excel.md)
  
[Excel XLL SDK API Function Reference](excel-xll-sdk-api-function-reference.md)
  
[C API Callback Functions Excel4, Excel12](c-api-callback-functions-excel4-excel12.md)
  
[Developing Excel XLLs](developing-excel-xlls.md)

