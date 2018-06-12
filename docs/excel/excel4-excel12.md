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
- excel4 函数 [excel 2007，] Excel12 函数 [Excel 2007]
localization_priority: Normal
ms.assetid: 2404f10d-8641-4ee6-a909-1c5a26610f80
description: ���÷�Χ�� Excel 2013?| Office 2013?| Visual Studio
ms.openlocfilehash: 1c2c775cc7c5b051e4a1381df09ef29e79e2aca4
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773736"
---
# <a name="excel4excel12"></a>Excel4/Excel12

 **适用于**： Excel 2013 |Office 2013 |Visual Studio 
  
内部 Microsoft Excel 工作表函数、 宏工作表函数或命令或仅 XLL 特殊函数或命令，从调用 DLL/XLL 或代码资源中。
  
所有的最新版本的 Excel 支持**Excel4**。 从 Excel 2007 开始，支持**Excel12** 。 
  
仅当 Excel 已传递给 DLL 或 XLL 的控件时，可调用这些函数。 他们也称为 Excel 过后控件间接通过调用 Visual Basic for Applications (VBA)。 他们不能在其他任何时间调用。 例如，他们不能调用为[DllMain](http://msdn.microsoft.com/library/base.dllmain%28Office.15%29.aspx)函数或其他时间在呼叫过程中时操作系统已调用 dll 文件，或从由 DLL 中创建的线程。 
  
[Excel4v 和 Excel12v](excel4v-excel12v.md)函数接受及其参数作为数组，，而**Excel4**和**Excel12**函数接受堆栈长度可变列表及其参数。 在所有其他方面， **Excel4** **Excel4v**，相同的行为和**Excel12**行为与**Excel12v**相同。
  
```cs
int Excel4(int iFunction, LPXLOPER pxRes, int iCount, LPXLOPER argument1, ...);
int Excel12(int iFunction, LPXLOPER12 pxRes, int iCount, LPXLOPER12 argument1, ...);
```

## <a name="parameters"></a>参数

 _iFunction_(**int**)
  
一个数字，指示命令、 函数或您要呼叫的特殊函数。 有效_iFunction_值的列表，请参阅下的备注部分。 
  
 _pxRes_（**LPXLOPER**或**LPXLOPER12**）
  
一个指向 （与**Excel4**) **XLOPER**或**XLOPER12** （与**Excel12**) 将保存计算函数的结果。
  
 _iCount_(**int**)
  
将传递给函数的后续参数的数目。 在最多为 2003年版本的 Excel，这可以是介于 0 到 30 任意数量。 从 Excel 2007 开始，这可以是任何介于 0 到 255。
  
 _argument1..._（**LPXLOPER**或**LPXLOPER12**）
  
函数的可选参数。 所有参数都必须为**XLOPER**或**XLOPER12**值的指针。 
  
## <a name="return-value"></a>返回值

返回下列的整数 (**int**) 值之一。
  
|**值**|**返回代码**|**说明**|
|:-----|:-----|:-----|
|0  <br/> |**xlretSuccess** <br/> |已成功调用的函数。 这并不意味着函数没有返回 Excel 错误值;若要了解，您必须查看的类型和生成_pxRes_参数的值。  <br/> |
|1  <br/> |**xlretAbort** <br/> |异常终止的命令或函数 （内部中止）。 发生这种如果 XLM 宏工作表关闭本身通过调用**CLOSE**，或者 Excel 内存不足。 如果 Excel 返回此错误，则必须立即退出调用的函数。 允许仅在退出之前调用**xlFree** DLL。 不允许与 C API 的所有其他呼叫。 用户可以通过使用**文件**菜单上的**保存**命令以交互方式保存任何工作。  <br/> |
|2  <br/> |**xlretInvXlfn** <br/> |提供无效的函数号。 如果使用 Xlcall.h 头文件中的常量，这不应发生除非您正在呼叫中的 Excel 运行版本不支持的内容。  <br/> |
|4  <br/> |**xlretInvCount** <br/> |输入无效的参数个数。 在最多为 Excel 2003 的版本中，可以执行任何函数的参数的最大数量为 30。 启动 Excel 2007 中的最大数目为 255。 一些需要固定或最小的参数数目。  <br/> |
|8  <br/> |**xlretInvXloper** <br/> |无效的**XLOPER**或**XLOPER12**已传递给该函数，或使用了错误类型的参数。  <br/> |
|16  <br/> |**xlretStackOvfl** <br/> |栈溢出出现。 使用**xlStack**监视堆栈中的聊天室左量。 避免在可能的情况下; 分配非常大的本地 （自动） 数组和堆栈上的结构使其静态。 （请注意，可能会被发现发生堆栈溢出）。  <br/> |
|32  <br/> |**xlretFailed** <br/> |一个命令等效函数失败。 这是等价于宏命令显示的宏错误警报对话框。  <br/> |
|64  <br/> |**xlretUncalced** <br/> |尝试取消，尚未计算的单元格的引用，因为它计划的当前单元格之后重新计算。 在这种情况下，将 DLL 应返回控件到 Excel 立即。 允许仅在退出之前调用**xlFree** DLL。 不允许与 C API 的所有其他呼叫。 有关哪些函数可以和无法访问尚未重新计算的单元格的值的详细信息，请参阅[Excel 命令、 函数和状态](excel-commands-functions-and-states.md)。  <br/> |
|128  <br/> |**xlretNotThreadSafe** <br/> |尝试调用的函数，不工作，也可能不是，线程安全多线程重新计算工作簿的过程。  <br/> 从 Excel 2007 开始，返回此值，并且仅在 XLL 工作表函数声明中 as 线程安全。  <br/> |
|256  <br/> |**xlRetInvAsynchronousContext** <br/> |无效的异步函数句柄。  <br/> 此值只使用 Excel 2010。  <br/> |
|512  <br/> |**xlRetNotClusterSafe** <br/> |在群集上不支持呼叫。  <br/> 此值只使用 Excel 2010。  <br/> |
   
