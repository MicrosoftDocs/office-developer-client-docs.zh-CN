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
- excel4 函数 [excel 2007]，Excel12 函数 [Excel 2007]
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
  
从 DLL/XLL 或代码Microsoft Excel调用内部工作表函数、宏工作表函数或命令或仅 XLL 的特殊函数或命令。
  
所有最新版本的 Excel都支持 **Excel4。** 从 2007 Excel开始，**支持 Excel12。** 
  
只有在将控件传递给 DLL Excel XLL 时，才能调用这些函数。 当通过调用 VBA Excel间接传递控制权时，也可以Visual Basic for Applications (这些) 。 无法在其他时间调用它们。 例如，在调用 [DllMain](https://docs.microsoft.com/windows/desktop/dlls/dllmain) 函数期间或操作系统调用 DLL 时的其他时间，或者从 DLL 创建的线程调用它们时，无法调用它们。 
  
[Excel4v 和 Excel12v](excel4v-excel12v.md)函数接受其参数作为数组，**而 Excel4** 和 **Excel12** 函数接受其参数作为堆栈上的可变长度列表。 在所有其他方面 **，Excel4** 的行为与 **Excel4v** 相同， **而 Excel12** 的行为与 **Excel12v 相同**。
  
```cs
int Excel4(int iFunction, LPXLOPER pxRes, int iCount, LPXLOPER argument1, ...);
int Excel12(int iFunction, LPXLOPER12 pxRes, int iCount, LPXLOPER12 argument1, ...);
```

## <a name="parameters"></a>参数

 _iFunction_ (**int)**
  
指示要调用的命令、函数或特殊函数的编号。 有关有效  _iFunction_ 值的列表，请参阅以下"备注"部分。 
  
 _pxRes_ (**LPXLOPER** 或 **LPXLOPER12**) 
  
指向包含 **Excel4** (的 **XLOPER**) 或包含 Excel12 (的 **XLOPER12** **) ，** 其中将保存计算函数的结果。
  
 _iCount_ (**int)**
  
将传递给函数的后续参数的数量。 在 2003 Excel版本中，它可以是 0 到 30 的任何数字。 从 Excel 2007 开始，可以是从 0 到 255 的任何数字。
  
 _argument1， ..._ (**LPXLOPER** 或 **LPXLOPER12**) 
  
函数的可选参数。 所有参数都必须是指向 **XLOPER** 或 **XLOPER12 值的** 指针。 
  
## <a name="return-value"></a>返回值

返回整数值中的 (**整数)** 之一。
  
|**值**|**返回代码**|**说明**|
|:-----|:-----|:-----|
|0  <br/> |**xlretSuccess** <br/> |函数已成功调用。 这并不意味着函数未返回错误Excel错误值;若要了解这一点，您必须查看生成的 _pxRes_ 参数的类型和值。  <br/> |
|1  <br/> |**xlretAbort** <br/> |命令或函数在内部中止 (异常) 。 如果 XLM 宏表通过调用 **CLOSE** 来关闭自身，或者如果 Excel内存不足，则会发生此情况。 如果Excel返回此错误，则调用函数必须立即退出。 仅在退出之前，DLL 才允许调用 **xlFree。** 不允许对 C API 进行所有其他调用。 用户可以使用"文件"菜单上的"保存 **"** 命令以交互方式保存 **任何** 工作。  <br/> |
|2  <br/> |**xlretInvXlfn** <br/> |提供了无效的函数编号。 如果使用 Xlcall.h 头文件的常量，则不应发生这种情况，除非调用的项在所运行的 Excel版本中不受支持。  <br/> |
|4   <br/> |**xlretInvCount** <br/> |输入的参数数目无效。 在 2003 Excel版本中，任何函数可以接受的参数的最大数量为 30。 从 2007 Excel，最大数量为 255。 一些参数需要固定或最小数量的参数。  <br/> |
|8   <br/> |**xlretInvXloper** <br/> |向函数 **传递了无效的 XLOPER** 或 **XLOPER12，** 或者使用了错误类型的参数。  <br/> |
|16   <br/> |**xlretStackOvfl** <br/> |发生堆栈溢出。 使用 **xlStack** 监视堆栈上留下的空间量。 如果可能，避免 (在) 数组和结构上自动分配非常大的本地数组和结构;使其静态。  (请注意，可能不会检测到堆栈溢出。)   <br/> |
|32  <br/> |**xlretFailed** <br/> |命令等效函数失败。 这等效于显示宏错误警告对话框的宏命令。  <br/> |
|64  <br/> |**xlretUncalced** <br/> |试图取消引用尚未计算的单元格，因为它计划在当前单元格之后重新计算。 在这种情况下，DLL 应立即将控件返回Excel。 仅在退出之前，DLL 才允许调用 **xlFree。** 不允许对 C API 进行所有其他调用。 有关哪些函数可以访问和无法访问尚未重新计算的单元格的值的信息，请参阅Excel、[函数和状态。](excel-commands-functions-and-states.md)  <br/> |
|128  <br/> |**xlretNotThreadSafe** <br/> |尝试在多线程重新计算工作簿期间调用非线程安全函数，也可能不是线程安全函数。  <br/> 从 Excel 2007 开始，将返回此值，并且仅在声明为线程安全的 XLL 工作表函数中返回此值。  <br/> |
|256  <br/> |**xlRetInvAsynchronousContext** <br/> |异步函数句柄无效。  <br/> 此值仅由 Excel 2010 使用。  <br/> |
|512  <br/> |**xlRetNotClusterSafe** <br/> |群集上不支持此调用。  <br/> 此值仅由 Excel 2010 使用。  <br/> |
   
## <a name="remarks"></a>备注

### <a name="valid-ifunction-values"></a>有效的 iFunction 值

有效的 **iFunction** 值是 Xlcall.h 头文件中定义的任何 **xlf...** 或 **xlc...** 常量或以下任何特殊函数。 
  
|||||
|:-----|:-----|:-----|:-----|
|**xlAbort** <br/> |**xlEnableXLMsgs** <br/> |**xlGetInst** <br/> |**xlSheetNm** <br/> |
|**xlCoerce** <br/> |**xlFree** <br/> |**xlGetName** <br/> |**xlStack** <br/> |
|**xlDefineBinaryName** <br/> |**xlGetBinaryName** <br/> |**xlSet** <br/> |**xlUDF** <br/> |
|**xlDisableXLMsgs** <br/> |**xlGetHwnd** <br/> |**xlSheetId** <br/> ||
   
### <a name="different-types-of-functions"></a>不同类型的函数

 **Excel4** 和 **Excel12** 区分三类函数。 这些函数根据三种状态进行分类，Excel调用 DLL。 
  
- 当由于重新计算而从工作表调用 DLL 时，类 1 适用。 
    
- 当从函数宏中或从在类型文本中用数字符号 (#) 注册的工作表中调用 DLL 时，类 2 适用。
    
- 从对象、宏、菜单、工具栏、快捷键 **、ExecuteExcel4Macro** 方法或 **工具/宏/运行** 命令调用 DLL 时，类 3 适用。 有关详细信息，请参阅[Excel、函数和状态](excel-commands-functions-and-states.md)。
    
下表显示了每个类中的有效函数。
  
|**1 类**|**2 类**|**3 类**|
|:-----|:-----|:-----|
|任何工作表函数  <br/> 除 **xlSet** 之外的任何仅 **XLL xl...** 函数。  <br/> **xlfCaller** <br/> |任何工作表函数  <br/> 除 **xlSet** 之外的任何 **xl... 函数**。  <br/> 宏表函数（包括 **xlfCaller）** 返回值，但不执行影响工作区或任何打开的工作簿的操作。  <br/> |任何函数，包括 **xlSet** 和命令等效函数。  <br/> |
   
### <a name="displaying-the-dialog-box-for-a-command-equivalent-function"></a>显示活动函数Command-Equivalent对话框

如果命令等效函数具有关联的对话框，可以在 **iFunction** 中设置 **xlPrompt** 位。 这意味着，Excel命令之前显示相应的对话框。
  
### <a name="writing-international-dlls"></a>编写国际 DLL

如果在 **iFunction** 中设置 **xlIntl** 位，将执行函数或命令，就像从国际宏表调用它一样。 这意味着该命令的行为与在美国版本的 Excel 上的行为一样，即使它运行在本地化版本上的 (也) 运行。
  
### <a name="xlretuncalced-or-xlretabort"></a>xlretUncalced 或 xlretAbort

收到这些返回值之一后，DLL 必须清除并返回控件，以Excel控件。 在收到这些Excel值之一后，将禁用通过 C API 的回调 **（xlFree** 除外）。
  
## <a name="example"></a>示例

以下示例使用 **Excel12** 函数选择从中调用该函数的单元格。 
  
此代码示例是 Excel 2010 XLL SDK 中提供的较大示例的一部分，位于安装 SDK 的以下位置：
  
\Samples\Example\Example.c.
  
> [!NOTE]
> 此函数在 xlcSelect (调用命令宏) 因此，它仅在从 XLM 宏表调用时有效。 
  
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

