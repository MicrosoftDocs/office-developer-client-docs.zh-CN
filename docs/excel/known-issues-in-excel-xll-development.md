---
title: Excel XLL 开发中的已知问题
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
keywords:
- 已知问题 [excel 2007]
localization_priority: Normal
ms.assetid: 3dfecc0b-a91c-448e-8721-5d3486b625fa
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 34784f6895386efe7e6c3ca7ec213c7d71931058
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32304002"
---
# <a name="known-issues-in-excel-xll-development"></a>Excel XLL 开发中的已知问题

 **适用于** Excel 2013 | Office 2013 | Visual Studio 
  
本主题介绍了在 XLL 开发过程中可能遇到的 Microsoft Excel 中的已知问题。
  
## <a name="unregistering-xll-commands-and-functions"></a>注销 XLL 命令和函数

当 XLL 注册函数或命令时, Excel 将为该资源创建一个新名称, 并将对 DLL 函数的引用与该名称相关联。 该名称取自[xlfRegister](xlfregister-form-1.md)函数的第四个参数*pxFunctionText* 。 此名称在用于管理工作表名称的常规对话框中是隐藏的。 若要注销函数或命令, 必须使用[xlfSetName](xlfsetname.md)函数删除该名称, 并传递名称但不传递定义。 但是, bug 阻止了从 "函数向导" 列表中删除该名称。 
  
## <a name="argument-description-string-truncation-in-the-function-wizard"></a>函数向导中的参数说明字符串截断

*pxArgumentHelp1*参数和**xlfRegister**函数的所有后续参数都是与 XLL 函数的参数相对应的可选字符串。 "函数向导" 将显示这些信息, 以在 "参数构建" 对话框中提供帮助。 有时, Excel 在对话框中显示与最终参数对应的字符串时, 会将其截断为一个或两个字符。 若要避免这种情况, 可以添加其他 "空字符串" 作为函数注册的最后一个 "参数帮助" 参数。
  
## <a name="binary-name-scope-limitation"></a>二进制名称作用域限制

只有在创建时处于活动状态的工作表再次处于活动状态时, 才能检索二进制名称及其数据。 由于工作表函数无法激活工作簿中的工作表 (只有命令可以这样做), 因此二进制文件名的应用程序非常有限。 例如, 如果您有一个仅从特定工作表调用的命令, 则可以使用二进制名称来存储与命令相关的数据。
  
## <a name="xlset-and-workbooks-with-array-formulas"></a>使用数组公式的 xlSet 和工作簿

在 Excel 2003 和早期版本中, 如果您尝试为非活动工作表的工作表上的区域分配值, 并且活动工作表上的等效范围包含一个数组公式, 则[xlSet 函数](xlset.md)将失败。 在这种情况下, Excel 显示 "无法更改数组的一部分" 的消息。 这是在 Excel 2007 中修复的。 
  
## <a name="circular-references-are-tolerated-in-data-tables"></a>数据表中的循环引用是容许的

如果模拟运算表所基于的计算引用了表本身中的内容, 则 Excel 当前不会引发错误。 与此方案的预期可能不一样, 在创建或修改用于计算数据表值的公式时, 应谨慎。
  
## <a name="converting-an-integer-xloper12-to-an-xloper"></a>将整数 XLOPER12 转换为 XLOPER

由于整数类型**xltypeInt**是**XLOPER12**数据类型中的32位带符号整数, 但它只是**XLOPER**数据类型中的16位带符号整数, 因此, 可以使用某些整数**XLOPER12**值不能包含在整数**XLOPER**。 在内部转换此类型的 Excel 中, 它通过将类型转换为浮点**xltypeNum** **XLOPER**来解决此问题。
  
框架[XLOper12ToXLOper](xloper12toxloper.md)函数将此行为镜像到内部, 以与 Excel 在内部保持一致。 调用此函数时, 不应假定返回的**XLOPER**将始终为**xltypeInt**;如果**my_xloper**类型为**xltypeNum**, 则读取**my_xloper**会给出一个 false 值。
  
## <a name="returning-xloper-or-xloper12-by-modifying-arguments-in-place"></a>通过就地修改参数来返回 XLOPER 或 XLOPER12

Excel 允许通过就地修改参数来注册返回**XLOPER**或**XLOPER12**的函数。 但是, 如果**XLOPER**/ **XLOPER12**参数指向内存, 然后指针被 DLL 函数的返回值覆盖, 则 Excel 可能会泄漏内存。 Excel 不显示错误, 但最终可能会崩溃。 此外, 如果 DLL 为返回值分配内存, Excel 可能会尝试释放该内存, 这可能导致即时应用程序崩溃。 因此, 不应就地修改**XLOPER**/ **XLOPER12**参数。 应将所有**XLOPER**或**XLOPER12**参数视为严格的只读。 
  
有关更多信息，请参阅 [Excel 中的内存管理](memory-management-in-excel.md)。
  
## <a name="see-also"></a>另请参阅



[XLOper12ToXLOper](xloper12toxloper.md)


[Developing Excel XLLs](developing-excel-xlls.md)
  
[Excel XLL SDK API Function Reference](excel-xll-sdk-api-function-reference.md)
  
[Excel 中的内存管理](memory-management-in-excel.md)