## <a name="remarks"></a>备注

### <a name="valid-ifunction-values"></a>有效 iFunction 值

有效**iFunction**值为任何 Xlcall.h 头文件或任何以下特殊功能中定义的**xlf...** 或**xlc...** 常量。 
  
|||||
|:-----|:-----|:-----|:-----|
|**xlAbort** <br/> |**xlEnableXLMsgs** <br/> |**xlGetInst** <br/> |**xlSheetNm** <br/> |
|**xlCoerce** <br/> |**xlFree** <br/> |**xlGetName** <br/> |**xlStack** <br/> |
|**xlDefineBinaryName** <br/> |**xlGetBinaryName** <br/> |**xlset，则** <br/> |**xlUDF** <br/> |
|**xlDisableXLMsgs** <br/> |**xlGetHwnd** <br/> |**xlSheetId** <br/> ||
   
### <a name="different-types-of-functions"></a>不同类型的函数

 **Excel4**和**Excel12**区分三个类的函数。 函数分类根据 Excel 可能在其中调用 DLL 的三种状态。 
  
- DLL 调用从由于重新计算工作表时，将应用类 1。 
    
- DLL 调用从函数宏内或从工作表它已注册以井号 （#） 中键入文本时，将应用类 2。
    
- DLL 调用从对象、 宏、 菜单、 工具栏、 快捷键、 **ExecuteExcel4Macro**方法或**工具 / 宏 / 运行**命令时，将应用类 3。 有关详细信息，请参阅[Excel 命令、 函数和状态](excel-commands-functions-and-states.md)。
    
下表显示了哪些功能可在每个类。
  
|**类 1**|**类 2**|**类 3**|
|:-----|:-----|:-----|
|任何工作表函数  <br/> 除**xlset，则**任何仅 XLL **xl...** 函数。  <br/> **xlfCaller** <br/> |任何工作表函数  <br/> 除**xlset，则**任何**xl...** 函数。  <br/> 宏工作表的功能，包括**xlfCaller**，返回一个值，但不会影响工作区的操作或任何打开的工作簿执行。  <br/> |任何函数，包括**xlset，则**和命令等效功能。  <br/> |
   
### <a name="displaying-the-dialog-box-for-a-command-equivalent-function"></a>对于命令等效函数显示对话框

如果命令等效函数具有关联的对话框中，您可以设置**iFunction** **xlPrompt**位。 这意味着 Excel 在执行命令之前显示适当的对话框。
  
### <a name="writing-international-dlls"></a>编写国际 Dll

如果在**iFunction**设置**xlIntl**位，函数或命令执行，如果已从国际宏工作表被调用。 这意味着命令行为像在美国版本的 Excel，即使国际 （本地化） 版本上运行它。
  
### <a name="xlretuncalced-or-xlretabort"></a>xlretUncalced 或 xlretAbort

后接收这些返回的值之一，您的 DLL 必须清除并立即返回到 Excel 的控件。 导入 Excel 通过 C API，除**xlFree**，回调后接收其中一个返回值将被禁用。
  
## <a name="example"></a>示例

下面的示例使用**Excel12**函数选择单元格调用它。 
  
此代码示例是示例的一个更大 Excel 2010 XLL SDK 安装 SDK 的以下位置中提供的一部分：
  
\Samples\Example\Example.c。
  
> [!NOTE]
> 此函数调用命令宏 (xlcSelect)，并因此，只有调用从 XLM 宏工作表。 
  
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

