---
title: XLL Excel中的已知问题
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
keywords:
- 已知问题 [excel 2007]
localization_priority: Normal
ms.assetid: 3dfecc0b-a91c-448e-8721-5d3486b625fa
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 34784f6895386efe7e6c3ca7ec213c7d71931058
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32304002"
---
# <a name="known-issues-in-excel-xll-development"></a>XLL Excel中的已知问题

 **适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
本主题介绍 XLL Microsoft Excel可能会遇到的已知问题。
  
## <a name="unregistering-xll-commands-and-functions"></a>注销 XLL 命令和函数

当 XLL 注册函数或命令时，Excel为资源创建一个新名称，并关联对 DLL 函数的引用和该名称。 该名称取自 [xlfRegister](xlfregister-form-1.md)函数的第四个参数 *pxFunctionText。* 此名称在用于管理工作表名称的正常对话框中隐藏。 若要取消注册函数或命令，必须使用 [xlfSetName](xlfsetname.md) 函数删除名称，传递名称但不传递定义。 但是，Bug 会阻止此操作从"函数向导"列表中删除名称。 
  
## <a name="argument-description-string-truncation-in-the-function-wizard"></a>参数说明 函数向导中的字符串截断

*pxArgumentHelp1* 参数和 **xlfRegister** 函数的所有后续参数是对应于 XLL 函数参数的可选字符串。 "函数向导"会显示这些参数，以在参数构造对话框中提供帮助。 有时Excel对话框显示最后一个参数时，该字符串会截断一个或两个字符。 通过将其他"空字符串"添加为函数注册的最后一个"参数帮助"参数，可以避免这一点。
  
## <a name="binary-name-scope-limitation"></a>二进制名称范围限制

只有当创建时处于活动状态的工作表再次处于活动状态时，才能检索二进制名称及其数据。 由于工作表函数无法激活工作簿中的工作表 (只有命令才能) ，因此二进制名称的应用程序非常有限。 例如，如果你有一个仅从特定工作表调用的命令，可以使用二进制名称来存储与命令相关的数据。
  
## <a name="xlset-and-workbooks-with-array-formulas"></a>xlSet 和包含数组公式的工作簿

在 Excel 2003 及更早版本中，如果尝试将值分配给非活动工作表（活动工作表上的等效区域包含数组公式）上的区域，[则 xlSet](xlset.md)函数将失败。 在这种情况下，Excel消息"您不能更改数组的一部分"。 2007 年 10 Excel修复了这种情况。 
  
## <a name="circular-references-are-tolerated-in-data-tables"></a>数据表中允许循环引用

Excel数据表所基于的计算引用表本身中的某些内容，则当前不会引发错误。 此方案不太可能出现，但创建或修改用于计算数据表值的公式时应谨慎。
  
## <a name="converting-an-integer-xloper12-to-an-xloper"></a>将整数 XLOPER12 转换为 XLOPER

由于整数类型 **xltypeInt** 是 **XLOPER12** 数据类型 中的 32 位有符号整数，但它在 **XLOPER** 数据类型 中只是一个 16 位有符号整数，因此某些整数 **XLOPER12** 值不能包含在整数 **XLOPER** 中。 在Excel转换此类型时，它会通过将此类型转换为浮点 **xltypeNum** **XLOPER** 来解决此问题。
  
Framework [XLOper12ToXLOper](xloper12toxloper.md)函数反映此行为，以与内部Excel一。 调用此函数时，不应假定返回的 **XLOPER** 始终为 **xltypeInt**;如果 **my_xloper.val.w** 的类型为 **xltypeNum，** 则读取 **my_xloper** 会提供 false 值。
  
## <a name="returning-xloper-or-xloper12-by-modifying-arguments-in-place"></a>通过就地修改参数返回 XLOPER 或 XLOPER12

Excel通过就地修改参数来注册返回 **XLOPER** 或 **XLOPER12** 的函数。 但是，如果 **XLOPER** /  **XLOPER12** 参数指向内存，并且指针随后被 DLL 函数的返回值覆盖，Excel内存。 Excel不显示错误，但最终可能会崩溃。 此外，如果 DLL 为返回值分配了内存，Excel可能会尝试释放该内存，这可能会导致应用程序立即崩溃。 因此，不应就地 **修改** /  **XLOPER XLOPER12** 参数。 所有 **XLOPER** 或 **XLOPER12** 参数应严格视为只读。 
  
有关更多信息，请参阅 [Excel 中的内存管理](memory-management-in-excel.md)。
  
## <a name="see-also"></a>另请参阅



[XLOper12ToXLOper](xloper12toxloper.md)


[开发 Excel XLL](developing-excel-xlls.md)
  
[Excel XLL SDK API 函数引用](excel-xll-sdk-api-function-reference.md)
  
[Excel 中的内存管理](memory-management-in-excel.md)

