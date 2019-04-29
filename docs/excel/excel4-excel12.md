---
title: Excel4/Excel12
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Excel12
- Excel4
keywords:
- excel4 函数 [excel 2007], Excel12 函数 [excel 2007]
localization_priority: Normal
ms.assetid: 2404f10d-8641-4ee6-a909-1c5a26610f80
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 7c3af5f380ae4144890b1f7b486a61a05c19de74
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33429444"
---
# <a name="excel4excel12"></a>Excel4/Excel12

**适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
从 DLL/XLL 或代码资源中调用内部 Microsoft Excel 工作表函数、宏工作表函数或命令, 或仅 XLL 特殊函数或命令。
  
Excel 的所有最新版本都支持**Excel4**。 从 Excel 2007 开始, 支持**Excel12** 。 
  
只有当 Excel 已将控制传递给 DLL 或 XLL 时, 才能调用这些函数。 当 Excel 通过对 Visual Basic for Applications (VBA) 的调用间接传递控制时, 也可以调用它们。 任何时候都不能调用它们。 例如, 在调用[DllMain](https://docs.microsoft.com/windows/desktop/dlls/dllmain)函数期间或其他操作系统调用 dll 的线程或由 DLL 创建的线程中, 不能调用这些函数。 
  
[Excel4v 和 Excel12v](excel4v-excel12v.md)函数接受其参数作为数组, 而**Excel4**和**Excel12**函数接受其参数作为堆栈上的可变长度列表。 在所有其他方面, **Excel4**的行为与**Excel4v**相同, **Excel12**的行为与**Excel12v**相同。
  
```cs
int Excel4(int iFunction, LPXLOPER pxRes, int iCount, LPXLOPER argument1, ...);
int Excel12(int iFunction, LPXLOPER12 pxRes, int iCount, LPXLOPER12 argument1, ...);
```

## <a name="parameters"></a>参数

 _iFunction_(**int**)
  
一个数字, 指示要调用的命令、函数或特殊函数。 有关有效_iFunction_值的列表, 请参阅以下备注部分。 
  
 _pxRes_(**LPXLOPER**或**LPXLOPER12**)
  
指向**XLOPER** (带有**Excel4**) 的指针或将包含计算函数结果的**XLOPER12** (带有**Excel12**)。
  
 _iCount_(**int**)
  
将传递给函数的后续参数的数目。 在 Excel 的 Excel 版本中, 最多为 2003, 可以是0到30之间的任意数字。 从 Excel 2007 开始, 可以是0到255之间的任意数字。
  
 _argument1 ..._(**LPXLOPER**或**LPXLOPER12**)
  
函数的可选参数。 所有参数都必须是指向**XLOPER**或**XLOPER12**值的指针。 
  
## <a name="return-value"></a>返回值

返回以下整数 (**int**) 值之一。
  
|**值**|**返回代码**|**说明**|
|:-----|:-----|:-----|
|0  <br/> |**xlretSuccess** <br/> |成功调用函数。 这并不意味着函数不返回 Excel 错误值;若要找到该参数, 您必须查看生成的_pxRes_参数的类型和值。  <br/> |
|1  <br/> |**xlretAbort** <br/> |命令或函数异常终止 (内部终止)。 如果 XLM 宏工作表通过调用**CLOSE**或 Excel 内存不足, 则会发生这种情况。 如果 Excel 返回此错误, 则调用函数必须立即退出。 仅允许 DLL 在退出之前调用**xlFree** 。 不允许对 C API 进行其他所有调用。 用户可以使用 "**文件**" 菜单上的 "**保存**" 命令, 以交互方式保存任何工作。  <br/> |
|双面  <br/> |**xlretInvXlfn** <br/> |提供了无效的函数编号。 如果使用的是 xlcall.h 头文件中的常量, 则不应发生此情况, 除非您调用的是运行的 Excel 版本中不支持的内容。  <br/> |
|4  <br/> |**xlretInvCount** <br/> |输入的参数数目无效。 在最高版本为 Excel 2003 的情况下, 任何函数可以执行的最大参数数为30个。 从 Excel 2007 开始, 最大数目为255。 有些参数需要固定的或最少的参数数目。  <br/> |
|utf-8  <br/> |**xlretInvXloper** <br/> |向函数传递了无效的**XLOPER**或**XLOPER12** , 或者使用了错误类型的参数。  <br/> |
|16   <br/> |**xlretStackOvfl** <br/> |堆栈溢出发生。 使用**xlStack**监视堆栈上留下的空间量。 尽可能避免在堆栈上分配非常大的本地 (自动) 数组和结构。使其成为静态的。 (请注意, 在未检测到堆栈溢出的情况下可能会发生。)  <br/> |
|32  <br/> |**xlretFailed** <br/> |命令等效的函数失败。 这与显示 "宏错误警告" 对话框的宏命令是等效的。  <br/> |
|64  <br/> |**xlretUncalced** <br/> |试图对尚未计算的单元格进行取消引用, 因为它计划在当前单元格后重新计算。 在这种情况下, DLL 应立即将控制返回到 Excel。 仅允许 DLL 在退出之前调用**xlFree** 。 不允许对 C API 进行其他所有调用。 有关哪些函数可以和无法访问尚未重新计算的单元格的值的详细信息, 请参阅[Excel 命令、函数和状态](excel-commands-functions-and-states.md)。  <br/> |
|128  <br/> |**xlretNotThreadSafe** <br/> |试图调用在工作簿的多线程重新计算期间线程安全的函数 (或可能不是线程安全)。  <br/> 从 Excel 2007 开始, 将返回此值, 并且仅在声明为线程安全的 XLL 工作表函数中。  <br/> |
|256  <br/> |**xlRetInvAsynchronousContext** <br/> |异步函数句柄无效。  <br/> 此值仅由 Excel 2010 使用。  <br/> |
|512  <br/> |**xlRetNotClusterSafe** <br/> |群集上不支持该呼叫。  <br/> 此值仅由 Excel 2010 使用。  <br/> |
   
## <a name="remarks"></a>说明

### <a name="valid-ifunction-values"></a>有效的 iFunction 值

有效的**iFunction**值为 xlcall.h 头文件中定义的任意 **.xlf**或 **.xlc**常量, 或以下任何特殊函数。 
  
|||||
|:-----|:-----|:-----|:-----|
|**xlAbort** <br/> |**xlEnableXLMsgs** <br/> |**xlGetInst** <br/> |**xlSheetNm** <br/> |
|**xlCoerce** <br/> |**xlFree** <br/> |**xlGetName** <br/> |**xlStack** <br/> |
|**xlDefineBinaryName** <br/> |**xlGetBinaryName** <br/> |**xlSet** <br/> |**xlUDF** <br/> |
|**xlDisableXLMsgs** <br/> |**xlGetHwnd** <br/> |**xlSheetId** <br/> ||
   
### <a name="different-types-of-functions"></a>不同类型的函数

 **Excel4**和**Excel12**区分三类函数。 根据 Excel 可能调用 DLL 的三种状态对函数进行分类。 
  
- 当从工作表中调用 DLL 作为重新计算的结果时, 将应用类1。 
    
- 当从函数宏或工作表中调用 DLL 时, 类2适用于在键入文本中用数字符号 (#) 注册的工作表。
    
- 当从对象、宏、菜单、工具栏、快捷键、 **ExecuteExcel4Macro**方法或**工具/宏/运行**命令调用 DLL 时, 将应用类3。 有关详细信息, 请参阅[Excel 命令、函数和状态](excel-commands-functions-and-states.md)。
    
下表显示了每个类中的有效函数。
  
|**1 类**|**2 类**|**3 类**|
|:-----|:-----|:-----|
|任何工作表函数  <br/> 除**xlSet**外的任何仅 XLL **xl ...** 函数。  <br/> **xlfCaller** <br/> |任何工作表函数  <br/> 除**xlSet**以外的任何**xl**函数。  <br/> 宏工作表函数 (包括**xlfCaller**) 返回一个值, 但不执行影响工作区或任何打开的工作簿的操作。  <br/> |任何函数, 包括**xlSet**和命令等效的函数。  <br/> |
   
### <a name="displaying-the-dialog-box-for-a-command-equivalent-function"></a>显示等效于命令的函数的对话框

如果等效命令的函数有关联的对话框, 则可以在**iFunction**中设置**xlPrompt**位。 这意味着在执行此命令之前, Excel 将显示相应的对话框。
  
### <a name="writing-international-dlls"></a>编写国际 dll

如果在**iFunction**中设置**xlIntl**位, 则会执行函数或命令, 就像它是从国际宏表中调用一样。 这意味着该命令的行为与 Excel 的美国版本相同, 即使它在国际 (本地化) 版本上运行也是如此。
  
### <a name="xlretuncalced-or-xlretabort"></a>xlretUncalced 或 xlretAbort

在接收到这些返回值之一之后, 您的 DLL 必须立即清除控件并将其返回到 Excel。 在接收到这些返回值之一后, 通过 C API 对 Excel 的回调 ( **xlFree**除外) 将被禁用。
  
## <a name="example"></a>示例

下面的示例使用**Excel12**函数选择从中调用它的单元格。 
  
此代码示例是 Excel 2010 XLL SDK 中提供的更大示例的一部分, 该示例位于您安装 SDK 的以下位置:
  
\Samples\Example\Example.c。
  
> [!NOTE]
> 此函数调用命令宏 (xlcSelect), 因此, 仅当从 XLM 宏表中调用该宏时, 才会运行该宏。 
  
```cs
short WINAPI Excel12Example(void)
{
    XLOPER12 xRes;
    Excel12(xlfCaller, &xRes, 0);
    Excel12(xlcSelect, 0, 1, (LPXLOPER12)&xRes);
    Excel12(xlFree, 0, 1, (LPXLOPER12)&xRes);
    return 1;
}
```

## <a name="see-also"></a>另请参阅



[Excel4v/Excel12v](excel4v-excel12v.md)

