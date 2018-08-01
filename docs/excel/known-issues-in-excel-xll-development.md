---
title: Excel XLL 开发中的已知的问题
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
keywords:
- 已知的问题 [excel 2007]
localization_priority: Normal
ms.assetid: 3dfecc0b-a91c-448e-8721-5d3486b625fa
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 9cdbb10ea68723bd7e1cd9289e8592a7cc087c46
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773756"
---
# <a name="known-issues-in-excel-xll-development"></a>Excel XLL 开发中的已知的问题

 **适用于** Excel 2013 | Office 2013 | Visual Studio 
  
本主题介绍在 XLL 开发过程中可能会遇到的 Microsoft Excel 中的已知的问题。
  
## <a name="unregistering-xll-commands-and-functions"></a>正在注销 XLL 命令和函数

时 XLL 注册函数或命令，Excel 创建资源的新名称，并将引用的 DLL 函数与该名称相关联。 名称取自第四个参数， *pxFunctionText* ， [xlfRegister](xlfregister-form-1.md)函数。 从管理工作表名称普通对话框中，此名称处于隐藏状态。 取消注册的函数或命令，您必须通过使用[xlfSetName](xlfsetname.md)函数，传递的名称，但不是传递定义删除的名称。 但是，bug 阻止此移除函数向导列表的名称。 
  
## <a name="argument-description-string-truncation-in-the-function-wizard"></a>在函数向导的参数说明字符串截断

*PxArgumentHelp1*参数和所有后续**xlfRegister**函数参数是可选的对应于 XLL 函数的参数的字符串。 函数向导显示这些提供参数构造对话框中的帮助。 有时，Excel 将截断对应的最后一个参数由一个或两个字符时显示在对话框中的字符串。 可以通过向最终字符串的末尾添加一个或两个空格来避免这种情况。 
  
## <a name="binary-name-scope-limitation"></a>二进制文件名称范围限制

仅在创建时所时处于活动状态的工作表再次处于活动状态时，可以检索二进制名称和它们的数据。 因为工作表函数 （仅命令可以执行此操作） 无法激活工作簿中的工作表，应用程序的二进制名称是非常有限。 如果您有才会调用从特定的表中的命令，例如，可以使用二进制文件的名称来存储与命令相关的数据。
  
## <a name="xlset-and-workbooks-with-array-formulas"></a>xlset，则和使用数组公式的工作簿

在 Excel 2003 和早期版本中，如果您尝试将值分配给不是活动工作表，其中活动工作表上等效的范围包含数组公式的形式为工作表区域[xlset，则函数](xlset.md)将失败。 在这种情况下，Excel 将显示消息"无法更改为数组的一部分。" 这被固定在 Excel 2007 中。 
  
## <a name="circular-references-are-tolerated-in-data-tables"></a>循环引用容许模拟运算表中

Excel 当前不会引发错误如果计算的模拟运算表基于表中的某些内容引用。 这种情况下可能会为太，您应该仔细时您正在创建或修改用于计算数据表值的公式。
  
## <a name="converting-an-integer-xloper12-to-an-xloper"></a>将整数 XLOPER12 转换为 XLOPER

因为整数类型**xltypeInt** **XLOPER12**数据类型，32 位有符号的整数，但是它是仅 16 位有符号的整数中**XLOPER**数据类型，则可能中不能包含某些整数**XLOPER12**值整数**XLOPER**。 在 Excel 内部转换此类型，它获取解决此问题通过转换到浮点**xltypeNum** **XLOPER**的类型。
  
框架[XLOper12ToXLOper](xloper12toxloper.md)函数镜像与保持一致 Excel 内部此行为。 当您调用此函数时，您不应假定返回的**XLOPER**将始终为**xltypeInt**;如果**my_xloper**类型为**xltypeNum**读取**my_xloper.val.w**提供值为 false。
  
## <a name="returning-xloper-or-xloper12-by-modifying-arguments-in-place"></a>通过修改就地参数返回 XLOPER 或 XLOPER12

Excel 允许通过修改就地参数返回**XLOPER**或**XLOPER12**函数的注册。 但是，如果**XLOPER**/ **XLOPER12**参数指向内存，并将指针然后 DLL 函数的返回值被覆盖，Excel 可以泄漏内存。 Excel 不显示错误，但它最终可能崩溃。 此外，如果 DLL 的返回值分配内存，Excel 可能尝试以释放内存，这可能导致即时应用程序崩溃。 因此，不应修改**XLOPER**/ 就地**XLOPER12**参数。 严格为只读的则应处理所有**XLOPER**或**XLOPER12**参数。 
  
有关详细信息，请参阅[在 Excel 中进行内存管理](memory-management-in-excel.md)。
  
## <a name="see-also"></a>另请参阅



[XLOper12ToXLOper](xloper12toxloper.md)


[Developing Excel XLLs](developing-excel-xlls.md)
  
[Excel XLL SDK API Function Reference](excel-xll-sdk-api-function-reference.md)
  
[Excel 中的内存管理](memory-management-in-excel.md)

